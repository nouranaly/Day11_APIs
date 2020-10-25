# Week 3-Fintech
## Day 11: APIs
#### Overview
**Students will be able to** 
- Explain what an API is 
- Go to a developers website for an API and get a Key
- Retrieve data by making GET requests to a specified endpoint 
- Make a request with parameters
- Parse through JSON responses (lists and dictionaries) from an API
- Explore data structure to isolate the elements that you want and build an API/Flask App

### Intro 
**Framing**

At the start of instruction frame for students that some of them may have worked with APIs before and for others, today will be their first day! For that purpose, API play time will give everyone a chance to explore APIs and build something new that they have not tried before. Expect that students will be at different levels today and be willing to provide the space for them to choose their own route for how they want to build and play with APIs. 

**What is an API**

An API is an *application programming interface*. It refers to connection points between 2 entities of code. Think of it as a set of rules that allows programs to talk to each other. Computer programs frequently need to communicate amongst themselves and APIs are one way they do that. Every time you go online shopping, browse a social media app, play a game on your smartphone, or visit a page online, you’re interacting with an API. A more specific example is when you’re listening to music on Spotify, the music playing application on Spotify communicated with your systems API in order to send music to your speaker. 

To use an API, you make a request to a remote web server and retrieve the data you need. 

**But why use an API?**

It’s worth taking time in the beginning of class to have students construct their own understanding of why APIs are useful. 
Before heading into the Giphy API Lab, have students go through the process of building a program that returns a gif based on the users query **WITHOUT** the use of an api.  

**To Get Started**

1. Clone the Giphy API Lab: (modify the flask-api template to a giphy api) 
2. Flask Run. 

**Questions for Students**
- Have students search for a “cat” gif and ask them what was the result of their search. Then have them search for a “koala” gif and ask them what was the result of that search 
- Ask students to explore the program and try to uncover why they received a gif for cat but not koala. Ask students to put a green check mark once they feel that they have uncovered why. *(Provide a hint halfway during wait time, directing students to the model.py file.)* 
- Once all students have their attention on the getImageUrlFrom function,  ask students what can a user search up and have a gif returned to them and where are those gifs stored?

At this point, students understand that only two gifs have been manually stored in the program, and if the program was to respond to more queries, then more gifs need to be uploaded in the images file. 

#### Time for the pain point: Challenge students to return a gif for as many animals from the list below as they possibly can in 10 min.
- Llama
- Chipmunk
- Alpaca
- Raccoon
- Hippo
- Koala
- Penguin
- Panda
- Rabbit
- Piglet
- Goat 

**Reflection:** as students return from the challenge have them reflect on their experience of what it was like searching, uploading and returning a gif for all the animals on the list and to try to imagine what it would it would be like if they were tasked with an even larger list or other categories that someone can possibly search for. 

**Take-away:** reveal to students that the hard work of compiling large data sets is already taken care of through APIs. While this process was made to be intentionally painful, it will pave the way for their understanding of why APIs provide a much more seamless and efficient way to request and retrieve data from data bases that have already been created.  

--- 
## Giphy API Lab 
As you head into lab time, have students select from the following two options based on their preference: 
* **Option 1:** If this is their first time working with APIs, provide them the option of doing the Giphy API Lab as a code-along with a teacher
* **Option 2:** Students who are comfortable working with APIs can opt into completing the Giphy API Lab with a partner in a separate breakout room. 

**The Goal**: We’re going to build a Flask app using the Giphy API. When it’s finished it will look something like this: 

