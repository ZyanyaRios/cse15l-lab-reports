# Lab Report 3 - Bugs and Commands 

## Part 1 - Bugs

Choosen buggy code - 

```
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

a. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

b. An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

c. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

d. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

Before - 
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

After - 
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1]; //changed line
    }
    return newArray; //changed line
  }
```

## Part 2 - Researching Commands

`find` command 
* Online, find 4 interesting command-line options or alternate ways to use the command you chose

For example, we saw the -name option for find in class. For each of those options, give 2 examples of 
using it on files and directories from ./technical. Show each example as a code block that shows the 
command and its output, and write a sentence or two about what it’s doing and why it’s useful.
