---
layout: post
title:      "My First Ruby CLI Gem - keto_snack_recipes!"
date:       2018-04-26 03:12:31 +0000
permalink:  my_first_ruby_cli_gem_-_keto_snack_recipes
---

After two weeks of learning Ruby online, I just finished my first project building a command-line interface Ruby application. Although I have developed web application in Python before, this is my very first Object Oriented application. I combined my personal interest in keto diet and provide users with an application to explore keto snack recipes.

#### keto_snack_recipes provides:**

* A command-line interface
* All keto snack recipes scraped from [KetoDash](https://ketodash.com/recipe?type=Snack)
* Users can interact to list 10 recipes each time and compare their macros
* Users can select one of the recipes to check the recipe detail

[Explore keto snack recipes here!](https://github.com/urnotjessie/keto-snack-recipes-cli-gem) 


#### **How do I build the Ruby Gem: **

Building Gem from scratch doens't mean creating our own wheels. There are many tools we can implement, to start with, Bundler is a great tool that can help us create the gemspec file and build out the structure. In the command line, "cd" to the directory where you want to put the Gem and then `bundle gem <gem name>`, then we have the scaffold directory.

![Imgur](https://i.imgur.com/bnXvSvh.png)

With no tests to pass or fail, I need to build my own objects and methods. I start with designing the *cli.rb* which handles the CLI display logic and user input. After figuring out the logic by playing with hard-coded data, I build scraper *scraper.rb* to scrape both the index page as well as recipe detail page from [KetoDash](https://ketodash.com/recipe?type=Snack). And add recipes' attributes through *recipes.rb* which contains all recipe method and attributes.

In order to better display the recipe list, I also implemented [table_print gem](http://tableprintgem.com/) and [colorize gem](https://github.com/fazibear/colorize). And along with all other required path and dependencis, I put them in the *environment.rb*. 

In my executable bin file keto-snack-recipes I call *call method* in CLI to start the program. 



