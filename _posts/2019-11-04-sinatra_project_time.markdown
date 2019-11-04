---
layout: post
title:      "Sinatra Project Time"
date:       2019-11-04 23:59:46 +0000
permalink:  sinatra_project_time
---


Eight Weeks in and two projects done! It's crazy to see how fast time has gone by since starting the bootcamp. 

The Sinatra portfolio project was all about making a simple Content Management System using an MVC (Model, View, Controller) structure. Another requirement was to use the CRUD (Create, Read, Update, Delete) actions that we learned about in the last four weeks. 

MVC is way of building your application so that the code is separated into different sections. Your views hold the code that renders what the client will see. They also get requests from the client. If the client clicks on a button that says "Create Account", that request gets passed to the controller. The controller holds all of the routes. It's basically the middleman between the views and the models, so when the controller gets that request it passes it to the model. Finally, the models hold all of the application's logic. They're also the one's communicating with the application's database. Once the model grabs the requested information from the database, it hands it off to the controller, who then hands it off to the views for the client to receive. 

I decided to make a very simple bank-like application. A user is able to sign up where their information will be stored in the application's database. Once the user is signed up and logged in, they have the ability to Create, Read, Update, or Delete their accounts. 

I'm excited to see what Rails magic is all about!



