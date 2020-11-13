# wordOccurrences
Given a string of text, 
- [x] write a program that prints a list of unique words contained in the string 
- [x] along with the number of occurrences of each word in the string. 
- [ ] The list should be sorted in descending order by frequency, 
- [ ] and ascending order alphabetically when multiple words occur with the same frequency. 

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
- start by creating a function called `wordOccurrences` that accepts one parameter `paragraph`
- inside of the function create a variable called `results` and set it to an empty object, this varible will contain the word and frequency pairings

## Input

```
let testStr = "This is a test. That is not a test. Test"

let fullParagraph = "From the moment the first immigrants arrived on these shores, generations of parents have worked hard and sacrificed whatever is necessary so that their children could have the same chances they had; or the chances they never had. Because while we could never ensure that our children would be rich or successful; while we could never be positive that they would do better than their parents, America is about making it possible to give them the chance. To give every child the opportunity to try. Education is still the foundation of this opportunity. And the most basic building block that holds that foundation together is still reading. At the dawn of the 21st century, in a world where knowledge truly is power and literacy is the skill that unlocks the gates of opportunity and success, we all have a responsibility as parents and librarians, educators and citizens, to instill in our children a love of reading so that we can give them the chance to fulfill their dreams."
```

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

## Output


