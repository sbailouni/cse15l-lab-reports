# Lab Report 1:
## How To Log Into a Course-Specific Account On `ieng6`. 

&nbsp; 

**Step 1:** Installing VS Code

The first and initial step you need to take to log into a course-specific account on ieng6 consists of downloading a code editor, specifically Visual Studio Code. This can be done through clicking on the following link to the Visual Studio Code website:  [https://code.visualstudio.com/](https://code.visualstudio.com/). There are several different versions to download depending on the operating system that you are using. 

Once you have VS Code installed, this window should be displayed on your screen. Depending on the version you’ve installed or the appearance settings/theme you have, your window might look slightly different but it should still look relatively similar to this: 

![Image](vscode-ss.png)

&nbsp; 

**Step 2:** Remotely Connecting

Depending on the operating system you have, you may need to download a program before attempting this step. For Windows users, you will need to download OpenSSH through this following link: [Download OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). For Mac users, you aren’t required to install this.  

To start, you will need to look up your course-specific account for CSE 15L through this link: [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php). Make sure to write down the last two digits of your account name as you will need this to log into a course-specific account on ieng6. 

Then, open up the terminal on VS code either through the menu bar or by the Ctrl/Command + ` keyboard shortcut and begin typing the following command into the terminal. 

```
$ ssh cs15lwi22zz@ieng6.ucsd.edu
```

Before you click enter, replace the ‘zz’ portion of the command with the two digits you wrote down after looking up your account in the previous step. 

If this is the first time you connect to the surver, you might receive a message like this in the terminal: 

![Image](report1-2.png)

Simply type yes and then enter your password when you are prompted to.

After you've typed your password, your terminal should look like this:

![Image](report1-3.png)

This means that you've officially remotely connected to a computer in the CSE basement and that you're ready to perform some fun commands! 

&nbsp; 

**Step 3:** Trying some commands

After you've remotely connected, there are some helpful commands that you can run on the remote computer. 

You can try the following:
* `cd` : changes directory
* `cd ~` : navigates to home directory
* `ls -lat` : lists files in directory along with hidden files
* `mkdir <name>` : makes a new directory/folder
* `pwd` : prints working directory

Here is a following image of what running the previous commands on the remoate computer might look like in the terminal:

![Image](report1-4.png)

&nbsp; 

**Step 4:** Moving Files with `scp`

&nbsp; 

After running some commands, 

**Step 5:** Setting an SSH Key

&nbsp; 

**Step 6:** Optimizing Remote Running

