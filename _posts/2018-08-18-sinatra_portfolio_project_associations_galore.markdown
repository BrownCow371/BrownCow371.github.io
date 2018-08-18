---
layout: post
title:      "Sinatra Portfolio Project – Associations Galore"
date:       2018-08-18 23:42:33 +0000
permalink:  sinatra_portfolio_project_associations_galore
---



Based on my experience with trying to decide on a topic for my first project, I started collecting ideas for my Sinatra project a few weeks ahead of time. When I reached project time, I was prepared with a few ideas that I was still agonizing over, but I was able to narrow down my choices based on the project requirements. The MVC for Sinatra only needed to have a “has_many”/”belongs_to” pair of relationships, so I settled on a “Books to Read” app that would allow Users to have a list of many Books (each book would belong to a user).  

This has_many/belongs_to approach sounded good until I started to write down my plan/requirements for the application. It didn’t make sense to me to have multiple copies of books in the database just because each one belonged to different users’ lists…..And so down the rabbit hole I went. 

I came up with a model that I am pretty happy with that still meets the project requirements .  My current solution involves a many-to-many relationship between books and users. Books and Users are  joined on a book_list_item table that contains both of the required foreign keys for user_id and book_id, as well as notes and links specific to a user’s entry of a particular book in their own book list. 

At first, despite the third class in the application models, I thought I could still get away with just two controllers, one for users and one for books. But as I started to build out the routes and views for books as they pertained to a single user’s list, I realized I really was going to need a book_list_items controller to manage the CRUD tasks for an entry in a user’s book list, separate from the CRUD tasks for an individual book. This third controller added a lot more work to the mix than I had anticipated, but it was worth it. The more complicated relationship made me really think about what methods were available to me through ActiveRecord and I learned a lot about what ActiveRecord does and does not allow you to do based on the model relationships I had set up. 

The many-to-many association also added some wrinkles in terms of validation that I had not been prepared to deal with. The only things that a user really owned were the book_list_items….meaning the entries in the join table between Users and Books. So it was a bit tricky to come up with some validation to allow users to edit or delete books that they had created. I settled on letting a user edit or delete a book if the only list it was in was their own. This approached actually urged me to learn how to disable buttons in my views via an if statement, which I thought was pretty cool. 
I feel like there are still a lot of things that I’d like to do with my application, like clean up the CSS and change the way validation works around editing categories, but for now I think it is in a good enough place for me to submit it for assessment. Excited to be almost done with project #2!


