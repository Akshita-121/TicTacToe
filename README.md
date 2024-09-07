
# TicTacToe: With FSM and Verilog

Tic-Tac-Toe is a very popular paper-and-pencil game in a 3x3 grid for two players. The player who makes the first three of their marks in a diagonal, vertical, or horizontal row wins the game.

![image](https://github.com/user-attachments/assets/17fcd61c-ef6f-4090-9004-2006d555d71d)

# Implementation of the game using FSM concept

The Tic-Tac-Toe game is implemented using a Moore FSM, with four states:

1.IDLE state: It is denoted by 00. When waiting for the player/ computer to play or when resetting the circuit, the FSM is at the IDLE state.

2.PLAYER state: Denoted by 01.The player turns to play and “01” to be stored into the decoded position of the board.

3.COMPUTER state: Denoted y 10.The computer turns to play and “10” to be stored into the decoded position of the board.

4.GAMEOVER state: Denoted by 11.The game is finished when there is a winner or no more space to play

Inputs to the controller are: 


1.Reset: If 0, game begins and if 1, game is over.

2.Play: If 0, remain in idle state and if 1,switch the controller to the PLAYER state and the player plays.

3.PC: If 1, then PC plays and then moves to the idle state.But if 0, it remains in the computer state

4.Illegal_move : When in PLAYER state, Illegal_move = 0 is to switch to COMPUTER state and let computer plays when PC = 1.But if 1, then go to idle state.

5.No_space: If 0, then space left to play, but if 1, then no space left to play and hence game over.

6.Win: If 0, no winner found yet, hence keep playing till no_space=1. If 1, then winner found,hence game over.

## FSM Controller for Tic Tac Toe 
![FSM controller](https://github.com/user-attachments/assets/3d536f8d-ff41-4a7e-8b3d-690101d70057)

## Modules used in the Verilog code

1.Position_registers: To store player or PC position when enaling by FSM controller

2.Winner_detector: To detect who the winner is. In order to win, need three similar (X) or (O) in any of- (1,2,3) or (4,5,6) or(7,8,9) or(1,4,7) or (2,5,8) or (3,6,9) or (1,5,9) or (3,5,7).

3.Position decoder: To decode the position played by the player or the computer. Here we have a 4bit input which signify the 9 available positions and an enable input. For the output we have considered a 16 bit wire,and based on the position selected,the bit becomes 1 in the output wire.

4.Illegal_move_detector: To detect if the player or the computer plays on an existing position which is already played earlier.

5.No_space_detector: To detect if there are places left to play or not.

6.FSM_controller: Controls how player and computer plays the game

## Schematic Model
![tic](https://github.com/user-attachments/assets/57d39d0d-4b13-4e8d-b919-3520873d30cf)

