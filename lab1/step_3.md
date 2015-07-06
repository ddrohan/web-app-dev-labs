
# Step 3 - Implement the 'About Us' Page

This step involves adding another navigation link to our navigation bar to take the user to an 'About Us' page, like so

![](../images/navbar.lab1.v2.png)

---

## Updating the Navigation Bar

Adding the link is quite straightforward so open up your **index.html** page and add the following html code to the list of links

```html
<li><a href="#about"><i class="fa fa-info"></i> About</a></li>

```
Save the file and a quick refresh of the page in your browser should display the expected result.

---

##Adding 'about.html'

We'll keep this page fairly simple for the moment so create a new file within the **'pages'** directory/folder of your webapp folder and place the following html inside it.

```html
<div class="jumbotron text-center">
	<h1>About Us</h1>
	
	<p>{{ message }}</p>
</div>
```
---

##Wiring it all up - the 'About Us' Controller and Routing

This is where most of the wok needs to be done in-so-far as we need to  

* create a new ***controller*** object to manage the page and
* add a new ***route*** to ensure the link is correctly associated with the **controller**


