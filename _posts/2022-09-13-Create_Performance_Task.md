---
toc: true
layout: post
description: A project idea for Create Performance Task.
categories: [markdown]
title: Create Performance Task
---

# Program Purpose and Function

An idea I came up with for the Create Performance Task project is a Math Quiz game. In this game there will be three difficulty levels: Easy, Medium, and Hard. There will be a random math question (based on difficulty selected) shown at the top of the screen. Below the question, there will be many boxes (one of them containing the answer) scattered across the screen. Every time you select the correct answer, you get 1000 points (for getting the question right) and the screen changes to show the next question. You can get the questions wrong infinite times, but each time you select and incorrect answer, your total score will decrease by 100 points. There will be a timer in the corner of the screen showing the amount of time left until the game ends. The goal of the game is to get the most points that you can.

# Data Abstraction

Many variables will be used to store different values in the program. Some variables that will be very useful are a variable for the score, a variable for the timer, variables for the answers scattered across the screen, and variables for the lists for each difficulty.

# Managing Complexity

To manage the complexity of my code, I will add the questions into a list and randomly generate questions from the list. There will be a list for each difficulty level.

# Procedural Abstraction

To manage the difficulty, there will be three different buttons to select how hard the user wants the quiz to be. The list that will be accessed during the quiz depends on the difficulty level selected. For example, if easy mode is selected, questions from the list containing the easy mode questions will be asked. 

# Algorithm Implementation

A way I can implement an algorithm is by including a percent representing how many questions the user got correct without selecting an incorrect answer.

# Testing

To test the project, I will run all three difficult modes and test whether the point system works. I will also make sure that the game ends and displays the final score when the timer ends.
