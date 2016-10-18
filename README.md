# Tournament Database Project
Designed to track players for any game in any simple Swiss Pairing playoff game. 
The game tournament will use the Swiss system for pairing up players in each round: players are not eliminated, and each player should be paired with another player with the same number of wins, or as close as possible.

This project has two parts: defining the database schema (SQL table definitions), and writing the code that will use it.

# Code Templates
The templates for this project are in the tournament subdirectory of your VM’s /vagrant directory. You’ll find three files there: tournament.sql, tournament.py, and tournament_test.py.

The template file tournament.sql is where you will put the database schema, in the form of SQL create table commands. Give your tables names that make sense to you, and give the columns descriptive names. You'll also need to create the database itself; see below.

The template file tournament.py is where you will put the code of your module. In this file you’ll see stubs of several functions. Each function has a docstring that says what it should do.

Finally, the file tournament_test.py contains unit tests that will test the functions you’ve written in tournament.py. You can run the tests from the command line, using the command python tournament_test.py.

# Getting Started
* Open Command Line,then open psql and enter
* We can execute psql statements in either of two ways:
  1) Paste each statement in to psql. 
  2) Use the command \i tournament.sql to import the whole file into psql at once.
* Create a new Database
  CREATE database tournament;
* To connect to the new database
  \c tournament
* To get all the tables and views necessary set up and ready to roll.
  \i tournament.sql
* From your command line, cd into the tournament directory, launch python, then pull in the tournament.py file:
  from tournament import *
* For test cases, from your command line in the tournament folder, simply run:
  python tournament_test.py
* In your python terminal, enter each player's name using:
  registerPlayer("[player's full name]")
  For example, if you need to enter Bob Smith, you'll run:

  registerPlayer("Bob Smith")
  That's it! your roster is now ready to start.

# FUNCTION LIST

1) registerPlayer(name) 
Adds a player to the tournament by putting an entry in the database. The database assigns an ID number to the player. Different players may have the same names but will receive different ID numbers.

2) countPlayers()
Returns the number of currently registered players. 

3) playerStandings()
Returns a list of (id, name, wins, matches) for each player, sorted by the number of wins each player has.

4) reportMatch(winner, loser)
Stores the outcome of a single match between two players in the database.

5) swissPairings()
Given the existing set of registered players and the matches they have played, generates and returns a list of pairings according to the Swiss system. Each pairing is a tuple (id1, name1, id2, name2), giving the ID and name of the paired players. For instance, if there are eight registered players, this function should return four pairings. This function uses playerStandings to find the ranking of players

6) deleteMatches() 
Clear out all the match records from the database.

7) deletePlayers()
Clear out all the player records from the database.


