# Trick or Treat

This game is developed for BSidesPDX 2024

## Game Mechanics

The objective of the game is to trade candy.

At the conference, you have the ability to "cash out", meaning, exchange virtual candy for real candy. For this situation, it makes sense to keep track of the total number of candies of a certain type there is in the "giant pot of candy". The way that happens is not covered here (and can actually lead to some interesting discussions as to how to implement decentralized currency, but that's up to you).

## Setup

At the beginning of the game, you will be asked for your username if you don't have one yet.

You will then be given some candy at random. You can then "rank" your candy. You will rank the candy that you like with a high number and the candy that you don't like with a low number.

Your score is calculated as the sum of the rank of the candy times the number of candies you have of that rank. Once you "cash out", your score is zeroed out and you can start over.

## Gameplay

1. You will be asked if you want to trade candy or steal candy. If you choose to trade, an exchange of candy will take place with your interlocutor. If you choose to steal, you will not trade in anything. Your interlocutor will not know which choice you made until it is too late!
2. You will then find a person to trade with or steal from. Here you can negotiate on what candy you are willing to trade. Once you figure that out, enter the candy and the number of candies you will trade. Your interlocutor will do the same.
3. Then you hold the badges close to trade the candy. The trade will be recorded in a transactions ledger. You can check it if you want to know whether someone traded or stole from you.
4. You can repeat this until you are ready to cash out.

## Code

The code is written using Python 3.10 on Ubuntu 22.04.

I set the environment up using:
```
$ python3.10 -m venv code
$ source code/bin/activate
```

Then you can clone this project and start working with it.

### Where everything is

`game.py` is the main program. You can run it using `./game.py`.

`settings` is a module that manages the initial setup, loads, and stores the settings during the game. It contains the username, the candy the user has, and the stored rank of each candy.

`trade` is a module that manages the trading of the candy and the balancing of the candy books. It also has a `trader.py` module that is only there to simulate another person.

`ui` only has a file with all the text messages I call in `game.py`.
