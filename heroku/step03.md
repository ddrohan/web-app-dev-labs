# Step 03 - The Heroku Toolbelt

At this stage you can now create repositories and manage you projects and files through git and Bitbucket + SourceTree. To actually deploy a Node Web App to Heroku you need the <b>Heroku Toolbelt</b>. 

The Heroku toolbelt will give us access to the Heroku Command Line Utility, as well as git, (tools we’ll use later).

After you've installed the Toolbelt, you have access to the heroku commands. Go into your command line and type:

~~~
$ heroku
~~~
![](images/heroku17.png)
~~~
$ heroku login
~~~
![](images/heroku18.png)
~~~
$ heroku create donationwebtest
~~~
![](images/heroku19.png)

Visit your Heroku Account online to confirm your app was created successfully.

![](images/heroku20.png)
~~~
$ git push heroku master
~~~

![](images/heroku21.png)

![](images/heroku22.png)