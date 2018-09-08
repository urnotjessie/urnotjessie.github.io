---
layout: post
title:      "Ruby on Rails app - PhotoGallery"
date:       2018-09-08 19:43:44 +0000
permalink:  ruby_on_rails_app_-_photogallery
---


#### Summary

Photo Gallery is a photo sharing application designed to let users share and collect photos. Users can signup/login through email or facebook. After logged in, users can upload photos, browse photos within the app and add photos to their own collection with labels. Photo Gallery was built with Ruby on Rails v5.2.

  ![Imgur](https://i.imgur.com/jLQ4fKt.jpg)


#### Features

*  Users signing up/logging in  through email
*  Third party facebook logging in
*  Users can collect photos uploaded by other users and add labels to each collect


#### Explanation

**1. Associations**

![Imgur](https://i.imgur.com/MhICNlZ.png)

- user
     - has many photos (as a creator)
     - has many photo_users (as a collector)
     - has many collected_photos through photo_users
- photo
     - balongs to a user
     - has many photo_users
     - has many collector(user) through photo_users
- photo_user
     - belongs to a collector(user)
     - belongs to a collected_photo(photo)

```
class User < ApplicationRecord

  has_many :photos
  has_many :photo_users, class_name: 'PhotoUser', foreign_key: :collector_id
  has_many :collected_photos, through: :photo_users, source: :collected_photo

end
```

```
class Photo < ApplicationRecord

	belongs_to :user
	has_many :photo_users, class_name: 'PhotoUser', foreign_key: :photo_id
	has_many :collectors, through: :photo_users, source: :collector
	
end
```

```
class PhotoUser < ApplicationRecord

  belongs_to :collected_photo, class_name: 'Photo', foreign_key: :photo_id
  belongs_to :collector, class_name: 'User', foreign_key: :collector_id

end
```

**2. Image attachments**

I utilized [Active Storage ](https://edgeguides.rubyonrails.org/active_storage_overview.html) to handle image attachments to the Photo Model. 
- To install active_storage, run `rails active_storage:install`. It creates two migrations for two tables: active_storage_blobs and active_storage_attachments. 
- And then in the Photo model, set up: `has_one_attached :image`
-  To resize the image:

    ```
    def thumbnail
        self.image.variant(resize:'300x300!').processed
    end
    ```
- Other methods applied including: `image.attached?`, `image.content_type`


#### Views

* Log in  view:

![Imgur](https://i.imgur.com/GWEbYUm.png)

* Sign up view:

![Imgur](https://i.imgur.com/Ub4REME.png)

* User index view:

Users can add photos, edit profile, log out through profile index page. Users can access to their collection, explore photos in the app and log out through navigation bar.

![Imgur](https://i.imgur.com/7U0Hxjb.png)




  
