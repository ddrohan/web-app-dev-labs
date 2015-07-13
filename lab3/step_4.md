
# Step 4 - Refactoring our Controllers

Our current version of Donation isn't fully functional mainly due to the fact that what was originally a client side app has now become a client-server app and we need to restructure how our views are managed (***controlled***).

The first thing we need to do is create a ***seperate controller*** for each of our views so navigate to the ***public/javascripts/*** directory and create a new folder called ***controllers/***.

Now, we need to move all the **controllers** in our single **angularApp.js** file into their own respective files, so create the following inside your ***controllers*** folder

