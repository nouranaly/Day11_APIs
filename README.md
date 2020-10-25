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




