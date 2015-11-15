# Step 03 - The Heroku Toolbelt

At this stage you can now create repositories and manage you projects and files through git and Bitbucket + SourceTree. To actually deploy a Node Web App to Heroku you need the <b>Heroku Toolbelt</b>. 

The Heroku toolbelt will give us access to the Heroku Command Line Utility, as well as git, (tools we’ll use later).

After you've installed the Toolbelt, you have access to the heroku commands. Go into your command line and type:

~~~
$ heroku
~~~
![](images/heroku17.png)

You get a full list of the available Heroku commands, but we'l only be using a few of them.

The next step is to login to your (already created!) Heroku account, so at the command line, type
~~~
$ heroku login
~~~

and enter your Heroku credentials

![](images/heroku18.png)

Now type
~~~
$ heroku create donationwebtest
~~~

where 'donationwebtest' is the name of the web app you wish to create.

<b>Note : the web app name needs to be unique, so if a node web app already exists with the name you've chosen, you'll get an error</b>

You can always leave the name empty

~~~
$ heroku create
~~~

and Heroku will generate a random web app name for you?

![](images/heroku19.png)

Visit your Heroku Account online to confirm your app was created successfully.

![](images/heroku20.png)
~~~
$ git push heroku master
~~~

![](images/heroku21.png)

![](images/heroku22.png)