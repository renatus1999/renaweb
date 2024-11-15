<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Personal Portfolio Website</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link
    href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&family=Playfair+Display:wght@700&display=swap"
    rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" />
</head>
<style>
  * {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
  }

  .hero {
    position: relative;
    width: 100%;
    height: 100vh;
    background: #eff4fd;
  }

  .logo {
    display: inline-block;
    font-family: 'Arial Black', sans-serif;
    font-size: 36px;
    font-weight: bold;
    color: #333;
    text-decoration: none;
    padding: 10px 20px;
    transition: all 0.3s ease;
  }

  .logo:hover {
    color: #fff;
    background-color: rgb(72, 69, 61);
  }

  .logo span {
    color: #007bff;
  }

  nav {
    display: flex;
    width: 84%;
    margin: auto;
    padding: 20px 0;
    align-items: center;
    justify-content: space-between;
  }

  nav ul {
    display: flex;
    /* Ensure the nav links are in a row for desktop */
  }

  nav ul li {
    list-style: none;
    margin: 10px 20px;
  }

  nav ul li a {
    text-decoration: none;
    color: #000;
    font-weight: bold;
  }

  nav ul li a:hover {
    color: red;
  }

  .detel {
    margin-left: 8%;
    margin-top: 13%;
  }

  .detel h1 {
    font-size: 50px;
    color: #212121;
    margin-bottom: 20px;
  }

  span {
    color: orange;
  }

  .detel p {
    color: #555;
    line-height: 22px;
  }

  .detel a {
    background: #212121;
    padding: 10px 18px;
    text-decoration: none;
    font-weight: bold;
    color: #fff;
    display: inline-block;
    margin: 30px 0;
    border-radius: 5px;
  }

  .images {
    width: 45%;
    height: 80%;
    position: absolute;
    bottom: 0;
    right: 100px;
  }

  .images img {
    height: 55%;
    position: absolute;
    left: 50%;
    bottom: 0;
    transform: translateX(-50%);
    transition: bottom 1s, left 1s;
  }

  .images:hover .shape {
    bottom: 40%;
  }

  .images:hover .girl {
    left: 45%;
  }

  /* Desktop Styles */
  @media (min-width: 768px) {
    nav ul {
      display: flex;
      /* Show links row-wise */
    }
  }

  /* Mobile Styles */
  @media (max-width: 767px) {
    .hero {
      height: auto;
      padding-bottom: 50px;
    }

    nav {
      width: 90%;
      flex-direction: column;
      align-items: center;
    }

    nav ul {
      position: absolute;
      top: 80px;
      left: 0;
      width: 100%;
      background-color: #eff4fd;
      padding: 20px 0;
      z-index: 1;
      display: none;
      /* Initially hidden */
      flex-direction: column;
      text-align: center;
    }

    nav ul li {
      margin: 10px 0;
    }

    .toggle-btn {
      display: flex;
    }

    .toggle-btn {
      display: none;
      flex-direction: column;
      justify-content: space-between;
      width: 30px;
      height: 21px;
      cursor: pointer;
    }

    .toggle-btn span {
      width: 100%;
      height: 3px;
      background-color: #333;
      transition: transform 0.3s ease-in-out;
    }

    .toggle-btn.active span:nth-child(1) {
      transform: translateY(9px) rotate(45deg);
    }

    .toggle-btn.active span:nth-child(2) {
      opacity: 0;
    }

    .toggle-btn.active span:nth-child(3) {
      transform: translateY(-9px) rotate(-45deg);
    }

    .detel {
      margin-left: 5%;
      margin-top: 50px;
      text-align: center;
    }

    .detel h1 {
      font-size: 36px;
    }

    .images {
      position: static;
      width: 100%;
      height: auto;
      margin-top: 30px;
    }

    .images img {
      position: static;
      transform: none;
      height: auto;
      max-width: 100%;
    }
  }



  /* Base Styles */
  .container {
    max-width: 1200px;
    /* Set a maximum width for the container */
    margin: 0 auto;
    padding: 40px 20px;
    display: flex;
    /* Use flexbox for layout */
    flex-wrap: wrap;
    /* Allows wrapping of sections */
    gap: 40px;
    /* Space between sections */
  }

  /* Main Content Styles */
  .about-section {
    display: flex;
    align-items: center;
    background-color: #fff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    padding: 40px;
    flex: 0 1 calc(50% - 20px);
    /* Each section takes half of the row */
    min-width: 300px;
    /* Minimum width for responsiveness */
  }

  .about-section img {
    max-width: 100px;
    margin-right: 40px;
    border-radius: 8px;
  }

  .about-section h2 {
    margin-top: 0;
    color: black;
    font-family: 'Playfair Display', serif;
    font-size: 28px;
  }

  .about-section p {
    line-height: 1.5;
    /* Reduced line-height for less space between lines */
    color: #333;
    text-align: left;
    margin: 0;
    /* Remove any default margin */
    padding: 0;
    /* Remove any default padding */
  }

  /* Desktop Styles */
  @media (min-width: 768px) {
    .container {
      padding: 60px 20px;
      gap: 60px;
      /* Space between sections */
    }

    .about-section {
      flex: 0 1 calc(40% - 20px);
      /* Two sections in a row on larger screens */
    }

    .about-section img {
      max-width: 150px;
      /* Adjust image size for larger screens */
      margin-right: 60px;
    }

    .about-section h2 {
      font-size: 32px;
      /* Larger heading size */
    }
  }

  /* Mobile Styles */
  @media (max-width: 767px) {
    .container {
      width: 750px;
      /* Full width for the container on mobile */
      padding: 20px;
      /* Adjusted padding for smaller screens */
      gap: 20px;
      /* Reduced space between sections */
    }

    .about-section {
      flex-direction: column;
      /* Stack elements on mobile */
      align-items: center;
      padding: 20px;
      /* Reduced padding on mobile */
    }

    .about-section img {
      max-width: 100%;
      /* Full width for images on mobile */
      margin-right: 0;
      margin-bottom: 20px;
    }

    .about-section h2 {
      font-size: 24px;
      /* Smaller heading size on mobile */
    }

    .about-section p {
      line-height: 1.5;
      color: #333;
      text-align: left;
      margin: 0;
      padding: 0;
    }
  }




  /* Contact Us Section */
  .contact-section {
    display: flex;
    flex-direction: row;
    /* Allows side-by-side layout */
    justify-content: space-between;
    /* Space between items */
    background-color: #fff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    padding: 40px;
    margin-top: 40px;
    /* Space above the contact section */
    width: 100%;
    /* Full width for the contact section */
  }

  .contact-info {
    flex: 1;
    /* Takes available space */
    margin-right: 20px;
    /* Space between contact info and form */
  }

  .contact-section h2 {
    color: black;
    font-family: 'Playfair Display', serif;
    font-size: 28px;
  }

  .contact-section p {
    line-height: 1.6;
    color: #333;
  }

  /* Form Styles */
  .contact-form {
    display: flex;
    flex-direction: column;
    /* Stack form elements vertically */
    flex: 1;
    /* Takes available space */
  }

  .contact-form label {
    margin-bottom: 5px;
    color: #333;
    font-weight: bold;
  }

  .contact-form input,
  .contact-form textarea {
    margin-bottom: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
    width: 100%;
    /* Full width for inputs */
    max-width: 500px;
    /* Maximum width for inputs */
  }

  .contact-form textarea {
    resize: vertical;
    /* Allow vertical resizing */
    height: 100px;
    /* Set a default height */
  }

  .contact-form button {
    padding: 10px 15px;
    background-color: #644536;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
    width: 50%;
    /* Width of the button */
    margin: 0 auto;
    /* Center the button */
    display: block;
    /* Make the button a block element to use margin auto */
  }

  button {
    background-color: #007bff;
    /* Bootstrap primary color */
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s, transform 0.2s;
  }

  button:hover {
    background-color: #0056b3;
    /* Darker shade on hover */
    transform: scale(1.05);
  }

  button:focus {
    outline: none;
  }

  /* Footer Styles */
  footer {
    background-color: #000;
    color: #fff;
    padding: 40px 20px;
    text-align: center;
  }

  .social-links {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }

  .social-link {
    color: #fff;
    font-size: 30px;
    margin: 0 10px;
    transition: color 0.3s ease;
  }

  .social-link:hover {
    color: red;
  }

  .footer-nav {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }

  .footer-nav a {
    color: #fff;
    margin: 0 10px;
    text-decoration: none;
    transition: color 0.3s ease;
  }

  .footer-nav a:hover {
    color: #dc1616;
  }

  .copyright {
    font-size: 14px;
    color: #ccc;
  }

  /* Responsive Styles */
  @media (max-width: 768px) {
    .footer-nav {
      flex-direction: column;
    }

    .footer-nav a {
      margin: 5px 0;
    }
  }
