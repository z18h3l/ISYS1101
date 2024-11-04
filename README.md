java c
ISYS1101/ 1102 Database Applications
Week 11: Tute/Lab – Web Database Applications with node.js
Semester 2 2024
1   Objective
The objective of this tute/lab session is to learn the basics of combining MongoDB and javascript. frameworks such as node.js, express etc to build a fullstack web application.
Node.js is popularly being used in web application development because it lets the application run    while it is fetching data from the backend server. It is asynchronous, event-driven and helps to build scalable web applications. In this lab session, we explore the elements of MERN stack which is widely used in the industry.
What is MERN framework?
MERN is a pre-built technology stack based on JavaScript. technologies. MERN stands for MongoDB, Express, React, and Node, after the four key technologies that make up the stack.
•    MongoDB — document database
•    Express(.js) — Node.js web framework
•    React(.js) — a client-side JavaScript. framework
•    Node(.js) — the premier JavaScript. web server (runtime)
MERN stack is an easy to learn, easy to implement full technology stack, which is considered to be a preferred full stack for beginners. MERN stack requires developers to have knowledge about only one programming language, i.e. JavaScript. Since MERN stack has a well-defined structure, developers can start building applications quickly and easily.Express and Node make up the middle (application) tier. Express.js is a server-side web framework, and Node.js is the popular and powerful JavaScript. server platform. MERN is the ideal approach to  working with JavaScript. and JSON, all the way through.
MERN Architecture

