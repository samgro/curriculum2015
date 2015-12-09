#Project 4 - Foursquare API
![Imgur](http://i.imgur.com/2kSeDCY.png)

##Do Now 
Begin this session by completing the [Do Now](doNow.md) activity.

##Scope
You have just been hired by APIs R US inc. This company relies entirely on using API for the many webapps. As a first project they have asked you to make a simple site that calls on the Foursquare API to test your skills.  
Since this is your first project, your manager has provided you with some helpful tools to get started. 

##Project Criteria
Your Manager has laid out the following requirements for the project: 

* The webapp will display the phone numbers of the best pizza places near an entered address.
* CSS is not a necessary feature for this project 

##Learning Objectives
By the end of this project the employee will be able to...

* Obtain a Client ID and Secret by registering their application with Forusquare
* Make an AJAX GET request to the Foursquare API, and examine the results on the console
* Use jQuery to append text to an HTML page

##References/Tools
* [Script Tag](http://javascript.crockford.com/script.html)
* [SoundCloud Developers Guide](http://web.archive.org/web/20150701150357/http://developers.soundcloud.com/docs)
* [HTTP Method explained](http://www.w3schools.com/tags/ref_httpmethods.asp)

 
##Vocabulary

* Client
* Server
* API
* AJAX
* Get
* Callback 

***
##Instructions

You are not given any Starter Code for this project. However, your manager has provided you with some useful direction to complete this project. Follow the step-by-step instructions below. 

Although these directions do not provide all the answers for this project, they do provide you with the guidance you will need to make this project.

###1) Create a GitHub repo and C9 workspace for this project
This should have already been completed during the [Do Now](doNow.md).

**Before moving on to step two, ensure your HTML is correct by having an instructor confirm you are ready to move on.** 

###2) Ready the Document
Now that you have initialized the yourwebapp it is time to "ready" the document. For information on how to do this, research the [jQuery ready function](https://api.jquery.com/ready/).  
*Hint: all of the remaining code for this project will fall inside of this .ready function.*

###3) Obtain a Client ID and Secret
In order to use a company's API you must request access and have them send you an API key. Foursquare asks you to do this by registering your app on the [Foursquare Developer website](https://foursquare.com/developers/apps) page.

Sign in or create a Foursquare account and create a new app. You will need to copy and paste the Client ID and Client Secret into your ```script.js```. Add them as variables called ```client_id``` and ```client_secret``` inside your ```ready``` function.


###4) Make a GET request to the Foursquare API
You can make a behind-the-scenes (asynchronous) request to Foursquare's API server using the jQuery .get() function. Read the [.get() documentation](https://api.jquery.com/jquery.get/) and then copy the code below into your ```ready``` function. Note that you'll need to create variables for ```client_id``` and ```client_secret``` using the values you copy and pasted from the Foursquare Developer website.

        $.get("https://api.foursquare.com/v2/venues/search" +
            "?client_id=" + client_id +
            "&client_secret=" + client_secret +
            "&v=20151209" +
            "&near=nyc" +
            "&query=pizza",
            function(data) {
                // Callback code goes here. This gets executed after receiving data from the Foursquare API.
            });

###4) Inspect a response from the Foursquare API
In the callback from ```.get()```, log the ```data``` variable to the console. Run the website in Chrome, and open View -> Developer -> Javascript console. Expand the data object to see what's inside. Poke around and explore! 

###5) Append the venue name and phone number to the ```#results``` element
Hint: you can append HTML using [jQuery .append()](http://api.jquery.com/append/).

###6) Use the address input by the user
Now that the document is ready you must store the user's response in a variable.  See the param ```&near=nyc``` in the sample code? You want to replace "nyc" with a variable for the address, which comes from the text entered by the user in the input field.


####Bonus) 
Your Manager has offered a stipend of $500 for each of the bonus requirements listed below:  

* Let the user search for things other than Pizza
* Add a "Current location" button that gets the user's current location from the browser
* Show a thumbnail photo specific to the venue
* Link to the venue’s website if it exists, or the Foursquare page if it doesn't
* Add anything else interesting from the API to the results, and spruce up the design

***

##Grading Criteria
Your manager will be grading your capibility on this project based on [this rubric](/assessment.md)

##How to Submit
The final code for this project must be pushed back up to your repo on GitHub. **Then share the link to your repo at the project submission link found in the header of the Daily Session Document (bit.ly/ScriptEd).**  

To push to GitHub run the following commands in your terminal:  
`git status`  
`git add .`  
`git commit -m "example comment"`  
`git push origin master`

##Homework
Instructor will assign homework based on progress in class.



