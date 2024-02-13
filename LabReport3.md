# Lab Report 3 - Bugs and Commands 

## Part 1 - Bugs
Chosen buggy code - 

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
<img width="603" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/4c989f87-824b-4602-807b-9f7de18f8782">

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

The bug was resolved by changing the array the data was being sorted to. Before the data from `newArray` was being assorted into `arr` array, however, `newArray` is an empty array and does not have the correct values we want to reverse.  
Hence, the data that is being assorted into `arr` is of the incorrect values.

So we want to sort `arr` data into `NewArray` in reverse order and return the `newArray`. To do this, `arr` is changed to the right side in the for loop and `NewArray` is placed on the left side. By setting up the code like this, we grab the values of `arr` and correctly add the values to the correct order of index in the  `newArray` array. 

## Part 2 - Researching Commands
Find 4 interesting command-line options or alternate ways to use the command you chose: `find` command 

1) `find -name` The `-name` argument finds files or directories under a specified name
2) `find -type`
3) `find -maxdepth`
4) `find -size`

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
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-name` which allows the user to find files and directories with matching names. In this case, I wanted to find files that were `.txt` and started with `1468`. This command is useful to help narrow down file searches with similar names. 

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
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-name`. In this case, I wanted to find files that were `.txt` and started with `chapter`. The following output shows the list of `.txt` tiles found within the `./technical` directory. 

Source: [Linux find command summary with examples](https://www.youtube.com/watch?v=8L1oQT7nBj4) 

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
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-type`. The `-type` option allows the user to find a certain type of file type. In this case, I wanted to find files that were directories as seen by the argument of `d`. This command was useful as it displays all the directories within the directories.
```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -type s
```
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-type`. The `-type` option allows the user to find a certain type of file type. In this case, I wanted to find files that were symbolic links as seen by the argument of `s`. Symbolic links, also refered to as soft links, are a special file type that act like a pointer. It's like a shortcut to a certain file or directory. The output shows that there are no symbolic link types within the `./technical` directory. 

Source: [Linux Crash Course - The find command](https://www.youtube.com/watch?v=skTiK_6DdqU)

3) Two Examples of `find -maxdepth`  
```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -maxdepth 0
./technical
```
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-maxdepth`. The `-maxdepth` option allows the user to limit how many directories deep the search can descend to. The number argument tells the system how many levels deep the user wants to search down. In this case, I wanted to find the files and directories that descended 0 levels deep, `-maxdepth 0`. Hence, the output only showed the directory I tried to find, `./technical`. This is a useful command if a user wants to avoid searching other subdirectories. 

```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -maxdepth 1
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/plos
```
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-maxdepth`. In this case, I wanted to find the files and directories that descended 1 level deep, `-maxdepth 1`. Hence, the output displays the next level of subdirectories within the `./technical` directory.

Source: [Computer Hope Linux Find Command Help and Examples](https://www.computerhope.com/unix/ufind.htm)

4) Two Examples of `find -size`
```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -size +200k
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
```
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-size`. The `-size` option allows the user to find files within a specified amount of data size. The number and letter argument specify how big and what type of data size (bytes, kilobytes, etc.). In this case, I wanted to find files that were greater than 200 kilobytes. The following output is of files that are greater than 200 kilobytes. This is command could be useful for mananging disk space.
```
zyany@ZRIOS MINGW64 ~/OneDrive/Documents/GitHub/docsearch! (main)
$ find ./technical -size -1M
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
* In the working directory of `/OneDrive/Documents/GitHub/docsearch!`. I used the command `find` with the option of `-size`. The `-size` option allows the user to find files within a specified amount of data size. In this case, I wanted to find files that were smaller than 1 megabyte. The following output is of files that are smaller than 1 megabyte.

Source: [Computer Hope Linux Find Command Help and Examples](https://www.computerhope.com/unix/ufind.htm)
