# CS110 Final Project

## Table of Contents
- [Overview](#overview)
- [Diagrams](#diagrams-(data-storage-and-access))
- [UI](#ui)
- [How To Run](#how-to-run-locally)
- [Dependencies](#dependencies)

Try it out at:
## https://teamcyd.herokuapp.com/
## Team
<a href="https://github.com/yugpatell" target="_blank">Yug Patel</a>
<a href="https://github.com/P-Dhruv20" target="_blank">Dhruv Parmar</a>
<a href="https://github.com/36tofu" target="_blank">Christopher Chen</a>

## Overview
CYD is a simple but refined media platform where users connect with each other through photo sharing. 
It is hosted by Heroku.

Security is the most important component of CYD. We want to ensure that user content remains secure 
as it is viewed and commented on by the rest of the internet. To maintain integrity of our app, 
we require users to create profiles in order to access shared content. User login passwords are secured using 
bycrpt hashing. 

The main features of our application are posting pictures and commenting on other user's posts. However, with a high volume of users, storing and displaying images can become an issue.
Our solution to handling images efficiently is uploading to a Cloudinary API endpoint, which returns us a URL. This is faster and saves space over storing it directly on our server.

We used Chakra UI to implement most of our styling. A cool feature is that it has baked in dark mode available. You can try this out by clicking the moon / sun on the top left corner!



## Diagrams (Data Storage and Access)

<ol>
    <li>
       MongoDB Tables:
        <ul>
            <li> 
                Users:
                <ul>
                    <li>User ID (type: String)</li>
                    <li>First Name (type: String)</li>
                    <li>Last Name (type: String)</li>
                    <li>Email (type: String)</li>
                    <li>Password (type: String)</li>
                    <li>Profile Picture URL (type: String)</li>
                </ul>
            </li>
              <li> 
                  Posts:
                <ul>
                    <li>Post ID (type: String)</li>
                    <li>Author/User ID (type: String)</li>  
                    <li>Author Name (type: String)</li>
                    <li>Author Profile Picture URL (type: String)</li>
                    <li>Title (type: String)</li>
                    <li>Description (type: String)</li>
                    <li>Date (type: Date)</li>
                    <li>Post Picture URL (type: String)</li>
                </ul>
            </li>
            <li> 
                Comments:
                <ul>
                    <li>Comment ID (type: String)</li>
                    <li>Post ID (type: String)</li>
                    <li>Author/User ID (type: String)</li>  
                    <li>Author Name (type: String)</li>
                    <li>Body (type: String)</li>
                    <li>Date (type: Date)</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        Requests: We use Axios to make these four following requests:
        <ul>
            <li>Post: Used for creating new posts, new comments and new user. These requests are made with all the necessary attributes to set in the database and returns a success or failure status.</li>
            <li>Get: Used to fetch posts on the home page, comments on the posts, all registered users on profiles page, login page, and edit proflie page. These requests returns a Array of JSON objects.</li>
            <li>Put: Used to edit/update profile. Retuens a success or failure status.</li>  
            <li>Delete: Used to delete posts and comments. These requests sends a success or failure status.</li>
        </ul>
    </li>
</ol>

## UI

Home Page
![](https://user-images.githubusercontent.com/68174967/172293844-39417f27-f41c-453f-89bd-e25a1716817a.JPG)

Dark Mode
![](https://user-images.githubusercontent.com/68174967/172300625-0f3fb667-9508-4b8f-9f51-22554f0da43a.JPG)

Creating a new post
![](https://user-images.githubusercontent.com/68174967/172293820-473b2b89-54cb-4ad0-b4bf-3777c4c4b9aa.JPG)

Adding a Comment
![](https://user-images.githubusercontent.com/68174967/172294175-a485c445-fabc-457d-8440-c25e43c68846.JPG)

Viewing all user profiles
![](https://user-images.githubusercontent.com/68174967/172293872-368b40c8-4e5c-4bbf-8fde-7b0768a24832.JPG)

Editing existing user profile
![](https://user-images.githubusercontent.com/68174967/172293829-9b62cf9a-16d0-49df-b028-51c332e60883.JPG)

Sign in page
![](https://user-images.githubusercontent.com/68174967/172293858-df56c215-f9dd-4940-89cc-a4e39d312cef.JPG)

User registration 
![](https://user-images.githubusercontent.com/68174967/172293868-819b2cde-9b62-409f-ab66-717a084707c4.JPG)



## How To Run Locally
To run our application, navigate to the `server` and `client` folders in separate terminals and run

### `npm i -force`

in both directories. After packages have finished installing, you can run

### `npm start` 

in both folders, and our application should be viewable at [http://localhost:3000](http://localhost:3000)



## Dependencies
Server 
<ul>
    <li>bcryptjs</li>
    <li>cors</li>
    <li>dotenv</li>
    <li>express</li>
    <li>express-validator</li>
    <li>jsonwebtoken</li>
    <li>mongoose</li>
</ul>
Client
<ul>
    <li>chakra-ui</li>
    <li>emotion</li>
    <li>axios</li>
    <li>dateformat</li>
    <li>framer-motion</li>
    <li>react</li>
    <li>react-dom</li>
    <li>react-router-dom</li>
    <li>react-scripts</li>
    <li>web-vitals</li>
</ul>

