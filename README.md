# project-1 MEMORY GAME
Table of Contents
/*
•	Description
•	Technical Requirements
•	What is a memory game?
•	Process Flow
•	Cards Shuffling
•	Matching Cards 
•	Moves Logic
•	Reset Button Logic
•	Congratulation Message
•	Star Rating
•	Timer
•	Conclusion

Description

This project is about programming a card memory game. The game is programmed using Hypertext Markup Language - html, Cascading Style Sheets – CSS and JavaScript.
The game is played by a single player at a time. The player will start by flipping a card and when the next card flipped is not a match to the first flipped, both cards get automatically flipped back to hidden.
The player will again flip a card until all matching cards are found and the game displays a message of congratulations to the user.
At the moment, there is a total number of 16 Cards but this number might increase with upcoming versions and the so as to make the game more challenging.

Technical Requirements
Your game must:
•	Render in the browser
Include separate HTML / CSS / JavaScript files
Add here the initial template with both css and js file links.
•	Use JavaScript for DOM manipulation
•	Be deployed online, using Github Project pages and/or to a custom domain.
•	Use semantic markup for HTML and CSS (adhere to best practices)
•	Show a good commit history with frequent commits
Additionally, your project should stick with KISS (Keep It Stupid Simple) and DRY (Don't Repeat Yourself) principles.

WHAT IS A MEMORY GAME?

A memory Game is a game of different sets of cards. Each pair of corresponding cards represent a corresponding attribute that must be matched for the cards to remain displayed, otherwise they remain hidden from the player.

PROCESS FLOW

o	First create an HTML Template and link the css and js files.
o	Within the <body></body> of the index.html file I added a section class with a class name as shown below:
o	 <section class="Flash-Cards"></section>
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Memory Games</title>
<link rel="stylesheet" href="css/styles.css" >
</head>
<body>
    <h1> Memory Game </h1>
    <button class="reset-button" id="resetButton">Restart Button</button>
<section class="Flash-Cards">
    
</section>
<script src="script/script.js"></script>
</body>
</html>

o	Within the section tags add 4 div classes of type row. Each row class will acontain four div elements of class backOfCard representing four cards.
o	Each Card will be assigned an onCardClicked event listener as shown below:.

<div class="row">
        <div
          class="backOfCard color-hidden"
          onclick="onCardClicked(event)">
        </div>
        <div
          class="backOfCard color-hidden"
          onclick="onCardClicked(event)">
        </div>
        <div
          class="backOfCard color-hidden"
          onclick="onCardClicked(event)">
        </div>
        <div
          class="backOfCard color-hidden"
          onclick="onCardClicked(event)">
        </div>
      </div>

o	The intention is to build a grid of even number of cards. The total number of cards is up to the developer. I used a 4 X 4 Grid = 16 cards. 
o	In the style file create the main padding for the template, in my case it is going to be a Flex template.

Css:
* {
    padding: 0;
    margin: 0; box-sizing: border-box;
    }
    body {
    font-family: monospace, Arial, Helvetica, sans-serif;
    height: 100vh;
    background: #62b206;
    display: flex;
    flex-direction: column;
    }

o	The following logic for the game will be added to the JavaScript file as follows:


