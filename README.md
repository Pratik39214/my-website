# my-website
project/
│── index.html
│── about.html
│── weather.html
│── contact.html
│── style.css
│── script.js
└── images/
<!DOCTYPE html>
<html>
<head>
  <title>My Responsive Website</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<header>
  <h1>Welcome to My Website</h1>
  <nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="weather.html">Weather</a>
    <a href="contact.html">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Explore Information in a Modern Way</h2>
  <p>Fully responsive website with real-time API data.</p>
</section>

<footer>
  <p>© 2025 My Website</p>
</footer>

</body>
</html>
body {
  font-family: Arial;
  margin: 0;
  background: #eef2ff;
}

header {
  background: #4b6cff;
  padding: 20px;
  color: white;
  text-align: center;
}

nav a {
  margin: 0 12px;
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.hero {
  background: white;
  padding: 40px;
  margin: 20px;
  border-radius: 10px;
  animation: fadeIn 1.2s ease-in;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

/* Responsive */
@media (max-width: 600px) {
  nav {
    display: flex;
    flex-direction: column;
  }

  nav a {
    margin: 10px 0;
  }
}
<!DOCTYPE html>
<html>
<head>
<title>Weather API</title>
<link rel="stylesheet" href="style.css">
</head>

<body>

<header>
  <h1>Weather Information</h1>
  <nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="weather.html">Weather</a>
    <a href="contact.html">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Check Live Weather</h2>

  <input type="text" id="city" placeholder="Enter city name">
  <button onclick="getWeather()">Get Weather</button>

  <p id="result"></p>
</section>

<script src="script.js"></script>
</body>
</html>
function getWeather() {
  let city = document.getElementById("city").value;

  if (city === "") {
    alert("Enter a city!");
    return;
  }

  let url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=4e3b0e6804f5ccbd39e61f1194666c45&units=metric`;

  fetch(url)
    .then(response => response.json())
    .then(data => {
      document.getElementById("result").innerHTML =
        `Temperature: ${data.main.temp}°C <br>
         Weather: ${data.weather[0].description}`;
    })
    .catch(error => {
      document.getElementById("result").innerHTML = "City not found!";
    });
}
<!DOCTYPE html>
<html>
<head>
<title>Contact</title>
<link rel="stylesheet" href="style.css">
</head>

<body>
<header>
  <h1>Contact Us</h1>
  <nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="weather.html">Weather</a>
    <a href="contact.html">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Send a Message</h2>
  <p>Email: support@example.com</p>
</section>

<footer>
  <p>© 2025 My Website</p>
</footer>

</body>
</html>
