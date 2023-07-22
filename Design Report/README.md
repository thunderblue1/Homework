# Cover Sheet

### Class Number: CST-391
### Application Name: PetersTable
### Author: John Keen

---
# Instructor Feedback

John, I LOVE IT!!! You get what I am asking!!! No more uploading ZIP files (I can see your code), no more Office requirements, MARKDOWN does all this for you AND FINALLY!!! This is a LIVING DOCUMENT.

BOTTOM LINE: FANTASTIC SIR - I AM SO PUMPED UP with what you posted. KEEP DOING WELL and GOD BLESS YOU BROTHER, Bobby :-)

---
# Outline of Feedback Addressed

Thank you for your support and encouragement.  I added a section entitled "Introduction to REST API" so that I could clearly outline
the API. I have also added the "Design Updates" section of this document.
I will continue to refine this document as the application is being developed as you have suggested.

Thank you and God bless you.

---
# Introduction

My organization will be called Saint Peter’s Table.  It is a charitable non-profit organization that will sell bibles to sponsor their good deeds.  Saint Peter’s Table is about bringing people to the table in regard to providing food for them to eat and knowledge for their souls to flourish.  In the bible Jesus had asked Peter to feed and take care of his sheep.

>NIV Version
John 21:15-17
> 
> 15 When they had finished eating, Jesus said to Simon Peter, “Simon son of John, do you love me more than these?”
“Yes, Lord,” he said, “you know that I love you.”
Jesus said, “Feed my lambs.”
16 Again Jesus said, “Simon son of John, do you love me?”
He answered, “Yes, Lord, you know that I love you.”
Jesus said, “Take care of my sheep.”
17 The third time he said to him, “Simon son of John, do you love me?”
Peter was hurt because Jesus asked him the third time, “Do you love me?” He said, “Lord, you know all things; you know that I love you.”
Jesus said, “Feed my sheep.
>
This is not a task that Saint Peter alone should carry and we should all try to carry out the will of God.  We do not believe that God was merely referring to Peters ability to provide food but also to his ability to provide truth and spiritual wisdom that people could consume in order to be fulfilled by the Holy spirit.  Peter was sad because he had betrayed God three times and when Jesus asked Peter to take care of his sheep three times, he knew it was because he had sin that needed forgiven.  We all have sins to be forgiven and we all share Peter’s mission to help those in need.  Bibles will be sold to care for and feed people.

>ESV John 6:35
>
>Jesus said to them, “I am the bread of life; whoever comes to me shall not hunger, and whoever believes in me shall never thirst.
>

---
# Design Updates

The API was changed very little.  The username member was added to the "user" interface and the changes are now reflected
in the ER diagram for the database and the class diagram.  The users database may be updated in the future to reflect the users relation to the company (i.e. Customer or Mangager).

|   Date    |                                      Updates                                       |                              Purpose                               |
|:---------:|:----------------------------------------------------------------------------------:|:------------------------------------------------------------------:|
| 7/6/2023  | Username was added to the users relation<br/>of the database and to the interface. |   Allow for the possability to look up a user by their username.   |
| 7/20/2023 |                  Relation field added to users table of database.                  | Allow the ability to differentiate between customers and managers. |
| 7/21/2023 |                     User Registration form slightly modified.                      |                  Ensure proper binding to model.                   |

##### Pending Issues for Angular Front End

|   Date    |                                                   Issue                                                    |
|:---------:|:----------------------------------------------------------------------------------------------------------:|
| 7/22/2023 |                                      Form validation is still needed                                       |
| 7/22/2023 |                                 A secure means of authorization is needed                                  |
| 7/21/2023 |                     The original design does not have a quantity for each item in cart                     |



---
# Introduction to REST API

There are really two sets of routes for this API.  The first set of routes is the bible routes for Creating, Reading, Updating and Deleting bibles in the database.
Then there are the users routes which are for Creating, Reading, Updating and Deleting a user of the site in the database.

### Bibles Routes

##### Route: GET /bibles
##### DAO method: +readAllBibles(): Bible[]
##### Purpose: Get all of the bibles from the database

![readAllBibles](./Diagrams/Milestone3-BiblesAPI-readAllBibles.jpg)

##### Route: GET /bibles?Id=2
##### DAO method: +readOneBible(): Bible
##### Purpose: Get the data for only one bible in the database

![readOneBible](./Diagrams/Milestone3-BiblesAPI-readOneBible2.jpg)

##### Route: GET /bibles/:bible
##### DAO method: +readOneBible(): Bible
##### Purpose: Get the data for only one bible in the database without using a URI string

![readOneBible](./Diagrams/Milestone3-BiblesAPI-readOneBible.jpg)

