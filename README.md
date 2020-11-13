# wordOccurrences
Given a string of text 
- [x] write a program that prints a list of unique words contained in the string 
- [x] along with the number of occurrences of each word in the string. 
- [x] The list should be sorted in descending order by frequency, 
- [x] and ascending order alphabetically when multiple words occur with the same frequency. 

For example, given the input

`“This is a test. That is not a test. Test”`

the expected output could be

````
test 3 
a 2 
is 2 
not 1 
that 1 
this 1 
````
After you have a working program, you should run it on this input, and send us the result: 

```
“From the moment the first immigrants arrived on these shores, generations of parents have worked hard and 
sacrificed whatever is necessary so that their children could have the same chances they had; or the chances 
they never had. Because while we could never ensure that our children would be rich or successful; while we 
could never be positive that they would do better than their parents, America is about making it possible to
give them the chance. To give every child the opportunity to try. Education is still the foundation of this 
opportunity. And the most basic building block that holds that foundation together is still reading. At the 
dawn of the 21st century, in a world where knowledge truly is power and literacy is the skill that unlocks 
the gates of opportunity and success, we all have a responsibility as parents and librarians, educators and 
citizens, to instill in our children a love of reading so that we can give them the chance to fulfill 
their dreams.” 
```

## Process

- The solution for this problem will be in JavaScript
- Start by creating a function(program) called `wordOccurrences` that accepts one parameter `paragraph`
- Inside of the function create a variable called `results` and set it to an empty object, this variable will contain the word and frequency pairings
    `let results = {}`
- Next, create a variable called `uniqueWords` to hold an array of the individual words from the `paragraph` parameter string
    
    `let uniqueWords = paragraph.toLowerCase().replace(/[^\w\s]/g, "").split(" ").sort()`
  - set this to our `paragraph` parameter
  - chain with `.toLowerCase()` so that duplicate words with different casings will be grouped together and all words will be completly lower cased
  - `.replace(/[^\w\s]/g, "")` so that all punctution will be removed and replaced 
  - `.split(" ")` to seperate each individual word into our array based on the space between words
  - `.sort()` to sort the words by ascending order alphabetically
- Then, use the `forEach()` method on the `uniqueWords` array to add each individual word to the `results` object while keeping a tally of each word
  
  ```
  uniqueWords.forEach(word => {
  if(results[word]) {
    results[word] = results[word] + 1
  } else {
    results[word] = 1
  }
})
```
- if you return the `results` object at this point, it will return an object of the words and thier frequencies sorted alphabetically, but we would like the object to be sorted by frequency FIRST and then we will sort that alphabetically
  

## Solution

```
function wordOccurrences(paragraph) {
let results = {}
let uniqueWords = paragraph.toLowerCase().replace(/[^\w\s]/g, "").split(" ").sort()

uniqueWords.forEach(word => {
  if(results[word]) {
    results[word] = results[word] + 1
  } else {
    results[word] = 1
  }
})

return results
}
```


## Input

```
let fullParagraph = "From the moment the first immigrants arrived on these shores, generations of parents 
have worked hard and sacrificed whatever is necessary so that their children could have the same chances they
had; or the chances they never had. Because while we could never ensure that our children would be rich or 
successful; while we could never be positive that they would do better than their parents, America is about 
making it possible to give them the chance. To give every child the opportunity to try. Education is still the
foundation of this opportunity. And the most basic building block that holds that foundation together is still 
reading. At the dawn of the 21st century, in a world where knowledge truly is power and literacy is the skill 
that unlocks the gates of opportunity and success, we all have a responsibility as parents and librarians, 
educators and citizens, to instill in our children a love of reading so that we can give them the chance to 
fulfill their dreams."
```


## Output

```
{
  the: 13,
  that: 7,
  and: 6,
  is: 6,
  of: 5,
  to: 5,
  we: 4,
  a: 3,
  children: 3,
  could: 3,
  give: 3,
  have: 3,
  never: 3,
  opportunity: 3,
  parents: 3,
  their: 3,
  they: 3,
  be: 2,
  chance: 2,
  chances: 2,
  foundation: 2,
  had: 2,
  in: 2,
  or: 2,
  our: 2,
  reading: 2,
  so: 2,
  still: 2,
  them: 2,
  while: 2,
  would: 2,
  '21st': 1,
  about: 1,
  all: 1,
  america: 1,
  arrived: 1,
  as: 1,
  at: 1,
  basic: 1,
  because: 1,
  better: 1,
  block: 1,
  building: 1,
  can: 1,
  century: 1,
  child: 1,
  citizens: 1,
  dawn: 1,
  do: 1,
  dreams: 1,
  education: 1,
  educators: 1,
  ensure: 1,
  every: 1,
  first: 1,
  from: 1,
  fulfill: 1,
  gates: 1,
  generations: 1,
  hard: 1,
  holds: 1,
  immigrants: 1,
  instill: 1,
  it: 1,
  knowledge: 1,
  librarians: 1,
  literacy: 1,
  love: 1,
  making: 1,
  moment: 1,
  most: 1,
  necessary: 1,
  on: 1,
  positive: 1,
  possible: 1,
  power: 1,
  responsibility: 1,
  rich: 1,
  sacrificed: 1,
  same: 1,
  shores: 1,
  skill: 1,
  success: 1,
  successful: 1,
  than: 1,
  these: 1,
  this: 1,
  together: 1,
  truly: 1,
  try: 1,
  unlocks: 1,
  whatever: 1,
  where: 1,
  worked: 1,
  world: 1
}
```

