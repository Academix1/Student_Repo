
## **Week-9** Advanced Python(FAST API)

---

### **Day 1: Installing and Introducing Python (venv and FastAPI)**

#### Step 1: Set up a virtual environment

1. **Create a new virtual environment:**
   ```bash
   python3 -m venv env
   ```

2. **Activate the virtual environment:**
   - For macOS/Linux:
     ```bash
     source env/bin/activate
     ```
   - For Windows:
     ```bash
     .\env\Scripts\activate
     ```

#### Step 2: Install FastAPI and Uvicorn

1. **Install FastAPI**:
   ```bash
   pip install fastapi
   ```

2. **Install Uvicorn** (for running the FastAPI app):
   ```bash
   pip install uvicorn
   ```

#### Step 3: Create a Basic FastAPI Application

Create a new Python file, `main.py`, and add the following content:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, FastAPI!"}
```

#### Step 4: Run the FastAPI app

Run the FastAPI app with Uvicorn:

```bash
uvicorn main:app --reload
```

Now, visit `http://127.0.0.1:8000` in your browser, and you should see:
```json
{"message": "Hello, FastAPI!"}
```

---

### Day 2
- Day2 We Will Deal With Basic CRUD Operation

```python
from fastapi import FastAPI
from pydantic import BaseModel

app=FastAPI()

class Item(BaseModel):
    name: str
    price: float

class ResponseModel(BaseModel):
    name: str


@app.get("/")
def root():
    return {"message": "Hello World"}


@app.get("/items/{item_id}")
def read_item(item_id:int):
    return {"item_id": item_id}

@app.get("/items")
def read_items(a,b):
    return {"a": a, "b": b}

@app.post("/item/")
def create_item(item: Item):
    return {"name": item.name, "price": item.price}

@app.post("/response/",response_class=ResponseModel)
def create_item(item: Item):
    return item
```
### Day 3

#### Database
```python
# database.py
from sqlalchemy import create_engine
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

DATABASE_URL = "sqlite:///./test.db" 

engine = create_engine(DATABASE_URL, connect_args={"check_same_thread": False})

SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

Base = declarative_base()
```
#### Models

```python
# models.py
from sqlalchemy import Column, Integer, String, Float
from database import Base

class Movie(Base):
    __tablename__ = "movies"  # Table name in the database

    id = Column(Integer, primary_key=True, index=True)
    title = Column(String, index=True)
    director = Column(String)
    release_year = Column(Integer)
    poster_url = Column(String)  # URL to the movie poster
    price = Column(Float)
```

#### Schemas

```python
# schemas.py
from pydantic import BaseModel

# Base schema for common movie fields
class MovieBase(BaseModel):
    title: str
    director: str
    release_year: int
    poster_url: str
    price: float

class Movie(MovieBase):
    id: int 

    class Config:
        orm_mode = True 
```

#### main.py

```python
from fastapi import FastAPI, Depends, HTTPException, status
from sqlalchemy.orm import Session
import models, schemas
from database import SessionLocal, engine

models.Base.metadata.create_all(bind=engine)

app = FastAPI()

def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()

@app.post("/movies/create", status_code=status.HTTP_201_CREATED)
def create(movie:schemas.MovieBase,db:Session=Depends(get_db)):
    new_movie=models.Movie(**movie.dict())
    db.add(new_movie)
    db.commit()
    db.refresh(new_movie)
    return {"message": f"Movie '{new_movie.title}' Saved Successfully!"}

@app.get("/movies/", response_model=list[schemas.Movie])
def read(db:Session=Depends(get_db)):
    movies=db.query(models.Movie).all()
    return movies
```
### Day4 

#### `Main.py`

```python

# Route to get all movies
@app.get("/movies", response_model=list[schemas.Movie])
def get_movies(db: Session = Depends(get_db)):
    movies = db.query(models.Movie).all()
    return movies

@app.get("/movies/{movie_id}", response_model=schemas.Movie)
def get_movie(movie_id: int, db: Session = Depends(get_db)):
    movie = db.query(models.Movie).filter(models.Movie.id == movie_id).first()
    if movie is None:
        raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="Movie not found")
    return movie

@app.put("/movies/{movie_id}", response_model=schemas.Movie)
def update_movie(movie_id: int, movie: schemas.MovieCreate, db: Session = Depends(get_db)):
    db_movie = db.query(models.Movie).filter(models.Movie.id == movie_id).first()
    if db_movie is None:
        raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="Movie not found")

    # Update movie fields
    db_movie.title = movie.title
    db_movie.director = movie.director
    db_movie.release_year = movie.release_year
    db_movie.poster_url = movie.poster_url or db_movie.poster_url  # Keep old poster_url if not provided
    db_movie.price = movie.price

    db.commit()
    db.refresh(db_movie)  # Refresh to get the updated data

    return db_movie

# Route to delete a movie (DELETE request)
@app.delete("/movies/{movie_id}", status_code=status.HTTP_204_NO_CONTENT)
def delete_movie(movie_id: int, db: Session = Depends(get_db)):
    db_movie = db.query(models.Movie).filter(models.Movie.id == movie_id).first()
    if db_movie is None:
        raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="Movie not found")

    db.delete(db_movie)
    db.commit()
    return {"message": "Movie deleted successfully"}

```
### Day 5

