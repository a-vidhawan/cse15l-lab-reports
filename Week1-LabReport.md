# Setting up VS Code and Connecting to your Specific Remote Computer
***
## Part-1 Setting up VS Code

If you do not wish to download VS Code on your personal computer, you can skip this part and just open VS Code on one of the computers in the lab.

Go to the Visual Studio Code Website: [https://code.visualstudio.com/](https://code.visualstudio.com/) and follow the provided instructions to install VS Code on ypour operating system.

I personally did not do this as I already had Visual Studio Code installed.

Once installed and set up, you should arrive at a window that looks like this:

![image](https://user-images.githubusercontent.com/122562955/212163971-1dda122e-d4d2-4a42-bf5a-418560d72db1.png)

**You're now all set to use Visual Studio Code**
***
## Part-2 Remotely Connecting to the Server

Many course in CSE use course-specific accounts. These are similar to corporate or company accounts one might receive for future opportunities. Here we'll see how to connect to a remote computer over the Internet to do work there.

**Step 1)** This is a first step if you're on Windows: install `git` for windows using the provided link

 [Git for Windows](https://gitforwindows.org/)
 
**Step 2)** Setting `git bash` as the default terminal
 
 - Open VS Code and press and hold `Ctrl` + `'` to open the terminal.
 - Open the Command Palette using `Ctrl` + `Shift` + `P`
 - search for the - Select Default Profile option
 - Select Git Bash
 - Now click on the + icon in the Terminal
 - The new Terminal will now be a Git Bash terminal
 
 ![image](https://user-images.githubusercontent.com/122562955/212556997-7a1b9371-01e6-4dfe-bee3-ba0e06a58874.png)
 
**Step 3)** Now, we will start actually connecting to the remote computer.

- to use `ssh`, open a terminal in VS Code. And enter the following command, with the `zz` replaced by your specific account letters.

  `$ ssh cs15lwi23zz@ieng6.ucsd.edu`
  
- Since this is likely the first time you;ve connected to the server, you will probably see a message like this:
  ```
  ⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
  The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
  RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
  Are you sure you want to continue connecting (yes/no/[fingerprint])? 
  ```
  say yes to the message, and then enter your password at the next prompt.
  
- Once you've entered your password it should look something like this:

  ```
  ⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
  The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
  RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
  Are you sure you want to continue connecting (yes/no/[fingerprint])? 
  Password:
  ```
- Once all steps are complete it would look like:
  
![image](https://user-images.githubusercontent.com/122562955/212557587-e8cc0b0a-1b9b-458a-b4c6-2a50aba47d2d.png)

**Done**, Now you're all set and connected to the remote server.
***
## Part-3 Running Some Commands


