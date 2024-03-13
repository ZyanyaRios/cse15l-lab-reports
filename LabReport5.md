## Lab Report 5 - Putting it All Together (Week 9)


# Part 1 – Debugging Scenario
1. Original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is

**Student101:** Help! I'm working on my `grade.sh` program and it works for `https://github.com/ucsd-cse15l-f22/list-methods-lab3` and `https://github.com/ucsd-cse15l-f22/list-methods-corrected` and the compiler error one, but it doesn't work for `https://github.com/ucsd-cse15l-f22/list-methods-filename` and `https://github.com/ucsd-cse15l-f22/list-methods-nested` in the sense that they don't compile, however the program continues to grade it and tells me that the program compiles correctly. Any tips for fixing this? Additionally, I'm trying to change the merge method so it works, 
<img width="559" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/8ab36bdb-785b-4142-934a-46bde55aa3f0">
<img width="522" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/255aa099-494a-4973-aa2e-ea1a15b8ae82">
<img width="569" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/5b1bd350-a653-4a62-9522-8fa81bc855ef">


2. A response from a TA asking a leading question or suggesting a command to try

**awesomeTA:** Hi, Student101! So far your code looks good! I would recommend you try out the `exit` command. Think about what an exit failure or success would output. Look at Wednesday's lecture and worksheet for more information on the exit command! Hope this helps.

4. Terminal output showing what information the student got from trying that, and a clear description of what the bug is

**Student101:** Thanks! I took your advice on using the `exit` command to exit my program in situations such as when there is a complimation error or if the file name can't be found! Here in my updated code to help clarify if the file is present, if not it returns a different error message that the file cannot be found! Then I made sure to make the exit code be one to indicate that there was an unsuccessful termination. That way, when I run `echo $?` after running `bash grade.sh` with a file name that can't be found or a file that has a compilation error, I will receive the exit code 1, indicating that my program had an unsuccesful termination. Now my program works!

<img width="558" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/47748790-2f5b-4d9c-b97a-148633527d19">
<img width="556" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/2130485d-9c55-4237-8b13-456567ede312">

<img width="489" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/3dd2a1cc-b356-4ba6-a309-b2ed466b769c">
<img width="530" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/4aa7089e-3ff8-4883-93b7-b0c1eeb49fae">
<img width="572" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/243af87a-d791-418a-a6d8-4e41a1a4a981">

4. Information needed about the setup
<img width="173" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/0f525ff8-cc87-4021-b460-9b32497aa74c">
- This program was ran in the `list-examples-grader` directory.
- Contents of each file before fixing the bug
<br>
  
`grade.sh`
```
CPATH='.;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar'
pwd
cd grading-area
pwd

javac -cp $CPATH *.java 

if [[ $? -ne 0 ]] 
then
    echo "Compilation error!"
fi 

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit-output.txt
echo "Program compiled correctly"

if [[ $( head -n 2 junit-output.txt | tail -n 1  | grep "E" ) != "" ]] 
then
    lastline=$(cat junit-output.txt | tail -n 2 | head -n 1)
    tests=$(echo "$lastline" | awk -F'[, ]' '{print $3}')
    failures=$(echo "$lastline" | awk -F'[, ]' '{print $7}')
    successes=$((tests - failures))
    echo "Test Failed"
    grep ".) test" junit-output.txt
    echo "Your score is $successes / $tests"
else
    lastline=$(cat junit-output.txt | tail -n 2 | head -n 1)
    numTests=$(echo $lastline | grep -o '[0-9]'* | head -1)
    echo "All Tests Passed!!!"
    echo "Your score is $numTests / $numTests"
fi

```

`ListExamples.java`

```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }


}
```
- The full command line (or lines) you ran to trigger the bug: `bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-lab3`
- A description of what to edit to fix the bug: To fix the bug, I had to add in the exit command so the bash would correctly work and terminate the program. 

# Part 2 – Reflection
From the last few labs I learned how to use VIM and jdb which I'm pretty sure I was suppose to use in this lab but my junit doesn't want to cooperate with me at all so now I'm facing the consequences of my actions. Besides that, I've never used jdb or vim before so using it and hearing how it's applied in jobs was interesting! I hope I get to continue to learn more about jbd (and I hope I somehow learn how to make it work) and I will be trying to use it to debug future programming challenges. Thank you!
