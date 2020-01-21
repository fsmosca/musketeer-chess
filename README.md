# Musketeer chess
Game rules and performance test

## Table of contents
* [A. Introduction](#a-introduction)
* [B. Musketeer pieces](#b-musketeer-pieces)
* [C. Piece selection](#c-piece-selection)
* [D. Gating preparation](#d-gating-preparation)
* [E. Gating move](#e-gating-move)
* [F. Piece movements](#f-piece-movements)
* [G. Game rules](#g-game-rules)
* [H. Performance test or perft](#h-performance-test-or-perft)
* [I. Musketeer GUI](#i-musketeer-gui)
* [J. Example game](#j-example-game)
* [K. References](#k-references)

## A. Introduction
Musketeer chess is a chess variant invented by Zied Haddad. It is basically a chess game but with new selectable piece types such as Leopard, Cannon and others, [see section B](#b-musketeer-pieces), that will be added to the game.

It is played on 10x8 board or 10 rows by 8 columns. But most of the game happens on 8x8 board as in chess.

##### Image 1: Initial board layout

![image 1](https://i.imgur.com/H0uCk6Q.png)

#### Board layout
There are 10 rows, row 0, row 1 ... up to row 9. There are also 8 columns, column a, column b up to column h. A row can also be called a rank and a column can also be called a file.

#### The drop areas
Drop area of white is at row 0 or squares [A0, B0 ... H0] while black is at row 9 or squares [A9, B9 ... H9]. The pieces in drop areas can only enter the playing area through gating moves. [See example in gating section](#a-normal-gating-move).

#### The playing area
The playing area is the same as in chess bounded by squares A1, H1, H8, A8. The pieces inside the playing area cannot move into the drop areas.

#### Game overview
Generally this game has 2 initial phases in order
1. PS (piece selection), [described in section C](#c-piece-selection)
2. GP (gating preparation) [described in section D](#d-gating-preparation) 
3. Then the game can continue as in chess. [See game example section.](#j-example-game)

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

#### The first move of musketeer chess

The first move in musketeer chess is PS (piece selection). A white player may select 1 piece type from the selectable 10 musketeer piece types in item B and black follows by selecting another piece type. Only 2 musketeer piece types are allowed, first is the one selected by white and second the one selected by black.

For example white may select a Leopard and Black can reply by selecting a Cannon (or any other piece but not the piece type selected by white). There after, both sides will have Leopard and Cannon as their additional pieces for the game. See image 1.1 below. See also an example [move sequence in example game section](#j-example-game) for first move.

##### Image 1.1: Piece selection phase is completed

![PS](https://i.imgur.com/wzZ0J9h.png)

## D. Gating preparation
Gating is a move that enters the musketeer piece into the playing area. But before a gate move can be executed on the board, the player has to decide which column the selected pieces will be gated. White can drop the musketeer pieces at row 0 at any column while Black can drop at row 9 at any column as gating preparations.

The second and third moves in musketeer chess can be called GP (Gating Preparation). It consists of dropping the musketeer pieces on the drop areas, [see image 1](#image-1-initial-board-layout).

#### The second move of musketeer chess
The second move will be dropping of first selected piece (leopard), for example white can play L@b0 or dropping a leopard to square B0. In this case white prepares its leopard to be gated at column b. Black can reply with L@g9 or leopard to square G9, planning to gate its leopard at column g.

#### The third move of musketeer chess
The third move will be dropping of second selected piece (cannon), for example white can play C@d0 and Black can reply with C@f9.

It is not allowed to drop a musketeer piece at column e and another at column a or h because it will gate the musketeer pieces at the same time during castling. [See item 5 in game rules section](#5-dropping-of-musketeer-pieces).

That completes the PS and GP phases.

##### Image 2: Position after PS and GP

![Image 2](https://i.imgur.com/EulKRvg.png)

## E. Gating move
After PS and GP phases see image 2, white can play a gating move `b1c3l` or `Nc3/L`, moving the knight to square C3 and leopard to B1 all in a single move. See image 3.

##### Image 3: Position after the gate move b1c3l or Nc3/L

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
  * ![dragon](https://i.imgur.com/KBb0u6U.png)
  
#### 5. Chancellor
* Move description
  * Can move like a rook as in chess.
  * Can move like a knight as in chess.
* Movement image
  * ![chancellor](https://i.imgur.com/4jZLzHB.png)
    
#### 6. Archbishop
* Move description
  * Can move like a bishop as in chess.
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
* The king cannot gate if in check except if that king captures the attacker. [See image 8](#image-8-king-evades-the-attack-by-capturing-its-attacker).

##### Image 8: King evades the attack by capturing its attacker

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
If a musketeer piece is dropped at column e or king file and if the king is in check and this king cannot capture its attacker, and is forced to make a move, see image 11, the player could no longer gate the musketeer piece for the rest of the game.

##### Image 11: White king is in check, attacker is far from king

![King in check](https://i.imgur.com/GNlDc2C.png)

White to play and its king is under check or attack, the king cannot capture the queen at H4, its only move is e1d2 or Kd2. See image 12.

##### Image 12: King loses the right to gate its leopard

![leopard loses the right to gate](https://i.imgur.com/miyJgHh.png)

The musketeer piece marked X cannot enter the playing area for the rest of the game.

### 5. Dropping of musketeer pieces
It is not allowed to drop a musketeer piece at column e or (king column) and the other musketeer piece at column a or h or (rook column). For example if the first selected piece is dropped at king column, the second selected piece must not be dropped at rook column. Likewise if the first selected piece is dropped at rook column, the second selected piece must not be dropped at king column. The reason for this is that the musketeer pieces at king and rook columns will enter the playing area at the same time when making a **castle** move - this is not allowed.

### 6. Gating and pinned piece
It is illegal to move a pinned piece even if it gates a musketeer piece covering the king attacker. In image 14, the rook pinned the knight, the knight could have gated by Nc3/H or Na3/H or Nd2/H gating the hawk to square B1 - covering the rook attacker, but this is illegal.

##### Image 14: White to move, black rook pins the white knight

![pinned knight](https://i.imgur.com/UPCSzn2.png)

## H. Performance test or perft
Counts leaf nodes from a given depth see typical ref for chess at https://www.chessprogramming.org/Perft

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
```
1. leopard  cannon
2. L@b0  L@g9
3. C@d0  C@f9
4. d4  Nf6/L
```
### Game comment

The start position will allow the user to select a piece, see image below. This system is the one used in https://musketeerchess.net/games/musketeer/index.php.

![](https://i.imgur.com/jELMGL0.png)

#### 1. Piece selection phase (move 1)
White selected a leopard in the first move. What white has selected, black can have that piece too. See image below.

##### Position after 1. leopard

![](https://i.imgur.com/y3cn7c2.png)

Black replied by selecting a cannon. What black has selected, white can have it too. See image below.

##### Position after 1... cannon

![](https://i.imgur.com/5VmiMxQ.png)

In this game, only 2 piece types are allowed to be selected, so piece selection phase is now complete. Both sides have now a leopard and a cannon. Selectable pieces that were not selected are removed from the board, [see image 1.1](#image-11-piece-selection-phase-is-completed). 

#### 2. Gating preparation phase (move 2 and 3)
On the second move, white dropped its leopard at column b. See image below.

##### Position after 2. L@b0

![](https://i.imgur.com/QiXBA58.png)

Black dropped its leopard at column g. See image below.

##### Position after 2... L@g9

![](https://i.imgur.com/ITMYgeh.png)

Third move dropped the cannons. That completes the gating preparation. See image below.

##### White to play after move 3

![](https://i.imgur.com/gMmsQa6.png)

#### 3. The moves in playing area and gating move
On move 4, white opens the game with d4, black replied with a gating move Nc3/L - moved the knight to square F6 and leopard enters at G8. See image 13.

##### Image 13: Black leopard enters the playing area by the gate move Nc3/L or g8f6l

![example game](https://i.imgur.com/sN1iuzC.png)

## K. References
* Official site
  * https://musketeerchess.net/home/index.html
* Official game rules
  * https://musketeerchess.net/site/game-rules/
* Rules of Chess
  * https://en.wikipedia.org/wiki/Rules_of_chess
* Musketeer Stockfish
  * https://github.com/ianfab/Musketeer-Stockfish
* Betza notation for pieces
  * https://www.gnu.org/software/xboard/Betza.html
* Play musketeer chess in a web page
  * https://musketeerchess.net/games/musketeer/index.php