##### Route: GET /bibles/search/:search
##### DAO method: +searchForBible(): BIble[]
##### Purpose: Get an array of bibles based on search of name, description and version

![searchForBible](./Diagrams/Milestone3-BiblesAPI-searchForBible.jpg)

##### Route: POST /bibles
##### DAO method: +createBible(): OkPacket
##### Purpose: Create a bible by inserting it into the database

![createBible](./Diagrams/Milestone3-BiblesAPI-createBible.jpg)

##### Route: PUT /bibles
##### DAO method: +updateBible(): OkPacket
##### Purpose: Update a bible in the database

![updateBible](./Diagrams/Milestone3-BiblesAPI-updateBible.jpg)

##### Route: DELETE /bibles/:bibleId
##### DAO method: +deleteBible(): OkPacket
##### Purpose: Delete a bible

![deleteBible](./Diagrams/Milestone3-BiblesAPI-deleteBible.jpg)

### Users Routes

##### Route: GET /users/:userId
##### DAO method: +readOneUser(): User
##### Purpose: Get the data for only one user in the database

![readOneUser](./Diagrams/Milestone3-UsersAPI-readOneUser.jpg)

##### Route: GET /users/:searchTerm
##### DAO method: +searchForUser(): User
##### Purpose: Get a user based on search of username

![searchForUser](./Diagrams/Milestone3-UsersAPI-searchForUser.jpg)

##### Route: POST /users
##### DAO method: +createUser(): OkPacket
##### Purpose: Create a user by inserting it into the database

![createUser](./Diagrams/Milestone3-UsersAPI-createUser.jpg)

##### Route: PUT /users
##### DAO method: +updateUser(): OkPacket
##### Purpose: Update a user in the database

![updateUser](./Diagrams/Milestone3-UsersAPI-updateUser.jpg)

##### Route: DELETE /users/:userId
##### DAO method: +deleteUser(): OkPacket
##### Purpose: Delete a user

![deleteUser](./Diagrams/Milestone3-UsersAPI-deleteUser.jpg)

---

# Functionality

List of requirements in user story format:

- As a customer I would like to see all the products so that I can browse for the bible I want.
- As a customer I would like to search for a particular product so that I can find the bible I need.
- As a customer I would like to see the details of a product so that I can better know what I am purchasing.
- As a customer I would like to add a product to a cart so that I can make a purchase.
- As a customer I would like to register as a user so that I can log in.
- As a customer I would like to be able to log in so that I can place an order.
- As a sales manager I would like to be able to log in so that I can manage inventory.
- As a sales manager I would like to be able to create a product so that I can update our inventory.
- As a sales manager I would like to browse all the products so that I can browse for a bible that may need information updated.
- As a sales manager I would like to search for a product by multiple criteria so that I can find the product that needs updated.
- As a sales manager I would like to be able to update a product so that I can keep the inventory information current.


---
# Initial Database Design
![DatabaseRelations](./Diagrams/Relations.jpg)
![ERDiagram](./Diagrams/ERDiagram.jpg)

---
# Initial UI Sitemap

![SiteMap](./Diagrams/SiteMap.jpg)

---
# Initial UI Wireframes
![UI1-About](./Diagrams/UI1-About.jpg)
![UI2-Registration](./Diagrams/UI2-Registration.jpg)
![UI3-Login](./Diagrams/UI3-Login.jpg)
![UI4-Shopping](./Diagrams/UI4-Shopping.jpg)
![UI5-Manage](./Diagrams/UI5-Manage.jpg)
![UI6-ProductDetails](./Diagrams/UI6-ProductDetails.jpg)
![UI7-CreateProduct](./Diagrams/UI7-CreateProduct.jpg)
![UI8-UpdateProduct](./Diagrams/UI8-UpdateProduct.jpg)
![UI9-ShoppingCart](./Diagrams/UI9-ShoppingCart.jpg)
---
# Initial UML Classes
![DaoAndModelUML](./Diagrams/UML.jpg) 

---
# Risks
I really have to balance my expectations with my available time so that I can stay on task.
My biggest risk is running into bugs and running out of time.  I also may run into risks like type mismatching between
objects returned from SQL and javascript types because I do not have experience using javascript to access SQL.
My lack of experience with typescript, React and Angular may cause me to spend a lot of time looking things up.
Another risk I run into is that the API we are creating is stateless and I may not be able to create a user session.
Without the ability to create a session I could not log in.  There may be a solution for the need for stateful connections
in Angular and React.  It may take time to learn stateful connections in Angular and React.
Learning such things may fall outside the scope of the activities and be a hindrance to the planned course of learning.

