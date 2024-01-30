
# Lab Report 2
Zyanya Rios; A17991938; Due: 1/30/24

## Part 1

Code for `ChatServer`

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    List<String> chatHistory = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
             return String.join("\n", chatHistory);
        } else if (url.getPath().equals("/add-message")) {
            String message = url.getQuery().split("&")[0].split("=")[1]; //grab message
            String user = url.getQuery().split("&")[1].split("=")[1]; //grab user
            String chatMessage = user + ": " + message;
            chatHistory.add(chatMessage);
            return String.join("\n", chatHistory);
        } else {
            return "404 Not Found!"; //exit if arguments is null 
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```

**Screenshot 1** <br>
<img width="620" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/bb34b0ab-0460-4abc-8957-831491cc812c">

**1. Which methods in your code are called?** <br>
When the server is intialized the 'main' and 'Server.start'method are called. Once the server is opened up and the user inputs a valid user and message input into the URL bar, the 'handleRequest' method is called.<br>

**2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?** <br>
Relevant arguments used in the 'handleRequest' method includes the arguments inputted after the first '=' to the frist '&', and after the second '='. By saving these arguments, the code saves the created message and the username. <br>

**3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.** <br> 
When the server <br>
   * 'user' value: '"zrios"'
   * 'message' value: '"Hello"'

**Screenshot 2** <br>
<img width="624" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/8fdb0306-0936-405e-b853-b1fbf7fdf451">

**1. Which methods in your code are called?** <br>
The 'handleRequest' method is called due to a change of input in the URL bar. Addtionally, the 'main and 'Server.start' methods won't run because the server has already been intialized. <br>
**2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?** <br>
Relevant arguments used in those methods include the <br>
**3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.** <br> 
When the server <br>
   * 'user' value: '"zrios"'
   * 'message' value: '"Hello"'

## Part 2
**The absolute path to the private key for your SSH key for logging into ieng6 (on your computer, an EdStem workspace, or on the home directory of the lab computer)** 
<img width="1120" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/702c4b32-82b6-4152-aa6b-f0616cce3a44">
* The absolute path to the public key is '/home/linux/ieng6/oce/2l/zrios/.ssh/id_rsa'

**The absolute path to the public key for your SSH key for logging into ieng6 (this is the one you copied to your account on ieng6, so it should be a path on ieng6's file system)**
<img width="1120" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/040668ca-a531-42be-8d6d-679435f8e60b">
* The absolute path to the public key is '/home/linux/ieng6/oce/2l/zrios/.ssh/id_rsa.pub'

**A terminal interaction where you log into your ieng6 account without being asked for a password.** 
<img width="1120" alt="image" src="https://github.com/ZyanyaRios/cse15l-lab-reports/assets/105988785/e50832a0-f306-461c-9f76-b4d7791d72f7">
* Allowed to enter without password because of the absolute path to '/home/linux/ieng6/oce/2l/zrios/.ssh/authorized_keys'

## Part 3
In the past two weeks, I've learned how to operate ssh on my local machine, how to open up servers, and how to use URL Handler. Noteably, I found opening up a server to be the most challeneging. However, after doing this lap report, I find it easier to navigate and understanding the componenets of the URL such as the protocal, domain, port number, path, query string separator, and the query string.


