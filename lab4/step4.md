
# Step 4 - Adding our 'Routes', Part 1 ( 'home' & 'findAll' )

With our backend models in place, it's now time to open some routes that the frontend client can interact with. The following are a list of actions a user can perform:

* view all donations
* Add a new donation
* Upvote a donation
* Delete a donation
* go home :-)

The actions map directly to several routes, which are described as follows:

* GET **/donations** - return a list of donations and associated metadata
* POST **/donations** - create a new donation
* GET **/donations/:id** - return an individual donation with associated metadata
* PUT **/donations/:id/upvote** - upvote a donation, notice we use the post ID in the URL
* DELETE **/donations/:id** - delete a donation by ID
