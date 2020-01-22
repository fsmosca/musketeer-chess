# Musketeer chess
Game rules and performance test

## Table of contents
* [A. Introduction](#a-introduction)
* [B. Musketeer pieces](#b-musketeer-pieces)
* [C. Piece selection](#c-piece-selection)
* [D. Gating preparation](#d-gating-preparation)
* [E. Gating move](#e-gating-move)
* [F. Piece movements](#f-piece-movements)
  * [1. Leopard](#1-leopard)
  * [2. Cannon](#2-cannon)
  * [3. Unicorn](#3-unicorn)
  * [4. Dragon](#4-dragon)
  * [5. Chancellor](#5-chancellor)
  * [6. Archbishop](#6-archbishop)
  * [7. Elephant](#7-elephant)
  * [8. Hawk](#8-hawk)
  * [9. Fortress](#9-fortress)
  * [10. Spider](#10-spider)
* [G. Game rules](#g-game-rules)
  * [1. Gating](#1-gating)
  * [2. Promotion](#2-promotion)
  * [3. Losing the right to gate](#3-losing-the-right-to-gate)
  * [4. Dropping of musketeer pieces](#4-dropping-of-musketeer-pieces)
  * [5. Gating and pinned piece](#5-gating-and-pinned-piece)
  * [6. The default musketeer piece type](#6-the-default-musketeer-piece-type)
* [H. Performance test or perft](#h-performance-test-or-perft)
* [I. Musketeer GUI](#i-musketeer-gui)
* [J. Example game](#j-example-game)
* [K. References](#k-references)

## A. Introduction
Musketeer chess is a chess variant invented by Zied Haddad. It is basically a chess game but with 10 new selectable piece types such as Leopard, Cannon and [others](#b-musketeer-pieces), that will be added to the game.

It is played on 10x8 board or 10 rows by 8 columns. But most of the actions happen on 8x8 board as in chess.

##### Image 1: Initial board layout

![image 1](https://i.imgur.com/H0uCk6Q.png)

#### Board layout
There are 10 rows, row 0, row 1 ... up to row 9. There are also 8 columns, column a, column b up to column h. A row can also be called a rank and a column can also be called a file.

#### The drop areas
Drop area of white is at row 0 or squares [A0, B0 ... H0] while black is at row 9 or squares [A9, B9 ... H9]. The pieces in drop areas can only enter the playing area through gating moves. [See example in gating section](#a-normal-gating-move).

#### The playing area
The playing area is the same as in chess bounded by squares A1, H1, H8, A8. The pieces inside the playing area cannot move into the drop areas.

#### Game overview
This game has 2 initial phases in order, before the the game starts like in chess
1. PS (piece selection), [described in section C](#c-piece-selection)
2. GP (gating preparation) [described in section D](#d-gating-preparation)  

Then the game can continue as in chess. [See game example section.](#j-example-game)

#### The official musketeer game rules
 * https://musketeerchess.net/games/musketeer/rules/rules-short.php
 * https://musketeerchess.net/site/game-rules/

## B. Musketeer pieces
[Back to table of contents](#table-of-contents)

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
[Back to table of contents](#table-of-contents)

#### The first move of musketeer chess

The first move in musketeer chess is PS (piece selection). White may select 1 piece type from the 10 selectable musketeer piece types in item B and black follows by selecting another piece type. Only 2 piece types are allowed, first is the one selected by white and second the one selected by black.

For example white may select a Leopard and Black can reply by selecting a Cannon (or any other piece but not the piece type selected by white). There after, both sides will have Leopard and Cannon as their additional pieces for the game. See image 1.1 below. See also an example [move sequence in example game section](#j-example-game) for first move.

##### Image 1.1: Piece selection phase is completed

![PS](https://i.imgur.com/wzZ0J9h.png)

#### The default musketeer pieces
During piece selection process, black has the option to use the default musketeer piece types to be used in the game, [see item 7 in game rule](#7-the-default-musketeer-piece-type).

## D. Gating preparation
[Back to table of contents](#table-of-contents)

Gating is a move that enters the musketeer piece into the [playing area](#image-1-initial-board-layout). But before a gate move can be executed on the board, a player has to decide which column the selected pieces will be gated. White can drop the musketeer pieces at row 0 at any column while Black can drop at row 9 at any column as gating preparations.

The second and third moves in musketeer chess can be called GP (Gating Preparation). It consists of dropping the musketeer pieces on the [drop areas](#image-1-initial-board-layout).

#### The second move of musketeer chess
The second move will be dropping of first selected piece (leopard in the example in section C), for example white can play L@b0 or dropping a leopard to square B0. In this case white prepares its leopard to be gated at column b. Black can reply with L@g9 or leopard to square G9, planning to gate its leopard at column g.

#### The third move of musketeer chess
The third move will be dropping of second selected piece (cannon), for example white can play C@d0 and Black can reply with C@f9.

It is not allowed to drop a musketeer piece at column e and another at column a or h because it will gate the musketeer pieces at the same time during castling. [See item 5 in game rules section](#5-dropping-of-musketeer-pieces).

That completes the PS and GP phases, see image below.

##### Image 2: Position after PS and GP

![Image 2](https://i.imgur.com/EulKRvg.png)

## E. Gating move
[Back to table of contents](#table-of-contents)

After PS and GP phases see image 2, white can play a gating move `b1c3l` or `Nc3/L`, moving the knight to square C3 and leopard to B1 all in a single move. See image 3.

##### Image 3: Position after the gate move b1c3l or Nc3/L

![image 3](https://i.imgur.com/vzqD0O1.png)

That enters the leopard into the playing area. It can now move according to its movement rules described in section F.

## F. Piece movements
[Back to table of contents](#table-of-contents)

See also the official site for musketeer chess at https://musketeerchess.net/site/game-rules/

#### 1. Leopard
* Move description
  * It can move like a knight as in chess.
  * It can move like a bishop as in chess but is limited to a maximum of 2 squares.
* Movement image
  * ![leopard](https://i.imgur.com/4m6AOzc.png)
  
#### 2. Cannon
* Move description
  * It can move like a knight as in chess but at the sides only.
  * It can move like a king as in chess.
  * It can jump to a distance of 2 squares horizontally and vertically.
* Movement image
  * ![cannon](https://i.imgur.com/M1v9LZj.png)
  
#### 3. Unicorn
* Move description
  * It can move like a knight as in chess.
  * It can jump to a square adjacent to the knight destination square in the north, south, east and west directions.
* Movement image
  * ![unicorn](https://i.imgur.com/axScV2u.png)
  
#### 4. Dragon
* Move description
  * It can move like a queen as in chess.
  * It can move like a knight as in chess.
* Movement image
  * ![dragon](https://i.imgur.com/KBb0u6U.png)
  
#### 5. Chancellor
* Move description
  * It can move like a rook as in chess.
  * It can move like a knight as in chess.
* Movement image
  * ![chancellor](https://i.imgur.com/4jZLzHB.png)
    
#### 6. Archbishop
* Move description
  * It can move like a bishop as in chess.
  * It can move like a knight as in chess.
* Movement image
  * ![archbishop](https://i.imgur.com/oGe1gkc.png)
  
#### 7. Elephant
* Move description
  * It can move like a king as in chess.
  * It can jump to a distance of 2 squares, horizontally, vertically and diagonally.
* Movement image
  * ![elephant](https://i.imgur.com/j2wgFLe.png)
  
#### 8. Hawk
* Move description
  * It can jump to a distance of 2 squares, horizontally, vertically and diagonally.
  * It can jump to a distance of 3 squares, horizontally, vertically and diagonally.
* Movement image
  * ![hawk](https://i.imgur.com/EWmlalw.png)
  
#### 9. Fortress
* Move description
  * It can move like a bishop as in chess but is limited to a maximum of 3 squares.
  * It can move like a knight as in chess, but only at front and back.
  * It can jump to a distance of 2 squares horizontally and vertically.
* Movement image
  * ![fortress](https://i.imgur.com/Y0rnhk4.png)

#### 10. Spider
* Move description
  * It can move like a bishop as in chess but is limited to a maximum of 2 squares.
  * It can move like a knight as in chess.
  * It can jump to a distance of 2 squares horizontally and vertically.
* Movement image
  * ![spider](https://i.imgur.com/uCD8pOA.png)
  
## G. Game rules
[Back to table of contents](#table-of-contents)

The following are the rules that are different from Chess.

### 1. Gating
A gating move enters the musketeer piece from drop area to the [playing area](#image-1-initial-board-layout).

##### Image 4: White to move.

![image 4](https://i.imgur.com/1e0uMMI.png)

#### a. Normal gating move
From image 4, white can play `b1c3l` or `Nc3/L` gating move. See image below.

##### Image 5: Position after `b1c3l` or `Nc3/L`
![](https://i.imgur.com/Bah6x1E.png)

The cannon is now in playing area at square B1.

#### b. Castle with gating at king column
From image 4, white can castle with `e1g1l` or `O-O/L` gating move. See image below.

##### Image 6: Position after `e1g1l` or `O-O/L`

![castle gating](https://i.imgur.com/O37xoXU.png)

Leopard is now in playing area at E1.

#### c. Castle with gating at rook column
Castle with gating at rook column is also possible. See image below.

##### White to move and ready to castle
![](https://i.imgur.com/w7fWtBE.png)

White castles with gating by `e1g1l` or `O-O/L`, see image below.

##### Position after `e1g1l` or `O-O/L`
![](https://i.imgur.com/e6KV32s.png)

The leopard has now entered the playing area at H1.

#### d. King captures the attacker as check evasion with gating

##### Image 7: White to move

![king in check](https://i.imgur.com/NA36dXg.png)

White king captures the attacker by `e1f2l` or `Kxf2/L` with gating. See image below.

##### Image 8: Position after Kxf2/L

![king capture check evasion](https://i.imgur.com/2MB76JC.png)

Since the king captures its attacker on square F2, it is able to gate the leopard to square E1.

### 2. Promotion
A pawn can promote to either N, B, R, Q, 1st selected piece or 2nd selected piece. For example in PS (piece selections) phase, a leopard and a cannon were selected, a pawn can promote to either of those piece type.

### 3. Losing the right to gate
There are situations where a player cannot gate its musketeer piece.

#### a. The gate helper is captured

##### Image 9: Black to play

![bishop captures knight](https://i.imgur.com/FraBYTh.png)

From image 9, black can capture the knight (gate helper) by f5b1 or Bxb1, as a result white could no longer gate its cannon. See image 10.

##### Image 10: Position after black's Bxb1

![cannon cannot enter the playing area](https://i.imgur.com/1JHmPFQ.png)

That cannon marked X cannot enter the [playing area](#image-1-initial-board-layout) for the rest of the game, because its gate helper is captured.

#### b. The king is in check and is forced to move without capturing the attacker
If a musketeer piece is dropped at column e or king file, king becomes the gate helper. If this king is in check and cannot capture its attacker, and is forced to make a move, see image below, the player could no longer gate the musketeer piece for the rest of the game.

##### Image 11: White king is in check, attacker is far from king

![King in check](https://i.imgur.com/GNlDc2C.png)

The king cannot capture the queen attacker at square H4, its only move is `e1d2` or `Kd2`. See image below.

##### Image 12: Position after `Kd2`, Leopard cannot gate

![leopard loses the right to gate](https://i.imgur.com/miyJgHh.png)

The musketeer piece marked X cannot enter the [playing area](#image-1-initial-board-layout) for the rest of the game.

### 4. Dropping of musketeer pieces
It is not allowed to drop a musketeer piece at column e or (king column) and the other musketeer piece at column a or h or (rook column). 

For example if the first selected piece is dropped at king column, the second selected piece must not be dropped at rook column. Likewise if the first selected piece is dropped at rook column, the second selected piece must not be dropped at king column. 

The reason for this is that the musketeer pieces at king and rook columns will enter the playing area at the same time when making a **castle** move - this is not allowed.

### 5. Gating and pinned piece
It is illegal to move a pinned piece even if it gates a musketeer piece covering the king attacker. In image 14, the rook pinned the knight, the knight could have gated by Nc3/H or Na3/H or Nd2/H gating the hawk to square B1 - covering the rook attacker, but this is illegal.

##### Image 14: White to move, black rook pins the white knight

![pinned knight](https://i.imgur.com/UPCSzn2.png)

### 6. The default musketeer piece type
Piece selection has default values and these are **cannon** and **leopard**.

During piece selection process, black has the option to choose the default musketeer piece types to be used in the game. For example white selected a spider, and if black does not like it, black should inform white that they will use the default musketeer piece types. The default cannon/leopard can be changed by the tournament director before the match or tournament starts.

## H. Performance test or perft
[Back to table of contents](#table-of-contents)

Counts leaf nodes from a given depth see typical ref for chess at https://www.chessprogramming.org/Perft

See the [Perft folder of this repo](https://github.com/fsmosca/musketeer-chess/tree/master/Perft) to see other perft of specific musketeer piece combinations.

#### Leopard/Cannon
* fen: `lc******/rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR/LC****** w KQkq - 0 1`
* perft 4: `195507`

## I. Musketeer GUI
[Back to table of contents](#table-of-contents)

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
[Back to table of contents](#table-of-contents)

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

Be noted that the first piece selected should be the first piece to be dropped in drop areas. In the example leopard was selected first so it was the piece that was dropped first followed by cannon.

#### 3. The moves in playing area and gating move
On move 4, white opens the game with d4, black replied with a gating move Nf6/L - moved the knight to square F6 and leopard enters at G8. See image 13.

##### Image 13: Black leopard enters the playing area by the gate move Nf6/L or g8f6l

![example game](https://i.imgur.com/sN1iuzC.png)

## K. References
[Back to table of contents](#table-of-contents)

* Official site
  * https://musketeerchess.net/home/index.html
* Official game rules
  * Short
    * https://musketeerchess.net/games/musketeer/rules/rules-short.php
  * Descriptive
    * https://musketeerchess.net/site/game-rules/
* Rules of Chess
  * https://en.wikipedia.org/wiki/Rules_of_chess
* Musketeer Stockfish
  * https://github.com/ianfab/Musketeer-Stockfish
* Betza notation for pieces
  * https://www.gnu.org/software/xboard/Betza.html
* Play musketeer chess in a web page
  * https://musketeerchess.net/games/musketeer/index.php


