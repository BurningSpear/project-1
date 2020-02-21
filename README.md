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

CARDS SHUFFLING 

o	The game will be made of an array of cards defined by colors or images corresponding to each pair of cards.
JSS-code

const colors = [
'pink',
'yellow',
'red',
'cyan',
'blue',
'purple',
'orange',
'green'
];


o	The shuffling will be achieved through a parseInt(Math.random() method to let the cards randomly shuffled before begin of every game.

MATCHING CARDS 

o	In JavaScript file, the match function will be written as shown below:


o	Once a card is opened, it will remain displayed and if on the next card click no matching card of the matching pair is opened, the card will flip back to hide the front face.
o	If a match is found, the card will remain displayed and the player can proceed to select the next card.
o	The main function of our game will be the function onCardClicked(e). In this function we will add the following logic for the card game:
	If a card has not been clicked, we will keep track of the card and display its color when clicked. This logic will be in function:

if (!clickedCard) 

o	We will use the event.target property together with the element.tagName property to find out which card element triggered the click event:

clickedCard = target;

o	Otherwise with the else statement, we will keep track of the color of the clicked card to match it to the next clicked card. 

lickedCard.getAttribute('data-color') !== target.getAttribute('data-color')
o	We will the declare a preventClick variable to be used in the function:
 function onCardClicked(e)
o	Let us set the value of this preventClick variable to false.
let preventClick = false;
o	Within the the clickedCard.getAttribute we will assign the Boolean true to the preventClick variable to prevent a matched card from being clicked on again.
function onCardClicked(e) {
            const target = e.currentTarget;
            if (
            preventClick ||
            target === clickedCard ||
            target.className.includes('done')
    ) {
        return;
    }}

MOVES LOGIC
o	The number moves (clicks) a player has executed for the duration of one game are not yet trackable by a counter. This is work in progress step.

