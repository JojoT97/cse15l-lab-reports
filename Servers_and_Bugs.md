# StringServer

## code for StringServer.java:
```Java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String message = "";
    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message"))
        {
            message += url.getQuery().substring(2) + "\n";
        }
        return message;
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
## StringServer screenshots
![Image](https://user-images.githubusercontent.com/130265120/233828404-b9c10beb-0433-4518-a9f6-77443fe2575b.png)
![Image](https://user-images.githubusercontent.com/130265120/233828440-eda1f5d5-a6a1-40ee-b1a4-6f85b3d51cd0.png)
## For each of the two screenshots
### The methods in my code that get called includes:
- the static start method from the Server class
- the handleRequest method from the Handler class
### Relevant method arguments and class fields:
- the start method takes in a port number and Handler object 
that it needs when creating the server.
- the message field in the Handler class is a String.
It is responsible for storing the complete message being displayed
on the page.
### In the first screenshot:
The url typed in the searchbar above is used as a URI argument for the Handler classes handleRequest
method. The handleRequest method first checks if the path of the uri (aka url) is equal to "/add-message". If so, The message field from the Handler class changes its value to include a parsed string from after the first 2 characters of the url's query. In the case of this screenshot, the message field of the handler class becomes "Apple(\n)" which is the input from the query, aswell as a hidden new line at the end.
### In the second screenshot:
The message field from the Handler class changes its value to
"Apple(\n)Pear(\n)" where (\n) is not text, rather a new line on the page. Unlike the first screenshot, the text displayed on the page is not exactly the same as the input (Pear) from the query. This is because the input each time gets appended to the message field, and then the message string is what gets displayed on the page. In the beginning the message field was an empty string. Like before the message displayed on the page has a hidden next line at the end of the text in preperation for any future inputs.

# Bug Handling

## Failure inducing input
```java
    @Test 
    public void testReverseInPlaceFail() {
        int[] input1 = {1,2,3};
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 3,2,1 }, input1);
    }
```

## Non failure inducing input 
```java
    @Test 
    public void testReverseInPlacePass() {
        int[] input1 = {1,2,1};
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 1,2,1 }, input1);
    }
```

## Bug symptoms
![Image](https://user-images.githubusercontent.com/130265120/233874030-4cac6568-4190-475e-82e8-026bdd6f4729.png)

## Code before bug fix:
```java
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
    }
```

## Code after bug fix:
```java
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length/2; i += 1) {
            int replacement = arr[i];
            arr[i] = arr[arr.length - i - 1];
            arr[arr.length - i - 1] = replacement;
        }
    }
```
A symptom of the bug in the initial code is producing an output that seems to mirror the back half of the array in the front half of the array, rather then reverse the array. Just from looking at the code i could tell it would not behave correctly. Though i did suspect it would appear to work if the first half and second half of the array were mirrors of each other. I made a test that contained mirrored elements {1,2,1} expecting it to pass, and a test with values increasing from least to greatest {1,2,3} expecting it to fail. The first array test {1,2,1} passed with expected output and actual output both being {1,2,1} which is also the same as the unreversed version of the array. The second test {1,2,3} failed, the expected output was {3,2,1} and was instead {3,2,3}. This is because the initial code simply replaces the code from the front of the array with its corresponding element from the back. As the index of the loop moves past the half way mark of the array, it starts replacing the back elements with the elements from the front that were already replaced with the back elements. Thus by the time the loop reaches the back half of the array, the back element values are simple replaced with the same value it had intitially

In the improved code, what i did to fix the bug is swap the frontside element with its backside counterpart, rather than simply replacing the frontside element with the backside element. Also, the new code does not iterate more times than half the array length. This is to prevent elements from being swaped back to its original position. 

## Knowledge gained from week 3
During week 3, i learned how to create a webserver using java.
Specifically i learned how to use input from the url to display messages on a webpage.
Before i did not know that you can make a webserver as well as program their behavior using java.
I previously thought it would be impossible or atleast very difficult to do so without using a scripting language like javascript along side
with html. 
