# Step 5 - Modifying our 'Routes', Part 2 ( 'deleteDonation' & 'incrementVotes' )

The first thing we need to do is add a new function to allow us to find a single donation, so add the following to your **routes/donations.js**, replacing the **getByValue** function

```
router.findById = function(req, res) {

    var id = req.params.id;
    
    console.log('Getting Donation for Id: ' + id);
    
    Donation.findById(id, function(err,donation) {
        if (err)
            res.send(err);

            res.send(donation);
        });
}
```
We're using Mongoose's own 'findById', but this will make things easier for us later on.

---
## Modifying Our Third Route - 'Delete a Donation'

Edit your **routes/donations.js** file and navigate to your existing 'deleteDonation' function.

Now, replace it with the following :

```javascript
router.deleteDonation = function(req, res) {

    var donation = new Donation();

    var id = req.params.id;
    console.log('Deleting donation: ' + id);
    
    Donation.findByIdAndRemove(id, function(err) {
        if (err)
            res.send(err);

        router.findAll(req,res);
  });
}
```

Notice how we use the Mongoose 'findByIdAndRemove' function to retrieve and delete the object from the 'Model'.

---
## Modifying Our Fourth Route - 'Increment Votes'

Again, edit your **routes/donations.js** file and navigate to your existing 'addDonation' function.

And replace it with the following :

```javascript
router.addDonation = function(req, res) {

    var donation = new Donation();
    
    donation.paymenttype = req.body.paymenttype;
    donation.amount = req.body.amount;

    console.log('Adding donation: ' + JSON.stringify(donation));
    
    // Save the donation and check for errors
  donation.save(function(err) {
    if (err)
      res.send(err);

      res.json({ message: 'Donation Added!', data: donation });
  });
}
```
There's a bit more going on here, so make sure you understand the general jist of how this works. (But I'll explain in the labs anyway)

You may need to restart your server but if everything goes to plan, you should now be able to store and retrieve 'donations' from your mongodb database.