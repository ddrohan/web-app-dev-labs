
# Step 4 - Adding our 'Routes', Part 1 ( 'home' & 'findAll' )

With our backend model in place, it's now time to open some routes that the frontend client can interact with. The following are a list of actions a user can perform:

* view all donations
* Add a new donation
* Upvote a donation
* Delete a donation
* go home :-)

The actions map directly to several routes, which are described as follows:

* GET **/donations** - return a list of donations and associated metadata
* POST **/donations** - create a new donation
* GET **/donations/:id** - return an individual donation with associated metadata
* PUT **/donations/:id/upvote** - upvote a donation, notice we use the donation ID in the URL
* DELETE **/donations/:id** - delete a donation by ID

---
## Creating Our First Route

To keep things organised we will be defining these routes in a **routes/donation.js** file. 

Let's begin by opening up the first route we listed, which should return a **JSON** list containing all donations. We start by creating a ***GET*** route for retrieving donations in our **routes/donation.js** file.

```javascript
var donations = require('../models/donations');
var express = require('express');
var router = express.Router();

router.findAll = function(req, res) {
  // Return a JSON representation of our list
    res.json(donations);
}

module.exports = router;
```



By right, we
