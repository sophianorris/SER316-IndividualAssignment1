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



