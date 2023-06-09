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
**Running the server**
![Image](lab 2, 1.png)

**Using the link**
![Image](lab 2, 2.png)
* Methods called: *handleRequest*
* Relevant arguments: *url*
* Values of relevant fields:
1. There is a field *messages* whose value is an empty ArrayList made of Strings.
2. There is a field *writing* whose value is a empty string
3. There is field *s* which is an array that holds part of the Query of the URL in idnex 0 and anything after the "=" to be stored as index 1. In this case, index 1 would be "hello"
* The index 1 of *s* which holds the text, in this case it would be "hello", gets *added* to the ArrayList of *message*. 
* Index 0 of *message* gets concatenated in *writing*, the value of *writing* is now "hello" and is then outputted to the site.

![Image](lab 2, 3.png)
* Methods called: *handleRequest*
* Relevant arguments: *url*
* Values of relevant fields:
1. the arraylist *messages* hold only one value which is "hello".
2. There is a field *writing* whose value is a empty string
3. There is field *s* which is an array that holds part of the Query of the URL in idnex 0 and anything after the "=" to be stored as index 1. In this case, index 1 would be "How are you"
* The index 1 of *s* which holds the text, in this case it would be "How are you", gets *added* to the ArrayList of *message*. 
* Index 0 of *message* gets concatenated in *writing*, the value of *writing* is now "hello".
* After the for loop, all the values after index 0 of *messages* gets concatenated each in a new line into *writing*. *wrinting* is now "hello \n How are you" and gets outputted into the site

## Part 2

* Buggy Program: ArrayExamples.java
* Method: reverseInPlace

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```


* Input that does not induce a failure:

```
    @Test 
    public void testReverseInPlace() {
    int[] input1 = { 10 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 10 }, input1);
```

* Failure-inducing input:

```
    int[] input2 = {1,2,3,4};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{4,3,2,1}, input2);
	}
```
* The SYMPTOM:
![Image](lab 2, 4.png)

* Before Code (Bug):

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
* After Code (No Bug):
```
  static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      temp[i] = arr[arr.length - i - 1];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = temp[i];
    }
  }
  ```
The buggy code was unable to reverse the last half of the list correcly becasue the for loop swaps the first half of the list and when trying to swap the second half the value have already been swapped, duplicaing them. The fix code fixes this problem by creating a duplicated list allowing for all the valaue to be reversed succesfully without affecting the original list. After, the values of the duplicated list is them copied over to the orignal list to be returned
## Part 3
Something new I learned was creating and working with my own server in lab 2. I learned that parts of the URL for my server and how to use it to make certian functions/methods wok. I enjoyed figuring our how to do part 1 of this lab using the URLs query. In lab 3, I learning how to use JUnit on vscode was interesting, as well as learning how to properly go about to fixing a bugs in code.
