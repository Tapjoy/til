# Save arbitrary data as global variable in chrome dev tool

One of the pretty cool feature of chrome dev tool that I've missed is "Save as global variable".
This feature allows user to extract and assign arbitrary data, which is logged on the chrome dev tool console,as global variable.

Assuming that you used `console.log()` to log an object to check the data inside.
People can click that logged object and check the data but can't do anything more than just logging.
What if you want to manipulate and play with the data?

Add more line of code like `console.log(data.doSomething())` whenever you want to test something is tedious.
There is more clever way to achieve that goal.

![2017-03-10 4 51 14](https://cloud.githubusercontent.com/assets/16456651/23786711/e0b730c4-05b1-11e7-9f07-fd958d25fd72.png)

![2017-03-10 4 51 39](https://cloud.githubusercontent.com/assets/16456651/23786714/e2d0b38a-05b1-11e7-9afb-860abdb450e6.png)

Voila! The object is assigned as `temp1` global variable!
By storing the logged data as global variable, you can do whatever you want to do with that data.
This is pretty basic feature but I've learned it just last weak.
