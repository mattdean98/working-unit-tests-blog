## Never say this to your teammates!

> tldr; when a teammate comes to you for help with a problem, be sure not to write it off as a small or minute issue even if it appears to work normally in your environment or machine. There may be factors you are unaware of and leaving the conversation at "it works at my machine" definitely smells like *bad workplace culture* to me.


# Introduction 
So far in my career I have noticed there are four types of responses a developer can make when a fellow teammate comes to them with a problem they are unable to solve on their own:
1. *"Cool, I remember when this occurred to me for the first time. Let me walk you through this so you know too!"*
2. *"Woah - that seems weird. Let's dig into this together and figure it out!"*
2. *"Woah - this seems odd, but I don't have the time right now to help, I can tomorrow though?"*
3. *"I don't know what to tell you, it works on my machine."*

My first situation with #4 was unpleasant. And is exactly why **EVEN IF** it **DOES** work on your machine you should be very careful not to ever leave that as the ending of the conversation.

# The context
Cut to a distant past, I was at a different company and a different team. There was a project that needed some revisions made that I had not started, but knew the tech stack and the business need well enough that I could jump in and make the quick change. Upon pulling down the code I quickly realized things may not seem as easy as I first thought. 

Firstly, the `node_modules` folder had been committed to the code repository. The `node_modules` folder is the managed folder that contains all of your dependencies for a typical Node.js project that uses npm. Needless to say it was a huge folder, thousands of files and folders that took way too long to download due to the sheer quantity of files that could be generated faster with a simple `npm install` command. Things were not looking good.

Secondly, one vital utility function that I needed to run the project was missing from the repository. Upon some research into the project, it looked like the file needed was there but it was a windows shortcut file `filename.lnk` rather than the expected `filename.js`. 

# The dreaded words we never say

After learning of this, I talked to the original author of the project and his response was simply that I *"perhaps didn't clone the code properly"* or *"missed something"* due to the fact that *"it worked on their machine"*. I was able to investigate the `filename.lnk` file and learn the location of the true `filename.js` and brought it to their attention. After some time, the file was eventually brought into the repository properly and things began to get better. 

# Conclusion
Working with others means your experience is vastly different from others - but don't discount someone else's problem or issue simply due to it seeming to work on other machines or environments. You never know... there might be a `.lnk` file somewhere hiding the issue from your system!

> Trying to mask "job security" through obscurity only leads to more problems. Just don't do it. Find better ways to make yourself invaluable.

Have you encountered something like this before? Let me know in the comments!