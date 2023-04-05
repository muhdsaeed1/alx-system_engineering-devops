
## Debugging a secure website ( webstack debugging) 


As the Internet evolves with an ever increasing demand for security, websites are taking a full-HTTPS approach combined with additional features like Strict Transport Security (HSTS) and Public Key Pinning (HPKP). Websites adopting HTTP/2 for its performance benefits are also required to use HTTPS everywhere.

The growing ubiquity of using TLS (the protocol that provides the security of HTTPS, which previously was provided by SSL) is great for our security and privacy but it can hinder our ability to troubleshoot problems that require us to inspect the traffic going over the wire. The Developer Tools in modern browsers are making this much easier with each release but sometimes you need to see the network packets and HTTPS makes this tricky.

Tools like Telerik Fiddler and Charles help a lot but sometimes they change a site’s behavior and if HSTS and HPKP are in use on your site then even these tools may be insufficient.


Debugging using bash script

Bash is a widely used command-line interface and scripting language in Unix-based operating systems. As with any software, Bash scripts can contain bugs that lead to errors, unexpected behaviors, or even crashes. Debugging is the process of identifying and resolving these issues, which is essential for maintaining script reliability and performance


Why debug Bash
Debugging Bash scripts is crucial for several reasons:

Identifying and fixing errors: Debugging allows you to identify and fix errors in your Bash scripts. This helps to ensure that your scripts run smoothly and produce the expected results.

Improving performance: Debugging can also help you identify areas of your Bash scripts that may be causing performance issues. By optimizing these areas, you can improve the overall performance of your scripts.

Saving time and effort: Debugging can save you time and effort by helping you quickly identify the root cause of issues in your scripts. This allows you to fix issues faster and move on to other tasks.

Enhancing script reliability: Debugging helps to enhance the reliability of your Bash scripts by ensuring that they handle errors and unexpected situations correctly.

15 Essential Bash Debugging Techniques and Tools

1. Use “set -x” to enable debug mode
The “set -x” command enables debug mode in Bash, which displays each command before it is executed. This can help you identify where errors are occurring in your script. To turn off debug mode, use “set +x”.

Working: Suppose we have a Bash script that is not behaving as expected. We can enable debug mode by adding “set -x” at the beginning of the script:

#!/bin/bash
set -x

# rest of the script

This will display each command before it is executed, which can help us identify where errors are occurring.

Practical example: Suppose we have a Bash script that is not behaving as expected and we want to enable debug mode to help us diagnose the issue. We can use “set -x” to enable debug mode:

#!/bin/bash
set -x

echo "Before the command"
ls -l /fake_folder
echo "After the command"

When we run this script, we will see detailed debugging information in the terminal:

+ echo 'Before the command'
Before the command
+ ls -l /fake_folder
ls: cannot access '/fake_folder': No such file or directory
+ echo 'After the command'
After the command


As we can see, debug mode displays the commands being executed with a “+” sign before each command. This can be extremely helpful for diagnosing issues in Bash scripts, especially when working with complex scripts that execute multiple commands.


2. Use “echo” to print variables and command output
The “echo” command can be used to print the value of variables or the output of commands. This can help you verify that the script is working as expected.


#!/bin/bash

my_var="hello world"
echo $my_var


3. Use “read” to wait for user input
The “read” command can be used to wait for user input. This can be useful for debugging scripts that require user interaction.

#!/bin/bash

echo "Enter your name:"
read name
echo "Hello, $name!"

4. Use “trap” to handle signals
The “trap” command can be used to handle signals, such as Ctrl+C. This can help you ensure that your script exits gracefully in response to unexpected events.

#!/bin/bash

function cleanup {
echo "Cleaning up..."
# cleanup code goes here
exit 1
}

trap cleanup SIGINT

# long-running task goes here


5. Use “set -e” to exit on error

The “set -e” command causes the script to exit immediately if any command fails. This can help you identify errors more quickly.


#!/bin/bash
set -e

# commands go here

6. Use “set -u” to error on undefined variables
The “set -u” command causes the script to exit immediately if an undefined variable is used. This can help you catch typos or other errors that may result in unexpected behavior.


#!/bin/bash
set -u

echo $my_var


7. Use “set -o pipefail” to check for errors in pipelines
The “set -o pipefail” command causes a pipeline to return an error if any of the commands in the pipeline fail. This can help you catch errors in complex pipelines.

#!/bin/bash
set -o pipefail

command1 | command2 | command3


8. Use “set -xv” to enable verbose mode
The “set -xv” command enables verbose mode in Bash, which displays each command and its arguments before it is executed. This can be useful for debugging complex scripts.

#!/bin/bash
set -xv

# complex script goes here


9. Use “declare -p” to print variable types
The “declare -p” command can be used to print the type and value of a variable. This can help you verify that variables are being set and used correctly.

#!/bin/bash

my_var="hello world"
declare -p my_var


10. Use “shopt -s extdebug” to enable extended debug mode
The “shopt -s extdebug” command enables extended debug mode in Bash, which provides additional debugging information. This can be useful for diagnosing complex errors.

#!/bin/bash
shopt -s extdebug

# rest of the script


11. Use “set -o functrace” to trace function calls
The “set -o functrace” command causes Bash to trace function calls, which can help you identify errors in functions.

#!/bin/bash
set -o functrace

my_function() {
echo "Hello from my_function"
}

another_function() {
echo "Hello from another_function"
my_function
}

echo "Before calling another_function"
another_function
echo "After calling another_function"


12. Use “set -o errexit” to exit on errors in functions
The “set -o errexit” command causes Bash to exit immediately if an error occurs in a function. This can help you identify errors more quickly.

#!/bin/bash
set -o errexit

# commands go here


13. Use “set -o nounset” to error on undefined variables in functions
The “set -o nounset” command causes Bash to exit immediately if an undefined variable is used in a function. This can help you catch typos or other errors that may result in unexpected behavior.

#!/bin/bash
set -o nounset

echo $my_var


14. Use “set -o xtrace” to enable tracing
The “set -o xtrace” command enables tracing in Bash, which displays each command before it is executed. This can be useful for diagnosing errors in complex scripts.

#!/bin/bash
set -o xtrace

# rest of the script


15. Use “shellcheck” to debug
bashdb was a good tool to debug bash scripts, but it is no longer maintained. It got pulled from Debian repository and later from Ubuntu repo as well. I suggest using spellcheck as an alternative.

shellcheck is a static analysis tool for shell scripts that can help identify and fix common issues and errors in your scripts.  It can help you write more reliable and maintainable shell scripts by identifying and fixing issues before they cause problems. It can be integrated into your development workflow, such as in your text editor or continuous integration system, to provide real-time feedback and improve the quality of your code.

Fire the following command to install it on your Linux PC.


sudo apt-get install -y shellcheck






