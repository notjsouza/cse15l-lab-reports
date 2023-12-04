# Lab Report 5 - Putting it All Together #
---

# Part 1 #
---

## Student Post ##

![Lab5_Error](Lab5_Error_Message.png) 
<br />
<br />

I ran two JUnit tests through my bash script and one of them is causing a "Java heap space" error. I've narrowed down the error to the second test, which is testing the merge function, but I can't figure out what would cause this type of error in my function. Maybe it could have something to do with the way I'm adding the elements to a new ArrayList? I've added screenshots of both the function and the test code if that helps.
<br />
<br />

![Lab5_Code](Lab5_Code.png) 
<br />
<br />

![Lab5_Test](Lab5_Test.png) 
<br />
<br />

## TA Response ##

>An OutOfMemoryError exception occurs when there is insufficient space to add another object to a Java heap, so is there anything in your code that would be infinitely adding values? I can see that you have multiple while loops for adding values to the result list. Maybe try taking another look at the conditions/contents of those while loops to make sure they are performing as intended.

## Student Response ##

![Lab5_Passing](Lab5_Passing.png)

I just noticed the error in the second while loop. In the case where all the elements from list1 are merged with only some of the elements from list2, it's supposed to add the remaining values of list2 by incrementing index2 after each added value. What it was doing was incrementing index1, leading to the same element from list2 being added infinitely. Thank you for the help, all tests are passing now.

---

## Part 2 ##

