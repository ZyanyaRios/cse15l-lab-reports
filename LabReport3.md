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

```
  @Test
  public void testReversedFailure() {
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }
```

b. An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

```
  @Test
  public void testReversed() {
    int[] input1 = {0,0};
    assertArrayEquals(new int[]{0,0}, ArrayExamples.reversed(input1));
  }
```

c. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
<img width="835" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/162982dc-b7b3-4282-953e-0f6de4d00d5d">



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
Two lines were changed. 

The issue was resolved by changing the array the data was being sorted to. Before the data from `newArray` was being assorted into `arr` array, however, `newArray` is an empty array. 
Hence, the data that is being assorted into `arr` would be of the incorrect values.

So we want to sort `arr` data into `NewArray` in reverse order and return the `newArray`. 

## Part 2 - Researching Commands

`find` command 
1) find -name (Explanation of what it does a bit)
2) find
3) find
4) find

* Online, find 4 interesting command-line options or alternate ways to use the command you chose

1) Two Examples of `find -name`

```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -name "1468*.txt"
./technical/biomed/1468-6708-3-1.txt
./technical/biomed/1468-6708-3-10.txt
./technical/biomed/1468-6708-3-3.txt
./technical/biomed/1468-6708-3-4.txt
./technical/biomed/1468-6708-3-7.txt
```

```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -name "chapter*.txt"
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-8.txt
./technical/911report/chapter-9.txt
```

The `-name` argument finds files or directories under a specified name
I found out about this method from the YouTube video [Linux find command summary with examples](https://www.youtube.com/watch?v=8L1oQT7nBj4)

2) Two Examples of `find -type`
```
$ find ./technical -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos

```

```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -type s
```
Trying to find types of `symbolic link` in the `docsearch!/technical/` directory

Source: [Linux Crash Course - The find command](https://www.youtube.com/watch?v=skTiK_6DdqU)

3) Two Examples of `find -user`
Find files made by a certain user slay 
4) Two Examples of `find -size`

