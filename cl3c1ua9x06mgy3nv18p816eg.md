## git bisect. What you need to know and why you need to know it!

# The Intro

We had a dilemma today of an issue found in our code that needed to be fixed. After some time hunting I was able to find a distinct "this is good" reference in time and a distinct "this is not good" reference - but had no idea which commit between the two introduced the issue. 

#### I was debating on going one commit at a time, until I learned about `git bisect`.

> git bisect quickly allows you to only focus on verifying if the next checked out commit is good or bad - without worrying about which commit to test next

 # An overview of what `git bisect` does
`git bisect` accepts a "good" commit reference, and a "bad" commit reference and orchestrates a binary search within the limits of the two commits. This quickly allows you (the developer) to only focus on verifying if the next checked out commit is good or bad - without worrying about which commit to test next. At the end it spits out (assuming it works right and you have used it correctly): `COMMIT_ID is the first bad commit`

# How it works - the cheatsheet
1. Initialize the search
`git bisect start`

2. Inform it of the commit instance that works
`git bisect good COMMIT_ID`

3. Inform it of the commit instance that does not work
`git bisect bad COMMIT_ID`

4. It will load up a new commit, test and check if it is a "good" or a "bad" commit, and let it know. 
`git bisect [good/bad]`

5. Repeat step 4 until the following appears:
`COMMIT_ID is the first bad commit` 
(hang on to this commit id)

6. Close the bisect session
`git bisect reset`

7. Investigate the differences in the first bad commit
`git diff COMMIT_ID~ COMMIT_ID`

Voila! You should now be able to quickly find the instance of the issue!