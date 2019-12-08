---
layout: post
title:      "Devise is Awesome"
date:       2019-12-08 19:24:18 +0000
permalink:  devise_is_awesome
---


Like in the Sinatra project, one of the requirements for the Rails project was to be able to authenticate users. The Devise gem takes care of it! 

The first things you have to do are to add `gem devise` to your gemfile and run `bundle install`.  To install devise for your project run` rails generate devise:install` in your terminal. Once that's done, you're going to want to generate your user model with devise. To do that, run `rails generate devise user`. This will create your migration file for your User with basically an email and password as attributes. If you take a look at the file, you'll see there are many more attributes commented out that you can choose to include if you want. You can also add more migrations to this model just like you would with any other model. Don't forget to run` rake db:migrate` after that's done. 

This gem comes with a bunch of useful helper methods like `current_user` and `user_signed_in?`. 

I highly recommend checking out the documentation for Devise to see just how powerful it is! 


