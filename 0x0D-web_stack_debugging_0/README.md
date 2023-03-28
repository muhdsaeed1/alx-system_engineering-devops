
## Web Stack Debugging

Debugging is the process of finding and resolving defects or problems within the program that prevent correct operation of a computer software or system

An important thing to understand is that the debugging as a skill is something that needs to be learned and takes time to master. Beginners in the field of software development should take time to familiarize themselves with the debugging basics in order to make their first attempts at building applications less stressful when unexpected behavior occurs

Steps for bug resolution

Bug reproduction

The first thing to do when trying to fix a reported bug is to actually try to reproduce it. This should always be the very first step. In order to accomplish this, ask the person that reported the bug for the instructions for the reproduction. Performing this step will save you time from chasing non-existing bugs or allow you to validate your fix later.

Of course, there are situations when you are unable to reproduce the bug, even though some sort of an error log is present. If you can tell that this error may present any kind of substantial danger to your application, try to catch the error in the code (using try/catch) and try to log more details regarding that error in order to try to figure out what behavior actually causes the bug in the first place.

In cases where you are absolutely certain that the error itself presents no danger to your system, you can use a defensive approach to the bug resolution, thus basically eliminating the reporting of that error from that point forward.

Analyze stack-trace

When viewing an error report, see if a stack trace is present. In the stack trace, try to find the last call of your business logic code (non-library and non-framework code), since, in most cases, this is where the problem lies. If you are catching and rethrowing exceptions in the code, try to customize them and set appropriate exception messages, so you can easily refer back to them later.

The problem can occur if the stack trace isn’t present at the place where the error occurred. A good idea would be to check if the main error logs contain any meaningful error-related data.

Also, if no error logs are present anywhere, that might be an indication that the error reporting mechanism in your app is broken, so it would be a good idea to fix that first. In the case where the error occurred in the response to an HTTP request, the HTTP status code might give you enough info on where to look for the problem.

If using TDD/BDD – This is also a good time to write a test case for the detected bug (in case you are writing automated tests). This will ensure that the bug doesn’t reappear sometime in the future due to some newly introduced code changes


Ask the rest of the dev team for help

Now that the stack trace is found, it is time to proceed with the actual bug resolution. If you are unable to understand the stack trace, ask the person that was the last one that edited that part of the code (if available) if they can quickly recognize the issue, or give you a clue where the potential problem might be.

If that doesn’t help (or that person is unavailable), ask the rest of the team if anyone can recognize the mentioned problem. More often than not, someone will be able to give you a hint where to look for the solution.

Google the error cause

If no lead to what caused the error was found, try Googling the error cause in the stack trace. Sites such as Stack Overflow are filled with answers that either solve or point to the solution of numerous coding errors, so you can always try your luck with that. If no business logic error has been found in the stack trace, try to Google library or framework errors that don’t seem to be generic and seem to you like something related to the app behavior that is you are dealing with.

Rubber duck and/or pair programming

Finally, if the previous steps didn’t work, you might want to resort to rubber duck programming and/or pair programming. Rubber duck programming consists of trying to explain out loud the code you are looking at (you can carry your rubber duck with you, or ask a colleague to listen to you). Simply explaining the problem and the application flow thoroughly often leads to an easy resolution of the problem itself.



Various bug resolution techniques
These are the actions that can be performed in the above-mentioned steps and increase the chance of achieving the desired outcome.

Log and stop technique

The best way to understand what’s going on in your code is to follow your application flow, log the current app state at a certain point (var_dump or console.log commands) and stop the code execution afterward (die or alert/debugger commands). Sometimes you might need to let the app flow continue, so the ‘stop’ part of the technique would be omitted in such cases.

By utilizing this technique you will be able to validate that the app flow indeed does happen, you will be able to check if the actual data is present in that state (ie. user input) and to analyze your fix attempts at that point.


Code removal technique

This particular technique is useful when no error stack trace is present (or the stack trace is completely useless).

Before utilizing it, make sure that no other app layer changes caused the problem (DB config change, server config change, etc.) and that the business logic code is responsible for the bug occurrence.

Next, try taking a look at the code changes in order to try to get a hint at which file might be responsible for the bug. If you aren’t sure, start from the top (e.g. the code responsible for receiving the user input) and comment out or delete parts of the code along the way and try to use the log and stop techniques after the commented-out code (if applicable) to see if the error has been removed.

If there is a large amount of code at the same level, use the halving technique – remove roughly one half of the code and detect if the bug is gone. If not, that means the bug is in the other half and we apply the same technique to the half, containing the bug until you can precisely localize the bug.

A special case which makes this technique difficult for application is a situation when a silent fail occurs after a lot of added code (e.g. after a branch merge). In such a situation, it’s imperative to first detect which exact commit introduced the problem. If that is too difficult to perform by simply skimming through the code (the number of commits is too big, or none of the commits seem suspicious), use the halving technique in a combination with git reset HEAD – go back a certain number of commits and see if the bug still appears. If it does, you know that you need to go back further in the git log; if it doesn’t, try to half the number of commits between the latest checked commit still containing the bug and the one that doesn’t contain it until you determine the commit that introduced the problem.

After the problematic commit is identified, apply the regular code removal techniques on it.

Use a technology-specific debugger

If you need additional insight and the previously mentioned techniques didn’t do the trick, install some technology-specific debugger. These include Xcode for PHP, vue-devtools if using VueJS, etc.

Moving forward

After you’ve successfully managed to resolve the bug, the first thing to do, naturally, is to celebrate. After celebrating, though, there are other things that can prove useful too – share the new knowledge (if any) of the cause of the bug with your colleagues and write a test for the case (if using automated tests), or at least write a test case in plain words somewhere so the team can remind themselves of the potential pitfalls going forward.

These small actions can bring great benefit to your code maintenance down the road.
