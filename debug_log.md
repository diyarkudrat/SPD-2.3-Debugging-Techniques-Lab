# Debug Log

**Explain how you used the the techniques covered (Trace Forward, Trace Backward, Divide & Conquer) to uncover the bugs in each exercise. Be specific!**

In your explanations, you may want to answer:

- What is the expected vs. actual output?
- If there is a stack trace, what useful information does it contain?
- Which technique did you use, on which line numbers?
- What assumptions did you have about each line of code, and which ones were proven to be wrong?

_Example: I noticed that the program should show pizza orders once a new order is made, and that it wasn't showing any. So, I used the trace forward technique starting on line 13. I discovered the bug on line 27 was caused by a typo of 'pzza' instead of 'pizza'._

_Then I noticed another bug ..._

## Exercise 1

    - Program should submit an order made for a pizza, but throws a TypeError. Used the trace backward technique starting on line 88 where the error is thrown at us. Discovered that 'topping' isn't a model field in the PizzaTopping mode, it's topping_type.

    - Noticed another bug where the user should be redirected to the home page after submitting an order, but i was throwing an error. I used the trace forward technique to discover that on line 93, the redirect method had an endpoint in it, instead of the function that you want to redirect to. It was '/' when it should be 'home'.

    - Noticed another bug where the program should show pizza orders once a new order is made, and it isn't showing the pizza order. So, I used the trace backward technique starting at line 89 where the call is made to add the pizza to the db. I discovered that the pizza_order_submit() was retrieving the wrong names of the input fields in the form. However, this still didn't fix the bug. I noticed that db.session.commit() was called in other areas after making calls to the database. So I added it after adding to the db when submitting an order, and before making a query call in the home function.

## Exercise 2

    - I noticed that the program was fetching the API key from a .env file, but there was no such file in the directory. So I added the .env file that contains the API key in it.
    - Another bug was that there was no data being retrieved from the API. So, I used the divide and conquer technique where I made breakpoints between the different code sections. I discovered that the program wasn't getting the correct info from the HTML form. Also discovered that the way the API is being called is wrong. I looked up the docs to the API and found the correct way to make an API Call. By making these changes, the program was able to retrieve data from the API.
    - Found another bug where the program should get the temperature from the json data, but threw an error saying that it couldn't find temperature in the json data. I used the trace backward technique, and discovered that the naming was wrong in the program. In the JSON data, the temperature is defined as 'temp', so I changed 'temperature' to 'temp' on line 54.

## Exercise 3

[[Your answer goes here!]]
