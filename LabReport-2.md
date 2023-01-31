# Lab Report 2
***
## Part-1: StringServer

Part 1 of the lab report involves writing code for a `StringServer` class, that keeps track of the contents of a String and responds with the String every time the URl is visited. Using the path `/add-message?s=<String>` adds a new line (`\n`) and the `<String>` to the String in the class, and displays the String on the web page.

Below is the Code for my `StringServer` class and `StringHandler` class. These class share many similarities with the classes we used in Lab-2, and also use the `Server.java` file we were provided with.

```
import java.io.IOException;
import java.net.URI;


class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}

class StringHandler implements URLHandler {
    String cont = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return cont;
        }  else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    cont+="\n"+parameters[1];
                    return cont;
                }
            }
            return "404 Not Found!";
        }
    }
}
```
**Starting the Server**

![WhatsApp Image 2023-01-30 at 19 15 09](https://user-images.githubusercontent.com/122562955/215654081-247632da-02a2-4519-bc61-2200b7847fb2.jpg)

**Example 1:** Path: `/add-message?s=Aarav Vidhawan`

The aforementioned path is typed after `localhost:4000` and results in the following web page:

![image](https://user-images.githubusercontent.com/122562955/215654582-2c609f15-2963-48d2-88cf-f928d7daf48f.png)

**Methods Called:**

- When starting the server, the `main` method in `StringServer` is called and the port number is passed in as a command line argument.
- The main method calls `Server.start(port, new StringHandler())`, this command starts the server and creates a new `StringHandler`.
- In the `Server.start` method, a `HttpServer` is created using Java provided constructor.
- A new `ServerHttpHandler` is created using the `handler` as a template.
- The `handle` method in `ServerHttpHandler` is called.
- In the `handle` method, the`handleRequest` method from StringHandler is called, with the extracted URI as an argument.
