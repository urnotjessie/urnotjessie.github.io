---
layout: post
title:      "Sinatra app - Cookbook365"
date:       2018-07-15 14:06:47 +0000
permalink:  sinatra_app_-_cookbook365
---


This is my second project through web developemnt program. I built an MVC (Model View Controller) Sinatra Application - Cookbook365, which allow users with an account to create their own recipes and share with other registered users. 

Check out the complete project on GitHub: [Cookbook365](https://github.com/urnotjessie/sinatra-app-cookbook365)

Cookbook 365 provides:
* Users logging in
* New user signing up
* Viewing other users' recipes
* Adding new recipes
* Editing recipes
* Deleting recipes
* Users logging out

**Models**

There are 2 models - user and recipe. 
* a user has_many recipes
* a recipe belongs_to a user

![](https://ibb.co/mcyE1o)

**Controllers**

I used 3 controllers to organize the routes for different functions. 
1. ApplicationController:
     * index route
     * helper functions 
   
2. UserController
     * user login route
     * user logout route
     * user signup route
     * user's account route
     
3. RecipesController
     * viewing recipe route
     * new recipe route
     * edite recipe route
     * deleting recipe route
 
 **Views**
 
For the views, I created 2 different layouts, one for the application home page, where users login or signup, and another layout for all the other pages after users log in.
![Home page](https://ibb.co/nLW91o)

I added the navigation bar for all the pages after users logged in. 
![After logged in](https://ibb.co/hnB91o)


