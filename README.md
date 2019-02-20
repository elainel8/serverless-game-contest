# Serverless Game Contest

**This is not an officially supported Google product**

This repository contains code that can be used as is or modified to run
a programming contest where participants write game playing apps as
functions as a service. It can also be the basis of an automated programming
assignment receiver and grading system.

There are three parts to this repository:

* */player* Example game playing apps
* */questioners* Functions to run and score the game playing apps
* */manager* An application participants can use to submit game playing apps
and view scores and overall standings

The examples here are all for the simplest possible game: guessing a number.
The can be a starting point for more complicated single-player games, or
even multi-player games. All code is in Python 3.7, but other languages such
as Node.js or Go could be used.

## player

Sample Python 3.7 code to play the "guess a number" game. The code can be
hosted on any function as a service platform, such as Google Cloud Functions,
or any web server that can accept HTTP requests over the Internet.

## questioners

Two example Python 3.7 programs to run any game player, asking for and
receiving successive moves until the player wins a game, fails to make a
valid move, or exceeds an allowed number of moves. There are two sample
programs for the "guess a number" game, one easier than the other for the
players. Any number of questioners can be run simultaneously, evaluating
the players in a variety of circumstances.

In order to allow multiple simultaneous questioner, these examples are to be
run as Google Cloud Functions, triggered by a Pub/Sub topic.

## manager

This Google App Engine Standard Python 3.7 program provides pages for
contestants to submit the web addresses of their players for evaluation and
scoring. It also displays current standings, and administrative features for
initializing new contests.

Questioners report scores either to this application, or to the function
in this folder if the App Engine program is restricted to logged in users.