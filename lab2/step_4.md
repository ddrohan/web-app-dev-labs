#Step 4 - 'Donate'

So now that we can display a list of the donations initially set up, the second feature we'll implement is our **'Donate'** option where the user can choose an *amount* and a *payment type*. Before we start, have a look again at what we want our completed page to look like

![](../images/donationwebapp2.jpg)

There's a bit more work involved to get this feature implemented, so the first thing we'll do is write a function to allow us to *add* a donation to our list (in the factory).

---

## The *factory* 'add' function

Have a quick look again at our list we declared in our **factory**, just to familiarise yourself with the data you'll be displaying

![](../images/lab2.step3.1.png)

Now we need to implement a function which will 'add' a donation made, to the above list. Here's the majority of the code you need, but try and work out what you need to complete the function (fill in the ...'s) and where to put it.

```javascript

donations.add = function(... , ...){
    donations.push(...);
  };

```
The next step is to somehow 'wire up' the click of the Donate Button on our view, with the add function you just implemented - we'll achieve this through a ***callback function***.
---

## Updating our *donateController* - the 'addDonation' Callback

Everything we need to display our list of donations is already implemented in our **'donations.html'** page (as per the solution) so test it out, but you should investigate how we actually achieve the rendering of the list and familarise yourself with the different ***angular directives*** used in the solution, below is an extract from the page but it's worth having a look at the complete html at some stage.

![](../images/lab2.step3.2.png)

You should pay particular attention to the following directives

* **ng-controller**
* **ng-repeat**
* **ng-click**

and how we display the individual properties of each donation via the current ***scope***.

