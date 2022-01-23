# CMPSC100: Computational Expression

## General
* CommonMark https://commonmark.org/help/
* Course Schedule and Video Playlist on Discord

## Week 0

### Adding Repositories, Branches, and Changes
|Command              |Action               |Extra Notes          |
|:--------------------|:--------------------|:--------------------|
|`gradle grade`       |Runs the grader.     |For the whole week |
|`git clone [ssh]`    |Adds a GitHub repository to your Jupyter        |[ssh] can be retrieved by clicking "Code" on GitHub   
|`git clone -b [branch name] [ssh]`  |Adds a GitHub branch to your Jupyter  
|`rm -rf [directory]`   |Deletes a directory     |destructive                     |
|`git status`           |Checks if there are changes in your files since you last committed on GitHub 
|`git add -A`               |Adds files to a queue so they can be committed      |“-A” stands for all files
|`git commit -m "[description]"`            |Takes a permanent snapshot|“-m” stands for message, description should be brief and includes the quotation marks
|`git push`               |sends changes to GitHub                  |After this step, all you need to do is enter your password.|

### Navigating Repositories
|Command              |Action               |Extra Notes          |
|:--------------------|:--------------------|:--------------------|
|`pwd`               |Tells you where you are  |Path to working directory |
|`ls`                |Gives a list of what’s under your current directory |List |
|`cd [location]`           |Moves forward                  |Change directory               |
|`cd ..`             |Moves backward    |Can go back more spaces by typing “..” more than once (ex. Going back thrice is “cd ../../..”
|`cd ~`           |Moves back home    |The tilde represents home |

### Collaboratory Work
|Command              |Action 
|:--------------------|:--------------------|
|`git branch`    |Checks what branch you’re in|    
|`git checkout -b [branch_name]`  |Makes a new branch and switches to it    |   
|`git checkout [branch_name]`  |Switches to a pre-existing branch          |  
|`git add -A` `git commit -m "[description]"`    |Done in succession
|`git push origin [branch_name]`           |Pushes to your specific branch 

In addition to the sequence above, pull requests are also made on GitHub. After pushing, open your branch on GitHub and make a pull request. Assign your teammates as reviewers and merge after approval.

### Variables and Functions
Pseudocode applies to all languages and is very helpful for planning projects. Variables come in different data types, particularly `int` or integer, `float` or real, `str` or string, `char` or character, and `bool` or boolean. To convert data types, just type int([variable]), float([variable]), etc. Functions can be productive or non-productive.
|Operator             |Pseudocode           |Operator             |Pseudocode           |
|:--------------------|:--------------------|:--------------------|:--------------------|
|`=`                  |GETS                 |`!=`                 |NOT EQUAL
|`+`                  |ADDS                 |`+=`                 |ADD GETS
|`-`                  |SUBTRACTS            |`-=`                 |SUBTRACT GETS
|`/`                  |DIVIDES              |`/=`                 |DIVIDE GETS
|`*`                  |MULTIPLIES           |`*=`                 |MULTIPLY GETS
|`input()`            |READS                |`print()`            |DISPLAYS
