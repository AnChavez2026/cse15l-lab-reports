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

## Part 2

## Part 3
