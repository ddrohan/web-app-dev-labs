# Step 5 - Updating our Views, Part 1

Now that we have our basic backend implemented, we're going to wire up the angular frontend we developed and imported in previous labs.

Our first step is going to be to query our new backend for all **donations** using the ***donations*** route. We do this by adding a new function inside our **donationscontroller**.

Our current controller looks like this

```javascript
var app = angular.module('DonationWebApp');

app.controller('donationsController', ['$scope','donations', function($scope, donations) {
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
So go ahead and delete the two existing **$scope** functions and replace them with the following

```javascript
$http.get('/donations')
        .success(function(data) {
            $scope.donations = data;
            console.log(data);
        })
        .error(function(data) {
            console.log('Error: ' + data);
        });
```
