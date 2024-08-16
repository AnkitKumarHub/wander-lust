# PHASE-I

* Databse set Up
* REST Apis for CRUD

 
Listing Model => place(apartment, flat , house, villa, hotel)

- title  (string)
- description (string)
- image url (string)
- price (number)
- location (string)
- country (string)


* INDEX ROUTE
get request =>  "/listings"  (all listings will be displayed)

get req => "/listing/:id    (show specific listing data (view))


* Read: (Show Route)
GET req /listings/:id => return all data for this particular id

- .tolocaleString method for currency in particular country
let text = num.toLocaleString("en-IN", {style:"currency", currency:"INR"});



* Create: New & Create Route
GET req  /listings/new  => form for new listing => form submit =>  
    Post req  /listings 



* Update: Edit & Update Route
edit 
GET  /listings/:id/edit => edit form => submit

PUT  /listings/:id


* Delete: Delete Route
DELETE  /listing/:id  => delete the listing of particular id 



# Phase 1 (Part - B) 

* styling through "ejs-mate" npm package

creating footer like component which are commonly used on every page of the website so we dont have a need of recreating  the component 

creating layout folder inside views 

creating a public folder to serve the static files such like css for styling or logic of javascript for ejs file or want to serve any image

if we want to change style like bg color to beige so we just link the stylesheet to boilerplate and it will apply to all pages of website

* creating a NAVBAR
created  includes folder and then navbar.ejs for bringing the modularity in the project 



* creating FOOTER


* Styling Index
creating card for listing page
creating card inside anchor tag if we click anywhere on the card we will be redirected to show page of that particular card
creating hover effect on cards


* Styling New Listing Page


* Styling Edit Listing


* Syling Show listing



# Phase 1 (Part - C)

it is of two type -
- client side validation ( through forntend to sever ) 
- server side validation ( ensure datbase rules/ schema ) / error handle


* Form Validations (client side validation)
when we enter data in the form, the browser and/or the web server will check to see that the data is in the "Correct Format" and "within the constraints"set by the application.

* success & Failure Text
 show messages depending on success and failure in forms while submitting the form we will now required the proper data

 But there is still a vulunerability in the project and i.e. we can still send the invalid data to the server via the hopscotch or postman.

 so we required the sever side validation also!!



*** Server side validation ***

* Custom Error Handler 
if we send price as of string type through postmen we will encounter the async error

so we uses a middleware to handle the error and also use try catch block 

* Custom WrapAsync (better than try-catch block)
 created a utils folder for error- class or wrapAsync
 to handle the error through wrapAsync function and error handling middleware 

 so that server doesnot get stop 

* Custom Express Error

* Error.ejs
 To show the error in a good way styling 

* Validations for Schema(incase the request is send from postman, hopscotch)
error which depends on individual field like we send the listing object right now we are handling error only if there is no listing object but if there is listing object (title , price, location) but missed the description so to handle that error

- we can handle in 2 ways
1.  if (!req.body.listing.title){
        throw new ExpressError(400, "title is misssing")
    }  

    individual checks for each fiels

2. using Joi => The most powerful schema description language and data validator for JavaScript

with the help of joi we define the schema for server side validation

* Validation for schema (Middleware)
converting in the form of middleware


# Phase 2 (Part - A)

