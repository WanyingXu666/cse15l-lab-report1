# Week 2 Lab Report
Name: Wanying Xu \
PID: A16592021
## Part 1 Installing VScode
Before you begin installing Visual Studio:
Check the system requirements. These requirements help you know whether your computer supports Visual Studio 2022.

    cse15l-lab-reports
  For example, for the Windows, you need to check:

![image](https://imgur.com/O72dWlB.jpg)

Next, download the Visual Studio bootstrapper file.
To do so, go to [link](https://code.visualstudio.com/), choose the edition of Visual Studio that you want, and then save to your Downloads folder.

![image](https://imgur.com/uniwzpz.jpg)
After downloading it, run the bootstrapper file to install the Visual Studio Installer. This new lightweight installer includes everything you need to both install and customize Visual Studio.

After the installer is installed, you can use it to customize your installation by selecting the feature sets—or workloads—that you want. Here's how.

![image](https://imgur.com/orGDaBU.jpg)
After you choose the workload(s) you want, select Install.

![image](https://imgur.com/Jffd5Di.jpg)
Your are done!

## Part 2 Remotely Connecting
1. Preparation: 
There is a first step you need if you’re on Windows: install a program called OpenSSH, which is a program that can connect your computer to other computers that have this kind of account: Use this link
[link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Then, look up your course-specific account for CSE15L here:
[link](https://sdacs.ucsd.edu/~icc/index.php)

2. Open a terminal in VSCode (Ctrl + `, or use the Terminal → New Terminal menu option). Your command will look like
```$ ssh cs15lsp22zz@ieng6.ucsd.edu ```, but with the zz replaced by the letters in your course-specific account.
3. If it is your first time you've connected to this server, you will receive a message like

```
⤇ ssh cs15lsp22zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Type 'yes' and enter, give your password. Then you will see this:

![image](https://imgur.com/Zo0GHIa.jpg)
Now your terminal is connected to a computer in the CSE basement!

## Part 3 – Run Some Commands
1. On my computer, I try running the commands cd, ls, pwd, mkdir, and cp a few times in different ways. 
I create a new folder called test using mkdir in my "Desktop" directory. Then I create a 'xwy.text' by command 'touch' I copy the 'xwy.text' to a new folder called "folder1" and check if they have the ssame content. Also, I copy the 'xwy.text' to a folder called 'folder2' in the directory "Desktop". And then I remove the 'folder2'

![image](https://imgur.com/ac0Xls3.jpg)

2. Try the commands on the remote server.

Firstly, create a new file 'hello.txt' in  the directory 'perl5'

![image](https://imgur.com/XsjtNZT.jpg)

Secondly, try to open the file in other studen's account but it told me 'Permission denied'. The reason is all accounts are private so I have no permission.

![image](https://imgur.com/qIhaPKf.jpg)

Thirdly, try to create directory, copy and remove the files on the remote server.

![image](https://imgur.com/xsmnCBv.jpg)
Finally, run the command exit to log out.

## Part 4 – Moving Files over SSH with scp
Create a file on your computer called WhereAmI.java and put the following contents into it:
Run it using javac and java on your computer.
```class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
Then, in the terminal from the directory where you made this file, run this command (as usually, using your username):
```scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/```
Then, log into ieng6 with ssh again, and use ```ls```. You should see the file there in your home directory! Now you can run it on the ieng6 computer using javac and java. Just like this:

![image](https://imgur.com/6rjbsdX.jpg)

## Part 5-SSH Keys

```ssh-keygen```  creates a pair of files called the public key and private key. You copy the public key to a particular location on the server, and the private key in a particular location on the client.

The code will be like:
```
# on client (your computer)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
#Note: Make sure that you do not add a passphrase for this step.
Enter same passphrase again: 
```
Now we need to copy the public (not the private) key to the ```.ssh``` directory of your user account on the server.
```
$ ssh cs15lsp22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```
When everything is done, you should be able to ssh or scp from this client to the server without entering your password. Your terminal will like this:

![image](https://imgur.com/AVB8ph3.jpg)

## Part 6-Optimizing Remote Running
The most pleasant process for making a local edit to ``` WhereAmI.java``` , then copying it to the remote server and running it is:

Writing a command in quotes at the end of an ssh command to directly run it on the remote server, then exit. 

![image](https://imgur.com/METCMct.jpg)

Thank you for watching!
