
# Step 4 - Refactoring our Controllers

Our current version of Donation isn't fully functional mainly due to the fact that what was originally a client side app has now become a client-server app and we need to restructure how our views are managed (***controlled***).

The first thing we need to do is create a ***seperate controller*** for each of our views so navigate to the ***public/javascripts/*** directory and create a new folder called ***controllers/***.

We need to move all the **controllers** in our single **angularApp.js** file into their own respective files, so create the following inside your ***controllers*** folder

![](../images/controllers.png)

Now, for each controller in our **angularApp.js** move it into its respective file in the ***controllers/*** (as above).

As each controller is going to be in a separate file we will need to add the following line of code to each file

```javascript
var app = angular.module('DonationWebApp');
```
As a start, here's our updated ***aboutcontroller.js***

```javascript
var app = angular.module('DonationWebApp');

app.controller('aboutController', ['$scope', function($scope) {
    // create a message to display in our view
      $scope.message = 'This is the about Page';
     }
  ]);
```
So initially, have a go at ***contactcontroller.js*** and ***maincontroller.js***.

There's a bit more work involved with last two controllers (***donatecontroller.js*** & ***donationscontroller.js***) so we'll complete those separately.

It's probably worth testing your app again just to confirm that the controllers you've updated still work so point your browser at [http://localhost:3000](http://localhost:3000) and try it out.

---

## Our 'donationsController' and Dependency Injection (D.I.)
To begin with, take the same approach with this controller as the previous ones, just move it into its own file and add the line of code at the top, so you'll have something like this

```javascript
var app = angular.module('DonationWebApp');

app.controller('donationsController', function($scope, donations) {
    // create a message to display in our view
    $scope.message = 'Donations Page!';
    $scope.donations = donations;

      $scope.delete = function(donation){
      if (confirm("Are you sure you want to delete? : ")) {
          donations.deleteDonation(donation);
         }       
      };

        $scope.incrementUpvotes = function(donation){
          donations.incrementUpvotes(donation);
      };
  });

```
If you try and test it, it may still not be functioning correctly - can you explain why, and how to fix it?

The problem lies in the fact that this controller is in a separate file so the ***$scope*** object needs to be *injected* into the controller (as well as the donations). 

**This wasn't an issue in our Angular version as everything was inside the one file (same scope).**

So here are the changes we need to make

```javascript
var app = angular.module('DonationWebApp');

app.controller('donationsController', 
<pre><b>['$scope','donations'</b></pre>, 
function($scope, donations) {
    // create a message to display in our view
    $scope.message = 'Donations Page!';
    $scope.donations = donations;

      $scope.delete = function(donation){
      if (confirm("Are you sure you want to delete? : ")) {
          donations.deleteDonation(donation);
         }       
      };

        $scope.incrementUpvotes = function(donation){
          donations.incrementUpvotes(donation);
      };
  }
  ]);
```
