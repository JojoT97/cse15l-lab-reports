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


