---
toc: true
layout: post
description: Written response for my create performance task.
title: CPT Written Response
---

## 3a. 

### 3.a.i.

This program was made made mostly with JavaScript (for the input to be worked with to reach the desired output) and HTML (for the information to be displayed in an organized way to the user). The purpose of the program is to help the user find the nearest airport to a city they want to travel to.

### 3.a.ii.

The video shows the user inputting the city they want to go to. Upon hitting the submit button, the nearest airport to the city is displayed under the text field box and the city with its corresponding airport is also added to the table at the top of the page. 


### 3.a.iii.

After the city is inputted, either the city along with its corresponding airport is displayed and added to the table, or an error message is displayed that states "City not found." because the city inputted by the user doesn't exist in the list of possible cities. 

## 3b.

### 3.b.i.

![]({{site.baseurl}}/images/CPTlist.png)

### 3.b.ii.

![]({{site.baseurl}}/images/CPTlistuse.png)

### 3.b.iii.

The name of the list is "users". 

### 3.b.iv.

The data contained in this list represents the different entries or city-airport pairs that are located in the database. These entries are stored and are later displayed to the user in an HTML table. 

### 3.b.v.

This list manages complexity in the way it makes it easy to access each individual entry of the data making it easy to display the data to the user in the form of a table. The program could not be written without this list because there is no other way to store the different entries as efficiently.


## 3.c.

### 3.c.i.

![]({{site.baseurl}}/images/CPTfunction.png)

### 3.c.ii.

![]({{site.baseurl}}/images/CPTfunctioncall.png)

### 3.c.iii.

The function, create_entry, takes in the city inputted by the user and the airport found through RapidAPI APIs and adds these to the database. 

### 3.c.iv.

The create_entry function takes in 2 parameters (the city and airport) and sends a POST request to send the city with its airport to the database. I've also added an error checking aspect to it which checks to see if POST request was successful. If a response of 200 is not returned, an error is printed in the console. If a response of 200 is returned (successful), another function, add_row, is called which adds the row to the HTML table for the user to see.

## 3.d

### 3.d.i.

#### Call One
In the first call, the user inputs a valid city name and submits this city.


#### Call Two
In the second call, the user inputs an invalid city name and submits the city.



### 3.d.ii.

#### Condition(s) tested by Call One
The first call tests how the program functions when the city inputted is present in the list of valid city names.


#### Condition(s) tested by Call Two
The second call tests how the program functions when the city inputted is not present in the list of valid city names. 


### 3.d.iii.

#### Results of Call One
In this call, the city inputted is in the list of valid city names, so the city and airport is both displayed to the user under the text field box and is added to the HTML table. 


#### Results of Call Two
Since the city inputted in this call isn't in the list of valid city names, the response "City not found." is displayed to the user. Nothing is added to the database and no new entries are added to the HTML table.