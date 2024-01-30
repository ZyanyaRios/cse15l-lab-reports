
# Lab Report 2
Zyanya Rios; A17991938; Due: 1/30/24

## Part 1
<img width="620" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/bb34b0ab-0460-4abc-8957-831491cc812c">
^ saying hi as zrios

1. Which methods in your code are called?
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
   * 'user' value: '"zrios"'
   * 'message' value: '"Hello"'

<img width="624" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/8fdb0306-0936-405e-b853-b1fbf7fdf451">
^ maria replying with hooray

1. Which methods in your code are called?
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

## Part 2
*  The absolute path to the private key for your SSH key for logging into ieng6 (on your computer, an EdStem workspace, or on the home directory of the lab computer)
```
[zrios@ieng6-201 ~/.ssh]$ ls ~/.ssh
id_rsa  id_rsa.pub  known_hosts
[zrios@ieng6-201]:.ssh:129$ ls id_rsa
id_rsa
```
* The absolute path to the public key for your SSH key for logging into ieng6 (this is the one you copied to your account on ieng6, so it should be a path on ieng6's file system)
```
[zrios@ieng6-201]:ieng6:125$ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/home/linux/ieng6/oce/2l/zrios/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/linux/ieng6/oce/2l/zrios/.ssh/id_rsa.
Your public key has been saved in /home/linux/ieng6/oce/2l/zrios/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:4fIVaOqxG0KdPGTZMK6LIsWeK+SfHvmgeNIR9RW0wHk zrios@ieng6-201.ucsd.edu
The key's randomart image is:
+---[RSA 2048]----+
|     .+oo.       |
|    ..o*Eo       |
|   . .=o* .      |
| ..  *.= . .     |
|  o.o O S .      |
| +.+.o * .       |
|=.+=o + .        |
|=o+.=. o         |
|.=++ ..          |
+----[SHA256]-----+
[zrios@ieng6-201]:ieng6:126$ cd ~/.ssh
[zrios@ieng6-201]:.ssh:127$ ls
authorized_keys  id_rsa  id_rsa.pub
```  
* A terminal interaction where you log into your ieng6 account without being asked for a password.
  * Completed by running ssh-keygen -t rsa in terminal, enter no passphrase,  
```
[user@sahara ~]$ ssh zrios@ieng6.ucsd.edu
Last login: Sun Jan 28 15:08:57 2024 from tower-us10.prod.edstem.org
quota: Cannot resolve mountpoint path /home/linux/ieng6/cs120wi24/public/.snapshot/daily.2023-12-28_0010: Stale file handle
Hello zrios, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   15:10:01   42  1.77,  1.42,  1.39
ieng6-202   15:10:01   33  1.83,  0.96,  0.93
ieng6-203   15:10:01   26  2.36,  2.63,  2.90

 

To begin work for one of your courses [ cs15lwi24 ], type its name 
at the command prompt.  (For example, "cs15lwi24", without the quotes).

To see all available software packages, type "prep -l" at the command prompt,
or "prep -h" for more options.
[zrios@ieng6-203]:~:99$ ls
perl5
[zrios@ieng6-203]:~:100$ cd ~/.ssh
[zrios@ieng6-203]:.ssh:101$ ls
authorized_keys
```
- I'm not really sure what they want me to show 

## Part 3
In the past two weeks, I've learned how to operate ssh on my local machine, how to open up servers, and how to use URL Handler. Noteably, I found opening up a server to be the most challeneging. However, after doing this lap report, I find it easier to navigate and understanding the componenets of the URL such as the protocal, domain, port number, path, query string separator, and the query string.


