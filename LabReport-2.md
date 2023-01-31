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
-  When we enter `http://localhost:4000/add-message?s=Aarav Vidhawan` in the browser, The `handle` method in `ServerHttpHandler` is called.
- In the `handle` method, the `handleRequest` method from StringHandler is called, with the extracted URI as an argument.
- In the `StringHandler` class, the String `contents` is initially `""`, and `count` is 0.
- The program checks if the path has `/add-message` in it.
- Since it does, an array `parameters` is created with `paramaters[0]="s"` and `parameters[1]="Aarav Vidhawan"`.
- Since this is the first String being added to `contents`, "Aarav Vidhawan" is added to `contents` and `count` is incremented by 1.
- `contents` is returned and displayed on the web page.

***

**Example 2:** Path: `/add-message?s=University of California San Diego`

The aforementioned path is typed after `localhost:4000` and results in the following web page:

![image](https://user-images.githubusercontent.com/122562955/215658469-526fbe7b-7da7-4d9f-8e0a-8fe372b84cb7.png)

**Flow of Code:**

- Here, the Server has already been started.
-  When we enter `localhost:4000/add-message?s=University of California San Diego` in the browser, The `handle` method in `ServerHttpHandler` is called.
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

**Failure Inducing Input:**

```
    @Test
    public void testFilter1()
    {
        List<String> dummy=new ArrayList<String>();
        dummy.add("Aarav");  
        dummy.add("Utkarsh");  
        dummy.add("agastya");       
        dummy.add("Saksham");  
        dummy.add("Madhav");  

        StringChecker sc=new StringChecker() {
            public boolean checkString(String st)
            {
                if(st.startsWith("a") || st.startsWith("A"))
                    return true;
                return false;
            }

        };
        List<String> expected =new ArrayList<String>();
        expected.add("Aarav");
        expected.add("agastya");
        List<String> filtered=ListExamples.filter(dummy,sc);
        assertEquals(expected, filtered);
    }
```
This test asks the program to filter for words that start with 'a' or 'A'.

**Input that doesn't Induce Failure:**

```
    @Test
    public void testFilter2()
    {
        List<String> dummy=new ArrayList<String>();
        dummy.add("Bansal");  
        dummy.add("Utkarsh");  
        dummy.add("agastya");       
        dummy.add("Bansal");  
        dummy.add("Madhav");  

        StringChecker sc=new StringChecker() {
            public boolean checkString(String st)
            {
                if(st.startsWith("b") || st.startsWith("B"))
                    return true;
                return false;
            }

        };
        List<String> expected=new ArrayList<String>();
        expected.add("Bansal");
        expected.add("Bansal");
        List<String> filtered=ListExamples.filter(dummy,sc);
        assertEquals(expected,filtered);
    }
```
This test asks the program to filter for words that start with 'b' or 'B'.

**Symptom:**

![WhatsApp Image 2023-01-30 at 21 44 30](https://user-images.githubusercontent.com/122562955/215676149-caac1e44-2258-443d-9674-6aaab688b567.jpg)

Here we can see that `testFilter2` passes, but `testFilter1` does not. You can also see that the actual list returned is actually in reverse order of the expected list.

**Bug:**

```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }
```

In the 5th line of the code block above, we can see that when a String satisfies the if condition, it is added at the 0th index of the List instead of being appended at the end of the List. This is why we get a reversed answer for `testFilter1`.

`testFilter2` still passed because both the Strings that satisfy the if condition are the same.

The bug can be easily fixed by altering the code to append the filtered Strings at the end of the List, the fixed code can be seen below.

```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
```
Terminal Output upon running JUnit again after altering the code to tackle the bug:

![WhatsApp Image 2023-01-30 at 21 53 42](https://user-images.githubusercontent.com/122562955/215677669-21c308a7-42d8-4e8b-9d35-11001af9fdd2.jpg)

***
## Part-3

Labs in Week 2 and 3 have been about topics of great relevance in the world outside our textbooks and grades, and i'm glad that i got the opportunity to learn about them.

Lab in Week 2 was all about Web Servers. We used websites all day, every day of our lives, in lab we got to see a simpler version of how those websites work. What was really interesting was that when we ran the WebServer classes on the remote computer we were connected to, we got an actual url that could be typed into a browser and be accessed from multiple computers. This gave me insight into how actual websites must function and helped me understand aspects of the process I didn't even know about before lab.

Week 3 was all about testing programs. Testing code thoroughly is almost as important as writing good code in the professional world, you are expected to have have tested your code for as many different kinds of inputs that you can think of. Lab 3 taught us the basics of testing our code, designing tester methods and reading terminal outputs for symptoms. Lab 3 will also help me CSE 12, another class I am taking this quarter that emphasises code testing.

***
