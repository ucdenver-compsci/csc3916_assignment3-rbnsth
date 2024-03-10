[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=14143622&assignment_repo_type=AssignmentRepo)
# Assignment Three
## Purpose
The purpose of this assignment is to get comfortable working with a NoSQL database (MongoDB). 

For this assignment you will create a Users collection to store users for your signup and signin methods.  You will pass Username, Name and Password as part of signup.  To get a token you will call SingIn with username and password only.  The token should include the Name and UserName (not password)

You will also create Movies collection to store information about movies.  All endpoints will be protected with the JWT token received by a signin call. 

## Requirements
Create a collection in MongoDB to hold information about movies
- Each entry should contain the following
    - title (string, required, index)
    - releaseDate
    - genre (Action, Adventure, Comedy, Drama, Fantasy, Horror, Mystery, Thriller, Western, Science Fiction)
    - Array of three actors that were in the film
        - actorName
        - characterName
    - The movie collection should have at least five movies
- Create a NodeJS Web API to interact with your database
    - Follow best practices (e.g. /movies collection)
    - Your API should support all CRUD operations (through HTTP POST, PUT, DELETE, GET)
    - Ensure incoming entities contain the necessary information.  For example if the movie does not contain actors, the entity should not be created and an error should be returned 
- All endpoints should be protected with a JWT token (implement signup, and signin)
    - For this assignment you must implement a User database in Mongo
        - name
        - username 
        - password (should be hashed)
    - If username exists the endpoint should return an error that the user already exists
    - JWT secret needs to be stored in an environment variable
- Update the Pre-React CSC3916_REACT placeholder project to support /signup and /signin methods.  The React Single Page App should use your Assignment 3 API to support those two operations.

## Submissions
- All source code should be stored on github (remember .gitignore for node_modules)
- API needs to be deployed to heroku or render
- React Website that allows user to signup and singin (we did this in class)
- PostMan test collection that 
    - Signs Up a user (create a random user name and random password in your pre-test)
    - SignIn a User – parse token and store in postman environment variable
    - A separate call for each endpoint (save a movie, update a movie, delete a movie and get a movie)
    - Test error conditions (user already exists)
        - SignUp (user already exist)
        - Save Movie (missing information like actors (must be at least three), title, year or Genre)

- Create a readme.md at the root of your github repository with the embedded (markdown) to your test collection
    - Within the collection click the (…), share collection -> Embed
    - Static Button
    - Click update link
    - Include your environment settings
    - Copy to clipboard 
- Submit the Url to canvas with the REPO CSC_3916
- Note: All tests should be testing against your Heroku or Render endpoint

| Route | GET | POST | PUT | DELETE |
| --- | --- | --- | --- | --- |
| movies | Return all movies| save a single movie | FAIL | FAIL |
| movies/:movieparameter | Return a specific movie based on the :movieparameter | FAIL | Update the specific movie based on the :movieparameter in your case it’s the title | Delete the specific movie based on the :movieparamters your case it’s the title |*

* If Query String (Later Homework) reviews=true aggregate in reviews |

## Rubic
- -5 for missing REACT site (-2 if you are not able to signup or signin on the react site) that is all we implemented
- -1 for MovieSchema missing any of the attributes (array of actors, genre, year released or title)
- -2 for missing routes for /movies (POST/PUT/DELETE/GET)
- -1 for missing authentication on routes
- -2 for not deployed on Heroku/Render
- -1 missing Test error conditions
- -1 missing PostMan tests (signup, signin, separate call for each route)

## Resources
- https://www.mongodb.com/cloud/atlas
- Create a Free Subscription *Amazon
- https://render.com/docs/deploy-create-react-app **important: Environment Variable for https://github.com/AliceNN-ucdenver/CSC3916_REACT env.REACT_APP_API_URL, this weekend I will look at changes (I believe only 1 change in the actions)



Step 1: Create MongoDB Movie and User Collections
- Create two MongoDB collections: Movie and User.
- Define the schema for the Movie collection, including attributes like title, releaseDate, genre, and actors.
- Define the schema for the User collection, including attributes like name, username, and password.

Step 2: NodeJS Web API
- Create a NodeJS Web API to interact with your MongoDB database.
- Implement separate routes for each collection (e.g., /movies).
- Ensure that your API supports all CRUD operations (GET, POST, PUT, DELETE).
- Validate incoming entities to ensure they contain the necessary information.

Step 3: User Authentication and JWT Token
- Implement JWT authentication for all your endpoints.
- Create a User collection in MongoDB to store user information.
- Hash the passwords in the User collection for security.
- Handle cases where a user tries to sign up with an existing username.

Step 4: Implement Signup and Signin in the Frontend
- Update your existing pre-react CSC3916_REACT project to support /signup and /signin operations.
- Make API calls to your Assignment 3 API for these operations.

Step 5: Deploy Frontend to Static Site Service
- Deploy your updated React app to a static site hosting service like Render or Netlify.
- Set any necessary environment variables (such as API URLs) in the hosting service's settings.

PeZzwTjUYTQYPmev


{
                title: 'The Dark Knight',
                releaseDate: new Date(2008, 7, 18),
                genre: 'Action',
                actors: [{ actorName: 'Christian Bale', characterName: 'Bruce Wayne' }, { actorName: 'Heath Ledger', characterName: 'Joker' }]
            },
            {
                title: 'TestMovies',
                releaseDate: new Date(2010, 7, 16),
                genre: 'Science Fiction',
                actors: [{ actorName: 'James DiCaprio', characterName: 'Rob' }, { actorName: 'Joseph Levitt', characterName: 'Arthur' }]
            },
            {
                title: 'The Matrix',
                releaseDate: new Date(1999, 3, 31),
                genre: 'Science Fiction',
                actors: [{ actorName: 'Keanu Reeves', characterName: 'Neo' }, { actorName: 'Laurence Fishburne', characterName: 'Morpheus' }]
            },
            {
                title: 'The Lord of the Rings: The Fellowship of the Ring',
                releaseDate: new Date(2001, 12, 19),
                genre: 'Fantasy',
                actors: [{ actorName: 'Elijah Wood', characterName: 'Frodo' }, { actorName: 'Ian McKellen', characterName: 'Gandalf' }]
            },
            {
                title: 'The Shawshank Redemption',
                releaseDate: new Date(1994, 9, 14),
                genre: 'Drama',
                actors: [{ actorName: 'Tim Robbins', characterName: 'Andy Dufresne' }, { actorName: 'Morgan Freeman', character
            }