#### React

```js
import React, { useEffect, useState } from "react";
import axios from "axios";

const MoviesList = () => {
  const [movies, setMovies] = useState([]);
  const [loading, setLoading] = useState(true);

  // Fetching the movie data from the FastAPI backend
  useEffect(() => {
    axios
      .get("http://localhost:8000/movies") // Replace with your FastAPI URL
      .then((response) => {
        setMovies(response.data);
        setLoading(false);
      })
      .catch((error) => {
        console.error("There was an error fetching the movies!", error);
        setLoading(false);
      });
  }, []); // Empty array ensures the useEffect runs only once after the component mounts

  if (loading) {
    return <p>Loading movies...</p>;
  }

  return (
    <div>
      <h1>Movie List</h1>
      {movies.length > 0 ? (
        <div>
          {movies.map((movie) => (
            <div key={movie.id}>
              <h3>{movie.title}</h3>
              {movie.poster_url && (
                <img
                  src={`http://localhost:8000/${movie.poster_url}`}
                  alt={`${movie.title} Poster`}
                  style={{ width: "150px", height: "200px" }}
                />
              )}
            </div>
          ))}
        </div>
      ) : (
        <p>No movies found.</p>
      )}
    </div>
  );
};

export default MoviesList;
```
### Day 6

#### `test_app.py`

````python
import pytest
from fastapi.testclient import TestClient
from main import app
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker
from database import Base
import models

# Setup the testing database
SQLALCHEMY_DATABASE_URL = "sqlite:///./test.db"
engine = create_engine(SQLALCHEMY_DATABASE_URL, connect_args={"check_same_thread": False})
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

# Create the tables for testing
Base.metadata.create_all(bind=engine)

@pytest.fixture(scope="module")
def test_db():
    # Create a new database session
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()

@pytest.fixture(scope="module")
def client():
    # Use TestClient to interact with the FastAPI app
    client = TestClient(app)
    yield client

# Test creating a movie
def test_create_movie(client, test_db):
    response = client.post("/movies/", json={
        "title": "Inception",
        "director": "Christopher Nolan",
        "release_year": 2010,
        "poster_url": "inception.jpg",
        "price": 15.99
    })
    
    assert response.status_code == 201
    assert response.json()["title"] == "Inception"
    assert response.json()["director"] == "Christopher Nolan"
    assert response.json()["release_year"] == 2010
    assert response.json()["price"] == 15.99

# Test getting a movie by ID
def test_get_movie(client, test_db):
    # First, create a movie to get
    create_response = client.post("/movies/", json={
        "title": "Interstellar",
        "director": "Christopher Nolan",
        "release_year": 2014,
        "poster_url": "interstellar.jpg",
        "price": 19.99
    })
    
    movie_id = create_response.json()["id"]

    # Now, retrieve the movie by its ID
    response = client.get(f"/movies/{movie_id}")
    
    assert response.status_code == 200
    assert response.json()["title"] == "Interstellar"
    assert response.json()["director"] == "Christopher Nolan"
    assert response.json()["release_year"] == 2014
    assert response.json()["price"] == 19.99

# Test getting all movies
def test_get_movies(client, test_db):
    # Add multiple movies
    client.post("/movies/", json={
        "title": "Dunkirk",
        "director": "Christopher Nolan",
        "release_year": 2017,
        "poster_url": "dunkirk.jpg",
        "price": 14.99
    })
    
    client.post("/movies/", json={
        "title": "The Dark Knight",
        "director": "Christopher Nolan",
        "release_year": 2008,
        "poster_url": "dark_knight.jpg",
        "price": 12.99
    })

    # Get the list of movies
    response = client.get("/movies")
    
    assert response.status_code == 200
    assert len(response.json()) >= 2  # We should have at least 2 movies created

# Test creating a movie that already exists
def test_create_duplicate_movie(client, test_db):
    # Create a movie
    client.post("/movies/", json={
        "title": "The Prestige",
        "director": "Christopher Nolan",
        "release_year": 2006,
        "poster_url": "prestige.jpg",
        "price": 18.99
    })
    
    # Try to create the same movie again
    response = client.post("/movies/", json={
        "title": "The Prestige",
        "director": "Christopher Nolan",
        "release_year": 2006,
        "poster_url": "prestige.jpg",
        "price": 18.99
    })
    
    assert response.status_code == 400
    assert response.json()["detail"] == "Movie already exists"

# Test cleanup: Delete the database file after the test
import os
def cleanup():
    if os.path.exists("test.db"):
        os.remove("test.db")
````
