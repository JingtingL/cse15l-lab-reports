# Lab Report 2 - Servers and Bugs (Week 3)

There are **three parts** to this lab

---
## Part 1 - Write a web server called StringServer
It should keep track of a single string that gets added to by incoming requests.


In order for StringServer to run, we need be able to create the server. 
So I used the Server class from last week's lab to create the StringServer.
**This is the code for Server Creation**

<img width="656" alt="image" src="https://user-images.githubusercontent.com/89711106/233763396-cc0d19cf-9297-4771-a79a-fda88653aff8.png">




### The StringServer just tell the computer how we want to organize the URL given to it to output the expected result.

```
# The code for StringServer
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    String result = "";

    public String handleRequest(URI url) {
        //If is at home page, don't change anything
        if (url.getPath().equals("/")) {
            return String.format(result);
        } else if (url.getPath().equals("/add-message")) {
            String[] parameter = url.getQuery().split("=");
            result += parameter[1] + "\n";
            return String.format(result);
        } else {
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

**This is two examples of using the /add-message**

1. 
First, I typed in "http://localhost:4000/add-message?s=My name is" and this is what I got

Result from the URL
<img width="634" alt="image" src="https://user-images.githubusercontent.com/89711106/233763775-c4f67813-7e7a-4554-ab18-1f9819a15e18.png">

Here the method called is called handleRequest method from the Handler class, main method from the string server class, handle method from the ServerHttpHandler class, start from the Server class. The relevant argument to the server method is that we take the first argument from the commandline and turn call that our port for the server. Then, we pass in how we want to handle the URL using the handler class. 

There is one field in the Handler class that updates everytime we call [add-message](http://localhost:4000/add-message?s=), which is the string variable/field. Everytime we call add-message, the string will take the "My name is" after the equal sign and adds onto the variable string. Finally, the webpage will output the string field, showing the result above.
2. 
Then, I typed in "http://localhost:4000/add-message?s=Jingting" and this is what I got

<img width="573" alt="image" src="https://user-images.githubusercontent.com/89711106/233763858-0d2e0488-130a-47f5-8bc0-828030055b09.png">

Again here, the method called is called handleRequest method from the Handler class, main method from the string server class, handle method from the ServerHttpHandler class, start from the Server class. The relevant argument to the server method is that we take the first argument from the commandline and turn call that our port for the server. Then, we pass in how we want to handle the URL using the handler class. 

Then the String type field str in the Handler class that updates everytime we call [add-message](http://localhost:4000/add-message?s=), which is the string variable/field. Everytime we call add-message, the string is currently "My name is \n" and will add "Jingting" after the equal sign onto the variable string. Finally, the webpage will output the string field, showing the result above.

---
## Part 2 
Choose one of the bugs from lab 3.

One bug I experience was in the ArrayExamples class, where the last element of the array did not get reverse.

'''
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
'''




