---

This program is a **console-based Tic Tac Toe game** designed for two players. It allows users to play the game interactively through a menu system.

---

### 🔹 Main Menu

* The program starts with a **main menu** that keeps running in a loop.
* It displays:

  * A welcome message
  * Instructions to either **play** or **exit**
* Based on user input:

  * Typing **"play"** starts the game
  * Typing **"exit"** ends the program

---

### 🔹 Player Setup

* When the game starts:

  * Player 1 and Player 2 enter their names
  * Each player chooses their own symbol (like X or O)

---

### 🔹 Game Board

* The game uses a **3×3 grid** represented internally as a list.
* The board is displayed in a structured format after every move so players can see the current state of the game.

---

### 🔹 Game Logic

* The game runs in a loop where players take turns.
* On each turn:

  * The current player is asked to choose a position from **1 to 9**
  * The chosen position is updated on the board
  * The board is printed again with the new move

---

### 🔹 Winning Condition

* After each move, the program checks if the current player has won.
* Winning is determined by matching any of the following:

  * Rows
  * Columns
  * Diagonals
* If a player meets any winning condition, the game ends and that player is declared the winner.

---

### 🔹 Draw Condition

* If all positions on the board are filled and no player has won:

  * The game is declared a **draw**

---

### 🔹 Turn Switching

* After every valid move:

  * The turn switches from one player to the other
* This continues until a win or draw occurs

---

### 🔹 Game End

* Once the game ends:

  * A message is displayed announcing the result
  * A thank-you message is shown
  * The user is asked to press ENTER to return to the main menu

---

### 🔹 Overall Description

This program:

* Implements a **two-player Tic Tac Toe game**
* Uses a **menu-driven system**
* Displays the board after each move
* Checks for **win and draw conditions**
* Allows continuous play through the main menu
