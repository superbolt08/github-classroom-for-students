# GitHub Classroom Guide for Students

This is a guide for students to setup Git and GitHub for use with GitHub Classroom. 

### Steps for getting setup with GitHub
1. Register for account on GitHub (https://github.com/). We recommend using a username that incorporates your name (rpaulson, robert-paulson, etc) and your UBC email.

2. Install Git. Directions for both Windows & Mac here: http://happygitwithr.com/install-git.html. Windows users should follow Option 1 in 7.2. Mac users can follow Option 1 in 7.3 if comfortable, otherwise follow Option 2

3. Setup options in Git. In you have a Mac, you can go to the terminal if you have a Mac (Applications -> Utilities -> Terminal). If you have a Windows, open Git BASH, which you should have downloaded in step 3. Enter the three lines of code here: http://happygitwithr.com/hello-git.html, changing the first two lines to your own name and email (this should be the email associated with your GitHub account). Note that Windows users should  read section 8.1 in the above link carefully

4. Generate a SSH key so you don’t need to enter your password every time you interact with GitHub. First check to see if you have a SSH key. Go into the shell (again, either through Terminal for Mac, or Git Bash for Windows) and complete on this page http://happygitwithr.com/ssh-keys.html, which is Chapter 10 in Happy Git with R.

5. Follow the instructions here (http://happygitwithr.com/push-pull-github.html) to ensure you can connect to GitHub from your computer.

### Steps for downloading and editing assignments from GitHub Classroom

1.  Have a folder specifically for your class (call it something like classroom-COSC310-Winter-2024-T1). Within this folder, I would recommend a folder titled lectures (this can be pulled from the organization--we will show you how to do this as it will be used to distribute sample code), as well a folder title labs.

    Note you can do this as you normally would with pointing and clicking, but you can also use the shell! This is good practice if you want to use Git outside of the class, as you normally have to use the Shell to interact with Git. Sean Kross has a great guide for using the shell here--http://seankross.com/the-unix-workbench/. However, we'll show you the basic steps you need.

 One thing that the shell does is allow you to navigate through all of your files by typing commands, rather than using your mouse. When you open up the shell, you can type `PWD`. This tells you the directory (folder) that you are in. You can also type `ls`. This lists the directories available to you. For example when I type `PWD`, the result is `/Users/sfazkace`. This tells me that I am in my own directory inside of my computer. When I type `ls`, I see directories such as Applications, Documents, etc... I can also enter into a directory using the `cd` command. If I type `cd Documents`, then I am now inside of the Documents directory. When I type `PWD`, the result is now `/Users/rpaulson/Documents`. I can go back to `/Users/rpaulson` by typing `cd ..`.

 Now I want to make a directory (note I'm using directory and folder interchangeably here). I can use the `mkdir` command. To make a directory called class-directory (it's good practice to not have spaces in your folder names), I can type `mkdir class-directory`. If you type `ls`, you'll now see `class-directory` appear. You can then enter `cd class-directory` to go into the class-directory. Finally, to make the two directories that I talked about, we type `mkdir lectures` and `mkdir labs`. Here is a basic illustration of how my directory structure looks for a class titled COSC 310 taken for Winter 2024 T1:
    
```
Users
│
│
│
└───rpaulson
    │
    │
    │
    └───class-documents
        │
        │
        |
        |---classroom-COSC310-Winter-2024-T1
            |
            |
            |
            |---labs
            |
            |
            |---lectures

```

2.  We will give you a link to an assignment, either through email or the class page. This will happen for each new assignment Then follow the instructions for getting the homework repository set up. You should now have a repository for this homework. Note that after you accept an assignment for the first time, we will send you an invite to join the classroom organization as a member. Please accept this. You will probably get an email with the invitation, but you should also see a link at the top of your main GitHub page.

3. Enter the homework repository on GitHub (this is online--GitHub is different from Git!). Click “Clone or Download”, and make sure it says “Clone with SSH” in bold in the top left of the pop-up box. If not, click on the blue “Use SSH” button on the top right of the pop-up box. Now copy the link in the box to your clipboard.

4.  Depending on the IDE you've chosen, some may offer native GIT support.  I use VS Code, which does have this feature, but actually find it easier to manage Git from the shell. Navigate inside of your `homeworks` directory and then type `git clone repository-link` where `repository link` should be replaced with the link you copied to your clipboard in step 3. You now have the files, and you will have to do all of your committing and pushing via the command line. This is fine, but only if you feel comfortable with it.

    Note that if you received an error in the above steps, you may have to clone with HTTPS instead of SSH. You can do this by again clicking on the "Clone or Download" button in the repository page, then clicking "Use HTTPS" in the top right of the pop-up box. Now copy the link and repeat this step.  Don't just zip and download the repository as it will now allow you to maintain your upstream repo connection. 
    
5.  After you make changes to the homework assignment, commit them. What are commits you ask? Commits are essentially taking a snapshot of your projects. For example, if I make changes to a code so that it prints "Hello world", and then commit them with an informative message, I can look at the history of my commits and view the code that I wrote at that time. If I made some more changes to the function that resulted in an error, I could go back to the commit where the code was originally working. This prevents you from creating several versions of your homework (homework-v1, homework-v2, ...) or from trying to remember what your code originally looked like.


    You can do this through the shell. Navigate to the lab directory. If I am are working on lab-1, when I type `PWD` I will see `/users/rpaulson/class-documents/classroom-COSC310-Winter-2024-T1/labs/lab-1`. Now type `git add -A`, and then `git commit -m "My commit message"`. `git add` is a command that tells git which files you want to record the changes to when you make your commit. For example, if I made changes to `file1` and `file2` since my last commit, I can choose to only commit (take a snapshot of) the changes I made to `file1`. `git add -A` says to add all of the files that have changed since the last commit. If I just want to add `file1`, I would instead type `git add file1`.

    Two things about committing. One, you should commit somewhat frequently. At minimum, if you're doing a homework assignment, you should make a commit each time that you've finished a question. Two, leave informative commit messages. "Added stuff" will not help you if you're looking at your commit history in a year. A message like "Added initial version of hello-world function" will be more useful.

6.  At somepoint you'll want to get the updated version of the assignment back onto GitHub, either so that teachers/TAs can help you with your code, or so that it can be graded. You can do this by using a command called `git push`. If you are ready to push, you can  do this in the shell. Simply navigate inside of your homework directory and then enter `git push`. Easy!  One thing that you can do is @mention your TA when you are done with the assignment, which will notify the TA that you have pushed your code back up to the classroom.  Your TA's will provide feedback to you directly on your assignments in your repo for the assignment. 

### Obtaining and pulling a shared repository

Your classroom may have a repository where everyone in the class has access to it, such as a class materials repository (if you're in my class, we will have this). This repository will probably be updated throughout the class, and it will be useful to constantly have the most updated materials on your local computer. You can do this by first cloning the repository, and then pulling in changes. Here are the steps.

1. Clone the repository via command line. Read through step 1 in the previous section if you want a refresher about navigating with the command line. Remember, Mac users should use Terminal, and Windows users should use Git Bash. Go into your class directory--in step 1, this would be the classroom-COSC310-Winter-2024-T1 directory.

    In GitHub, navigate to the shared directory. Repeat step 3 from above, where we copy the link that we will use to clone this repository. If you get an error using SSH, you should instead use HTTPS. Go back to the command line and type `git clone repo-url` where the `repo-url` is replaced with the URL you just copied. If you type `ls`, the directory should now appear.
    
2. To pull in changes, navigate inside of this shared directory. For example, let's say the repo we just copied is called `class-materials` if you are in the `classroom-COSC310-Winter-2024-T1` directory, and you type ls, you should see a directory called `class-materials`. Now type `cd class-materials`. You should now be inside of this directory. To get the most recent version of this directory, you simply have to type `git pull`. If you get an error about merge conflict, don't freak out! This can happen if you edit locations in files that are also changed by a professor. Professors should be doing their best to ensure this doesn't happen, but if it does, simply contact your professor or TA to get it worked out. Or even better, try to google the error message and try to fix it yourself!

### Resources
* [Happy Git and GitHub for the useR](http://happygitwithr.com/)
* [The Unix Workbench](http://seankross.com/the-unix-workbench/)
* [Interactive learning guide for Git](http://learngitbranching.js.org/)
* [GitHub Guides](https://guides.github.com/)
* [Git setup for Windows (video)](https://youtu.be/F_fPEMnr1OQ)
* [Git setup for Mac (video)](https://www.youtube.com/watch?v=kbmSZwK0k-A&t)
* [How to clone, edit, and push homework assignments with GitHub Classroom (video)](https://youtu.be/pAcMgGbCtQw)
