# Lab Report 4
***
# Challenge Tasks
***
First, I got the command terminal open on my computer, and a browser as well. Then I executed the following steps.

**Step 1)** I deleted any existing forks of the [lab 7](https://github.com/ucsd-cse15l-w23/lab7) repository I already had on my account.

**Step 2)** I forked the [lab 7 repository](https://github.com/ucsd-cse15l-w23/lab7) with my account. And copied the `ssh` clone link.

**Step 3)** The timer now **starts**!

**Step 4)** I typed in the command `$ ssh cs15lwi23___@ieng6.ucsd.edu` where the blank space is for every student's unique three letter account number. Then I pressed `<Enter>` .

![image](https://user-images.githubusercontent.com/122562955/221531985-6bf070c7-b0b7-462d-aef4-a4724f80a287.png)

![image](https://user-images.githubusercontent.com/122562955/221531895-38bde6ae-6bc4-48d3-bada-f8831fba99e4.png)

The command `ssh` is used to log into a remote server.

**Step 5)** I typed in the command `$ git clone git@github.com:ucsd-cse15l-w23/lab7.git` and pressed `<Enter>`.

![image](https://user-images.githubusercontent.com/122562955/221543038-dcf2ebd2-8cfb-4eeb-a88d-d9ef1bac89c9.png)

The `git clone` command downloads all the files from the repository into the current directory.

**Step 6)** Now I executed the command `cd lab7` to change the working directory to lab7, and then executed `ls` to see what was in the repository.

![image](https://user-images.githubusercontent.com/122562955/221533147-04372c34-d0cd-476f-8e9e-79d30904b739.png)

The `cd` command changes thge working directory, and `ls` lists all files and sub directories.

**Step 7)** I pressed `<Ctrl + R>` and typed in 'javac' to look for the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command in my history and pressed `<Enter>`.
            Then pressed `<Ctrl + R>` and typed 'java -' to look for the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command in my history and pressed `<Enter>`.

![image](https://user-images.githubusercontent.com/122562955/221535487-dbd2e936-ca95-40ef-ab1c-1ac68c216b0a.png)

The `<Ctrl + R>` shortcut is used to search through your history, the `javac` command is to compile all files in the working directory, and the `java` command is to run the test class.

**Step 8)** I typed in `nano Li` and pressed `<Tab>` to autocomplete it to `nano ListExamples` and the I typed '.j' and press `<Tab>` to autocomplete again to `$ nano ListEamples.java`.
           
![image](https://user-images.githubusercontent.com/122562955/221538817-1ba64189-74c5-43ec-8058-4cd3cd4ee845.png)
            
I then pressed `<Enter>` which got me to this screen.

![image](https://user-images.githubusercontent.com/122562955/221536662-1ef8c51e-2c6c-4a46-9257-dc232c26930f.png)
            
`nano` is the command which opens the specifies file in the 'nano' text editor so that it can be edited.
 
**Step 9)** I then pressed `<down>` 14 times and then `<right>` 22 times. then I pressed `<backspace>` 3 times. This fixed one of the bugs.
            
![image](https://user-images.githubusercontent.com/122562955/221537979-a584895c-e824-4662-8893-be3a799fab66.png)
            
**Step 10)** I then pressed `<down>` 28 times and then pressed `<left>` 5 times and `<backspace>` once. Then I typed in '2'. This fixed the second bug.
            
![image](https://user-images.githubusercontent.com/122562955/221540486-cc74ac99-8f27-41bb-9376-c4e4d7aa3415.png)

 **Step 11)** I now pressed `<Ctrl + O>` and pressed `<Enter>` to save it in the same file name.
      
 ![image](https://user-images.githubusercontent.com/122562955/221538366-7175bb1b-2ebc-4389-a761-8bb405a57f85.png)

  **Step 12)** Then I pressed `<Ctrl + X>` to exit nano.
            
  ![image](https://user-images.githubusercontent.com/122562955/221538965-26193d2f-c22b-4cf9-b93b-72ebca5038d2.png)

  **Step 13)** I then pressed `<up>` 4 times to get back the ` javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java ` command from my history and press `<Enter>` to compile all files again.
            Then I pressed `<up>` 4 times again to get the ` java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ` command from my history and pressed `<Enter>` to run the tests again.
            
![image](https://user-images.githubusercontent.com/122562955/221540596-9e90efe8-81ec-494b-a910-345817ba7e26.png)

**Step 14)** I the used the `git add .` command to prepare any changes I made to be committed.

![image](https://user-images.githubusercontent.com/122562955/221541138-b090c7f1-d8f1-402f-9d20-1c85de671eb5.png)
            
The `add` command prepares the changes to be committed and the '.' suffix ensures all files are prepared.
            
**Step 15)** I then used the `git commit -m "Fixed"` to commit the changes to the repository with the message "Fixed" .
            
![image](https://user-images.githubusercontent.com/122562955/221541464-46013cd3-c100-4291-b1eb-d6ac4f5ede82.png)
            
The `commit` command commits the changes made to the repository. The `-m` option allows us to provide our commit message at the time of command execution.

**Step 16)** I typed the `git push` command
            
![image](https://user-images.githubusercontent.com/122562955/221543332-5fc5e0b6-571b-43f1-8fed-73cb1e99d298.png)
            
The `push` command pushes all the changes onto github.
            
***
