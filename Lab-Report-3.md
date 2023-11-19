# Part 1 #
---

## ReverseInPlace Bug ##

>**Code for the reverseInPlace() function as reference**
>```
>// Changes the input array to be in reversed order
>  static void reverseInPlace(int[] arr) {
>    for(int i = 0; i < arr.length; i += 1) {
>      arr[i] = arr[arr.length - i - 1];
>    }
>  }
>```

<br />

1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown) <br />

```
@Test 
public void testReverseInPlace() {
  int[] input1 = { 3, 2, 1 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 1, 2, 3 }, input1);
}
```
>_**This is a failure-inducing input due to an error in both the limit of the for loop and the swapping procedure of the function.**_

<br />

2. An input that does not induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown) <br />

```
@Test 
public void testReverseInPlace() {
  int[] input1 = { 1 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 1 }, input1);
}
```
>_**This input does not induce a failure because no swapping is required. The function runs only once and replaces 1 with itself.**_ <br />
>_**For this input, arr[0]=arr[arr.length-i-1] is the same as saying arr[0]=arr[1-0-1], which is arr[0]=arr[0].**_

<br />
3. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

![JUnit test output](Lab3_P1_S3.png)
<br />

>_As expected, the first case fails where the input array is {1, 2, 3},_ <br />
>_while the second case passes where the input array is { 1 }_ <br />

<br />
4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown) <br />
<br />

>_In this case, there are two bugs. The first one is an issue with the for loop, which is looping through the entire array when it should only loop through the first half. The second bug is with the way the values are being swapped. As it is, the values are being overridden rather than swapped._
<br />

>_To fix both of these, we can make two changes. The first change is in the declaration of the for loop, where we change arr.length to arr.length/2 to loop through the first half instead of all of it. The second change is adding a temporary variable so we don't lose any values. We would change_

```
arr[i] = arr[arr.length - i - 1];
``` 

>_to_ 

```
int temp = arr[i];
arr[i] = arr[arr.length - i - 1];
arr[arr.length - i - 1] = temp;
```

<br />

>_This fix addresses the issue because when we loop through the array, we swap the first half of elements with the last half while not losing any values._

---

# Part 2 #

---

**Find command**
<br />