The MERN architecture allows you to easily construct a three-tier architecture (front end, back end, database) entirely using JavaScript. and JSON.
Important Note: In this lab session we focus mainly on MongoDB, Node.js and Express.js components due to time constraints. However, you are encouraged to extend the lab activities to include React.js to build the top tier of the stack.
Front End (top tier) with React.js
The top tier of the MERN stack is React.js, the declarative JavaScript. framework for creating dynamic client-side applications in HTML. React lets you build complex interfaces through simple components, connect them to data on your back-end server, and render them as HTML.
React.js has great important modern web framework features such as support for forms, error handling, events, lists, and more.
Application Tier with Node.js and Express.js
The program logic is implemented using node.js and embedded express.js functionality. Express web framework allows you to handle GET and POST requests from the React.js
Node.js allows you to write backend (server-side) application logic in JavaScript. With the MongoDB Node.js driver, you can easily connect a MongoDB database to the application in a few simple steps. This driver lets you implement CRUD tasks required for database operations which in turn sent to database backend to be executed.
Database Tier with MongoDB
A MongoDB database, either hosted locally or on cloud, will form. the database tier. It receives the CRUD requests from the application tier and returns documents (in JSON format) back to the requestor.
Once you successfully complete this Lab/ Tute session, you will be able to build a basic, but fully-    functional Web Database Application. You will still require to learn further web programming skills to improve the usability and functionality of your web database application. Complete the LinkedIn  Learning tutorials (refer to Pre-reading section), MongoDB University developer path
(https://learn.mongodb.com/learning-paths/mongodb-nodejs-developer-path),  and other web resources to acquire these skills.
2   Preparation Tasks
2.1   Hosting your database on Mongo Atlas
In this lab session, you will use a sample database hosted on Mongo Atlas. If you haven’t done yet, you must completed Week 9 Lab Activities (Getting Started with MongoDB) and Week 10 Lab Activities (Using MongoDB).This lab sheet assumes that the name of the sample database is “Movies” and the nameof the document collection is “Movie”. A typical document in the “Movie” collectionfollows the following structure.{"mvNumb": 1,"mvTitle": "Annie Hall","yrMade": 1977,"mvType": "COMEDY","Crit": 4,"MPAA": "PG","Noms": 5,"Awrd": 4,"dirNumb": 1}If your database or the document collection is named differently, you may need somechanges in the skeleton node.js code snippets given in the following sections. If youdidn’t see any results from these code snippets, check the database and collectionnames. Also relevant are the field names used in the documents in this collection. Theyare also referred in node.js files as well as html forms.If your database environment is set up properly, you should be able to run a MongoDBmql query, such as:db.Movie.find({mvType:"DRAMA"})on Mongo Atlas and receive results.Please note that database names, collection names, and field names are case-sensitive.
2.2   Setting up Visual Studio Code as your coding environment
2.2.1   Install Visual Studio Code
Visual Studio Code (VS Code, in short) is a free coding editor that helps you start coding quickly. Use it to code in any programming language, without switching editors. Visual Studio Code has    support for many languages, including Python, Java, C++, JavaScript, and more.
Download and install Visual Studio Code, downloadable from: https://code.visualstudio.com
Useful resources:
•   Getting Started -- https://code.visualstudio.com/docs
•   Node.js tutorial in Visual Studio Code -- https://code.visualstudio.com/docs/nodejs/nodejs- tutorial
2.3   Install and set up Node.js and NPM (Node Package Manager).
In order to complete this Lab Session and the Assignment 4, you will require Node.js and NPM (Node Package Manager) installed in your computer.
If you have completed a course previously that uses these technologies, you may have already installed them.
2.3.1   Check if they are already installed
Run the following commands on the interactive terminal on VS Code.node –versionIf it exists, you will see the version number. The most recent version is 22.9.0npm –versionAgain, if it exists, you will see the npm version number. The most recent version is10.8.3
2.3.2   Installation
If you do not have them already installed, follow the Node.js official installation guide, available here: https://nodejs.org/en/learn/getting-started/how-to-install-nodejs
Choose the most recent stable version for your operating system. You may use a package manager   or a pre-built binary for your operating system. We recommend using the package manager option.  For Windows, you can use fnm (Fast Node Manager) and for Mac, you can use nvm (Node Version Manager).
Windows:

Mac:

Different operating systems may present different quirks, so, if you encounter any issues, please refer to original installation guide or search internet forums.
After the completion of the installation, close VS Code and re-open it to get the above modules activated on its interactive terminal. Then, check the versions as above 2.3.1.
3   Activities
3.1   A simple Node.js Application
Let’s start with a console application. Create a new directory on your computer, change to this directory and open VS Code.
Edit a new node.js file, say “hello.js” in this directory. Add this line and save it.console.log("Hello World");
To run this console application, open the interactive terminal on VS Code, and run:Node hello.js
Did it work?

Now that you were able to run your first node.js console application, try out a few more node.js programs.
3.2   More Console-based Activities
After completing the “Hello World”, it is time to get yourself familiarised with basic language syntax. Try out all the activities given in the following pages:
3.2.1   Output to the command line using Node.js
https://nodejs.org/en/learn/command-line/output-to-the-command-line-using-nodejs
3.2.2   Accept input from the command line in Node.js
https://nodejs.org/en/learn/command-line/accept-input-from-the-command-line-in-nodejs
3.2.3   Asynchronous flow control
One of the strengths of Node.js is its asynchronous nature of operations. While it may not be important in console-based applications, it will become an important aspect of th


3.3   Web Application with Node.js and Express.js
In this activity, you build a minimalist web application using Express.js web framework. Create a new directory on your computer, change to this directory and open VS Code.
Edit a new node.js file, say “app.js” in this directory. Add the following program code and save it.const express = require('express')const app = express()const port = 3000app.get('/', (req, res) => {res.send('Hello World!')})app.listen(port, () => {console.log(`Example app listening on port ${port}`)})
The objects “req” (request) and “res” (response) are responsible for handling the HTTP requests and responses in the web applications. Please read the explanation here:
https://www.geeksforgeeks.org/explain-the-use-of-req-and-res-objects-in-express-js/
for more information on the inner workings of this program.
To run this program, you will need to set up a few things.





On the VS Code Interactive Terminal, run the following commands.First, initiate a new project. Run:npm init -yThis command will initiate a new node.js project ion the current working directory bygenerating a package.json file in your project route that describes all the dependenciesof your project. This file will be updated when adding further dependencies during thedevelopment process.Add the other dependencies, such as express.js, required for this project. Run:npm install expressAfter the above, check the contents in the package.json file, which should have alldependencies listed in it.



{"name": "hello-express","version": "1.0.0","main": "app.js","scripts": {"test": "echo \"Error: no test specified\"  exit 1"},"keywords": [],"author": "","license": "ISC","dependencies": {"express": "^4.21.0","nodemon": "^3.1.7"},"description": ""}Now, your project is ready to deploy. Run:node app.jsOpen a new browser, load http://localhost:3000/ in the browser to see the output.After testing out the output on browser, kill the active express.js server. On VS Codeinteractive terminal, press CTRL-C to kill the process.



3.4   Handling Form Inputs
Using web forms and use form. inputs in running a web application is a very common task. In this activity, we learn how to write a Node.js application with Express. 代 写ISYS1101/ 1102 Database Applications Semester 2 2024C/C++
代做程序编程语言We will use both GET and
POST methods to communicate with the server.
3.4.1   Create a Project Directory and Initiate a New Project

Create a new project directory, say “Forms”, and open VS Code from this directory.On the VS Code Interactive Terminal, enter the following command to initiate a newproject.npm init -y

When this command successfully completes, you will have a package.json file inyour Mongo directory.The static html pages (such as form.html used in this application sit on a separate subdirectory, called public. On VS code Interactive Terminal, run the following command:mkdir publicThis will create the required sub-directory.


3.4.2   Install required Drivers

Run the following command in your shell to install the driver in your project directory:npm install expressnpm install body-parserThis command performs the following actions:• Downloads the express and body-parser packages and thedependencies it requires• Saves the package in the node_modules directory• Records the dependency information in the package.json file


If you created the required directories, initialise the project, install required drivers, your project
directory should look like this:

3.4.3   Create your Node.js Application
On VS Code, create a Node.js file, say index.js and copy the following code:var express = require('express');var http = require('http');var path = require("path");var bodyParser = require('body-parser');var app = express();var server = http.createServer(app);app.use(bodyParser.urlencoded({extended: false}));app.use(express.static(path.join(__dirname,'./public')));app.get('/', function(req,res){res.sendFile(path.join(__dirname,'./public/form.html'));});server.listen(3000,function(){console.log("Server listening on port: 3000");});
3.4.4   Create the Web Form
On VS Code, inside public directory, create an html file, say form.html and copy the following code:

 My Form. A DatabaseItem
ID

Thing

ResetSubmit


3.4.5   Run your Application

Run the following command:node index.jsThen, open localhost:3000 on your browser.


Did it work?
If not, why not?
You will notice that the index.js does not include a section to handle POST requests (i.e. what to do when the form. is submitted and makes a POST request to the server.
To rectify this issue, kill the current running application, and add the following section of code to the end of the index.js file.//Add this section to handle form. actions (after submitting the form.)app.post('/item', function(req,res){console.log([req.body.id, req.body.thing]);const text =`
${req.body.id}
${req.body.thing}
`;res.statusCode = 200;res.setHeader('Content-Type', 'text/html');res.end(text);});
Then, run it again.

Run the following command:node index.jsThen, open localhost:3000 on your browser.


Does it work this time?
3.5   Fetching documents from a MongoDB databaseIn this activity, we learn how to fetch data (JSON documents) from a MongoDB database. We use  mongodb library which allows us to establish a database connection from a node.js application and implements the mongo CRUD functions in Node.js.
We use sample “Movies” database with the document collection “Movie” . We have used this document collection during last week’s lab. If it doesn’t exist on your Mongo Atlas, add/ create it before this activity.
3.5.1   Create a Project Directory and Initiate a New Project

Create a new project directory, say “Mongo”, and open VS Code from this directory.On the VS Code Interactive Terminal, enter the following command to initiate a newproject.npm init -yWhen this command successfully completes, you will have a package.json file inyour Mongo directory.


3.5.2   Install the Node.js Driver

Run the following command in your shell to install the driver in your project directory:npm install mongodbThis command performs the following actions:• Downloads the mongodb package and the dependencies it requires• Saves the package in the node_modules directory• Records the dependency information in the package.json file


3.5.3   Obtain MongoDB Atlas Connection String
In the previous labs, you were required to obtain the connection string required for Mongo Compass application. Similarly, you are required to obtain the connection string customised for Node.js applications.
Follow the steps outlined here: https://www.mongodb.com/docs/drivers/node/current/quick- start/create-a-connection-string/
Each of your connection string would be different, however, it has a similar format, including the username, password, cluster uri combined together with some additional directives.
e.g.:  mongodb+srv://:@-
cluster.pkhgj.mongodb.net/?retryWrites=truew=majorityappName=Santha- Cluster
3.5.4   Create your Node.js Application
On VS Code, create a Node.js file, say index.js and copy the following code:

const { MongoClient } = require("mongodb");// Replace the uri string with your connection string.const uri = "Your Connection String";const client = new MongoClient(uri);async function run() {try {const database = client.db('Movies');const movies = database.collection('Movie');// Query by Movie Title (mvTitle)const query = { mvTitle: 'Judgment at Nuremberg' };const movie = await movies.findOne(query);// display result on the console (VS Code Interactive Terminalconsole.log(movie);} finally {// Ensures that the client will close when you finish/error

await client.close();}}run().catch(console.dir);
3.5.5   Run your Application

Run the following command:node index.js


3.5.6   Exercises
In the activity in Section , you learned how to write a Node.js application (using Express) to serve the results on a browser. Convert the above console-based application into web-based application.
Hint: You will be required to install both mongodb driver AND express driver at the initialisation stage.
3.5.7   More Exercises
Copy the files in the above working directory to a new directory, and complete the following tasks:
•   Replace the Movies database with sample_airbnb database and collection with listingsAndReviews collection.
•   Write a node.js program to find 3-bedroom apartments in Barcelona. Assume there are more than one such listing in the chosen location.
4   Putting things together – Full MERN stack (excl. React.js
component).
This is the final piece in the jigsaw puzzle!
In this activity, we learn how to put all of the components we built in previous activities --- using express, create and use web forms and use PUT method to send form. inputs to the server, using    mongodb driver and write CRUD functions to operate on Mongo Atlas --- together to build a
complete the MERN stack.
DISCLAIMER: The only component we do not use in this stack is the React.js to build front-end (presentation layer) web pages. In this exercise we simply use plain html, however, they can be generated in Javascript. using React.js.
4.1.1   Create a Project Directory and Initiate a New Project

Create a new project directory, say “insertAndBrowse”, and open VS Code from thisdirectory.On the VS Code Interactive Terminal, enter the following command to initiate a newproject.npm init -yWhen this command successfully completes, you will have a package.json file inyour Mongo directory.The static html pages (such as form.html used in this application sit on a separate subdirectory, called public. On VS code Interactive Terminal, run the following command:mkdir publicThis will create the required sub-directory.


4.1.2   Install required Drivers

Run the following command in your shell to install the driver in your project directory:npm install expressnpm install mongodbnpm install body-parsernpm install nodemon -gThis command performs the following actions:• Downloads the express, mongodb and body-parser packages andthe dependencies it requires• Saves the package in the node_modules directory• Records the dependency information in the package.json file• Set up nodemon runtime. This is a better option for running your application.Instead of running node server.js, run your application using nodemon. Thiswill keep looking for any code changes you do interactively and refresh theserver to take the changes into effect as soon as you save such changes to thecode base.


If you created the required directories, initialise the project, install required drivers, your project directory should look like this:

4.1.3   Create your Node.js Application
On VS Code, create a Node.js files and html files: server.js on home directory, index.html, index.js, add.html, add.js inside public directory.
Download copies of these files from Canvas and edit them to include correct Mongodb connection strings and any other desired changes.

Be careful when you edit the server.js file!Sections for handling GET and POST requests are critical, even simple typos can stophandling form. inputs or stop running the server altogether.


4.1.4   Run your Application

Run the following command:nodemonThen, open localhost:3000 on your browser.


Did it work?
5   Exercise -- “Search Movies by Director” Application
In Section 4, you build an application to insert a new “movie” document and browse the whole “Movie” document collection.
Make a copy of the project (including files in the both home directory and files in the public
directory). Make necessary changes to convert this copy into a new “ Search Movies by Director” project.
The application will present the user with a form. with one field when it is called with the following URL:
https://localhost:3000/search.html



Once the form. is duly filled with a valid Director Number (dirNumb in the database) and submitted, it will send a POST request to the node.js backend, which in turn uses mongodb library, forms an
mql query and fetches the matching “Movie” documents from the database.
If the user input (director number) is invalid, i.e. it does not exist in the database, an appropriate error message should be displayed.


         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
