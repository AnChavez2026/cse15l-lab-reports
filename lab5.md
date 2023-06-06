# Lab 5
## theoretical EdStem Post by a student

## What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?
Computer: Asus g14, operating system: Windows 11, web browser: Google chrome, terminal/editor: Visual Studio Code

## Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.
When running grade.sh bash with a file that is supposed to pass all the test, all the files are are succefully loaded into the grading area. After this, J Unit is supposed to run and then echo out that all test 
passed. However, my program is unable to run the j unit test and I am met with this error:
![Image](lab 5, 1.png)
![Image](lab 5, 2.png)

## Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.
My current working dirctory is ~/OneDrive/Documents/GitHub/list-examples-grader which has all the files I need that allows me to run grade.sh script. My lab partner has the same program and his is able to run fine, so im think something might be wrong with my laptop. This is the command I wrote in my terminal ``` bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected``` 

# 1. TA Response:
Hi Angel,

Many students are having this same issue with running J unit. I can see from you screenshots the the lib folder is in the grading area so this code should theoreticaly be working. You mentioned that your partner successfully ran the code, what kind of laptop does he have? When trying to compile J unit macbooks and windows laptop need to have different code. For Example, assuming your friend has a macbook line 32 ``` .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ``` should run just fine, however Laptops running window should run ```.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar```. The same goes for line 33, macbooks should be able to run ``` .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar```, but for windows it should be replaces with ```".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar"```. 

