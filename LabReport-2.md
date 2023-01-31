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
    String contents = "";
    int count=0;
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return contents;
        }  else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    if (count!=0)
                    {
                        contents+="\n"+parameters[1];
                    }
                    else
                    {
                        contents+=parameters[1];
                        count++;
                    }
                    return contents;
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

![image](https://user-images.githubusercontent.com/122562955/215658266-a834e997-7c44-4443-af69-72037ab1e3c3.png)

**Flow of Code:**

- When starting the server, the `main` method in `StringServer` is called and the port number is passed in as a command line argument, and gets stored in `int port`.
- The main method calls `Server.start(port, new StringHandler())`, this command starts the server, sends the port number as an argument and creates a new `StringHandler`.
- In the `Server.start` method, a `HttpServer` is created using `HttpServer.create` method and the SocketAddress of the port number as an argument.
- The server's request entrypoint is created , and a new `ServerHttpHandler` is passed as an argument.
- `server.start()` is called and the server is started.
- When we enter `/add-message?s=Aarav Vidhawan` in the browser, The `handle` method in `ServerHttpHandler` is called.
- In the `handle` method, the `handleRequest` method from StringHandler is called, with the extracted URI as an argument.
- In the `StringHandler` class, the String `contents` is initially `""`, and `count` is 0.
- When we enter `http://localhost:4000/add-message?s=Aarav Vidhawan` in the browser, the program checks if the path has `/add-message` in it.
- Since it does, an array `parameters` is created with `paramaters[0]="s"` and `parameters[1]="Aarav Vidhawan"`.
- Since this is the first String being added to `contents`, "Aarav Vidhawan" is added to `contents` and `count` is incremented by 1.
- `contents` is returned and displayed on the web page.

**Example 2:** Path: `/add-message?s=University of California San Diego`

The aforementioned path is typed after `localhost:4000` and results in the following web page:

![image](https://user-images.githubusercontent.com/122562955/215658469-526fbe7b-7da7-4d9f-8e0a-8fe372b84cb7.png)

**Flow of Code:**

- Here, the Server has already been started.
-  When we enter `/add-message?s=University of California San Diego` in the browser, The `handle` method in `ServerHttpHandler` is called.
- In the `handle` method, the `handleRequest` method from StringHandler is called, with the extracted URI as an argument.
- In the `StringHandler` class, the String `contents="Aarav Vidhawan` and `count=1`. 
- The program checks if the path has `/add-message` in it.
- Since it does, an array `parameters` is created with `paramaters[0]="s"` and `parameters[1]="University of California San Diego"`.
- Since `count!=0`, a new line - `"\n"` - is added to `comtents` and then "University of California San Diego" is added to it.
- `contents` is returned and displayed on the web page.

***
## Part-2: Program Testing

Part 2 of the lab report involves choosing 1 bug from lab 3, and providing tester methods, symptoms, the bug and the fixed code for it.

I've chosen the bug in the `filter` method of the `ListExamples` class.



***
##Part-3



***
