---
layout: post
title:      "Ruby on Rails with JavaScript"
date:       2018-11-02 15:22:33 +0000
permalink:  ruby_on_rails_with_javascript
---


The goal of this project was to build upon the PhotoGallery Rails project with JavaScript that features application data updates without refreshing the page. I built rails backend as an api, serialize the data, turn the data into JavaScript objects, and utilize these objects to display data to the view page. 

#### Create JSON responses with ActiveModel::Serializer
There are User, Photo and PhotoUser models in PhotoGallery application, and each model has an accompanying serializer. In order to include *has_many* and *has_many through* relationships as nexted array structure in the serialized responses, I utilized the ActiveRecord realtionships, for example here is a part of PhotoSerializer:
```
class PhotoSerializer < ActiveModel::Serializer
    belongs_to :user, serializer: UserSerializer
    has_many :collectors, class_name: 'User', through: :photo_users, serializer: UserSerializer
end
```
now `/photos/:id` has: 

```
{
  user: {  
     id: ,
		 username:  ,
	},
	collectors: [
		 {  
           id: ,
					 username: ,
      },
      {  
           id: ,
					 username: ,
      }
    ]
}
```

#### Create Model Objects in JavaScript
In order to make the code more reusable and easily extendable, I created objects through Constructor Functions. In JavaScript, a function can be written to be used as a constructor, and constructor functions allow us to write reusable and easily extendable code by acting as the template for other objects, lending their functionality and properties to the object using it as a prototype. 
```
// declare collector object
function Collector(id, username) {
  this.id = id;
  this.username = username;
}

// prototype to display collectors
Collector.prototype.showCollector = function() {
  var showCollector = '';
  showCollector += ' <span class="underline"><a href="/users/' + this.id + '">' + 
	this.username + '</a></span>';
  return showCollector;
}
```


#### Preview of the "Dynamic"

![](http://recordit.co/rvp938cXIc/gif/notify)

#### GitHub Repo
[PhotoGallery with JavaScript](https://github.com/urnotjessie/rails-project-photo-gallery/tree/add-JavaScript)
