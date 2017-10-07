# Homework 2: Extracting and storing information with Dictionaries, Working with Functions

Due: 	Monday, October 16, 8:00p 

What to hand in:
* hw2-part1.py program (all your code from part 1)
* hw2-part2.py program (all your code from part 2)
* hw2-feedprocessor.py program (all your code from parts 3-6)

## Part 1: Exercises with Dictionaries
The following code should be at the top of your starter file, hw2-part1.py:

```python
dinocount = {'triceratops': 2, 'tyrannosaurus rex': 1, 'dilophosaurus': 2, 'parasaurolophus': 3, 'gallimimus': 12}
```

The dictionary dinocount represents the number of pets in a small dinosaur zoo. Complete the exercises embedded in the code. 
Your output should look like:

```
== 1 ==
12
== 2 ==
3
== 3 ==
4
== 4 ==
Parasaurolophus: 4
== 5 ==
triceratops
tyrannosaurus rex
dilophosaurus
parasaurolophus
gallimimus
velociraptor
== 6 ==
triceratops: 3
tyrannosaurus rex: 1
dilophosaurus: 2
parasaurolophus: 4
gallimimus: 12
velociraptor: 4
== 7 ==
velociraptor: 4
Sorry, no stegosaurus in the zoo.
== 8 ==
velociraptor: 4
tyrannosaurus rex: 1
brachiosaurus: 0
archaeopteryx: 0
gallimimus: 12
=== 9 ===
triceratops,3
tyrannosaurus rex,1
dilophosaurus,2
parasaurolophus,4
gallimimus,12
velociraptor,4
=== 10 ===
```

but please note that the order of dinosaurs may vary; dictionaries have no order.

Your CSV file contents should look like the table below when opened in Excel or another spreadsheet application. Again, order may vary, and your header row won't be bold.

| type | count
| --- | ---
| triceratops	| 3
| tyrannosaurus rex |	1
| dilophosaurus |	2
| parasaurolophus |	4
| gallimimus |	12
| velociraptor |	4

## Part 2: Exercises with Functions
This section will give you some practice with defining and invoking functions. Once complete, your output should look like:
```
=== 1 ===
a word?
nice job?
=== 2 ===
progress?
nicer job??
=== 3 ===
fun
John Frens
```

## Working with the feed
From th next part in the assignment, we will be working with hw2-feedprocessor.py, which we will use to process the feed in hw2feed.txt. You may also want to open the feed to get a sense of it. 

## Part 3: fieldType() function
In hw2feed.txt, note that there are both posts and replies in this feed. There are also posters. These lines each start with `post:`, `reply:`, and `from:` respectively.

You are probably thinking "it would be really helpful if we had a function that I could use to figure out which type of content a line contains." The good news is that now you will write one. Find the part 3 line in `hw2-feedprocessor.py`. We have included some starter code to define a function `fieldType()`. This function should take a line as a parameter and return the field type (either post, comment, or from).

Note that you will get an error if you run this code before you fill in `fieldType()`.

## Part 4: Total number of posts and comments
Find and print the total number posts and comments in the file. Print it as

`Total posts: <number>`
`Total replies: <number>`

## Part 5: Printing posting and commenting users
Your next task is to print who posted each comment or post from the Slack channel. See the file for more details.
The first part of the of part 4 should look like (It’s a long list, so I have clipped it!):  

## Part 6: Counting poster contribution frequency
Your next task in hw2-feedprocessor.py is to count how often each user posts or comments to the group. You will need to use a dictionary to keep a running count of how many times each user posted or commented (a combined count for each) to the group:
*	The starter code begins by creating an empty dictionary, called pc_count. Note that you will need to open the file again, because looping through its lines in Part 5 will have “consumed” those lines. 
*	Once you’ve extracted a user name (the same thing that you printed out in part 4), think of it as a key in the dictionary, whose value is the number of posts encountered by that user so far. If the key is not in the dictionary, set the value to 1. If the key is already in the dictionary, set its value to 1 more than its current value. (In the language of the accumulation pattern, the count is our accumulator variable for that user.) Hint: You have to handle when you have not seen that user before. You can do that with either `.get()` or with if/else statements. This is your choice.
*	Once your program finishes reading through the file, print how many times each user posted or commented. To do this, create a string of the form: `<name>: <X>`, where <name> is the user’s name, and X is the number of times they posted. (See example screenshot for what it should look like.). Print that string.

The output of part 6 should look like the following, though your usernames may be in different order (recall that dictionaries are in arbitrary order!): 

## Part 7: Counting word frequency in posts
For part 7, we will count the word frequency in posts (not replies!) to the Slack channel. For this part:
*	Use `stripWordPunctuation()` to remove punctuation from each word. This function will only work if you pass it a word (i.e., not a line).
*	Convert all text to lower case before counting.

Put your code in hw2-feedprocessor.py. 

Example output below. It has been trimmed and yours may be in a different order.

## Part 8: Counting word frequency in posts or comments
For this part, write a function, `wordFreq()`, that will return the word frequency in either posts or comments as a dictionary
As parameters, it must take a file name and the field type (either post or comment) as a parameter. For example, if I want to get a dictionary of word counts in the posts in hw3feed.txt, I should be able to call:
`wordFreq('hw2feed.txt','post')`

You can use your code from part 7 as a starting point, or if you wrote part 6 using a function, you may simply edit it to meet the requirements for this part.

There are a few lines of code at the end that you can use to test your function. If all goes well, you’ll get:


## P0: Identify an API
Please see a separate assignment on Canvas -> Assignments -> Project (to be introduced in class on Thursday).

## Just For Fun
Remember, you don’t have to do this. Modify your code from the feed processor to:
1. Separately keep track of comments and posts per user. 
2. For an extra challenge, print the users in alphabetical order by name. 
3. Extra extra challenge: print users by post count, from most to least (we’ll be doing this in future homeworks, so even if you don’t do it – spend a few minutes thinking about why it is hard).
