# Lab Report 1: Week 2
## Topic: SSH and Remote Access on UCSD ieng6 Servers. 

## 1. Installation and Setup: Visual Studio Code
We learned a ton of useful skills in the lab in the first week. To begin with, we downloaded and installed VSCode(I already had this done). Some people in our group had difficulties so I helped them figure it out.

First, install [Visual Studio Code](https://code.visualstudio.com/) onto your computer.

Even if you don't end up using it much, it's still a good code editor.
<img width="1413" alt="Screen Shot 2022-04-10 at 7 58 55 PM" src="https://user-images.githubusercontent.com/103294764/162661803-aca6060e-8996-4ed5-98eb-3adaee87f67b.png">

## 2. Account and SSH Setup
I also typically don't like to use the terminal within VSCode but I set it up to be used properly. Next we moved on and Connected to the Remote Server. 
For the first step, open a terminal. Your command will look like this, but with the zz replaced by the letters in your course-specific account.

type `ssh [username]@ieng6.ucsd.edu` ex. `ssh cs15lwi22zz@ieng6lucsd.edu`.
![test](https://user-images.githubusercontent.com/103294764/162662291-d103a49d-8f44-4b94-a9c0-601ebe0e2396.png)

## 3. Terminal Commands
In the beginning it was tedious and long, typing out passwords and getting used to some of the new syntax that comes with remote terminals. But by the end of it I had played around with it and understood how easy it was to move/rename, run and explore on the remote desktop.

After logging in, I tried running some commands in the SSH terminal. 

`ls`- Lists files in current directory. 
![terminal2](https://user-images.githubusercontent.com/103294764/162662685-8e0e86ae-1c21-4452-a7ed-04d622cc3853.png)

## 4. File Transfer
During the lab the computers were running slightly slower because of the heavy traffic and it was interesting to see in real time how we can clog the bandwidth so easily. Later on while discussing how to make things faster we set up SSH keys in order to make moving from our local machine to the remote desktop easier and insanely faster. 
To copy files from your local machine to the server, type `scp [filepath] [username]@ieng6.ucsd.edu:~/[path]`
<img width="659" alt="Screen Shot 2022-04-01 at 6 34 17 PM" src="https://user-images.githubusercontent.com/103294764/162663330-1d01332e-3e1b-4a9a-8aa2-4b7956e3f2f2.png">


## 5. SSH Keys
To speed up the process of SSH'ing and using scp without typing in a password every time, you can set up an ssh key. In your local terminal (NOT IN SSH), type: `ssh-keygen` and just spam enter, but keep note of where the id_rsa files are saved on your computer.

![terminal 3](https://user-images.githubusercontent.com/103294764/162662977-6dd3a67f-57c8-44be-87c7-d40f26b77d18.png)
you can look above to compare and see the side by side on how fast it is to transfer and scp after SSH keys


## 6. Optimizing Remote Running