1. `$ find ./technical -name 'filename'` <br />
_This command searches for a file with a name matching 'filename' within the directory and then returns the path._ [GeeksForGeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/#)
>```
>[user@sahara ~/docsearch]$ find ./technical -name chapter-1.txt
>./technical/911report/chapter-1.txt
>
>[user@sahara ~/docsearch]$ find ./technical -name 1472-6963-3-6.txt
>./technical/biomed/1472-6963-3-6.txt
>```

2. `$ find ./technical -name '*file*'` <br />
_This command operates similarly to the last one, only instead of looking for an exact match within the ./technical directory, it looks for any file name containing 'file' and returns the path(s)._ [GeeksForGeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/#)
>```
>[user@sahara ~/docsearch]$ find ./technical -name chapter*
>./technical/911report/chapter-6.txt
>./technical/911report/chapter-11.txt
>./technical/911report/chapter-3.txt
>./technical/911report/chapter-13.5.txt
>./technical/911report/chapter-1.txt
>./technical/911report/chapter-10.txt
>./technical/911report/chapter-13.1.txt
>./technical/911report/chapter-9.txt
>./technical/911report/chapter-7.txt
>./technical/911report/chapter-13.4.txt
>./technical/911report/chapter-5.txt
>./technical/911report/chapter-13.2.txt
>./technical/911report/chapter-13.3.txt
>./technical/911report/chapter-2.txt
>./technical/911report/chapter-12.txt
>./technical/911report/chapter-8.txt
>
>[user@sahara ~/docsearch]$ find ./technical -name 1472*
>./technical/biomed/1472-6785-2-7.txt
>./technical/biomed/1472-6920-2-1.txt
>./technical/biomed/1472-6793-1-12.txt
>./technical/biomed/1472-6947-2-7.txt
>./technical/biomed/1472-6882-1-10.txt
>./technical/biomed/1472-6823-2-2.txt
>./technical/biomed/1472-6750-2-21.txt
>./technical/biomed/1472-6904-3-1.txt
>./technical/biomed/1472-6963-3-7.txt
>./technical/biomed/1472-6793-2-1.txt
>./technical/biomed/1472-6750-1-13.txt
>./technical/biomed/1472-6831-3-1.txt
>./technical/biomed/1472-6920-2-3.txt
>./technical/biomed/1472-6874-3-2.txt
>./technical/biomed/1472-6793-1-6.txt
>./technical/biomed/1472-6785-1-3.txt
>./technical/biomed/1472-6793-1-8.txt
>./technical/biomed/1472-6793-2-16.txt
>./technical/biomed/1472-6831-2-2.txt
>./technical/biomed/1472-6750-1-12.txt
>./technical/biomed/1472-6750-2-14.txt
>./technical/biomed/1472-6750-2-2.txt
>./technical/biomed/1472-6807-2-1.txt
>./technical/biomed/1472-6793-2-4.txt
>./technical/biomed/1472-6793-2-19.txt
>./technical/biomed/1472-6807-2-4.txt
>./technical/biomed/1472-6963-3-14.txt
>./technical/biomed/1472-6793-1-2.txt
>./technical/biomed/1472-6793-2-8.txt
>./technical/biomed/1472-6750-3-11.txt
>./technical/biomed/1472-6882-1-7.txt
>./technical/biomed/1472-6904-1-2.txt
>./technical/biomed/1472-6882-1-11.txt
>./technical/biomed/1472-6769-1-4.txt
>./technical/biomed/1472-6750-3-4.txt
>./technical/biomed/1472-6882-1-12.txt
>./technical/biomed/1472-6963-3-1.txt
>./technical/biomed/1472-6750-2-10.txt
>./technical/biomed/1472-6793-2-5.txt
>./technical/biomed/1472-6963-3-13.txt
>./technical/biomed/1472-6785-1-5.txt
>./technical/biomed/1472-6955-2-1.txt
>./technical/biomed/1472-6882-3-3.txt
>./technical/biomed/1472-6807-2-5.txt
>./technical/biomed/1472-6793-3-6.txt
>./technical/biomed/1472-6963-3-11.txt
>./technical/biomed/1472-6750-1-8.txt
>./technical/biomed/1472-6874-2-1.txt
>./technical/biomed/1472-6904-2-4.txt
>./technical/biomed/1472-6769-1-1.txt
>./technical/biomed/1472-6963-3-6.txt
>./technical/biomed/1472-6793-3-3.txt
>./technical/biomed/1472-6823-3-1.txt
>./technical/biomed/1472-6890-2-5.txt
>./technical/biomed/1472-6793-2-17.txt
>./technical/biomed/1472-6807-2-2.txt
>./technical/biomed/1472-6947-1-2.txt
>./technical/biomed/1472-6750-1-6.txt
>./technical/biomed/1472-6793-2-2.txt
>./technical/biomed/1472-6815-2-3.txt
>./technical/biomed/1472-6963-1-11.txt
>./technical/biomed/1472-6890-1-4.txt
>./technical/biomed/1472-6769-1-2.txt
>./technical/biomed/1472-6874-2-8.txt
>./technical/biomed/1472-6785-2-6.txt
>./technical/biomed/1472-6947-3-5.txt
>./technical/biomed/1472-6947-1-6.txt
>./technical/biomed/1472-6793-3-5.txt
>./technical/biomed/1472-6890-3-2.txt
>./technical/biomed/1472-6947-1-5.txt
>./technical/biomed/1472-6904-2-5.txt
>./technical/biomed/1472-6807-1-1.txt
>./technical/biomed/1472-6947-2-4.txt
>./technical/biomed/1472-6793-2-18.txt
>./technical/biomed/1472-6882-3-1.txt
>./technical/biomed/1472-6793-1-15.txt
>./technical/biomed/1472-6807-2-3.txt
>./technical/biomed/1472-6750-1-11.txt
>./technical/biomed/1472-6963-2-10.txt
>./technical/biomed/1472-6920-1-3.txt
>./technical/biomed/1472-684X-1-5.txt
>./technical/biomed/1472-6963-1-8.txt
>./technical/biomed/1472-6793-1-11.txt
>./technical/biomed/1472-6807-3-1.txt
>./technical/biomed/1472-6947-3-8.txt
>./technical/biomed/1472-684X-2-1.txt
>./technical/biomed/1472-6793-3-4.txt
>./technical/biomed/1472-6882-2-5.txt
>./technical/biomed/1472-6750-2-13.txt
>./technical/biomed/1472-6904-2-7.txt
>./technical/biomed/1472-6769-1-3.txt
>./technical/biomed/1472-6874-2-13.txt
>./technical/biomed/1472-684X-2-2.txt
>./technical/biomed/1472-6882-2-10.txt
>./technical/biomed/1472-6963-3-12.txt
>./technical/biomed/1472-6750-3-6.txt
>./technical/biomed/1472-6807-2-9.txt
>./technical/biomed/1472-6807-3-2.txt
>./technical/biomed/1472-6793-2-11.txt
>```

3. `$ find ./technical -name 'filename' -exec rm -i {} \;` <br />
_This command searches for a file with a name matching 'filename' within ./technical then prompts the user to delete it with a (y/n) input._ [GeeksForGeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/#)
>```
>[user@sahara ~/docsearch]$ find ./technical -name chapter-1.txt -exec rm -i {} \;
>rm: remove regular file './technical/911report/chapter-1.txt'? n
>
>[user@sahara ~/docsearch]$ find ./technical -name 1468-6708-3-1.txt -exec rm -i {} \;
>rm: remove regular file './technical/biomed/1468-6708-3-1.txt'? n
>```

4. `$ find ./technical -maxdepth 'n'` <br />
_This command returns all files/directories within the ./technical directory with a maxdepth (number of subdirectories) equal to 'n'._ [RedHat](https://www.redhat.com/sysadmin/linux-find-command)
_(Simplified the second example with `-name *a*.txt` to somewhat limit the size of the output, limited to all filenames containing an 'a')_
>```
>[user@sahara ~/docsearch]$ find ./technical -maxdepth 1
>./technical
>./technical/biomed
>./technical/911report
>
>[user@sahara ~/docsearch]$ find ./technical -maxdepth 2 -name *a*.txt
>./technical/biomed/ar624.txt
>./technical/biomed/ar619.txt
>./technical/biomed/ar118.txt
>./technical/biomed/ar309.txt
>./technical/biomed/ar93.txt
>./technical/biomed/ar778.txt
>./technical/biomed/ar615.txt
>./technical/biomed/ar408.txt
>./technical/biomed/ar612.txt
>./technical/biomed/ar104.txt
>./technical/biomed/ar792.txt
>./technical/biomed/ar774.txt
>./technical/biomed/ar331.txt
>./technical/biomed/ar130.txt
>./technical/biomed/ar297.txt
>./technical/biomed/ar383.txt
>./technical/biomed/ar319.txt
>./technical/biomed/ar430.txt
>./technical/biomed/ar140.txt
>./technical/biomed/ar79.txt
>./technical/biomed/ar799.txt
>./technical/biomed/ar68.txt
>./technical/biomed/ar601.txt
>./technical/biomed/ar407.txt
>./technical/biomed/ar387.txt
>./technical/biomed/ar321.txt
>./technical/biomed/ar328.txt
>./technical/biomed/ar422.txt
>./technical/biomed/ar429.txt
>./technical/biomed/ar120.txt
>./technical/biomed/ar750.txt
>./technical/biomed/ar149.txt
>./technical/biomed/ar409.txt
>./technical/biomed/ar795.txt
>./technical/biomed/ar745.txt
>./technical/911report/preface.txt
>./technical/911report/chapter-13.5.txt
>./technical/911report/chapter-13.2.txt
>./technical/911report/chapter-13.4.txt
>./technical/911report/chapter-6.txt
>./technical/911report/chapter-8.txt
>./technical/911report/chapter-13.1.txt
>./technical/911report/chapter-13.3.txt
>./technical/911report/chapter-2.txt
>./technical/911report/chapter-3.txt
>./technical/911report/chapter-9.txt
>./technical/911report/chapter-12.txt
>./technical/911report/chapter-7.txt
>./technical/911report/chapter-11.txt
>./technical/911report/chapter-5.txt
>./technical/911report/chapter-1.txt
>./technical/911report/chapter-10.txt
>```
