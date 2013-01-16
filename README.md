gitDojo
=======

Train your git fu. Learn how to defend against the strongest of confusing error messages.
***

# Phase 1 - Bootcamp

## I'm the magic man. Now you see me.. now you dont.
Sometimes you make a change, but then that change breaks your heart.. or your code.

Now you want to get rid of that change and pretend that it never existed. 

Learning how to revert changes an essential weapon in your git arsenal.

### Start here

Run ./start.sh

It will change some files, then your training can begin.

### What changed?

If you run the command: git status
You'll see what files have changed.

But, what changed?

If you run the command: git difftool
You'll see what changed in the files.

### Revert one file

Let's revert the changes made to the file named one.
It's completely false anyway.

git checkout -- one

The -- means that the git checkout command wont treat 'one' as a branch pointer.

Run git status again. See that the file has not changed.

### Revert to the latest commit on your current branch

You want to revert everything. _Everything_. Nothing good came from the changes.

git reset --hard HEAD

Run git status again. See that there are no changes.

## Lets make a change

Run these commands:
touch three
echo "this is the third file" >> three
mkdir four
touch four/fourPointOne

The astute grasshopper may notice that there is now an untracked file. (git status for proof)

Lets try to revert that file. What is your weapon of choice?

Are you thinking about trying the same reset command? You have chosen wrong!

git clean is the command you are looking for.

What files will git clean remove? git clean -n

Lets remove those files: git clean -f

Why is the four directory still there? 
Because '-f' only removes files!
Lets remove the directory now: git clean -fd

### Revert to the latest commit of another branch

Lets bump your current branch back one commit so we can setup the next tutorial.

git reset --hard HEAD^

or 

git reset --hard HEAD~1

Excellent. Now that we've navigated back one, notice that the file, "ostrich" is missing.

Lets revert all of the changes we've been making locally and reset our branch to the version that we first started with.

git reset --hard origin/phase1

### Burry (stash) your treasure

Lets make a change.
touch five
echo "five five five" >> five
echo "one one one" >> one

Lets say.. we dont really like our changes. But.. we spent a lot of time on them, and are likely pretty attached to them. We want to start over.. but we dont want to lose the changes.

git stash

Now.. lets say that we've been working a while. Look at our files with dissatisfaction. The changes we made before were way better than anything we've come up with thusfar.

git stash pop

Now, our changes are back!

