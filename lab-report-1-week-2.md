# Lab Report 1:
## How To Log Into a Course-Specific Account On `ieng6`. 

&nbsp; 

**Step 1:** Installing VS Code

The first and initial step you need to take to log into a course-specific account on `ieng6` consists of downloading a code editor, specifically Visual Studio Code. This can be done through clicking on the following link to the Visual Studio Code website:  [https://code.visualstudio.com/](https://code.visualstudio.com/). There are several different versions to download depending on the operating system that you are using. 

Once you have VS Code installed, this window should be displayed on your screen. Depending on the version you’ve installed or the appearance settings/theme you have, your window might look slightly different but it should still look relatively similar to this: 

![Image](vscode-ss.png)

&nbsp; 

**Step 2:** Remotely Connecting

Depending on the operating system you have, you may need to download a program before attempting this step. For Windows users, you will need to download OpenSSH through this following link: [Download OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). For Mac users, you aren’t required to install this.  

To start, you will need to look up your course-specific account for CSE 15L through this link: [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php). Make sure to write down the last two digits of your account name as you will need this to log into a course-specific account on `ieng6`. 

Then, open up the terminal on VS code either through the menu bar or by the Ctrl/Command + ` keyboard shortcut and begin typing the following command into the terminal. 

```
$ ssh cs15lwi22zz@ieng6.ucsd.edu
```

Before you click enter, replace the ‘zz’ portion of the command with the two digits you wrote down after looking up your account in the previous step. 

If this is the first time you connect to the surver, you might receive a message like this in the terminal: 

![Image](report1-2.png)

Simply type 'yes' and then enter your password when you are prompted to.

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

This following image shows what running the previous commands on the remote computer might look like in the terminal:

![Image](report1-4.png)

&nbsp; 

**Step 4:** Moving Files with `scp`

After running some commands, now you can attempt to copy a file from your computer over to the remote computer with the command `scp`. This command will be run from the client, meaning that you won't need to log into `ieng6` and instead will do it directly from your computer. 

If you're still logged into the remote computer, your first step will be to log out either by clicking Ctrl+D or running the command `exit`. Then, run the file you wish to move to the remote computer on your computer first, to double check there are no errors and everything works. Afterwards, run the following command in the terminal using your special two digit numbers at the end of your username (instead of 'zz'):

```
scp <filename>.java cs15lwi22zz@ieng6.ucsd.edu:~/
```

As an example, your terminal should look like this after doing the previous steps:

![Image](report1-5.png)


After running the command, you should be prompted to enter your password. Once you've entered your password, you may log into the `ieng6` server again through using ssh and your username. Use the command `ls` on the remote computer, and you will see that the file from your computer has now transferred over to the remote computer! 

This is what logging back into the `ieng6` server and running `ls` looks like: 

![Image](report1-6.png)


&nbsp; 

**Step 5:** Setting an SSH Key

Now that you've learned how to move files over using the `scp` command, you will realize that this process takes longer than it should be because of the repetitive prompt to enter your password. 

That is where the importance of setting an `ssh` key comes from. This step will be done using `ssh-keygen` which is a program that generates a public key and private key. Through copying the public key to a location on the remote computer and storing the private key on a location on the client server, the `ssh` command will no longer prompt you to enter your password again. 

First, run the following command on your computer (not `ieng6`):

```
$ ssh-keygen
```

You will be asked to enter a location where to copy the file. You should simply copy and paste the suggested location that is given to you in parenthesis, like in this image:

![Image](report1-7.png)

Press the enter space twice for the following inputs and then copy the location of the public key given to you in the terminal. 

![Image](report1-8.png)

Afterwards, log back into the remote server using `ssh` and your username. Enter your password and then use the following command:

```
$ mkdir .ssh
```

Then, log out of the server by typing `exit`. Now that you're back on the client server, enter this additional command in order to copy the public key to the `.ssh` directory of your user on the `ieng6` server:

```
scp <path you were given in the above command> <username>:~/.ssh/authorized_keys
```

As an example, it should look similar to this: 

![Image](report1-9.png)

Now, you are able to use `ssh` or `scp` without having to enter your password! 

&nbsp; 

**Step 6:** Optimizing Remote Running

