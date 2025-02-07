TicTacToeGame
---------------
TicTacToe Game using Multithreading in C++ and POSIX
Objective:
Create a multi-threaded TicTacToe Game where two players, X and O, make random moves.
The game should be controlled by two threads, one for each player. 
The board should be updated and printed every time a move is made.
The game ends when a player wins or draws (the board is full).

Structure
---------
1. Game Board:
3x3 grid.
Holds either X or O. Or is empty.
2. Players:
Two players: Player X and Player O.
Each player will make random moves.
3. Threads:
One thread for Player X.
One thread for Player O.
4. Mutex Lock:
The board should be protected using a mutex to avoid any issues
when both players try to move at the same time.
5. Move Logix:
Each player picks a random empty spot and places a mark (X or O).
The game prints the board after each move.
6. Game End Conditions:
The game ends when either Player X or Player O wins.
The game also ends if there's a draw (the board is full).
7. Synchronization:
No conflict between threads (race conditions/deadlocks)

------
1. Game Board Setup and Logic (Player Representation)
Tasks:
- Implement a 3x3 game board.
- Handle printing board.
- Implement the logic that checks if a player won the game (rows, columns, diagonals). Also, check the draw here.

------
2. Multithreading And Mutex (Player Actions)
Tasks:
- Create the thread for Player X. This thread should run in a loop,
  -  making random moves on the board
  -  locking the mutex before making a move
  -  unlocking it afterward
- Make sure here that we print the thread after each move.
- Create the thread for Player O. Refer to the Player X step above.
------
3. Main Thread & Game Management
Tasks:
- Set up the main function to initialize the game.
- Create the threads for Player X and O.
- Use pthread_create() and pthread_join().
- Implement the logic that checks when the game is over.
  - Trigger this after each move.
  - Once triggered, the game ends and prints the results.
