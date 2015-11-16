# Step 04 - Heroku & MongoLab

As previously mentioned, the web app didn't load correctly. It failed to launch due to no backend database present - this final step will take you through the process of setting up a mongodb database via one of Heroku's many addons <b>MongoLab</b>

First, visit your Heroku dashboard for your web app and select the ' Resources' tab

![](images/heroku23.png)

In the 'Add-ons' Search box, enter mongo (or mongolab to be complete)

![](images/heroku24.png)

and select the 'mongoLab' Add-on. 'Provision' the Free Sandbox Plan, and the MongoLab Add-on will be added to your web app.

![](images/heroku25.png)

Now, select the new Add-on and you'll be taken to the associated MongoLab Account

![](images/heroku26.png)

and a randomly generated database (as below)

![](images/heroku27.png)

The connection string is very important

![](images/heroku27a.png)

![](images/heroku28.png)

![](images/heroku29.png)

![](images/heroku30.png)

![](images/heroku31.png)

![](images/heroku32.png)

![](images/heroku33.png)

![](images/heroku34.png)

![](images/heroku35.png)

![](images/heroku36.png)


## THE END!