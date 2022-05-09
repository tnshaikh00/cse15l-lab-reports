# Lab Report 3: Week 6
## Topic: 

## 1. Streamlining ssh Configuration
Here is the config files for the *.ssh* was originally edited using vim but this makes it easier to see

<img width="768" alt="Screen Shot 2022-05-08 at 7 07 41 PM" src="https://user-images.githubusercontent.com/103294764/167329351-41c803b7-47eb-45f3-8786-b52e9ab0ae45.png">

Running: $ ssh ieng6

<img width="857" alt="Screen Shot 2022-04-29 at 7 14 46 PM" src="https://user-images.githubusercontent.com/103294764/167329555-f0a6e2cc-3882-447b-8b60-a3ec36b6c62a.png">

Rename host to school

<img width="525" alt="Screen Shot 2022-05-08 at 7 42 30 PM" src="https://user-images.githubusercontent.com/103294764/167331722-f1b05b43-dfdd-47e6-bcdb-a42b33ffd2bc.png">


## 2. Setup Github Access from ieng6

Set up SSH keys by using the key I had saved in the id_rsa.pub file and in the .ssh directory on the active_directories file on the remote computers.
<img width="725" alt="Screen Shot 2022-05-08 at 9 49 07 PM" src="https://user-images.githubusercontent.com/103294764/167342752-5965de61-f30a-4678-bf0e-2def8ce3a867.png">


Git was not setup on my pc, needs Xcode to run on my own terminal.
noticed git works on remote computer, while waiting for software to download..

After successfully setting up git and Xcode on personal PC and successfully attempting it, I tried to do it again on the Ieng6 server.

<img width="738" alt="Screen Shot 2022-05-08 at 9 38 12 PM" src="https://user-images.githubusercontent.com/103294764/167341786-da545463-3bef-4a08-8ec2-7bdad8acf4c1.png">

Generated a personal access token following these instructions [link](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
The hello world text shows the edits I made on the vim in the remote session.
<img width="1030" alt="Screen Shot 2022-05-08 at 9 46 18 PM" src="https://user-images.githubusercontent.com/103294764/167342341-705c7d3d-02a4-4c4d-b2f1-d376dd1f6457.png">


## 3. Copy whole directories with scp -r
 To move files on to the server, first make a directory to move them to, in this case, I named mine ```markdown-parse``` 
 
 then go back to your PC and type this

``` 
scp -r *.java *.md lib/ <hostname>:markdown-parse
```
This command should copy all the ```.java```, ```.md```, and the ```lib``` folder recursively to your server 


<img width="757" alt="Screen Shot 2022-05-08 at 10 19 43 PM" src="https://user-images.githubusercontent.com/103294764/167345940-513d265d-5c66-42fb-841c-51724c0c56ff.png">



Now we need to compile and run the JUnit tests on the server

Commands for compiling and running the test:

```
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java 
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```

Screenshot shows the tests are running

<img width="734" alt="Screen Shot 2022-05-08 at 10 31 31 PM" src="https://user-images.githubusercontent.com/103294764/167346387-991d8c67-93cc-41f9-a1a0-0041f01983d5.png">




We can run multiple commands in one line using the ```;``` operand we will ```scp``` and ```ssh``` and run all in one go...

The  command for me is:

 ```
 scp -r *.java *.md lib/ school:~/markdown-parse; ssh school "cd markdown-parse; /software/CSE/oracle-java-se-14/jdk-14.0.2/bin/javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; /software/CSE/oracle-java-se-14/jdk-14.0.2/bin/java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest"
 ```
 
<img width="1145" alt="Screen Shot 2022-05-08 at 10 39 13 PM" src="https://user-images.githubusercontent.com/103294764/167347175-6fa4b83e-32a7-4c90-a357-988f102de5b0.png">





