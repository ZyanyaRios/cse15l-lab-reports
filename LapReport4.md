# Lab Report 4 - Vim (Week 7)


## Step 4: Log into ieng6

```
[user@sahara ~]$ ssh zrios@ieng6.ucsd.edu
Last login: Tue Jan 30 12:29:43 2024 from tower-us2.prod.edstem.org
Hello zrios, you are currently logged into ieng6-202.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   16:40:01   7  0.86,  0.44,  0.38
ieng6-202   16:40:01   6  0.64,  0.39,  0.34
ieng6-203   16:40:01   5  0.15,  0.28,  0.28

To begin work for one of your courses [ cs15lwi24 ], type its name 
at the command prompt.  (For example, "cs15lwi24", without the quotes).

To see all available software packages, type "prep -l" at the command prompt,
or "prep -h" for more options.
[zrios@ieng6-202]:~:191$ 
```
The first step was to log into my `@ieng6` account, so I first opened up terminal and manually typed in the command `ssh zrios@ieng6.ucsd.edu` and pressed `<enter>`. I automatically enter without a password since I made a SSH key before hand. 
## Step 5: Clone your fork of the repository from your Github account (using the SSH URL)
```
[zrios@ieng6-202]:~:191$ git clone https://github.com/ZyanyaRios/currlabReport7
Cloning into 'currlabReport7'...
remote: Enumerating objects: 61, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 61 (delta 0), reused 1 (delta 0), pack-reused 60
Receiving objects: 100% (61/61), 376.60 KiB | 2.02 MiB/s, done.
Resolving deltas: 100% (23/23), done.
```
After entering my `@ieng6` account, I copied and pasted the clone command given from the lab, `git clone https://github.com/ZyanyaRios/currlabReport7` and then pressed `<enter>`. 

## Step 6: Run the tests, demonstrating that they fail
```
[zrios@ieng6-202]:currlabReport7:201$ bash test.sh
JUnit version 4.13.2
..E
Time: 0.525
There was 1 failure:
1) testMerge2(ListExamplesTests)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at java.lang.System.arraycopy(Native Method)
        at java.util.Arrays.copyOf(Arrays.java:3213)
        at java.util.Arrays.copyOf(Arrays.java:3181)
        at java.util.ArrayList.grow(ArrayList.java:267)
        at java.util.ArrayList.ensureExplicitCapacity(ArrayList.java:241)
        at java.util.ArrayList.ensureCapacityInternal(ArrayList.java:233)
        at java.util.ArrayList.add(ArrayList.java:464)
        at ListExamples.merge(ListExamples.java:42)
        at ListExamplesTests.testMerge2(ListExamplesTests.java:19)

FAILURES!!!
Tests run: 2,  Failures: 1
```
After I cloned, I wanted to check if the tests were failing, so I manually typed in the command `bash test.sh` into the terminal and hit `<enter>`. 
Once I hit the `<enter>` key, the terminal displayed one test failure. 

## Step 7: Edit the code file to fix the failing test
```
[zrios@ieng6-202]:currlabReport7:204$ vim ListExamples.java
```
**Before: 
<img width="714" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/f7ce5973-2be9-47d2-90ce-44a945710b90">
**After: 
<img width="703" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/ca65832d-e793-4078-8e06-631381fa45ef">

To fix the test error, I had to fix a bug in the `ListExamples.java` file. To do so, I had to manually enter the command `vim ListExamples.java` in the terminal to enter and edit the `ListExamples.java` file.
Once I entered file, I had to press the `<down>` key 39 times, press the `<right>` key 11 times, then entered `I` to use Insert mode. I then pressed `<backspace>` once to get rid of the `1`, and then added the number `2`. After that, I used the `<esc>` key to go back to Normal mode.
I saved my changes by entering `:w` then `<enter>`. I repeated that process but instead entered `:q!` to exit the program and then `<enter>`. 

## Step 8: Run the tests, demonstrating that they now succeed
```
[zrios@ieng6-202]:currlabReport7:205$ bash test.sh
JUnit version 4.13.2
..
Time: 0.012

OK (2 tests)
```
To run the test again, I had to manually type in `bash test.sh` and press `<enter>`
All my test now run correctly. 

## Step 9: Commit and push the resulting change to your Github account
```
zyany@ZRIOS MINGW64 ~/OneDrive/Desktop/cse15l/labReport7/currlabReport7 (main)
$ git add .

zyany@ZRIOS MINGW64 ~/OneDrive/Desktop/cse15l/labReport7/currlabReport7 (main)
$ git commit
[main e762178] Commit and push lab7
 1 file changed, 1 insertion(+), 1 deletion(-)
```
<img width="1116" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/e3a4f7fe-eed3-4f19-8b7e-e4117fc7044d">

<img width="753" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/70263d2c-b62a-4286-a0fd-d3a8ad4256ef">
<img width="747" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/93dd7a20-e9f2-43f7-b1bf-c075270f189c">

 To commit and push the changes to my GitHub account, in the terminal I first ran the command `git add .` in which I hit `<enter>` once I type it out . I then proceeded to type in `git commit` and `<enter>`. The finally, I ran the command `git push` to push the files. I was prompted to add a message so I quickly added `Commit and push lab7` and then `<enter>`. After that my code has now been updated on my main. 