![Gifbot](https://media.giphy.com/media/NPdrfe4ox96zm8QCMW/giphy.gif)

We're going to write a program to asks the user what kind of gif they would like to see and return a gif based on the user’s request. 

#### Part 1: Getting Started
- Go to developer.giphy.com 
- Sign up for a developers key
- Clone the flask API template:(https://github.com/upperlinecode/Flask-API-Template) 
- Flask run 

#### Part 2: Create a route for yourgif.html page 
- Try submitting something in the form, figure out why it doesn’t work!
- Create a route for (‘/yourgif’, methods=[‘GET’, ‘POST’]), which returns any text for now ex: “Yay” 
- After confirming that your route works, render_template the yourgif.html page instead of the text. 

#### Part 3: Write the API request
- Go to https://developers.giphy.com/explorer
- Choose an endpoint (you probably want “search”) 
- Copy the URL
- Go to the model.py file, create a variable called “endpoint” that stores your URL as a string inside the function *getImageUrlFrom*
- Create a variable called “response” where the data from your URL will be stored and convert it to a JSON to view the data as a python dictionary 
   response = requests.get(endpoint).json( ) 
- Add: print(response) to the end of the *getImageUrlFrom* function to view the data from your search 

#### Part 4: Retrieve and request data for your query 
- In app.py uncomment from model import *getImageUrlFrom*
- In  the yourgif route, add image = getImageUrlFrom(“pugs”) 
- Make sure you import requests in model.py
- Run the program and make sure it works- if you search for pugs, the program should print the data from your query in your terminal.

#### Part 5: Parse and narrow down your response 
- Open the response in your browser. Use JSONView or similar extension to figure out your data structure 
- Your first key is “data”.  Keep digging to find the specific data elements you want.  Try to specify the response in model.py to print the fixed height images.

#### Part 6: Return the data to the user 
- Rather than print, Return the data element you want in your *getImageUrlFrom* function 
- In app.py set image=image in your render_template
- Display the image from your query in yourgif.html,  <img src=”{{ image }}” />
- Flask run to make sure it works before moving on 

#### Part 7: Respond to different user queries 
- Now, what happens if you request a cat gif?
- In the yourgif route, create a variable called query that takes in the user’s query from the form in index.html   
- In app.py, replace “pugs” with “query” in your route
- In model.py replace “pugs” with “query” using string formatting endpoint = f”...{query}...”

#### Extensions 
- What if whatever the user types gets a “cat” search added to it?  So if they search for Beyonce, they get a “Beyonce cat” gif?
- What if half the time the user gets what they searched for, and the other half the time, you serve them your favorite gif?
- What if the user only gets the gif they want if they say “please” in front of their search?
- Don’t take the first gif [0], take a random one.
--- 

## API Play Time (1) 
After the Giphy API lab, give students the chance to practice working with APIs by either: 
* **Option 1:** Continue working on the Giphy API Lab (extensions, customize it, keep making it beautiful/ user friendly) 
* **Option 2:**  Parsing and extracting JSON data through the [Jeopardy CLI Lab](https://github.com/upperlinecode/jeopardy-cli-python-apis) 
* **Option 3:** Build a flask/API app using the Spoonacular API Lab 

Frame to students that all 3 options allow them to work with APIs. If you want to explore what else you can build with the Giphy API then option 1 is a good fit.  If you wish to practice digging through nested data structures and display specific elements from a large data set that’s included within the lab then option 2 is a good fit. If you wish to build an app from scratch that takes in the user’s query and returns the results from their request, then option 3 is a good fit. 

### Option 3: Spoonacular API Lab 
![spoonacular](https://media.giphy.com/media/10u6gt11vnm812/giphy.gif) 

**The Goal:** We’re going to build a Flask app using the Spoonacular API. Your app should take in the user’s preference for what type of recipes they are interested in and return a list of recipes based on their request. 

#### Possible App Ideas: 
While exploring the Spoonacular documentation you will realize that there are hundreds of thousands of recipes that you can filter through. You can search and filter through these recipes by query, and/or by ingredients, and/or by nutrients, giving you many different options for building this app. Here are some possible app ideas that you can create using the Spoonacular API: 

* **Option 1: The Ain’t No Body Got Time for Cooking App**
Create an app that allows users to find recipes based on their food preference and set a limit for how long it should take to prepare and cook the recipe in their search 
* **Option 2: Diet Specific App**
Create a diet preference app that takes the users query for food and allows them to select from recipes that fall under a particular diet, ex: vegetarian, gluten-free, paleo

* **Option 3: Nutrient-Based App**
Create an app that allows users to find recipes based on the limits they set for macronutrients (calories, proteins, fats, and carbs) and/or micronutrients

*You are not limited to these ideas. Feel free to combine any of the queries above to create a more dynamic app or come up with your own app idea if you wish to be more creative and so something else.*

#### IMPORTANT NOTE:  there are dozens of available endpoints so be sure to read through all the different options carefully in order to select the one most most suitable for your app!

![Note](https://media.giphy.com/media/f9kyJwcyoqSKoPLIo2/giphy.gif) 

#### Extensions: 
- Sort the recipes returned to the user by the type of cuisine 
- Display the recipe results using bootstrap card components 
- Build a form that allows the user to select a recipe from the results and view the cooking instructions (Hint: Use the “Get Analyzed Recipe Instructions” endpoint) 

#### To Get Started: 
- Go to https://spoonacular.com/food-api
- Sign up for a developers key
- Clone the flask API template:(https://github.com/upperlinecode/Flask-API-Template)  
---

### Post Lunch Playtime: 
1. Continue working on the Jeopardy, Giphy, or Spoonacular API/Flask app 
2. Choose a new API and build your own API/Flask App with your partner 
   - APIs to Consider Exploring: 
      - Makeup API: https://github.com/twant/APIs-Lab
      - Google Books API: https://developers.google.com/books
      - Recipe API: https://developer.edamam.com/edamam-recipe-api
      - NYTimes API: https://developer.nytimes.com/apis
      - List of public APIs: https://github.com/public-apis/public-apis

**EOD Reflection** 
- What advantages do APIs provide developers?
- What are some types of programs you could build that might need an API to reach their full potential?

**Why Use APIs** 
- **APIs are useful when data changes quickly**- Stock prices are a great example of datasets that change quickly and it would make no sense to regenerate a dataset and download it every minute or every time there is a change in stock prices. (trip data) (user) 
- **You can scoop a small piece of a larger data set**- Imagine creating a Taylor Swift fan page and wanting to display all of Taylor Swift’s tweets from twitter on your fan page. It doesn’t make much sense to download the entire twitter database, then filter out just Taylor Swift’s tweets. (user) 
- **Security**- Using APIs, developers can control the exposure of code without having to expose their entire database. This allows you to send small amounts of information that the API then delivers and the server sends it back without you having to access the entire backend of the server. (provider) 
---
---
## Day 12: Intro to MongoDB
#### Overview
**Students will be able to** 
- Sign up for and configure a MongoDB account
- In the MongoDB dashboard, create a database, create a database user, and whitelist IP addresses
- Connect to MongoDB from a Flask app using PyMongo
- Push data to MongoDB from a Flask app
- Use a form to collect user data and store data to MongoDB
- Query MongoDB for data using various methods
- Sort and limit MongoDB query results

### Intro (9:30 - 10:15) 
Now that we have been building apps using flask, you might have recognized a need to store and retrieve data. This problem gives us a chance to explore some of the creative solutions that databases offer, which allows us to do just that. MongoDB is a database that you can use with any python/flask app in any project you are building. Whether its a website, a mobile app, or a desktop app, you’re probably working with some kind of data that you will need to store and fetch fast and efficiently without worrying about setup and data structures, and MongoDB is a great solution for that. 

Frame to students that we will first take time to set up our MongoDB accounts and before we write data to MongoDB, we’ll play around with some of the built in methods in the PyMongo library that will allow us to read, request, and display particular data from MongoDB. 

#### Initial Setup- Sign Up for MongoDB
[Setting up MongoDB Account Tutorial Video](https://www.youtube.com/watch?v=LLbV4n-uKrA&list=PLetu2kRAyoeCvogwvGGq94QgATwfj5viJ)
Once the cluster is created on MongoDB, we need to do three things to complete the database setup before we can connect to it from our app:[(Instructions Here)](https://teacherhub.upperlinecode.com/app/teach/ftf-day-12/databases-intro#create-a-database)  
- Step 1: Create a Database
- Step 2: Create a Database User
- Step 3: Whitelist IP Addresses





