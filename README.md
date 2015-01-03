Git-Rebasing-Tutorial
=====================

All this is based on a example you can re-do all this on your own repository

This Tutorial was created to complete a Google Code-In task (GCI):

https://www.google-melange.com/gci/task/view/google/gci2014/5847124067483648

This Tutorial was applied on this repository (created by Aruna Herath):

https://github.com/RoonyH/learn-git

And the story he created for us to have fun and learn 

(Thank you Aruna Herath)

Story:
======
* Forget the first commit (Initial Commit) for now.

* The next commit adds a new file to the repo.

* The third adds another file to the repo. But the commit message has gone wrong. The committer has mistakenly put "bbbad message" when what he actually meant to put was "Added the second file". Such a common mistake; Could have happened to anyone :)

* The forth adds a line to the second.txt file. It contains a typo. But not noticing this the work has been commited. "I am so mad to be here" really should have bee "I am so glad to be here"

* So the fifth commit corrects it.

* Sixth adds another file.


How to solve ?
==============

## A)Cloning:-

1- clone the repo by running (Just add the repo's link beside git clone)

    git clone URL
    git clone https://github.com/RoonyH/learn-git.git

2- change directory to where your repo has been cloned

    cd path/to/cloned/repo
    cd learn-git

(If you also want to know how to fork before cloning then cloning the forksee this: https://help.github.com/articles/fork-a-repo/)

## B)Check the commits:-

1-Install gitk by following this link: http://git-scm.com/downloads

2-now while in your repo's directory run:
  
    gitk

(this is where you will see the commits)

![1](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/1.png)

3- then go back to your command-line and run:

    git log

(you will see the commits again, but this is also done to start rebasing)

![2](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/2.png)

## C)Rebasing:-

Look at either the gitlog or the gitk you will see an ID for commits, see which commit you want to start editing from (like I wanted to start from the begining), and run this:

    git rebase -i ID
    git rebase -i 8d9cbc6a337

(where 8d9cbc6a337 is the ID of the commit I choose and as you see I didn't have to write it all so you can write like ten alphanumeric characters)

### When I ran it I faced something strange:

![3(1)](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/3(1).png)

So I just followed the stated instructions to identify, who I am!! (My computer doesn't know its owner epic xD)

But, after Identifying who I am I ran the same code again, successfully:

![3(2)](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/3(2).png)

As you see the commits are infront of you and are open in a text editor!

(Do you remember the story?yes, you should read it and focus on what happened)

Well, there is an error on the second commits comment it says "bbbad message" while it should be "Added the second file"
(look at the previous picture and look at the commit to understand better)

So, as the instructions (also on the previous picture) say that "reword" will use the commit and edit its message and that is what I want right ?!So, lets change the "pick" beside that commit to "reword":

![4](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/4.png)

Now the you should save and exit, how? Well, it depends on the editor, but, in my case, it was (ctrl+X). It will prompt for yes or no, make sure you choose the correct commit then confirm. After that the editor will show you the commit message and will allow you to edit it: (as we choose reword so we can only edit the message)

![5](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/5.png)

Now, I will edit the message to "Added the second file":

![6](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/6.png)

Then save and exit the editor (as before), the command line should give you that it was successfully rebased and updated:

![7](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/7.png)

Now take a second look at gitlog and gitk to see the changes:

![8%20and%2010](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/8%20and%2010.png)

![9%20and%2011](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/9%20and%2011.png)

### Congrats you have completed your first rebase

## But wait lets take another example okay?!

we will continue with the same story, look up at the top and read it you will find there is another fix I need to do and it is combine the fourth and fifth commit

(look at the last two pictures these are how my gitk and gitlog look now)

I will re-run:

    rebase -i

But this time I don't want it from the first commit, So I will run:

    rebase -i a5761b2d8be3723

(again! I did not write the entire ID)

![12](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/12.png)

See this time the editor has less commits written (as I ran a diffrent -i)

![13](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/13.png)

NOW! If you remember the fifth commit was a fix for the fourth, So I want to combine them right?!And, I don't want to discard of the commit's log message of the fifth, so, I used Squash:

![14](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/14.png)

It will show you the messages of both commits to edit either (if you want, I did not)

![15](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/15.png)

now! another look after another successful rebase at git log and gitk (take a good look at the git log both fifth and fourth commit's log message are there)

![16](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/16.png)

![17](https://github.com/amroto/Git-Rebasing-Tutorial/blob/master/pics/17.png)


Now! you should have the basics of rebasing :D

Summary:
=======
1- clone the repo

2- go to repository's directory

3- check the commit on gitk

4- run: git log

5- run: git rebase -i ID

6- Choose the type of edit

7-edit

7- confirm edit and you are done!




