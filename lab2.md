# Lab Report 2

## Part 1

**Code to run Server**
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> messages = new ArrayList<String>();

    public String handleRequest(URI url) {
        String writing = "";
        if (url.getPath().equals("/")) {
            if (messages.size() > 0){
                writing = messages.get(0);
            }
            for(int i = 1; i < messages.size(); i++){
                writing += "\n" + messages.get(i);
            }
            return writing;
        }else if (url.getPath().equals("/add-message")) {
            String[] s = url.getQuery().split("=");
            messages.add(s[1]);
            writing = messages.get(0);
            for(int i = 1; i < messages.size(); i++){
                writing += "\n" + messages.get(i);
            }
            return writing;
        }else {
            System.out.println("Path: " + url.getPath());
            return "404 Not Found!";
        }
       
    }
}

class StringServer {
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
**Running the server
![Image](lab 2, 1.png)

**Using the link
![Image](lab 2, 2.png)
* Methods called: *handleRequest*
* Relevant arguments: *url*
* Values of relevant fields:
1. There is a field *s* whose value is an empty string.
2. There is field *parameters* which is a string of arrays and holds parts of the url after I split it.
* The value of *s* changes to hold the words we enter in which is "Hello" in this case.
* 
![Image](lab 2, 3.png)
* Methods called: *handleRequest*
* Relevant arguments: *url*
* Values of relevant fields:
1. There is a field *s* whose value is an empty string.
2. There is field *parameters* which is a string of arrays and holds parts of the url after I split it.
* The value of *s* changes to hold the words we enter in which is "Hello" and "How are you" in this case.

## Part 2

## Part 3
