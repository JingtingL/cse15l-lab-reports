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

**1. **
First, I typed in "http://localhost:4000/add-message?s=My name is" and this is what I got

Result from the URL

<img width="634" alt="image" src="https://user-images.githubusercontent.com/89711106/233763775-c4f67813-7e7a-4554-ab18-1f9819a15e18.png">

Here the method called is called handleRequest method from the Handler class, main method from the string server class, handle method from the ServerHttpHandler class, start from the Server class. The relevant argument to the server method is that we take the first argument from the commandline and turn call that our port for the server. Then, we pass in how we want to handle the URL using the handler class. 

There is one field in the Handler class that updates everytime we call [add-message](http://localhost:4000/add-message?s=), which is the string variable/field. Everytime we call add-message, the string will take the "My name is" after the equal sign and adds onto the variable string. Finally, the webpage will output the string field, showing the result above.


**2.**
Then, I typed in "http://localhost:4000/add-message?s=Jingting" and this is what I got

<img width="573" alt="image" src="https://user-images.githubusercontent.com/89711106/233763858-0d2e0488-130a-47f5-8bc0-828030055b09.png">

Again here, the method called is called handleRequest method from the Handler class, main method from the string server class, handle method from the ServerHttpHandler class, start from the Server class. The relevant argument to the server method is that we take the first argument from the commandline and turn call that our port for the server. Then, we pass in how we want to handle the URL using the handler class. 

Then the String type field str in the Handler class that updates everytime we call [add-message](http://localhost:4000/add-message?s=), which is the string variable/field. Everytime we call add-message, the string is currently "My name is \n" and will add "Jingting" after the equal sign onto the variable string. Finally, the webpage will output the string field, showing the result above.

---
## Part 2 
Choose one of the bugs from lab 3.

One bug I experience was in the ArrayExamples class, where the last element of the array did not get reverse.

The reverseInPlace method has a bug, because the first element got change to the third element before the third element can refer to it.
```
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

This is the test that showed an error in the buggy program. This test had an error because when we loop through the test in the first iteration, we had already change the reference of the element at index 0 to be the reference to the the element in index 2. So when the element in index 2 tries to refer back to the original value in the element at index 0, it is no longer there. Instead, it will be refering to the same value as itself.

```
  @Test
  //bug might be it doesn't go all the way to the end of the array
  public void testReverseInPlace1(){
    int[] input1 = {1,2,3};
    int[] exp1 = {3,2,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(exp1,input1);
  }
```

This is a test that showed no error in the buggy program. This test had no error because all the elements in the loop have the same value, thus when changing it's reference, the reference that it gets refer to is the same value as the original, which creates the correct output.
```
    @Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

This is the error that I got.

<img width="623" alt="image" src="https://user-images.githubusercontent.com/89711106/233765343-e3f56edf-6679-4398-99ef-be05af6ca00d.png">

**The bug is the element at the last index can no longer refer back to the original value in the element in index 0.**
So to fix this issue, I simply created a temp variable to store the value in the element at index 0 before the loop runs. Then, inside the loop, I tell the computer that if the loop is iterating through the element at the last index, then assgin it the variable temp, which store the original value in the element at index 0. 

This is the reverseInPlace method after I fix the bug
```
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    if (arr.length != 0) {
      int temp = arr[0];

      for(int i = 0; i < arr.length; i += 1) {
        if(i!=arr.length-1){
          arr[i] = arr[arr.length - i - 1];
        } else {
          arr[i] = temp;
        }
      }
    }
  }
```

## Part 3
What did I learn from lab 2 and 3?
From lab 2, I got more practice on distinguising query and path. I also learned how to create a web server using vscode and commandline. From lab 3, I got more practice on testing my code and finding out what the error was. I learn that it is better to write the test before you write you code (Test Oriented Programming), because it allow your coding experience to be more efficient.






