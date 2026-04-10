#Tic Tac Toe
This is a **Python console-based Tic Tac Toe game** for two players. I’ll explain it clearly so you understand how each part works 👇

---

## 🔹 1. `mainmenu()` function

This is the **starting point of the program**.

* It runs an **infinite loop (`while True`)**
* Displays:

  * "MAIN MENU"
  * "WELCOME TO TIC TAC TOE"
* Asks user for input:

  * `'play'` → starts the game by calling `playgame()`
  * `'exit'` → ends the program using `break`
  * Any other input → shows error message

👉 So this function controls whether the game starts or exits.

---

## 🔹 2. `playgame()` function

This function contains the **actual game logic**.

### 👤 Player Setup

* Takes names of **Player 1 and Player 2**
* Each player chooses their **symbol** (like `X` or `O`)

---

### 🧩 Game Board

```python
board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]
```

* A list of 9 elements represents a **3×3 grid**
* Each index corresponds to a position:

```
0 | 1 | 2
3 | 4 | 5
6 | 7 | 8
```

---

### 🖨️ `printboard()` function

* Displays the current board in a **grid format**
* Helps players see the game state after each move

---

### 🏆 `winner(player)` function

* Checks if a player has won
* Uses predefined **winning combinations**:

```python
[0,1,2], [3,4,5], [6,7,8]  # rows
[0,3,6], [1,4,7], [2,5,8]  # columns
[0,4,8], [2,4,6]           # diagonals
```

* Returns `True` if player matches any winning condition

---

### 📦 `isfull()` function

* Checks if the board is completely filled
* If no empty spaces → returns `True` (draw condition)

---

## 🔹 3. Game Loop

```python
while True:
```

This loop runs until the game ends.

### Steps:

1. Print board
2. Identify current player
3. Ask for position (1–9)
4. Handle errors:

   * Non-number → error
   * Invalid position → error
   * Already taken → error
5. Place symbol on board

---

### 🏁 Win Check

* If `winner(currentplayer)` → declare winner and break loop

### 🤝 Draw Check

* If board is full → declare draw and break

---

### 🔄 Player Switch

```python
if currentplayer == s1:
    currentplayer = s2
else:
    currentplayer = s1
```

* Alternates turns between players

---

## 🔹 4. Game End

* Displays:

  ```
  !!! THANKS FOR PLAYING !!!
  ```
* Waits for user to press ENTER
* Returns to main menu

---

## 🔹 5. `mainmenu()` call

```python
mainmenu()
```

* Starts the whole program

---

## ✅ Summary

This program:

* Creates a **2-player Tic Tac Toe game**
* Uses:

  * Functions for modular design
  * Lists for board representation
  * Loops for continuous gameplay
  * Condition checks for win/draw

---

## 💡 Small Improvements You Can Add

* Prevent both players choosing same symbol
* Add AI (computer opponent 🤖)
* Add score tracking
* Use numbers on board for easier selection
