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

