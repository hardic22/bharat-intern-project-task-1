Blog Application
This project is a simple blog application built using Node.js, Express, MongoDB, and Edge.js templating engine. The app allows users to register, login, create blog posts, and view posts. It also implements middleware for authentication, session management, and file uploads.

Table of Contents
Features
Installation
Technologies Used
Project Structure
Usage
Middleware Explanation
Contributing
Future Enhancements
Features
User authentication with session support (sign up, login, and logout).
Blog post creation and display functionality.
Middleware for user authorization.
Flash messages for feedback.
File uploads (e.g., for images).
Protected routes to ensure only authenticated users can post.
Templating engine (Edge.js) for rendering dynamic content.
MongoDB as a backend database to store users and posts.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/your-username/BlogApp.git
cd BlogApp
Install dependencies:

bash
Copy code
npm install
Set up MongoDB:

Ensure MongoDB is running locally on mongodb://localhost:27017/blog or update the connection string accordingly in the app.
Run the application:

bash
Copy code
node app.js
Open your browser and navigate to http://localhost:3000 to view the app.

Technologies Used
Node.js: Backend JavaScript runtime for building server-side applications.
Express: A fast and minimalist web framework for Node.js.
MongoDB: NoSQL database for storing user and post data.
Mongoose: Object Data Modeling (ODM) library for MongoDB and Node.js.
Edge.js: Templating engine to render dynamic HTML pages.
Express-Session: Middleware for session management and user authentication.
Express-Fileupload: Middleware for handling file uploads, such as images for posts.
Connect-Flash: Middleware to provide flash messages, useful for passing success or error messages.
Connect-Mongo: MongoDB-based session storage.
Project Structure
lua
Copy code
/BlogApp
|-- /controllers         # Handlers for routes
|   |-- createPost.js
|   |-- homePage.js
|   |-- storePost.js
|   |-- getPost.js
|   |-- createUser.js
|   |-- storeUser.js
|   |-- loginController.js
|   |-- loginUser.js
|   |-- logout.js
|
|-- /database
|   |-- /models           # Mongoose models
|       |-- User.js
|       |-- Post.js
|
|-- /middleware           # Custom middleware functions
|   |-- auth.js
|   |-- redirectIfAuthenticated.js
|   |-- storePost.js
|
|-- /public               # Static files (CSS, JS, images)
|
|-- /views                # Edge.js templates
|   |-- home.edge
|   |-- post.edge
|   |-- login.edge
|   |-- register.edge
|
|-- app.js                # Main server-side file
|-- package.json          # Project metadata and dependencies
Usage
Home Page:

The root route (/) displays all blog posts.
Sign Up / Log In:

Navigate to /auth/register to create a new account.
Navigate to /auth/login to log into an existing account.
Creating a Post:

After logging in, navigate to /posts/new to create a new post. Only authenticated users can access this route.
Once a post is created, it will be displayed on the homepage.
Viewing a Post:

Click on a post's title to view it in detail. The route for viewing a specific post is /post/:id.
Logout:

Navigate to /auth/logout to log out of the system.
Middleware Explanation
authMiddleware: Ensures that only authenticated users can access certain routes like creating new posts.

redirectIfAuthenticatedMiddleware: Redirects users to the homepage if they try to access the login or register page when they are already logged in.

storePostMiddleware: Validates form submissions when creating new posts. It checks if the required fields are filled and if a file (image) has been uploaded.

Contributing
Contributions are welcome! If you'd like to help improve this project, feel free to fork the repository, create a new branch, and submit a pull request with your changes.

Future Enhancements
User Profiles: Allow users to view and edit their profiles, showing the posts they have created.
Comment System: Enable users to comment on blog posts.
Post Categories: Implement categories for blog posts to allow easier navigation and filtering.
Enhanced Validation: Add more robust form validation, both client-side and server-side.
Password Encryption: Use bcrypt to hash passwords before storing them in the database for enhanced security.
