---
layout: posts
title:  "Customizing Active Admin Controller Actions"
date:   2019-03-21 19:31:11 +0000
categories: active-admin
---

##Specs:
* Ruby 2.6.0
* Rails version 5.2.2
* Active Admin version 1.4.3

I love how easy and quickly Active Admin (AA) makes it to throw together a simple CRUD interface. This is really important being one of two devs at the shop I currently work at. Speaking of where I work, we have to be sure to maintain parity between two different data stores, yay! The database for all web app interactions and the ERP system. So for a few of our resources I had to customize the controller actions in AA.

I really like AA, but the documentation feels a bit lacking in some areas. I didn't find it very helpful for adding my own custom actions, (which is why I'm writing this!) there's a bit in the docs about it, but it doesn't tell the full story. It took a bit of Googling/StackOverflowing to finally find the solution that worked for the version of AA that I'm using.

#The Problem
I have a resource that needs to send it's info to a REST API and get back an ID _before_ saving it to the database. If there's an error, then we should not save the resource to the database.

#The Solution

With the version of AA that I'm using, you can easily define your own controller actions through the DSL provided.
    
    ActiveAdmin.register Resource do
      # Don't forget to permit the params you need for your resource!!
      permit_params :name, :description
      
      # Call the get_id_from_api before the resource is created
      before_action :get_id_from_api, only: [:create]
      
      controller do
        def get_id_from_api
          resource = Resource.new(name: params[:name], description: params[:description]) 
          begin
           resource.api_id = ApiService.create_resource(resource)
           resoure.save!
           flash[:success] = 'Resource was saved'
          rescue ApiServiceError => e
            flash[:error] = 'Could not save resource to API at this time'
          end
        end
      end
    end
