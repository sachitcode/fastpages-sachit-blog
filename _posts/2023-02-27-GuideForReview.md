---
toc: true
layout: post
description: Key information about my part of the project.
categories: [markdown]
title: "Guide for Review"
---

# Frontend

### Frontend Function

Overview: The function called getAirportName uses the city inputted by the user form the following sentence which is displayed to the user at the end of the function: "Nearest Aiport to City Name: Airport Name".

[Link to File](https://github.com/raunak2007/RECS-repo/blob/gh-pages/nearest_airport.md?plain=1)
Line Numbers: 105 - 206

### Error Testing

Overview: In order to prevent garbage input from getting executed in my code, I created this if statement to check if the "city" inputted is valid and if it's in the RapidAPI API.

[Link to File](https://github.com/raunak2007/RECS-repo/blob/gh-pages/nearest_airport.md?plain=1)
Line Numbers: 132 - 141

# Backend

### Backend API Model

Overview: My API model serves as a model for my API to reference. To make this, I adjusted Mr. Mortensen's code to my own project's needs.

[Link to File](https://github.com/EdwinKuttappi/farmersflask/blob/main/model/airportmodel.py)

### Backend API

Overview: This API uses the API model as a structure for itself. This API includes the create and read functions that I made for me to be able to display the data in the API and add more data to it.

[Link to File](https://github.com/EdwinKuttappi/farmersflask/blob/main/api/airport.py)
