
# Step 6 - Adding our 'Routes', Part 2 ('Add', 'Delete' & 'UpVotes')

Recall our routes, described as follows:

* GET **/donations** - return a list of donations and associated metadata
* POST **/donations** - create a new donation
* GET **/donations/:id** - return an individual donation with associated metadata
* PUT **/donations/:id/upvote** - upvote a donation, notice we use the donation ID in the URL
* DELETE **/donations/:id** - delete a donation by ID

We've already implemented the first one, so now let's have a go at 

* Adding a new donation
* Deleting a donation and
* 'Upvoting' a donation

We'll leave finding an individual donation for the final lab - Lab 5.

---
## Creating Our 'Add' Route - 'addDonation'
Similar to the previous step, we start by creating a function (***addDonation***) for adding a single donation in our **routes/donations.js** file.

```javascript
router.addDonation = function(req, res) {
    //Add a new donation to our list
    var id = Math.floor((Math.random() * 1000000) + 1); //Randomly generate an id
    // parameters to store
    // id (for id)
    // req.body.paymenttype (for paymenttype)
    // req.body.amount (for amount)
    // 0 (for upvotes)
    
    donations.push(/*fill in missing code here */);

    res.json({ message: 'Donation Added!'});
}
```
Notice we only return a json message confirming we've added the donation.


---
## Creating Our 'Delete' Route - 'deleteDonation'


---
## Creating Our 'Upvote' Route - 'incrementVotes'


