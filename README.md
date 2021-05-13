# Background - Sylver Coinage:

### GAMEPLAY:

Sylver Coinage is a game played between two players. On each player’s turns they list a positive integer that can’t be made as a linear combination of the previously named numbers. The first player to pick the number 1, loses. An example game could work as follows:

Player 1 picks the number 4

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Now no player can pick any multiple of 4

Player 2 picks the number 5

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The only numbers left that players can now pick are: {1, 2, 3, 6, 7, 11}

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;9 for instance can be made using one 4 and one 5. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To show that any number greater than 4 also can be made using 4’s and 5’s we see the following:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;12 can be made by three 4’s

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;13 can be made with two 4’s and a 5

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;14 can be made with two 5’s and a 4

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;15 can be made with three 5’s

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Now every number can be made as 12 + 4k, 13 + 4k, 14 + 4k, or 15 + 4k for k >= 0

Player 1 picks 11

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The only numbers left that players can pick from are: {1, 2, 3, 6, 7}

Player 2 picks 7

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The only numbers left that players can pick from are: {1, 2, 3, 6}

Player 1 picks 6

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The only numbers left that players can pick from are: {1, 2, 3}

Player 2 picks 3

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The only numbers left that players can pick from are: {1, 2}

Player 1 picks 2

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The only number left that players can pick from are: {1}

So player 2 must choose 1 and therefore lose. 


### THE GOAL:

Design a bot that plays the game best under all circumstances. This means that whatever the starting move, the bot still makes the best move from there. There are known states that result in winning and losing positions, but there are only complete strategies for a very small number of starting states. 

### RULES FOR THE BOT:

•	The program that tests the bots is written in Python3* and each bot has a function "nextMove" that gets called. 

•	The inputs for the function are 1) The moves played so far, 2) The remaining possible moves if there is a finite number of them, 3) The remaining time the bot has to make a move

•	The function returns an integer which represents its move

•	If the function returns an integer that is not a legal move, they lose.

•	The bot has a chess clock with 36 total seconds. The time it takes for the program to verify your bot's move is taken out of your time. 

•	During the competition, the largest move your bot can play is 10000000. For the purposes of testing your bot there is no cap on the move played. 

*Specifically, the bot has to work in the conda environment that can be loaded from sylverEnv.txt.


# Usage

This package contains code for testing a new bot. 
To make sure that your bot is compatible with the competition testing protocol, please download the `sylverEnv.txt` file and run `conda create --name <env> --file sylverEnv.txt` in the command line. 
In order to test your bot, please download the following list of files from this folder into the same folder on your device:
- `testingSylver-version-1.2.py`
- `numericalSemigroupLite.py`

The following files are optional but will allow you to test your bot against my bots:
- `bestBot.py`
- `betterBot.py`
- `mediumBot.py`
- `randomBot.py`
- `worstBot.py`

Once these files are downloaded into a folder, add a file called "myOwnBot.py" which has a class "myBot" with a function "nextMove" to the folder.

Then, simply run the code `testingSylver-version-1.2.py` to test your bot. 
