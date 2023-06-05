# Part 1: Debugging

**Student's Post:**

*What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?*

I am using a Macbook with an IOS operating system. I use the command line of terminal of Visual Studio Code to put in bash commands.


*Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.*

The symptom I'm seeing is that there are a couple errors with the asserts for the test and the "@Test" of every test. There is also an error that says it could not find or load main class TestListExamples.

![Image](Screenshot%202023-06-05%20at%203.30.26%20PM.png)


*Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.*

The failure-indicing input is `bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-lab3`. I'm using `bash` to run the `grade.sh` file to grade a repository I put in, which is the `https://github.com/ucsd-cse15l-f22/list-methods-lab3` part of the input.
Once I open the grade.sh file and save my edits there, that's the only input I put in the terminal.
The working directory is `/Users/alianacalpe/Documents/GitHub/list-examples-grader-1` which includes the files `grade.sh`, `ListExamples.java`, and `TestListExamples.java`.

This is the file I'm running: 

![Image](Screenshot%202023-06-05%20at%203.31.50%20PM.png)

This is the tests I'm running: 

![Image](Screenshot%202023-06-05%20at%203.34.09%20PM.png)

This is the directory and its files: 

![Image](Screenshot%202023-06-05%20at%203.37.37%20PM.png)


**TA's Repsonse:**

I suggest looking at all your variables and make sure there are no spelling mistakes when calling on those variables.


**Terminal Output:**

Output when trying the command after trying TA's suggestions: ![Image](Screenshot%202023-06-05%20at%203.43.22%20PM.png)

The bug is that when trying to call on CPATH in lines 17 and 19, the student put `SPATH` instead of `CPATH`, so the Junit is not actually compiling.
When the terminal tried reading the input and going into grade.sh to compile and run, instead of running the right path, it's taking in a null input, thus, it can't run Junit or look for the class TestListExamples.
In order to fix that, in all lines that have `SPATH`, replaced it with `CPATH.` Check all other lines for any mispelling mistakes with the variables.


## Part 2: Reflection

I learned a lot from the second half of this quarter that I didn't know before, like the vim editor. I did not know that existed at all and it's actually a really cool way of editing, especially with so many shortcuts and commands.
When we had that time during lab where we just studied vim and everything it could do was honestly a very great experience for me just because of everything I learned and all the ways to make editing more efficient. 
I also didn't really understand vim that well in class and was just confused on what we were even doing with it, but after this, now I understand it a lot mroe than I did and know how to use it.
There was an exercise where we had to do a couple steps in the vim editor and time ourselves, and by understanding how vim works, I could really maximize my time and something that used to take me more than 10 minutes to do ended with me only needing to spend 1 minute on it.


