# 1. Example of using the command with no arguments for cd, ls, and cat

## cd 
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```

* Working directory: lecture1
* The output of cd without an argument resulted in a change of directories. The directory was changed to home after running cd as indicated by the removal of /lecture1 in the second line.
* The output is not an error. 

## ls
```
[user@sahara ~]$ ls
lab1  lecture1
```
* Working directory: home
* The output of ls without an argument is the printing of the file names found in the home directory because ls by itself 
* The output is not an error. 
  
## cat
```
[user@sahara ~]$ cat
hello
hello

```

* Working directory: home
* The output of cat without an argument allow the user to enter an input, in which the console with echo back the input once the user has pressed enter.
* The output is not an error.


# 2. Example of using the commend with a path to a directory as an argument with cd, ls, and cat
## cd Example
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
* Working directory: home
* The output of cd with an argument, `cd lecture1`, is a change of directories from the home to lecture1
* The output is not an error.

## ls
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```

* Working directory: home
* The output of ls with an argument, `ls lecture1`, is the console printing out all the files in the lecture1 directory. 
* The output is not an error.

## cat
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
* Working directory: home
* The output of cat with an argument, 
* The output is not an error.


# 3. Example of using the command with a path to a file as an argument
## cd

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
* Working directory: lecture1
* The output of cat with an argument, 
* The output is an error due to the nature of `cd` only applicable for 

## ls
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```
* Working directory: lecture1
* The output of ls with an argument, 
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
* Working directory: lecture1
* The output of cat with a file argument will result in an output of ... because 
* The output is not an error.
