\# BRANCH STRUCTURE



* main: Stable production branch



* dev: Branch for working on new features. Branches off of main



* feature1: Adds "play again" functionality, added guess guidance, and invalid answer guardrail. Branches off of main.



* feature2: Limits user to 10 attempts and counts down each attempt. Game over message added. Branches from dev



* feature3: Two separate hint feature added after 3 guesses ("You're very close!") and 5 guesses ("Getting warmer!"). Branches off of main.



* hotfix: Fixes bug in main where mystery number can only be 99, not 100. Branches off of main.



\## CHANGES BY BRANCH



MAIN: This is a game where you try to guess a number between 1 and 100. For each attempt, the system tells you if your guess is too high or too low. When you guess the correct number, you're told how many guesses it took to get the correct answer.



DEV: Differs from main due to added "Good Luck!" message in the greeting.



FEATURE1: Asks you if you want to play again after the game concludes. Says, "Thanks for playing" if you answer "n". Tells you to try a higher number if your guess is too low, and to try a lower number if your guess is too high. Tells you if you inputted an invalid number. No good luck message. Option to quit by entering a negative number.



FEATURE2: Lists how many attempts you have remaining (out of 10) and counts down with each guess. "Game over" message when you've used all attempts. Tells you what the correct answer was and thanks you for playing. Good luck message intact (because it's built on dev).



FEATURE3: No good luck message. Added "hint" feature that's triggered after 3 attempts if you're within 10 of the answer. After 5 attempts and within 20, "getting warmer" message triggered.



HOTFIX:  Fixes bug where the correct answer could only be 99, not 100. Now it can be 100. Adds new test file.



\## LEARNING SUMMARY 



\### Differences between merge, rebase, squash, and cherry pick: 

* Merge effectively "ties together" the branches, including their history. The parents of the merge commit are the branch you were on and the one you merge in. The original commits keep their original hashes. 



* Rebase "moves" the current branch onto another branch. Using rebase keeps the history linear, unlike merge. A downside is that using rebase causes you to lose information about which branch the code is coming from. You generally shouldn't use it if you're working with others. New hashes generated. 



* Squash "squashes" commits into one commit. Using this means that you only have to resolve conflicts once per squashed commit instead of once per original commit. You can use it to "declutter" your history. 



* Cherry pick can be used to apply a single commit to one branch without disturbing others. You can use this in urgent situations where you need a quick fix, but you should later merge the change you made with the other branches. New hash is generated for the copy. 



\### Observations In GIT History for feature1 vs. feature2 vs. feature3



* feature1: This was a merge. It added a new merge commit. The hashes didn't change. I had one conflict. All the messages were intact. On the graph, there was a "/|" to represent the branches coming together. 
* feature2: This was a rebase. There was no new merge commit. New hashes were generated. I had one conflict per commit. The messages were kept. On the graph, there was a "|" since the information from the branch was moved onto another one entirely. 
* feature3: This was a squash. It combined all of the commits into one. There was a new hash generated. The messages were replaced by one all-encompassing message. Represented on the graph as a "|" since the commits all became one. 



\### When I Would Use Each Strategy In Real Projects



* I would use a merge in a case where another party needed to be able to track changes, progress, and history. This would likely be the case in any project where I was working on a team. Generally, dev gets merged into main so they are aligned. 



* I would use rebase only when working on a solo endeavor, since you lose the information about which branch the code came from. Additionally, it's helpful because it replays the commits one at a time so you can fix the conflicts in each one separately. 



* I would use squash if I had a lot of commits that may cause clutter or confusion to whoever might need to read through them. It's the best choice if you're looking to tidy things up. You do this before you merge into dev. 



* I would use cherry pick in a situation where I needed to get a change committed right away, like if there was a bug in code that is live, and I knew with certainty that the code I came up with to fix it is ready to be deployed. You would use cherry-pick over something else because it allows you to deploy one change without deploying all the others you're working on. 

