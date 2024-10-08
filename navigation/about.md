---
layout: page
title: About
description: About Me
permalink: /about
hide: false
comments: true
---
<style>
  .page-header {
    color: $header-heading-color;
    text-align: center;
    background-color: $header-bg-color;
    background-image: conic-gradient(from 215deg, $header-bg-color, $header-bg-color-secondary) !important;
  }

  .grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
    gap: 10px;
  }

  .grid-item {
    text-align: center;
    position: relative;
  }

  .grid-item img {
    width: 100%;
    height: 100px; /* Fixed height for uniformity */
    object-fit: contain; /* Ensure the image fits within the fixed height */
    cursor: pointer; /* Indicate that the image is clickable */
  }

  .grid-item p {
    margin: 5px 0; /* Add some margin for spacing */
  }

  .image-gallery {
    display: flex;
    flex-wrap: nowrap;
    overflow-x: auto;
    gap: 10px;
  }

  .image-gallery img {
    max-height: 150px;
    object-fit: cover;
    border-radius: 5px;
  }

  .description {
    display: none;
    margin-top: 10px;
    color: #f0f0f0;
    font-size: 14px;
    text-align: center;
  }

  .notebooks {
      display: none;
      margin-top: 10px;
    }
  .notebooks a {
      display: block;
      margin: 10px 0;
      text-decoration: none;
      color: blue;
    }
  .category {
        border: 1px solid #5f73b8;
        background: #424549;
        color: white;
        width: 270px;
        padding: 15px 20px;
        font-weight: bold;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 15px;
        transition-duration: 0.1s;
        cursor: pointer;
        font-family: serif;
    }
</style>
<p>Try out some other page header colors:</p>
<input type="color" id="headerColorPicker1" name="headerColorPicker1" value="#2921ff">
<input type="color" id="headerColorPicker2" name="headerColorPicker2" value="#00ff62">
## About Me
- Name: **Akhil Singamneni**
- <p>CSA is lit</p>
- <p>Junior :)</p>
- **Quiz at the bottom of the page, so pay attention!**
- Face: <img src="./images/IMG_7261.png" alt="Image" style="max-width: 100%; height: auto; width: 200px;">
  - Classes:
    - 📖 APEL (Mansour)
    - 📝 AP Calculus BC (Lanzi)
    - 💻 Can you guess?
    - 🍃 AP Physics Mechanics (Eckman)
    - 🌎 US History (Ayres)
- <p>Class of 2026</p>
- Countries I've been to (Click on the flags):
<div class="image-gallery" id="image_gallery"></div>
- [My Github](https://github.com/Akhil353)


<script>
  function updateGradient() {
    var color1 = document.getElementById('headerColorPicker1').value;
    var color2 = document.getElementById('headerColorPicker2').value;
    var gradient = `conic-gradient(from 215deg, ${color1}, ${color2})`;
    document.querySelector('.page-header').style.setProperty('background-image', gradient);
  }

  document.getElementById('headerColorPicker1').addEventListener('input', updateGradient);
  document.getElementById('headerColorPicker2').addEventListener('input', updateGradient);

  var container = document.getElementById("image_gallery");

  var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
  var places_visited = [
    {"flag": "a/a4/Flag_of_the_United_States.svg", "description": "United States of America", "extra_info": "This is where I lived for most of my life, and I have made a lot of memories here, good and bad."},
    {"flag": "4/41/Flag_of_India.svg", "description": "India", "extra_info": "This is where I was born, and going here for summer is always fun. Both my grandparents live here, and the temples are very nice to visit."},
    {"flag": "c/c3/Flag_of_France.svg", "description": "France", "extra_info": "I went here for my 7th grade summer, and I visited the Eiffel Tower and went to the Louvre."},
    {"flag": "0/03/Flag_of_Italy.svg", "description": "Italy", "extra_info": "We visited Rome and the Colosseum during my 7th grade summer."},
    {"flag": "f/f3/Flag_of_Switzerland.svg", "description": "Switzerland", "extra_info": "During my 7th grade summer, we visited here. There were very beautiful sights to see here in nature."}
  ];

  for (const location of places_visited) {
    var imageGallery = document.createElement("div");
    imageGallery.className = "grid-item";

    var img = document.createElement("img");
    img.src = http_source + location.flag;
    img.alt = location.description + " Flag";
    img.setAttribute('data-description', location.extra_info);

    var description = document.createElement("p");
    description.textContent = location.description;

    var extraInfo = document.createElement("p");
    extraInfo.className = "description";
    extraInfo.textContent = location.extra_info;

    img.addEventListener('click', function() {
      // Toggle display of the extra description
      var desc = this.parentElement.querySelector('.description');
      desc.style.display = desc.style.display === 'block' ? 'none' : 'block';
    });

    imageGallery.appendChild(img);
    imageGallery.appendChild(description);
    imageGallery.appendChild(extraInfo);

    container.appendChild(imageGallery);
  }
</script>

# A Youtube Video I liked
<iframe width="560" height="315" src="https://www.youtube.com/embed/qf7ws2DF-zk?si=ltS-quE6vk3uYMWn" frameborder="0" allowfullscreen></iframe>


# Quiz Time

<form id="quiz-form">
  <label for="question1">Which country did I not visit?</label><br>
  <input type="radio" id="france" name="question1" value="france">
  <label for="france">France</label><br>
  <input type="radio" id="italy" name="question1" value="italy">
  <label for="italy">Italy</label><br>
  <input type="radio" id="greece" name="question1" value="greece">
  <label for="greece">Greece</label><br>
  <br>

  <label for="question2">What is my 4th period class?</label><br>
  <input type="radio" id="physics" name="question2" value="physics">
  <label for="physics">AP Physics Mechanics</label><br>
  <input type="radio" id="calculus" name="question2" value="calculus">
  <label for="calculus">AP Calculus BC</label><br>
  <input type="radio" id="history" name="question2" value="history">
  <label for="history">US History</label><br>
  <br>

  <label for="question3">When will I graduate?</label><br>
  <input type="radio" id="2024" name="question3" value="2024">
  <label for="2024">2024</label><br>
  <input type="radio" id="2025" name="question3" value="2025">
  <label for="2025">2025</label><br>
  <input type="radio" id="2026" name="question3" value="2026">
  <label for="2026">2026</label><br>
  <br>

  <input type="submit" value="Submit">
</form>

<p id="result" style="font-weight: bold; color: green;"></p>

<script>
  document.getElementById("quiz-form").addEventListener("submit", function(event) {
    event.preventDefault();

    var correctAnswers = 0;

    var question1Answer = document.querySelector('input[name="question1"]:checked');
    if (question1Answer && question1Answer.value === "greece") {
      correctAnswers++;
    }

    var question2Answer = document.querySelector('input[name="question2"]:checked');
    if (question2Answer && question2Answer.value === "physics") {
      correctAnswers++;
    }

    var question3Answer = document.querySelector('input[name="question3"]:checked');
    if (question3Answer && question3Answer.value === "2026") {
      correctAnswers++;
    }

    var resultMessage;
    if (correctAnswers === 3) {
      resultMessage = "Perfect! You got all 3 questions correct!";
    } else {
      resultMessage = "You might want to pay more attention and take the quiz again";
    }

    document.getElementById("result").textContent = resultMessage;
    document.getElementById("result").style.color = correctAnswers === 3 ? "green" : "red";
  });
</script>

