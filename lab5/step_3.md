#Step 3 - Creating our Database Schema

Our first step in making a persistent data store is to configure our data models. To do this, we are going to be adding a schema layer on top of **MongoDB** using a nice library called ***Mongoose***. Before we begin, let's make sure our **MongoDB** server is running.

If Mongo isn't running on your machine, enter this into your terminal:

```
mongod
```
and to run a mongo client

```
mongo
```

We connect to our local MongoDB instance by adding the following code into our donations.js **routes** file:

```
var mongo = require('mongodb');
var mongoose = require('mongoose'); 

...

mongoose.connect('mongodb://localhost:27017/donationsdb');
```

This will open a connection with the ***donationsdb*** database running on our Mongo server. Now we can modify our existing model and introduce a database schema.

---
## Creating a Schema with Mongoose

In our **models/** directory edit **donations.js** and add the following code:

```
var mongoose = require('mongoose');

var DonationSchema = new mongoose.Schema({
  paymenttype: String,
  amount: Number,
  upvotes: {type: Number, default: 0}
});

module.exports = mongoose.model('Donation', DonationSchema);
```
Here we've defined a model called ***Donation*** with several attributes corresponding to the type of data we'd like to store. We've declared our upvotes field to be initialized to 0.

Next we register that model with the global mongoose object we imported using require() so that it can be used to interact with the database anywhere else mongoose is imported.


