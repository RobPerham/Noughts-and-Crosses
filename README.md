# Noughts-and-Crosses
I planning to going create a Noughts & Crosses (tick tac toe)game with using html and css and javascrpit 
to help understand funtermeal of the Javascript which i am currently learning here but I need work real world practice of combinme in 

 first step is create the block code for the Bacic website
 in VSC they have block code html5 which gives a quick start start promoting 
 but I need put in css and javascript in so every thing should link together 

 I need to make the borad for the game itself whihc i going used the <table > 

<body>
  <table>
    <tr>
      <td class="cell" id="0"></td>
      <td class="cell" id="1"></td>
      <td class="cell" id="2"></td>
    </tr>

    <tr>
      <td class="cell" id="3"></td>
      <td class="cell" id="4"></td>
      <td class="cell" id="5"></td>
    </tr>

    <tr>
      <td class="cell" id="6"></td>
      <td class="cell" id="7"></td>
      <td class="cell" id="8"></td>
    </tr>

  </table>
  <div class="endagme">
    <div class="text"></div>
  </div>
  <button onclick="startGame()">Replay</button>

  <script src="script.js"></script>
</body>

this a is grid for the broad but need to add the css to make show on the website 
so add target the <td> element to make the show up on used border and height width and other show the board for outline of the game 

td {
  border: 2px solid black;
  height: 00px;
  width: 200px;
  text-align: center;
  vertical-align: center;
  font-family: 'Times New Roman', Times, serif;
  font-size: 70px;
  cursor: pointer;
}

these funtantion all show the show the grid 

now we have to gtraget the postion and gap between the the boxes 
so take the table class becuse the will effect the all look of the table here 

table {
  border-collapse: collapse;
  position: absolute;
  left: 50%;
  margin-left: -305px; (600px + 10 = 610 /2 =305px)
  top: 50%;
}
 this code will put the board on the  cnetre on the screen  prefect !!!

GAME OVER BOX
 but we need to place the start/ repaly funtion in the centre of the board which the Called .enggame
 at monnt is box over the board when get on the typeing out the javacript will show up when the game is finsih 
 atm i would need still need to style the box bit more but move on the next step is starting java-script 

 Start of the Java-scprit for Noughts & Crosses

 we started with a make board visable for the for java-sript so place the the this code the make the give put player in stystem and show the different winning combo 

java-scritp.js
var origBoard; ( this var allow how the script show the to code )
const huPlayer = 'O'; 
const aiPlayer = 'X';
these two code above used the const function which who and what Noughts & Crosses there are .
const winCombs = [
  [0, 1, 2],
  [3, 4, 5],
  [6, 7, 8],
  [0, 3, 6],
  [1, 4, 7],
  [2, 5, 8],
  [0, 4, 8],
  [6, 4, 2]
]
this code above implase that diffecnernt way wmethod the win the combo to beat the coputer 


this code the show the imput the funcation the the HUplayer choices and restart the game with that.

this make the grid cell invidution 
const cells = document.querySelectorAll('.cell')
startGame();


function startGame() {
  document.querySelector(".endgame").style.display = "none";
  origBoard = Array.from(Array(9).keys());
  for (var i = 0; i < cells.length; i++) {
    cells[i].innerText = '';
    cells[i].style.removeProperty('background-color');
    cells[i].addEventListener('click', turnClick, false);
  }
}
function turnClick(square) {
  turn(square.target.id, huPlayer)
}

function turn(squareId, player) {
  origBoard[squareId] = player;
  document.getElementById(squareId).innerText = player;
}

this code allow me put my input in the code and restart the game
