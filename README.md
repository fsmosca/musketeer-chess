# Musketeer chess
Game rules and performance test

## A. Introduction
Musketeer chess is a chess variant invented by Zied Haddad. It is basically a chess but with added new piece types such as Leopard, Cannon, Unicorn, Dragon, Chancellor, Archbishop, Elephant, Hawk, Fortress and Spider.

It is played on 10x8 board or 10 rows by 8 columns.

#### Image 1: Initial board layout

![image 1](https://i.imgur.com/H0uCk6Q.png)

There are 10 rows, row 0, row 1 ... till row 9. There are also 8 columns, column a, column b till column h. Drop area of white is at row 0 or squares [A0, B0 ... H0] while black is at row 9 or squares [A9, B9 ... H9]. The playing area is the same as in chess bounded by squares A1, H1, H8, A8. A row can also be called a rank and a column can also be called a file.

Generally this game has 2 initial phases in order
1. PS (piece selection)
2. GP (gating preparation)  

After which the game may start as in chess but with gating moves.

## B. Musketeer pieces
#### Piece names
1. Leopard
2. Cannon
3. Unicorn
4. Dragon
5. Chancellor
6. Archbishop
7. Elephant
8. Hawk
9. Fortress
10. Spider

#### Piece id
* L = Leopard
* C = Cannon
* U = Unicorn
* D = Dragon
* M = Chancellor
* A = Archbishop
* E = Elephant
* H = Hawk
* F = Fortress
* S = Spider

#### Betza notation
* L = NB2
* C = llNrrNDK
* U = CN
* D = QN
* M = RN
* A = BN
* E = KDA
* H = DHAG
* F = B3DfNbN
* S = B2DN

## C. Piece selection
The first move in musketeer chess is PS (piece selection). A white player may select 1 piece type from the selectable 10 musketeer piece types in item B and black follows by selecting another piece type. 

For example white may select a Leopard and Black can reply by selecting a Cannon (or any other piece but not the piece selected by white). There after, both sides will have Leopard and Cannon as their additional pieces for the game.

## D. Gating preparation
Gating is a move that enters the musketeer piece into the playing area. But before a gate move can be executed on the board, the player has to decide which column these new pieces will be gated. White can drop its new pieces at row 0 at any column while Black can drop at row 9 at any column too. See Initial board layout.

The second and third moves in musketeer chess can be called GP (Gating Preparation). It consists of dropping a piece on drop areas. The first piece selected in PS will be the first to be dropped. In the example in section C, it is Leopard first then cannon second.

For example on their second move, white can play L@b0 or dropping a Leopard to square B0, that is Leopard will enter the playing area at column b specifically at square B1 when white will play for example b1c3l (gating move). Black can reply with L@g9 or Leopard to square G9, intending to gate the leopard at column g which can enter the playing area at square G8.

The third move will be dropping of cannons, similar to second move except that it is not allowed to drop a piece behind a rook (columns a or h) and the other behind the king (column e). White can play C@d0 and Black can play C@f9.

That completes the PS and GP phases.

#### Image 2: Position after PS and GP

![Image 2](https://i.imgur.com/EulKRvg.png)

## E. Gating move
After PS and GP phases see image 2, white can play a gating move `b1c3l` or `Nc3/L`, moving the knight to square C3 and leopard to B1 all in a single move. See image 3.

#### Image 3: Position after the gate move b1c3l or Nc3/L

![image 3](https://i.imgur.com/vzqD0O1.png)

That enters the leopard into the playing area. It can now move according to its movement rules described in section F.

## F. Piece movements
See how musketeer pieces move in a playing area at https://musketeerchess.net/site/game-rules/

#### 1. Leopard
* Move description
  * It can jump like a knight as in chess.
  * It can slide like a bishop as in chess but is limited to a maximum of 2 squares.
* Movement image
  * ![leopard](https://i.imgur.com/4m6AOzc.png)
  
#### 2. Cannon
* Move description
  * Can jump like a knight as in chess but at the sides only.
  * Can move like a king as in chess.
  * Can jump at a distance of 2 squares horizontally and vertically.
* Movement image
  * ![cannon](https://i.imgur.com/M1v9LZj.png)
  
#### 3. Unicorn
* Move description
  * Can jump like a knight as in chess.
  * Can jump to a square adjacent to the knight destination square in the north, south, east and west directions.
* Movement image
  * ![unicorn](https://i.imgur.com/axScV2u.png)
  
#### 4. Dragon
* Move description
  * Can move like a queen as in chess.
  * Can move like a knight as in chess.
* Movement image
  
## G. Game rules

### 1. Gating
A gating move enters the musketeer piece into the playing area, after the PS and GP phases.

##### Image 4: Sample position after PS and GP, white to move.

![image 4](https://i.imgur.com/1e0uMMI.png)

##### a. Normal gating move
From image 4, white can play `b1c3l` or `Nc3/L` gating move.

##### Image 5: Position after b1c3l
![](https://i.imgur.com/Bah6x1E.png)

##### b. Castle gating move
From image 4, white can castle with `e1g1l` or `O-O/L` gating move.

##### Image 6: Position after e1g1l gating move

![castle gating](https://i.imgur.com/O37xoXU.png)

### 2. Promotion
After PS and GP phases, a pawn can promote to either N, B, R, Q, 1st selected piece or 2nd selected piece.

### 3. When the king of side to move is in check or under attack

##### Image 7: White to move, its king is in check

![king in check](https://i.imgur.com/NA36dXg.png)

* As in chess a king cannot castle if in check.
* The king cannot gate if in check except if that king captures the attacker. See image 8.

##### Image 8: King capture check evasion

![king capture check evasion](https://i.imgur.com/2MB76JC.png)

### 4. Losing the right to gate
There are situations where a player cannot gate its musketeer piece.

#### a. The piece in front of it, is captured.

##### Image 9: Black to play

![bishop captures knight](https://i.imgur.com/FraBYTh.png)

From image 9, black can capture the knight by f5b1 or Bxb1, as a result white could no longer gate its cannon. See image 10.

##### Image 10: White loses the right to gate its cannon.

![cannon cannot enter the playing area](https://i.imgur.com/1JHmPFQ.png)

That cannon marked X cannot enter the playing area for the rest of the game.

#### b. The king is in check
If a musketeer piece is located at e column or king file and if this king is in check and this king cannot capture its attacker, see image 11, the player could no longer gate that piece for the rest of the game.

##### Image 11: White king is in check, attacker is far from king

![King in check](https://i.imgur.com/GNlDc2C.png)

White to play and its king is under check or attack, the king cannot capture the queen at H4, its only move is e1d2 or Kd2. See image 12.

##### Image 12: King loses the right to gate its leopard

![leopard loses the right to gate](https://i.imgur.com/miyJgHh.png)

The musketeer piece marked X cannot enter the playing area for the rest of the game.

## H. Performance test or perft

See the Perft folder of this repo to see other perft of specific musketeer piece combinations.

#### Leopard/Cannon
* fen: `lc******/rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR/LC****** w KQkq - 0 1`
* perft 4: `195507`

## I. Musketeer GUI
  * Winboard
    * Windows desktop
      * Program
        * http://hgm.nubati.net/WinBoard-AA.zip
      * Discussion
        * http://talkchess.com/forum3/viewtopic.php?f=7&t=72572
  * Musketeer home page
    * Web page
      * https://musketeerchess.net/games/musketeer/index.php

## J. Example game

## K. References
* Official site
  * https://musketeerchess.net/home/index.html
* Official game rules
  * https://musketeerchess.net/site/game-rules/
* Musketeer Stockfish
  * https://github.com/ianfab/Musketeer-Stockfish
* Betza notation for pieces
  * https://www.gnu.org/software/xboard/Betza.html
* Play musketeer chess in a web page
  * https://musketeerchess.net/games/musketeer/index.php


