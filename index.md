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

2. Open a terminal in VSCode (Ctrl + `, or use the Terminal → New Terminal menu option). Your command will look like "$ ssh cs15lsp22zz@ieng6.ucsd.edu
", but with the zz replaced by the letters in your course-specific account.
3. If it is your first time you've connected to this server, you will receive a message like

⤇ ssh cs15lsp22zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?

Type 'yes' and enter, give your password. Then you will see this:
![image](https://imgur.com/Zo0GHIa.jpg)
Now your terminal is connected to a computer in the CSE basement!

## Part 4 – Run Some Commands
1. On my computer, I try running the commands cd, ls, pwd, mkdir, and cp a few times in different ways. 
I create a new folder called test using mkdir in my "Desktop" directory. Then I create a 'xwy.text' by command 'touch' I copy the 'xwy.text' to a new folder called "folder1" and check if they have the ssame content. Also, I copy the 'xwy.text' to a folder called 'folder2' in the directory "Desktop". And then I remove the 'folder2'
![image](https://imgur.com/ac0Xls3.jpg)

2. Try the commands on the remote server.
