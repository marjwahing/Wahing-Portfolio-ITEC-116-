Laboratory Activity #1: Introduction to FastAPI

This code creates a simple API endpoint that calculates the factorial of a given integer.  You can run this code using a Python ASGI server like Uvicorn.  
Once running, you can make a GET request to a URL like /factorial/5 (or whatever port your server is running on) and the API will respond with a JSON object like {"starting_number": 5, "factorial": 120}.  
It also handles the case where the input is 0, returning {"result": False}.  The use of FastAPI makes this process concise and efficient, handling routing, request parsing, and response generation automatically.


Laboratory Activity 2: Working with HTTP actions and API parameters

It uses a tool called FastAPI to make it work on the web.
First, it sets up the basic tools it needs, like how to handle web requests and how to organize the to-do list items.
Then, it creates a pretend database, which is just a list of to-do items in the computer's memory.  In a real app, this would be a real database that saves the data.
It also creates templates for what a to-do item looks like:  It has a title, a description, and a checkbox for whether it's finished.  
There are separate templates for adding a new item, changing an item, or replacing an item completely.
Then, it sets up the different things you can do with the to-do list:

GET /tasks/{task_id}: View a specific item.
POST /tasks: Add a new item (title and description required).
PATCH /tasks/{task_id}: Change part of an item.
PUT /tasks/{task_id}: Replace an entire item.
DELETE /tasks/{task_id}: Remove an item.

Reuirements.txt, It tells your computer which extra tools (called "packages") it needs to make the project work.  When you run a special command, it goes and gets all those tools in the correct versions.  
Some of the important tools are:

fastapi: The main tool for making the website part of your project.
pydantic: A tool for making sure the data you use is organized correctly.
uvicorn: A tool for running the website.
typing_extensions: A helper tool for older computers.
The file also lists a bunch of other tools that the main tools need to work.



Laboratory Activity #3: Working with JSON

This code defines a FastAPI endpoint /detailed_post/{userID} that retrieves posts and comments for a given user ID from the JSONPlaceholder API.  
It uses requests to make HTTP GET requests to the API endpoints.  The code includes robust error handling using try...except blocks to catch potential issues during the API calls.  
It structures the retrieved data into a nested dictionary format, where each post contains its title, content, and a list of comments.  If fetching comments for a post fails, it adds an error message instead of crashing. 
If fetching the initial list of posts fails, it returns a 500 error. The final structured data is returned as a JSON response, which FastAPI handles automatically.  
In short, it fetches, structures, and handles errors related to retrieving posts and comments for a specific user from an external API, returning the data in a well-defined JSON format.



Laboratory Activity #4: Advanced API Implementation

This FastAPI application implements a versioned (v1 and v2) task management API secured with API key authentication.  
It leverages Pydantic models for request body validation and uses an in-memory list as its data store.  
The API offers endpoints for retrieving tasks by ID (available in both versions), creating new tasks, updating existing tasks, deleting tasks, and retrieving all tasks (all available in v2).  
It incorporates comprehensive error handling, returning appropriate HTTP status codes (400, 403, 404, 200, 201, 204) and informative error messages for invalid requests, missing resources, or authentication failures.  
The API key is securely loaded from a .env file.  Version 1 provides a basic read-only interface, while version 2 expands the functionality to include full CRUD (Create, Read, Update, Delete) operations on tasks.  
Input validation ensures that task titles and descriptions are not empty strings.  The use of APIRouters organizes the code and facilitates versioning.