</style>

<body>
  <div class="hero">
    <nav>
      <a href="#" class="logo">
        RE-WORLD<span>CREATIVITY</span>
      </a>
      <div class="toggle-btn" id="toggle-btn">
        <span></span>
        <span></span>
        <span></span>
      </div>
      <ul id="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="about us.html">About</a></li>
        <li><a href="#">Service</a></li>
      </ul>
    </nav>
    <div class="detel">
      <h1>I’m Renatus <span>Edward</span></h1>
      <p>This is my official portfolio website to display all<br> my work details and what I can do for you in web
        development. <br> I MAKE SURE YOU RECEIVE THE BEST!</p>
      <a href="#">DOWNLOAD MY CV</a>
    </div>
    <div class="images">
      <img src="./image/web.jfif" class="girl">
      <img src="./image/gradu.jfif" class="shape">
    </div>
  </div>

  <div class="container">
    <section class="about-section">
      <img src="./image/CV_PIC-removebg-preview.png" alt="Bean Boutique Team">
      <div>
        <h2><u>My Mission</u></h2>
        <br>
        <p>As a young web developer, my mission is to continuously enhance my skills in both front-end and back-end
          technologies, build a diverse portfolio of projects, and stay updated with industry trends.</p>
        <br>
        <p>I aim to contribute to open-source projects, network with other professionals, and ultimately create
          user-friendly, innovative web applications that solve real-world problems. My ambition is to establish a
          successful career in web development while fostering a passion for learning and collaboration within the tech
          community.</p>
        <a href="https://youtube.com/@renatusrichard?si=u6DwdvAzMlVldSC6" target="_blank">
          <button>Visit my YouTube channel</button>
        </a>
      </div>
    </section>

    <section class="about-section">
      <div>
        <h2>My story!</h2>
        <p>My name is Renatus Edward, and I am a passionate young web developer dedicated to mastering both front-end
          and back-end technologies. </p>
        <p>My journey began with a fascination for how websites are built, leading me to explore coding through Speciss
          College, online courses and finally got my hands-on projects.</p>
        <p>I thrive on challenges and enjoy creating innovative, user-friendly web applications that solve real-world
          problems. <br> With a commitment to continuous learning, I aim to contribute to the tech community and build a
          diverse portfolio that showcases my skills and creativity.</p>
      </div>
      <img src="./image/back.jfif" alt="Bean Boutique Cafe">
    </section>

    <section class="about-section">
      <div>
        <h2>Daily News</h2>
        <div id="news-container">
          <!-- News articles will be dynamically inserted here -->
        </div>
      </div>
    </section>

    <section class="about-section">
      <div>
        <h2>Currency Exchange Rates</h2>
        <button id="toggle-currency" onclick="toggleCurrencyRates()">Show Foreign Exchange</button>
        <div id="currency-container" style="display: none;">
          <!-- Currency rates will be dynamically inserted here -->
        </div>
      </div>
    </section>
  </div>

  <script>
    // NewsAPI key
    const newsApiKey = 'eeef44ce6d8446a68425fae148dfc866';

    // Function to fetch and display news articles
    function displayNews() {
      fetch(`https://newsapi.org/v2/top-headlines?country=us&apiKey=${newsApiKey}`)
        .then(response => response.json())
        .then(data => {
          const newsContainer = document.getElementById('news-container');
          newsContainer.innerHTML = '';

          data.articles.slice(0, 3).forEach(article => {
            const newsItem = document.createElement('div');
            newsItem.classList.add('news-item');

            const title = document.createElement('h3');
            title.textContent = article.title;

            const description = document.createElement('p');
            description.textContent = article.description;

            const link = document.createElement('a');
            link.href = article.url;
            link.textContent = 'Read more';

            newsItem.appendChild(title);
            newsItem.appendChild(description);
            newsItem.appendChild(link);
            newsContainer.appendChild(newsItem);
          });
        })
        .catch(error => {
          console.error('Error fetching news:', error);
        });
    }

    // Function to fetch and display currency exchange rates
    function displayCurrencyRates() {
      const currencyApiKey = 'YOUR_CURRENCY_API_KEY_HERE'; // Replace with your currency API key
      fetch(`https://api.exchangerate-api.com/v4/latest/USD`) // Example API endpoint
        .then(response => response.json())
        .then(data => {
          const currencyContainer = document.getElementById('currency-container');
          currencyContainer.innerHTML = '';

          const rates = data.rates;
          for (const [currency, rate] of Object.entries(rates)) {
            const currencyItem = document.createElement('div');
            currencyItem.classList.add('currency-item');

            const currencyText = document.createElement('p');
            currencyText.textContent = `${currency}: ${rate.toFixed(2)}`; // Displaying rate to 2 decimal places

            currencyItem.appendChild(currencyText);
            currencyContainer.appendChild(currencyItem);
          }
        })
        .catch(error => {
          console.error('Error fetching currency rates:', error);
        });
    }

    // Function to toggle the visibility of currency exchange rates
    function toggleCurrencyRates() {
      const currencyContainer = document.getElementById('currency-container');
      const button = document.getElementById('toggle-currency');

      if (currencyContainer.style.display === 'none') {
        currencyContainer.style.display = 'block';
        button.textContent = 'Hide Foreign Exchange';
        displayCurrencyRates(); // Fetch rates when showing
      } else {
        currencyContainer.style.display = 'none';
        button.textContent = 'Show Foreign Exchange';
      }
    }

    // Call the functions to display news and currency rates
    displayNews();
  </script>


  <div class="containera">
    <section class="contact-section">
      <div class="contact-info">
        <h2>Let's talk</h2>
        <p><strong>Email:</strong> onemacource@gmail.com</p>
        <p><strong>Address:</strong> De Noon Road, H NO:9, Avondale, Harare-Zimbabwe</p>
        <p><strong>Phone:</strong> (+263) 780250449</p>
      </div>

      <form class="contact-form">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="subject">Subject:</label>
        <input type="text" id="subject" name="subject" required>

        <label for="message">Message:</label>
        <textarea id="message" name="message" required></textarea>

        <button type="submit">Send Message</button>
      </form>
    </section>
  </div>

  <footer>
    <div class="social-links">
      <a href="#" class="social-link facebook">
        <i class="fab fa-facebook-f"></i>
      </a>
      <a href="#" class="social-link youtube">
        <i class="fab fa-youtube"></i>
      </a>
    </div>
    <nav class="footer-nav">
      <a href="#">Home</a>
      <a href="#">News</a>
      <a href="#">About</a>
      <a href="#">Our Team</a>
    </nav>
    <div class="copyright">
      Copyright &copy; 2024, Designed by RENATUS EDWARD
    </div>
  </footer>
  <script>
    const toggleBtn = document.getElementById("toggle-btn");
    const navLinks = document.getElementById("nav-links");

    toggleBtn.addEventListener("click", () => {
      toggleBtn.classList.toggle("active");
      navLinks.style.display = navLinks.style.display === "none" ? "flex" : "none";
    });
  </script>
</body>

</html>
