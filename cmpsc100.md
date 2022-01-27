# CMPSC100: Computational Expression

## General
* CommonMark https://commonmark.org/help/
* Course Schedule and Video Playlist on Discord
* You should be able to find a table of contents somewhere on the screen

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
|`=`                  |GETS                 |`!=`                 |NOT EQUAL?
|`+`                  |ADDS                 |`+=`                 |ADD GETS
|`-`                  |SUBTRACTS            |`-=`                 |SUBTRACT GETS
|`/`                  |DIVIDES              |`/=`                 |DIVIDE GETS
|`*`                  |MULTIPLIES           |`*=`                 |MULTIPLY GETS
|`input()`            |READS                |`print()`            |DISPLAYS
|`for :`              |FOREACH              |`==` or "double equals"  |EQUAL?

## Week 1

### Lists
* Lists start counting from the number 0.
* The count number is called the **“index”** and can be said to be *n-1*
* Different from dictionaries
* **Commands**
  * **Create**: To make a list, use the snippet: `listName = [“item0”, “item1”, “item2”, “item3”]`
  * **Display list**: `print(listName)` will give you `['item0', 'item1', 'item2', 'item3']`
  * **Display item**: `print(listName[0])` will give you `item0`
  * **Sort**: `listName.sort()` will sort alphabetically
  * **Reverse sort**: `listName.reverse()` will reverse the sort
  * **Add item**: `listName.append("item4")` will add the item to the end of the list `['item0', 'item1', 'item2', 'item3', 'item4']`
  * **Remove item**: `listName.remove("item4")` will edit the list to be `['item0', 'item1', 'item2', 'item3']`
  * **Add item**: `listName.insert(3, "item4")` will add the item to the 3rd spot on the list `['item0', 'item1', 'item2', 'item4', 'item3']`
  * **Secret item**: `listName.pop(3)` will hide the third index (item4); only accepts index numbers, not item name itself

### Loops
#### While loops
* Use conditions and loop over and over until condition isn't true

#### [For loops](https://youtu.be/kJSv7-KBJ9w)
* Good for counting
* For a set size
* Holds the last value after loop is done
  * ex.
  * `for name in listNames:` <br> `print(name)`
  * will print all the list items
  * typing `print(name)` again will print out the last item
* `len(name)` will give the number of items in the list (*n*)
* We can combine the for loop and len function by using the snippet below
  * `letters = 0` <br> `for name in listNames:` <br> `letters += len(name)` <br> `print(letters/len(listName))` <br>
  * will show the average length
* example
```
for i in range(len(list)):
     print(list[i])
```

slicing
```python
#  start  skip
#    |   /
deck[0:5:2]
#      |
#     stop
```

### Control Structures

#### Boolean
* `True` or `False`
* you can use `>`, `<`, `==`, and `!=` to compare values (not to assign)
example
```
result = 7 == 9   # "7 is equal to 9?"
print(result)
```
will result in `false`

#### [If-Else Statements](https://youtu.be/K5QezomnVVs)
* you can compare integers
```
cats = int(input("How many cats?"))
dogs = int(input("How many dogs?"))

if cats > dogs:
   print("luman has fooled us")
elif dogs > cats:
   print("luman has failed us")
else:
   print("it is true that they are both amazing")
```

* you can compare string
```
name = input("Cat name: "

if name == "Ulysses":
   print("best cat!!"
elif name == "not Ulysses":
   print("pretty good but meh")
else:
   print(
```

#### [And-Or](https://youtu.be/xUCWbUZwY_w)
```
if cat_is_here == true and dog_is_here == true:
   print("dan is happy")
else:
   print("i need them all :(")
```

#### [While Loops](https://youtu.be/7p80y8JKvYk)
```
while snake_hp > 0:
   sidekick_name = input("What is sidekick name: ")
   sidekick_type = input("What is sidekick type: ")
   attack_value = ulysses_secret_super_attack(sidekick_type, sidekick_name)
   snake_hp -= attack_value
print("snake defeated")
```
<!-- 27 January 2022 -->
### Strings
<!-- video 1 -->
* a data type that acts as a list (of characters)
* immutable, can't be changed directly
* `print(len(word))` displays the number of letters
* given `word = cat` and using `print(word[1])` will give `a`
* use of loops with string
```
word = "gel"
changed_word = []
for letter in word:
    shift = ord(letter) + 13            # ord stands for ordinal
    changed_word.append(chr(shift))     # chr stands for character
print(changed_word)                     # gives the traditional list, not like string
```
* combining lists to string
```
transformed = "".join(changed_word)     # gives "try"
transformed = " ".join(changed_word)    # gives "t r y"
```
<!-- video 2 -->
* verifying if uppercase or lowercase
```
while True:
    the_crew = input("Enter the names of the crew (separated by ,): ")
    response = input("Enter another set [Y/N]: "
    if response.upper() == "N":             # forces input for response to be uppercase
        break                               # ends if you put "N" or "n"
```
* changing capitalization
```
for name in members:
    name = name.strip()
    if name.lower().startswith("c"):
        print("Oh, that's Claude!")
    else:
        print("That's not Claude!")
```
* methods

| Method | Argument(s) |Effect |
|--------|-------------|-------|
|`.lower()`|None | Converts entire string to lower case |
|`.upper()`|None |Converts entire string to upper case |
|`.count()`|`string` to count instances of|Counts the number of times a given substring appears in a `string`|
|`.endswith()`|`string`/`tuple` of `string`s to look for | Returns `boolean` if string does/n't end with `string` argument |
|`.startswith()`|`string`/`tuple` of `string`s to look for| Returns `boolean` if string does/n't start with `string` argument |
|`.replace()`|`string` to find, `string` to replace it with, `integer` times to replace| Replace searched string with specified replacement `N` times|
|`.split()`|`string` on which to to "split" `string` (default: spaces) |Splits a `string` into parts (a `list`)|
|`.join()`|`list` to "glue" together into a string|Fuses a `string` together from a `list` of `string`s|

In the above table, `join()` behaves a bit differently than the others.
* f-string
* `\n` = new line
* `\t` = tab
* print(f"{line_num}\t{line}") would give
```
1    line
```
