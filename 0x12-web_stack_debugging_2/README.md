
## DEBUGGING IN WEB STACK

There are various types of errors that can result in your program not doing what’s expected or failing to run at all.

Syntax errors
Syntax refers to the “rules” that define a programming language. Syntax errors, therefore, result from “breaking” programming language “rules.”

Syntax errors include typos or missing a semicolon.

Logical errors
A logical error occurs when your program doesn’t work the way it should. The program is able to execute, though. 

Let’s look at an example.

for (var i = 1; i <= 10; i++) {

    if (i % 2 == 0) {

        console.log(i);

    }

}

n the above for loop, we’re trying to generate all the even numbers below 10. The above code runs, giving the following even numbers: 2, 4, 6, 8, and 10. 

However, there’s a problem with the results. Even numbers less than ten should include the number zero. Because we set our loop to begin at one instead of zero, we miss out on the first even number, zero.

Runtime errors
A runtime error occurs when you’re executing a program but execution stops. Sometimes, runtime errors can be caused by the environment in which you run your program. 

There are many other types of errors that you’ll learn as you keep learning code. Better still,  learn how to “catch” them in your code via concepts like “errors and exception handling.”

Types of debugging
Debugging can be largely categorized into two types: reactive and proactive. Let’s dig deeper and learn a little more about them.


Reactive debugging
This is done after the bug has been identified. In the previous section, we looked at different types of errors. 

All the types of errors we’ve come across so far are resolved via reactive debugging.

Proactive debugging
In proactive debugging, developers write code (as part of the program) that’s on the “lookout” for errors.

This “extra” code doesn’t affect the functionality of the rest of the program. 

Proactive debugging is also referred to as preemptive debugging.

Proactive debugging is a part of both defensive and offensive programming, which are two other types of programming.

The five steps of debugging
In the quest to really understand what is debugging, there must be a way to make it more manageable and, who knows, maybe even pleasant.


Step One: Gather information about the error
As a beginner programmer, you’re highly likely to make syntax errors. As a result, keeping an eye on these should be high on your priority list. Another thing you need to do is read error messages and try to understand them.

If you’re working with any data, for example, user data, check that too. You may have forgotten to perform data validation checks.

Step Two: Isolate the error
In this step, the goal is to try and identify the source of the error. You might need to “recreate” the error so as to know when it happens.

You could also comment out parts of the code and keep checking to see what section of your program could be causing the error. 

You can also add print statements within your code (console.log in JavaScript). For example, if you’re able to print the output of a function, then it isn’t likely to be the one causing the error.

Keep doing this after every few lines of code. Eventually, you’ll see the section of your code that’s causing the error.

Step Three: Identify the error
Once you’ve narrowed down the section of the program that’s causing the error, you need to find the error itself. A great place to start is with a hypothesis.

For example, if you find that an error is coming from a field on your form, your hypothesis might be that you’re using the wrong data type. 

You might be trying to add strings and integers, for instance. 

Step Four: Determine how to fix the error
Once you have your hypothesis, it’s time to test it. For example, you might add data conversion logic to your program and run it to see if the error is gone.

If the error is still there, formulate another hypothesis and keep testing it. Keep doing this until the error is fixed.

Sometimes the solution to an error might not be obvious. You can visit sites like StackOverflow and find out whether anyone has experienced the same error and how they fixed it.

You might also ask a colleague for help or talk to an inanimate object and explain to it what you’re trying to do with your code (rubber duck debugging).

And now that we have ChatGPT, you can also ask it to help you find the error in your code and how to fix it. 

Step Five: Apply and test
You can rerun the code to see if the error is fixed. Testing is a great way to ensure that you don’t end up creating more bugs when fixing the ones you’ve been focusing on!

Sometimes, you might not be able to figure out how to fix the error, despite your best efforts and even those of your colleagues. 

In these situations, you’ll need to settle for a workaround that can keep the program running while you continue to find ways to completely get rid of the error. 


