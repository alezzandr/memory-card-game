# memory-card-game
<!DOCTYPE html>
<html>
<head>
  <title>Memory Card Game</title>
<link rel="stylesheet" type="text/css" href="style.css">
<style id="jsbin-css">
.board {
	height: 50%;
	width: 75%;
	display: inline-block;
}
.card {
	height: 200px;
	width: 150px;
	background-color: #ffff00;
	border:1px rgb(0,0,0) solid;
	border-radius: 10px;
	float: left;
	margin: 8%;
	position: relative;
}
h1 {
	color: rgba(2,132,130,1);
}
h2 {
	color: #ffd700;
}
h3 {
	color: #dd4400;
}
.name {
	color: #ff0000;
}
body {
	text-align: center;
}
nav {
	background-color: #808080;
}
a {
	background-color: #ffbf00;
	color: white;
	padding: 35px;
	display: block;
	float: left;
}
a:hover {
	background-color: #ee5f3c
}
.clearfix:after {
	visibility: hidden;
	display: block;
	content: " ";
	clear: both;
	height: 0;
	font-size: 0;
}
footer {
	background-color: #808080;
}
img {
	height: 201px;
	width: 151px;
	background-color: #ffff00;
	border:1px rgb(0,0,0) solid;
	border-radius: 12px;
	float: left;
}
</style>
</head>
<body>
  <nav class="clearfix nav">
    <a href="#">Instructions</a>
    <a href="#">Game</a>
  </nav>
  <h1>Memory Game</h1>
  <h2>Instructions</h2>
  <p>Concentration, also known as Match Match, Memory, Pelmanism, Shinkei-suijaku, Pexeso, or Pairs, is a card game in which all of the cards are laid facedown on a surface and two cards are flipped face up over each turn. The object of the game is to turn over pairs of matching cards.</p>
  <hr>
  <div class="board" id="game-board">
<!--
    <div class="card"></div>
    <div class="card"></div>
    <div class="card"></div>
    <div class="card"></div>
-->
  </div>
  <h3>This game is crazy cool.  I have heard that you are actually not that cool unless you play this game.</h3>
  <footer>
    <h3>Created with ♥ by <span class="name">Todd C. Gerdy</span>.</h3>
  </footer>
  <script src="main.js"></script>
<script id="jsbin-javascript">
console.log("JS file is connected to HTML! Woo!");
// find how many elements have 'game-board as Id'
var board = document.getElementById('game-board');
var cards = ['queen','queen','king','king'];
var cardsInPlay = [];
function createBoard() {
	//instead of looping through a fixed number
	//loop through the length of the cards
	for (var i = 0; i<cards.length; i++) {
		//this will set the card's 'data-card' to be the element of the array
		//data - attributes are meant to store data about element that is not
		//tied to a style,
		//i.e., 'king'.
		var cardElement = document.createElement('div');
		cardElement.className = 'card';
		cardElement.setAttribute('data-card', cards[i]);
		//when a card is clicked the function isTwoCards will be executed
		cardElement.addEventListener('click', isTwoCards);
		// append the card to the board
	  board.appendChild(cardElement);
		board.appendChild(cardElement);
	}
}
//checks to see if there are cards in play
function isTwoCards() {
	//add card to array of cards in play
	//'this' hasn't been covered in this pre-work, but
	//for now, just know it gives you access to the card the user clicked on
	cardsInPlay.push(this.getAttribute('data-card'));
	if (this.getAttribute('data-card') === 'king') {
		this.innerHTML = '<img src="kingOfSpades.png" alt="King of Spades" />';
	} else {
		this.innerHTML = '<img src="queenOfHearts.png" alt="Queen of Hearts"/>';
	}
	if (cardsInPlay.length === 2) {
		isMatch(cardsInPlay);
		cardsInPlay = [];
	}
}
var cardReset = [];
//check for a match
function isMatch() {
	if (cardsInPlay[0] === cardsInPlay[1]) {
		alert ("You found a match!")
		console.log(cardsInPlay);
		console.log(cardsInPlay[0]);
		// cardsInPlay[0].innerHTML='';
	} else {
		alert ("Sorry, try again.");
	}
	for(var x = 0; x<cards.length;x++) {
		console.log(cardReset);
		cardReset.push(this.getElementByClassName('card'));
		cardReset[x].innerHTML='';
	}
}
createBoard();
</script>

