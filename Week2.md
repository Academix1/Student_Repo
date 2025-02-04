
### **Day 1: HTML Basics & Introduction to CSS**  
**File**: `day1.html`  
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Day 1: HTML Basics</title>
  <style>
    /* Basic CSS Styles */
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      padding: 0;
      background-color: #f0f0f0;
    }
    h1 {
      color: #2c3e50;
      text-align: center;
    }
    img {
      width: 200px;
      border-radius: 10px;
      display: block;
      margin: 10px auto;
    }
    p {
      color: #34495e;
      line-height: 1.6;
    }
    a {
      color: #3498db;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <h1>My Bio Page</h1>
  <img src="https://via.placeholder.com/200" alt="Profile Picture">
  <p>Hi! I'm Jane Doe, a web developer passionate about creating user-friendly websites.</p>
  <p>Check out my <a href="#">projects here</a>.</p>
</body>
</html>
```

---

### **Day 2: CSS Selectors & Layout Basics**  
**File**: `day2.html`  
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Day 2: Flexbox Navbar</title>
  <style>
    /* Flexbox Navigation Bar */
    .navbar {
      background-color: #2c3e50;
      padding: 15px;
      display: flex;
      justify-content: space-around;
      gap: 20px;
    }
    .navbar a {
      color: white;
      text-decoration: none;
      padding: 5px 10px;
    }
    .navbar a:hover {
      background-color: #3498db;
      border-radius: 4px;
    }

    /* Flexbox Layout Example */
    .container {
      display: flex;
      gap: 10px;
      margin: 20px;
    }
    .box {
      background-color: #3498db;
      color: white;
      padding: 20px;
      text-align: center;
      flex: 1;
    }
  </style>
</head>
<body>
  <nav class="navbar">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </nav>

  <div class="container">
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>
  </div>
</body>
</html>
```

---

### **Day 3: HTML Forms & Semantic HTML**  
**File**: `day3.html`  
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Day 3: Contact Form</title>
  <style>
    /* Form Styling */
    body {
      font-family: Arial, sans-serif;
      max-width: 600px;
      margin: 20px auto;
      padding: 20px;
    }
    form {
      background-color: #f9f9f9;
      padding: 20px;
      border-radius: 8px;
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input, textarea, button {
      width: 100%;
      padding: 8px;
      margin-bottom: 10px;
      border: 1px solid #ddd;
      border-radius: 4px;
    }
    button {
      background-color: #3498db;
      color: white;
      border: none;
      padding: 10px;
      cursor: pointer;
    }
    button:hover {
      background-color: #2980b9;
    }
  </style>
</head>
<body>
  <header>
    <h1>Contact Me</h1>
  </header>
  <main>
    <section>
      <form action="#" method="POST">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="message">Message:</label>
        <textarea id="message" name="message" rows="4" required></textarea>

        <button type="submit">Send Message</button>
      </form>
    </section>
  </main>
  <footer>
    <p>&copy; 2023 My Website. All rights reserved.</p>
  </footer>
</body>
</html>
```

---

### **Day 4: CSS Grid & Positioning**  
**File**: `day4.html`  
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Day 4: Grid and Positioning</title>
  <style>
    /* Grid Layout */
    .gallery {
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* 3 equal columns */
      gap: 15px; /* Space between grid items */
      max-width: 800px; /* Limit gallery width */
      margin: 20px auto; /* Center the gallery */
    }

    /* Grid Items */
    .gallery-item {
      position: relative; /* For positioning child elements */
      overflow: hidden; /* Hide overflow content */
      border-radius: 8px; /* Rounded corners */
      border: 2px solid #ccc; /* Add border for clarity */
    }

    /* Images inside Grid Items */
    .gallery-item img {
      width: 100%; /* Fill the container */
      height: 200px; /* Fixed height */
      object-fit: cover; /* Crop images to fit */
    }

    /* Positioning Example: Overlay Text */
    .overlay {
      position: absolute; /* Position relative to .gallery-item */
      top: 10px; /* 10px from the top */
      left: 10px; /* 10px from the left */
      background-color: rgba(0, 0, 0, 0.7); /* Semi-transparent black */
      color: white; /* White text */
      padding: 5px 10px; /* Padding for text */
      border-radius: 4px; /* Rounded corners */
    }
  </style>
</head>
<body>
  <div class="gallery">
    <div class="gallery-item">
      <img src="https://via.placeholder.com/300x200" alt="Image 1">
      <div class="overlay">Top Left</div>
    </div>
    <div class="gallery-item">
      <img src="https://via.placeholder.com/300x200" alt="Image 2">
      <div class="overlay">Top Left</div>
    </div>
    <div class="gallery-item">
      <img src="https://via.placeholder.com/300x200" alt="Image 3">
      <div class="overlay">Top Left</div>
    </div>
  </div>
</body>
</html>
```

---

### **Day 5: Advanced Styling & Final Project**  
**File**: `day5.html`  
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Day 5: Portfolio</title>
  <style>
    /* Advanced Styling */
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background: linear-gradient(45deg, #f3f4f6, #e5e7eb);
    }
    .header {
      background-image: url('https://via.placeholder.com/1200x400');
      background-size: cover;
      background-position: center;
      color: white;
      text-align: center;
      padding: 100px 20px;
    }
    .projects {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
      max-width: 1000px;
      margin: 40px auto;
      padding: 20px;
    }
    .project-card {
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      transition: transform 0.3s;
    }
    .project-card:hover {
      transform: translateY(-5px);
    }
    .contact-form {
      max-width: 600px;
      margin: 40px auto;
      padding: 20px;
      background: white;
      border-radius: 10px;
    }
    .btn {
      background: #3498db;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .btn:hover {
      background: #2980b9;
    }
  </style>
</head>
<body>
  <header class="header">
    <h1>Jane Doe's Portfolio</h1>
    <p>Web Developer & Designer</p>
  </header>

  <div class="projects">
    <div class="project-card">
      <h3>Project 1</h3>
      <p>A responsive website built with HTML/CSS.</p>
      <button class="btn">View Project</button>
    </div>
    <div class="project-card">
      <h3>Project 2</h3>
      <p>An interactive dashboard using JavaScript.</p>
      <button class="btn">View Project</button>
    </div>
  </div>

  <div class="contact-form">
    <h2>Contact Me</h2>
    <form>
      <input type="email" placeholder="Your email" required>
      <textarea placeholder="Your message" rows="4" required></textarea>
      <button class="btn" type="submit">Send</button>
    </form>
  </div>
</body>
</html>
```
---
### **Day 6: Implementing Personal Portfolio using HTML and CSS**

### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Portfolio</title>
    <link rel="stylesheet" href="newStyle.css">
</head>
<body style="background-color: white;">
    <header>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#additional-details">Get in Touch</a></li>
            </ul>
        </nav>
    </header>

    <section id="intro">
        <div class="intro-text" >
            <p style="font-size: 50px;">I'm Chanakya, a</p>
            <h1 style="font-size: 120px;margin-top: 50px;">Full Stack Developer</h1>
            <h3 style="font-size: 60px;margin-top: 50px;">Python and AI Enthusiast.</h3>
            <div class="social-icons">
                <a href="https://github.com/your-github-link" target="_blank">
                    <img src="GitHub.svg" alt="GitHub" class="icon" />
                </a>
                <a href="https://www.linkedin.com/in/your-linkedin-link" target="_blank">
                    <img src="LinkedIn.svg" alt="LinkedIn" class="icon" />
                </a>
            </div>
        </div>
        <!-- <div >
            <img src="GitHub.jpg"><img/>
            <img src="LinkedIn.png"/>
        </div> -->
    </section>

    <section id="about" style="background-color: white;">
        <h2 style="padding-left: 20px;">About Me</h2>
        <p style="padding-left: 30px;padding-right: 50px;font-size: 40px;color: #242222;">
            My mission is to turn complex ideas into seamless user experiences, combining robust backend logic with stunning frontend designs. 
            Whether it's building dynamic interfaces or architecting efficient systems, I thrive on solving challenges and creating solutions that make an impact. Let’s build something amazing together!
        </p>
        <h3 style="padding-left: 20px;font-size: 28px;padding-top: 40px;color: black;">My Expertise</h3>
        <div class="skills-icons" style="gap: 20px;">
            <img src="15.png" alt="Git" title="Git" />
            <img src="Git.png" alt="GitHub" title="Github">
            <img src="Html.png" alt="Html" title="HTML">
            <img src="css.svg" alt="CSS" title="CSS" style="height: 80px;margin-top: 4px;">
            <img src="JS.png" alt="JS" title="JavaScript">
            <img src="React.png" alt="React" title="React">
            <img src="Redux.png" alt="Redux" title="Redux">
            <img src="Python.png" alt="Python" title="Python">
            <img src="FastAPI.svg" alt="FastAPI" title="Fast API">
            <img src="MonogDB.png" alt="MonogDB" title="MonogDB">
            <img src="MySQL.png" alt="MySQL" title="MySQL">
            <img src="HuggingFace.svg" alt="HuggingFace" title="HuggingFace" style="width: 200px;">
           <p><img src="Netlify.svg" alt="Netlify"  title="Netlify"> Netlify </p>
            <img src="OpenAI.svg" alt="OpenAI" title="OpenAI" style="width: 200px;">
            <h2 style="font-weight: 900; margin-top: 20px; transition: transform 0.3s ease-in-out;" 
            onmouseover="this.style.transform='scale(1.1)'" 
            onmouseout="this.style.transform='scale(1)'">
            RAG
        </h2>
        
            <img src="Docker.png" alt="Docker" title="Docker">
            <img src="REST.jpg" alt="REST API" title="REST API" style="width:auto;height: 100px;">
            <img src="AWS.png" alt="AWS" title="AWS" style="width: auto;">

            
            
            
        </div>
    </section>
    
    <section id="projects">
        <h2 style="padding-left: 50px;color: black;">My Projects</h2>
        <div class="project-gallery">
            <div class="project">
                <div class="project-title">
                    <h3>OTT Streaming Platform</h3>
                    <div class="project-links" style="position: relative">
                        <a href="https://github.com/your-repo-link-1" target="_blank">
                            <img src="GitHub.jpg" alt="GitHub" class="github-icon" />
                        </a>
                        <p style="background-color: rgba(51, 132,255,100%);padding: 2px;border-radius: 25px; top: 10px;position:relative ;">
                        <a href="https://github.com/your-repo-link-1" target="_blank" class="project-link">Project Link</a>
                    </p>
                    </div>
                </div>
                <div class="project-image">
                    <img src="Rectangle 161.svg" alt="Project 1">
                </div>
            </div>
            <div class="project">
                <div class="project-title">
                    <h3>Weather App</h3>
                    <div class="project-links" style="position: relative">
                        <a href="https://github.com/your-repo-link-1" target="_blank">
                            <img src="GitHub.jpg" alt="GitHub" class="github-icon" />
                        </a>
                        <p style="background-color: rgba(51, 132,255,100%);padding: 2px;border-radius: 25px; top: 10px;position:relative ;margin-right: 10px;">
                        <a href="https://github.com/your-repo-link-1" target="_blank" class="project-link">Project Link</a>
                    </p>
                    </div>
                </div>
                <div class="project-image">
                    <img src="Rectangle 162.svg" alt="Project 2">
                </div>
            </div>
            <div class="project">
                <div class="project-title">
                    <h3>To-Do List Platform</h3>
                    <div class="project-links" style="position: relative">
                        <a href="https://github.com/your-repo-link-1" target="_blank">
                            <img src="GitHub.jpg" alt="GitHub" class="github-icon" />
                        </a>
                        <p style="background-color: rgba(51, 132,255,100%);padding: 2px;border-radius: 25px; top: 10px;position:relative ;margin-right: 10px;">
                        <a href="https://github.com/your-repo-link-1" target="_blank" class="project-link">Project Link</a>
                    </p>
                    </div>
                </div>
                <div class="project-image">
                    <img src="Rectangle 163.svg" alt="Project 3">
                </div>
            </div>
            <div class="project">
                <div class="project-title">
                    <h3>Calculator</h3>
                    <div class="project-links" style="position: relative">
                        <a href="https://github.com/your-repo-link-1" target="_blank">
                            <img src="GitHub.jpg" alt="GitHub" class="github-icon" />
                        </a>
                        <p style="background-color: rgba(51, 132,255,100%);padding: 2px;border-radius: 25px; top: 10px;position:relative ;margin-right: 10px;">
                        <a href="https://github.com/your-repo-link-1" target="_blank" class="project-link">Project Link</a>
                    </p>
                    </div>
                </div>
                <div class="project-image">
                    <img src="Rectangle 164.svg" alt="Project 4">
                </div>
            </div>
        </div>
        <div class="other-projects" style="color: black;">
            <h2 style="color: black;">Other Projects,<a href="#project"><img style="width: 30px;" src="GitHub.jpg"/></a></h2>
            <p style="color: black;padding-top: 20px;margin-bottom: 20px;">ATM/Bank (Deposit/Withdrawal Functions)</p>
            <p style="color: black;">Inventory Management</p>
            <div style="padding-top: 20px;">
            <span style="display: inline-block;color: white;background-color:black;border-radius: 10px;width: auto;height: auto;padding: 10px;font-size: small;">Download My Resume</span>
        </div>
     </div>
    </section>
    <section id="additional-details">
        <h1 style="color: black; margin-bottom: 20px;">Additional Details</h1>
        <div class="additional-content">
            <h3 style="color: black; margin-bottom: 10px;">Highest Education</h3>
            <p style="color: black; margin-bottom: 20px;">B.Com Computers</p>
            
            <h3 style="color: black; margin-bottom: 10px;">Certifications</h3>
            <div class="certificate-image" style="margin-bottom: 20px;">
                <img src="Certificates_codeacad.png" alt="certificates_codeacad.png" />
            </div>
            
            <div class="contact" style=" display: flex; flex-direction: column;">
                <h3 style="color: black;">Contact</h3>
                <p style="color: black; margin-bottom: 5px;">Chanakya Manas Korada</p>
                <p style="color: black; margin-bottom: 5px;">Email: your-email@gmail.com</p>
                <p style="color: black;">Phone: +123-456-7890</p>
            </div>
            
        </div>
    </section>
        <!-- Contact Form -->
        <!-- <form id="contact-form" method="POST" action="your-server-endpoint">
            <div class="form-group">
                <label for="name">Your Name</label>
                <input type="text" id="name" name="name" placeholder="Enter your name" required />
            </div>

            <div class="form-group">
                <label for="email">Your Email</label>
                <input type="email" id="email" name="email" placeholder="Enter your email" required />
            </div>

            <div class="form-group">
                <label for="message">Your Message</label>
                <textarea id="message" name="message" placeholder="Enter your message" required></textarea>
            </div>

            <button type="submit" class="submit-btn">Send Message</button>
        </form> -->
    

    <footer>
        <p style="font-size: 20px;">&copy; 2024  Chanakya Manas Korada. All rights reserved.</p>
    </footer>
</body>
</html>
```
### CSS
```css
@import url('https://fonts.googleapis.com/css2?family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=Noto+Serif+Telugu:wght@100..900&display=swap');

/* General Reset */
body, h1, h2, h3, p, ul, li, a {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
h1{
    color: white;
    /* text-shadow: 0 0 10px rgba(60, 102, 69, 0.5), 0 0 10px rgba(235, 230, 230, 0.3), 0 0 30px rgba(2, 41, 22, 0.7), 0 0 40px rgba(19, 204, 19, 0.8); */
    /* font-family: 'Libre Baskerville', serif; */
    font-family: 'Instrument Sans', sans-serif;
    font-weight: 400; /* For bold text */
}
h2{
    color: white;
    /* text-shadow: 0 0 10px rgba(60, 102, 69, 0.5), 0 0 10px rgba(235, 230, 230, 0.3), 0 0 30px rgba(2, 41, 22, 0.7), 0 0 40px rgba(19, 204, 19, 0.8); */
    /* font-family: 'Libre Baskerville', serif; */
    font-family: 'Instrument Sans', sans-serif;
    font-weight: 600; /* For bold text */
} 
h3{
    color: white;
}
p{
    color: white;
    /* text-shadow: 0 0 10px rgba(60, 102, 69, 0.5), 0 0 10px rgba(235, 230, 230, 0.3), 0 0 30px rgba(2, 41, 22, 0.7), 0 0 40px rgba(19, 204, 19, 0.8); */
    /* font-family: 'Noto Serif Telugu', serif; */
    font-family: 'Instrument Sans', sans-serif;
    font-weight: 200; /* Regular weight */
} 
/* Body Styling */
body {
    /* font-family: 'Arial', sans-serif; */
    font-family: 'Libre Baskerville', 'Noto Serif Telugu', serif;
    line-height: 1.7;
    color: #333;
    /* background: linear-gradient(190deg,#0a0a0a,#041b05); */
    background-color: #000;
}

/* Header and Navigation */
header {
    /* background: linear-gradient(135deg,#109c17, #148dff); */
    display: flex;
    padding: 12px 10px;
    position: sticky;
    top: 0;
    background: white;
    height: fit-content;
    flex-direction: row-reverse;
    
}

nav ul {
    list-style: none;
    text-align: center;
    padding: 2px 0;
}

nav ul li {
    display: inline-block;
    margin: 0 15px;
}
nav ul li a {
    color: #070707;
    text-decoration: none;
    font-size: 18px;
    font-weight: 500;
}

nav a:hover {
    color: rgb(27, 179, 53);
    border-bottom: 1px solid black;
}

/* Intro Section */
#intro {
    /* background: url('background_acad.svg') no-repeat center center/cover; */
    color: rgb(28, 10, 31);
    text-align: left;
    padding: 1rem 1rem;
    background-color:rgb(51, 132, 255);
    height: auto;
    padding-top: 70px;
    padding-bottom: 50px;
    padding-left: 70px;
    line-height: 4.7rem;
    
}

#intro h1 {
    font-size: 3rem;
    margin-left: 1%;
     
}
#intro h3 {
    margin-top: 0; /* Remove the top margin of the paragraph */
    font-family: 'Instrument Sans', sans-serif;
    margin-left: 1%; /* Align to the same left as the h1 */
}

#intro p {
    padding: 0;
    font-size: 1rem;
    color: #f8f5f7;
    font-weight: 700;
    padding-left: 17px;
    
    
    /* text-shadow: 0 0 10px rgba(255, 255, 255, 0.5), 0 0 20px rgba(255, 255, 255, 0.3), 0 0 30px rgba(2, 41, 22, 0.7), 0 0 40px rgba(19, 204, 19, 0.8); */
}
.my-links img{
    width: 100px;
    margin-left: 20px;
}
.intro h1, .intro h3 {
    margin: 0;
    padding: 0;
}



/* About Section */
#about {
    width: auto;
    padding: 1.1rem;
    height: auto;
    margin-top: 1px;
    text-align: left;
     background-color: white;
     margin-bottom: 10px;
     padding-left: 70px;
     
     padding-top: 40px;
     padding-right: 30px;
}


#about h2 {
    font-size: 2.2rem;
    color: black;
    margin-bottom: 1rem;
}

#about p {
    font-size: 1.2rem;
    max-width: 95%;
    color: black;
    padding-left: 10px;
    color: #A1A1A1;
    
}

.social-icons {
    margin-top: 10px; /* Adds space below the heading */
    display: flex;
    width: 100px;
    height: auto;
    justify-content: flex-start; /* Align icons to the left */
    gap: 25px; /* Space between icons */
    padding-left: 30px;
}

.social-icons a {
    display: inline-block;
    transition: transform 0.3s ease-in-out; /* Smooth zoom effect */
}

.social-icons a:hover {
    transform: scale(1.1); /* Slight zoom on hover */
}

.icon {
    width: 50px; /* Adjust size of the icons */
    height: 50px;
    border-radius: 5px;
}

.skills-icons {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 10px;
    padding-left: 20px;
    padding-bottom: 40px;
}

.skills-icons img {
    width: 90px;
    height: 90px;
    transition: transform 0.3s ease-in-out;
    
}

.skills-icons img:hover {
    transform: scale(1.1);
}


/* General Reset
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
} */

/* Body Styles */
/* body {
    background-color: #0b0d22;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
} */

/* Skills Section */
#skills{
    justify-items: center;
    align-items: center;
}
.skills-section {
    text-align: center;
    width: 90%;
    max-width: 1100px;
    background-color: #090a1a;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
}

.skills-title {
    margin-bottom: 20px;
    font-size: 2rem;
    color: #00bcd4;
}

/* Skills Container */
.skills-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 20px;
}

/* Individual Skill Card */
.skill-card {
    background-color: #22264c;
    border-radius: 10px;
    padding: 15px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    transition: transform 0.3s ease;
}

.skill-card:hover {
    transform: scale(1.05);
}

.skill-icon {
    width: 50px;
    height: 50px;
    margin-bottom: 10px;
}

.skill-card p {
    font-size: 1rem;
    color: #ffffff;
}


/* Projects Section */
#projects {
    /* background: linear-gradient(135deg, #ff7f50, #ff1493); */
    padding: 1rem;
    padding-left: 40px;
    background-color: white;
    color: black;
    /* background-color: #f0f0f0; */
}

#projects h2 {
    text-align: left;
    font-size: 2rem;
    margin-bottom: 0.6rem;
}

.project-gallery {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* Two items in a row */
    gap: 1.5rem;
    padding-right: 30px;
}

/* .github-icon {
display: flex;
flex-direction: row-reverse;
} */


/* .project-gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
} */

.project-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5px;
    font-weight: bold;
}

.project-links {
    display: flex;
    align-items: center;
    gap: 10px; /* Space between icon and link */
    margin-left: 5px; /* Moves the entire links container towards the left */
    
    
}

.project-links img.github-icon {
    width: 25px;
    height: 25px;
    transition: transform 0.3s ease-in-out;
}

.project-links img.github-icon:hover {
    transform: scale(1.2);
}

.project-link {
    color: #e7e4e4;
    text-decoration: none;
    font-size: 12px;
    transition: color 0.3s ease-in-out;
    padding-left: 10px;
}

.project-link:hover {
    color: #0a0a0a;
}

.project-image img {
    width: 100%;
    height: auto;
    display: block;
    object-fit: cover;
}

.project {
    /* background: white; */
    border-radius: 8px;
    overflow: hidden;
    width: 90%;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding-left: 40px;
}

.project img {
    width: 100%;
    height: 100%;
    display: block;
}

.project-info {
    padding: 1rem;
}

.project-info h3 {
    font-size: 1.4rem;
    margin-bottom: 0.5rem;
}

.project-info p {
    font-size: 1.6rem;
    color: #c5baba;
    font-weight: 500;
}

.project {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px;
}

.project-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin-bottom: 10px;
}
.project-title h3{
    font-weight: 500px;
    color: black;
}

.project-title p {
    font-size: 16px;
    font-weight: bold;
    margin: 0;
}
.project-title a{
    width: 30px;
    height: 10px;
    padding-right: 10px;
    margin-right: 2px;
}
.project-title img{
    width: 10px;
    height: 10px;
}

.github-icon {
    width: 10px;
    height: 10px;
    margin-left: 10px;
    transition: transform 0.3s;
}

.github-icon:hover {
    transform: scale(1.2);
}

.project img {
    width: 100%; /* Adjust based on the desired image size */
    height: auto;
    display: block;
}


.other-projects{
    margin-top: 30px;
    gap: 20px;
    padding-left: 60px;
    color: black;
    line-height: 2rem;
    padding-bottom: 50px;
    font-size: 30px;
}
.other-projects img{
    color: black;
    border-radius: 5px;

}
#additional-details {
    padding: 20px;
    max-width: 800px; 
    text-align: left;
    margin-left: 100px;/* Center the section on the page */
}

#additional-details h1 {
    color: black;
    text-align: left; /* Center align the title */
    margin-bottom: 20px;
    font-size: 3rem;
}

.additional-content h3 {
    color: black;
    margin-bottom: 10px;
    font-size: 1.6rem;
}

.additional-content p {
    color: black;
    margin-bottom: 20px;
    font-size: 2rem;
    word-wrap: break-word; /* Handle long words */
}

.certificate-image img {
    max-width: 100%; /* Ensure the image scales properly */
    height: auto;
    display: block;
    margin: 0 auto; /* Center align the image */
}

.contact {
    display: flex;
    flex-direction: column; /* Stack items vertically */
    gap: 20px; /* Add space between elements */
    margin-top: 20px;
}

.contact h3 {
    margin-bottom: "-20px";
    font-size: 2rem;
}

.contact p {
    margin-bottom: 0;
    font-size: 1.5rem;
    line-height: 1.5; /* Adjust line spacing */
}

/* Contact Links */
.contact-links {
    display: flex;
    justify-content: center;
    gap: 30px;
    margin-bottom: 30px;
}

.contact-link {
    display: flex;
    align-items: center;
    text-decoration: none;
    font-size: 20px;
    color: #333;
    transition: color 0.3s ease;
}
.contact-links a{
    color: white;
    /* text-shadow: 0 0 10px rgba(60, 102, 69, 0.5), 0 0 10px rgba(235, 230, 230, 0.3), 0 0 30px rgba(2, 41, 22, 0.7), 0 0 40px rgba(19, 204, 19, 0.8); */

}

.contact-link img {
    width: 30px;
    margin-right: 10px;
}

.contact-link:hover {
    color: #bb4603;
}


/* Footer */
footer {
    text-align: center;
    background: #333;
    color: white;
    padding: 1rem 0;
    font-size: 0.9rem;
}

/* Responsive Design */
@media (max-width: 768px) {
    nav ul {
        display: flex; /* Flex layout */
        padding: 0; /* Remove any padding */
        margin: 0; /* Remove any margin */
        gap: 10px; /* Removes any gap between elements */
    }
    #additional-details {
      
        margin: auto; /* Reduce padding for smaller screens */
    }

    #additional-details h1 {
        font-size: 2.5rem;
    }

    .additional-content h3 {
        font-size: 1rem;
    }

    .additional-content p {
        font-size: 0.9rem;
    }

    .contact {
        gap: 15px;
    }

    nav ul li {
        margin: 0.2rem; /* Remove margin between list items */
    }

    #intro h1 {
        font-size: 63px !important; /* Example of a more realistic size */
    }
    #intro h3 {
        font-size: 33px !important; /* Example of a more realistic size */
    }
    
    #intro p{
        padding-left: 0.4rem;
    }
    #intro{
        line-height: 3rem;
        padding-left: 50px;
    }
    #projects {
        padding-left: 10px;
    }
    #projects h2, #about h2, #contact h2 {
        font-size: 1.8rem;
    }
    #projects p{
        font-size: 1rem;
    }
    .project-gallery{
        padding-right: 10px;
        width: 170%;
    }
    .project-title h3{
        font-size: 1rem;
    }
    #intro p{
        width: 100%;
        font-size: 1.5rem;
        font-weight: 700;
    }
    nav ul li a {
        font-size: 1.1rem; /* Even smaller font for mobile screens */
    }
    .certificate-image img{
        width: 90%;
    }
    
    #about{
        padding-left: 40px;
    }
    #about p {
        font-size: 0.8rem;
        
    }
    .icon {
        width: 30px; /* Adjust size of the icons */
        height: 30px;
        border-radius: 5px;
    }
    .project-link-container {
        padding: 6px 10px;
    }

    .project-link {
        font-size: 10px;
    }
    #additional-details{
        padding-left: 65px;
    }
    .other-projects {
        padding: 10px;
        margin-left: 30px;
    }

    .other-projects h2 {
        font-size: 1.4em;
        flex-direction: column; /* Stack title and image */
    }

    .resume-button {
        font-size: 0.8em;
        padding: 8px 16px; /* Adjust padding for smaller screens */
    }
    .social-icons {
        margin-top: 10px; /* Adds space below the heading */
        display: flex;
        justify-content: flex-start; /* Align icons to the left */
        gap: 25px; /* Space between icons */
        padding-left: 30px;
    }
    .project-gallery {
        grid-template-columns: 1fr; /* Single column for small screens */
    }
    .project{
        width: 50%;
    }
    body{
        overflow-x: hidden;
    }
    

}

```
