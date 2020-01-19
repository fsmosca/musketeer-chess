# Musketeer chess
Game rules and performance test

### A. Introduction
Musketeer chess is a chess variant invented by Zied Haddad. It is basically a chess but with added new piece types such as Leopard, Cannon, Unicorn, Dragon, Chancellor, Archbishop, Elephant, Hawk, Fortress and Spider.

It is played on 10x8 board or 10 rows by 8 columns.

#### Initial board layout

![](https://i.imgur.com/RmW4vkO.png)

Generally this game has 2 initial phases in order
1. PS (piece selection)
2. GP (gating preparation)  

After which the game may start as in chess but with gating moves.

### B. Musketeer pieces
#### Piece names, id and betza
1. name: Leopard, id: L, betza: NB2
2. name: Cannon, id: C, betza: llNrrNDK
3. Unicorn
4. Dragon
5. Chancellor
6. Archbishop
7. Elephant
8. Hawk
9. Fortress
10. Spider

### C. Piece selection
The first move in musketeer chess is PS (piece selection). A white player may select 1 piece type from the selectable 10 musketeer piece types in item B and black follows by selecting another piece type. 

For example white may select a Leopard and Black can reply by selecting a Cannon (or any other piece but not the piece selected by white). There after, both sides will have Leopard and Cannon as their additional pieces for the game.

### D. Gating preparation
Gating is a move that enters the musketeer piece into the playing area. But before a gate move can be executed on the board, the player has to decide which file these new pieces will be gated. White can drop its new pieces at row 0 at any file while Black can drop at row 9 at any file too. See Initial board layout.

The second and third moves in musketeer chess can be called GP (Gating Preparation). It consists of dropping a piece on drop areas. The first piece selected in PS will be the first to be dropped. In the example in section C, it is Leopard first then cannon second.

For example on their second move, white can play L@b0 or Leopard to square B0, that is Leopard will enter the playing area at b file specifically at square B1 when white will play b1c3l (gating move) or b1a3l, the move suffix l in b1c3l refers to leopard. Black can reply with L@g9 or Leopard to square G9, intending to gate the leopard at g file which can enter the playing area at square G8 after the move g8f6l or g8h6l.

The third move will be dropping of cannons, similar to second move except that it is not allowed to drop a piece behind a rook (a or h files) and the other behind the king (e file). White can play C@d0 and Black can play C@f9.

That completes the PS and GP phases. See image below.

![](https://i.imgur.com/EulKRvg.png)

White can make a gate move on its 4th move by `b1c3l` or `Nc3/L` - moving the knight to c3 square and moving the leopard to b1 square in one move.

### E. Piece movements
* Leopard
* Cannon

### F. Game rules

#### Gating

#### Castling

#### Promotion

### G. Performance test or perft
#### Leopard/Cannon
See the Perft folder of this repo to see other perft of specific musketeer piece combinations.
* fen: `lc******/rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR/LC****** w KQkq - 0 1`
* perft 4: `195507`

### H. Musketeer GUI
  * Winboard
    * Windows desktop
      * Program
        * http://hgm.nubati.net/WinBoard-AA.zip
      * Discussion
        * http://talkchess.com/forum3/viewtopic.php?f=7&t=72572
  * Musketeer home page
    * Web page
      * https://musketeerchess.net/games/musketeer/index.php

### I. Example game

### J. References
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


