---
layout: essay
type: essay
title: "Checkpoint Assignment 3"
# All dates must be YYYY-MM-DD format!
date: 2023-12-12
published: true
labels:
  - E6
  - Assignment3 
  - Checkpoint Essay
---

## Show what each page will look like. The pages do not have to be “functional” but the design should clear. 

Here are what my pages look like, these are going to be based off of the layouts I had in assignmnet2.
![Homepage](https://cdn.discordapp.com/attachments/837862215427162122/1184278970078859296/image.png?ex=658b64bd&is=6578efbd&hm=08b9b43c704e26d7f9cb03b313aabd70889915746a720f20d49e172820248e22&)  
![Store](https://cdn.discordapp.com/attachments/837862215427162122/1184278970473119794/image.png?ex=658b64bd&is=6578efbd&hm=87579bb50cf5f108ad75fa670136d3ae974dc38ed1cbd5b5ef76028527b6f4f3&) 
![Sidebar](https://cdn.discordapp.com/attachments/837862215427162122/1184278970871586957/image.png?ex=658b64bd&is=6578efbd&hm=bea81e522eaac70c0924eb255134e6a6110e35d9f844ad20039766ef399641e0&)
![Cart](https://cdn.discordapp.com/attachments/837862215427162122/1184278971496530010/image.png?ex=658b64bd&is=6578efbd&hm=fd3eedd92841959669833098b85528ff6cfd4cf4124ea147d6beab57e4ca65bd&)  
![Confirm Order](https://cdn.discordapp.com/attachments/837862215427162122/1184278971798528040/image.png?ex=658b64bd&is=6578efbd&hm=329b3458d171294aa7991e1a3188ca2599a74561d6be3ea7075219f595eeed36&)  
![Thank you Page](https://cdn.discordapp.com/attachments/837862215427162122/1184278972054376480/image.png?ex=658b64bd&is=6578efbd&hm=eaaa7cc35c3e020f36c189080cb4bc302df5ee02a60237fc37d4f010ffb89746&))  

## Describe your design for your site’s shopping cart. That is, will it be a separate page that the user can view and edit, or will it be integrated into the product pages? If so, describe in detail how this will work on your site. Provide several examples of using the cart.

For me, it will be a separate page that the user can view and edit the cart. Everytime they push the add to cart button they will be taken to a page where they can view their cart items, along with their items they wanted to add to cart. There is also a button on the sidebar that has a view cart, along with a logout and login feature. In the cart, I plan on making it like amazon's where it is initially a drop down, 1 - 10+, and if the user selects 10+ then a text field will appear in place of the drop down, in where the user is able to type out the amount of quantities they want. If the user wants to remove quantities, they can just type 0 or select zero for the item. If the user wants to add more quantities, there is a back to cart button, which brings them back to the snacks page. If the user selects a quantity that is more than 10, the cart will automatically generate the text box instead of the select input. 

## Explain specifically how you will use sessions to manage your shopping cart. In particular, what shopping cart data will be stored in the session, what data format will be used (NOT what data type, but the format like with the data format used for your registration data). Use code examples showing what data structures (such as arrays and their objects) you will use to manage the shopping cart data and how they will be used in a session.
By using sessions, all the data is stored in a json like format, so 
{
  "softdrinks": [
    {
      "productId": 1,
      "name" : "Sprite",
      "price" : 1,
      "image" : "/images/softdrink/spritedrink.webp",
      "quantity_available" : 500,
      "total_sold": 0
    },

and instead of it being the data of the product it will be 
{
  "softdrinks": [
    {
      "softdrink0": 1
      "softdrink1": 2
    },
  }
  This data will be stored in the session, and will loop by using Object.keys().forEach( (category))
  I also use fetch to get the data, and then from there I get the data and print it out in the cart.

## How will you avoid access to your application when the user has not logged in or registered? What are the particular security concerns you must address?
For every page that needs a user to log in, the first check will be to see if they are logged in. otherwise, they will be redirected to the log in page. You have to address the main one, which is failure to validate items, and also if the user just puts the link to your get requests in the browser URL/

## Upon a successful login, how do you provide personalization in your UI? Explain how you did or will do this (paste code if necessary)
I made it so that the user can see their cart items on the top right corner of the screen. It will change from Welcome! and a button that says click here to log in to Welcome, (their name)

I did this by calling a fetch on every page load to a /sessionInfo, and then the server will send back the data of the user if they are logged in, along with the data of the current cart so that it can be appended to the element id's.

## If you are working with partners, how will you split up the work in your team so that you are working in parallel as effectively as possible? That is, who is doing what and when?
I am working on my own

## How are you approaching Assignment 3 differently than Assignment 2?
It has to be done with sessions, so everything that you did in assignment2 had to go, and I had to rewrite how each webpage gets data from the server.
