# 1. Example of using the command with no arguments for cd, ls, and cat

## cd 
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```

* Working Directory: lecture1
* The output of `cd` without an argument results in a change of directories from lecture1 back to home because `cd` with no arguments is a default command that brings the user back to the previous directory. 
* The output is not an error. 

## ls
```
[user@sahara ~]$ ls
lab1  lecture1
```
* Working Directory: home
* The `ls` command without an argument is defaulted to print all visible files and directories within the directory the `ls` command was ran on. Hence the output of `ls` without an argument is the display of other directories and file names located within the current directory. 
* The output is not an error. 
  
## cat
```
[user@sahara ~]$ cat
hello
hello

```

* Working Directory: home
* The output of `cat` without an argument allows the user to enter an input, in which the console will echo back the input once the user has entered their input. The `cat` command without an argument will do this because it is deafaulted to reading from standard input when there is no argument present. 
* The output is not an error.


# 2. Example of using the command with a path to a directory as an argument with cd, ls, and cat
## cd Example
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
* Working Directory: home
* The output of `cd` with a directory as an argument, `lecture1`, results in a change of directories from home to lecture1. The reasoning for this output is the `cd` command with a specified directory name will move the user to the specificed directory.
* The output is not an error.

## ls
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```

* Working Directory: home
* The output of `ls` with a directory as an argument, `lecture1`, results in the console printing out all the files in the lecture1 directory. When the `ls` command has a specificed directory as an argument, it will print all the directories and files visible in the specified directory. 
* The output is not an error.

## cat
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
* Working Directory: home
* The output of `cat` with a directory as an argument, results in the error message of `Is a directory`. The command cannot execute its function to concatenate and print content of files. 
* The output is an error as the command `cat` was designed to print the content of files, not directories. 


# 3. Example of using the command with a path to a file as an argument
## cd
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
* Working Directory: lecture1
* The output of `cd` with a file as an argument results in the error message of `Not a directory`. The command cannot execute its function to change directories.
* The output is an error because the command `cd` can only be used with a directory as an argument, not a file. The `cd` command cannot change directories to a file.  

## ls
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```
* Working Directory: lecture1
* The `ls` command functions with both files and directories as arguments, but the terminal will only print the file name when a file is used as an argument as it's the only element found within the file. Hence the output of `ls` with a file as an argument results in the display of the file that was used as the argument. 
* The output is not an error.
## cat
```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UT
F_8);    
    System.out.println(content);
  }
```
* Working Directory: lecture1
* The output of `cat` with a file as an argument results in the display of the contents of the specified file. This is the main purpose of the `cat` command, to print out the content of files. 
* The output is not an error.
