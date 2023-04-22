# Lab Report 2 - Servers and Bugs (Week 3)

There are **three parts** to this lab

---
## Part 1 - Write a web server called StringServer
It should keep track of a single string that gets added to by incoming requests.

The code for StringServer:

### The StringServer just tell the computer how we want to organize the URL given to it to output the expected result.

```
# code block
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

In order for StringServer to run, we need be able to create the server. 
So I used the Server class from last week's lab to create the StringServer.
**This is the code for Server Creation**

<img width="656" alt="image" src="https://user-images.githubusercontent.com/89711106/233763396-cc0d19cf-9297-4771-a79a-fda88653aff8.png">

