# Lab Report 4 - Vim (Week 7)


## Step 4: Log into ieng6
```
[user@sahara ~]$ ssh zrios@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.238)' can't 
be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1
x99wUQcec.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprin
t])? yes
Warning: Permanently added 'ieng6.ucsd.edu' (RSA) to the list of
 known hosts.<img width="313" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/c893ce8c-2e96-4481-8b01-24fcd49524cd">
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
- I opened up a new terminal, hence I had to manual type in the command 'ssh zrios@ieng6.ucsd.edu' and enter my password to access my '@ieng6' account 
## Step 5: Clone your fork of the repository from your Github account (using the SSH URL)
```
[zrios@ieng6-202]:~:191$ git clone https://github.com/ZyanyaRios/lab7
Cloning into 'lab7'...
remote: Enumerating objects: 61, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 61 (delta 0), reused 1 (delta 0), pack-reused 60
Receiving objects: 100% (61/61), 376.60 KiB | 2.02 MiB/s, done.
Resolving deltas: 100% (23/23), done.
```
- Ran and copied and past clone command given from the lab, 'git clone https://github.com/ZyanyaRios/currlabReport7'
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
- One failure 
## Step 7: Edit the code file to fix the failing test
```
[zrios@ieng6-202]:currlabReport7:204$ vim ListExamples.java
```
![Uploading image.png…]()


- 39 down keys
- 11 right keys
- Pressed I to insert
- Back space to delete
- Replaced 1 with 2
- pressed esc key to get out
- Did :w to save
- did :wq! to exit
## Step 8: Run the tests, demonstrating that they now succeed
'''
[zrios@ieng6-202]:currlabReport7:205$ bash test.sh
JUnit version 4.13.2
..
Time: 0.012

OK (2 tests)
'''
- Manual typed in bash test.sh
- Now all the test pass, time to commit it my github account 
## Step 9: Commit and push the resulting change to your Github account

 