<script id="jsbin-source-html" type="text/html"><!DOCTYPE html>
<html>
<head>
  <title>Memory Card Game</title>
<link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
  <nav class="clearfix nav">
    <a href="#">Instructions</a>
    <a href="#">Game</a>
  </nav>
  <h1>Memory Game</h1>
  <h2>Instructions</h2>
  <p>Concentration, also known as Match Match, Memory, Pelmanism, Shinkei-suijaku, Pexeso, or Pairs, is a card game in which all of the cards are laid facedown on a surface and two cards are flipped face up over each turn. The object of the game is to turn over pairs of matching cards.</p>
  <hr>
  <div class="board" id="game-board">
<\!--
    <div class="card"></div>
    <div class="card"></div>
    <div class="card"></div>
    <div class="card"></div>
-->
  </div>
  <h3>This game is crazy cool.  I have heard that you are actually not that cool unless you play this game.</h3>
  <footer>
    <h3>Created by <span class="name">Alex V. Dodita</span>.</h3>
  </footer>
  <script src="main.js"><\/script>
</body>
</html>
</script>

<script id="jsbin-source-css" type="text/css">.board {
	height: 50%;
	width: 75%;
	display: inline-block;
}
.card {
	height: 200px;
	width: 150px;
	background-color: #ffff00;
	border:1px rgb(0,0,0) solid;
	border-radius: 10px;
	float: left;
	margin: 8%;
	position: relative;
}
h1 {
	color: rgba(2,132,130,1);
}
h2 {
	color: #ffd700;
}
h3 {
	color: #dd4400;
}
.name {
	color: #ff0000;
}
body {
	text-align: center;
}
nav {
	background-color: #808080;
}
a {
	background-color: #ffbf00;
	color: white;
	padding: 35px;
	display: block;
	float: left;
}
a:hover {
	background-color: #ee5f3c
}
.clearfix:after {
	visibility: hidden;
	display: block;
	content: " ";
	clear: both;
	height: 0;
	font-size: 0;
}
footer {
	background-color: #808080;
}
img {
	height: 201px;
	width: 151px;
	background-color: #ffff00;
	border:1px rgb(0,0,0) solid;
	border-radius: 12px;
	float: left;
}
</script>

<script id="jsbin-source-javascript" type="text/javascript">console.log("JS file is connected to HTML! Woo!");
// find how many elements have 'game-board as Id'
var board = document.getElementById('game-board');
var cards = ['queen','queen','king','king'];
var cardsInPlay = [];
function createBoard() {
	//instead of looping through a fixed number
	//loop through the length of the cards
	for (var i = 0; i<cards.length; i++) {
		//this will set the card's 'data-card' to be the element of the array
		//data - attributes are meant to store data about element that is not
		//tied to a style,
		//i.e., 'king'.
		var cardElement = document.createElement('div');
		cardElement.className = 'card';
		cardElement.setAttribute('data-card', cards[i]);
		//when a card is clicked the function isTwoCards will be executed
		cardElement.addEventListener('click', isTwoCards);
		// append the card to the board
	  board.appendChild(cardElement);
		board.appendChild(cardElement);
	}
}
//checks to see if there are cards in play
function isTwoCards() {
	//add card to array of cards in play
	//'this' hasn't been covered in this pre-work, but
	//for now, just know it gives you access to the card the user clicked on
	cardsInPlay.push(this.getAttribute('data-card'));
	if (this.getAttribute('data-card') === 'king') {
		this.innerHTML = '<img src="kingOfSpades.png" alt="King of Spades" />';
	} else {
		this.innerHTML = '<img src="queenOfHearts.png" alt="Queen of Hearts"/>';
	}
	if (cardsInPlay.length === 2) {
		isMatch(cardsInPlay);
		cardsInPlay = [];
	}
}
var cardReset = [];
//check for a match
function isMatch() {
	if (cardsInPlay[0] === cardsInPlay[1]) {
		alert ("You found a match!")
		console.log(cardsInPlay);
		console.log(cardsInPlay[0]);
		// cardsInPlay[0].innerHTML='';
	} else {
		alert ("Sorry, try again.");
	}
	for(var x = 0; x<cards.length;x++) {
		console.log(cardReset);
		cardReset.push(this.getElementByClassName('card'));
		cardReset[x].innerHTML='';
	}
}
createBoard();
</script></body>
</html>

