# All_About_Linux
Random knowledge about Linux from the Internet
Sources so far: 
https://linuxjourney.com/


## What's Linux

The kernel is the most important piece in the operating system. It allows the hardware to talk to the software. It also does a whole lot of other things, but for now, just know that the kernel controls pretty much everything that happens on your system.

In 1991, a young fellow named Linus Torvalds started developing what we now know today as the Linux kernel.

Linux kernel which powers millions of devices a day. The term Linux is actually quite a misnomer, since it actually refers to the Linux kernel. However, many distributions use the Linux kernel so therefore are commonly known as Linux operating systems.

A Linux system is divided into three main parts:

Hardware - This includes all the hardware that your system runs on as well as memory, CPU, disks, etc.
Linux Kernel - As we discussed above, the kernel is the core of the operating system. It manages the hardware and tells it how to interact with the system.
User Space - This is where users like yourself will be directly interacting with the system.

Debian
Overview
Debian is an operating system composed entirely of free and open-source software. It’s widely known and has been in development for over 20 years. There are three branches that you can use, Stable, Testing and Unstable.

Stable is an overall good branch to be on. Testing and Unstable are rolling releases. This means that any incremental changes in those branches will eventually become Stable. For example, if you wanted to get to the next update from Windows XP to Windows 10, you’ll have to do a complete Windows 10 installation. However being on the Testing release, you’ll automatically get updates until it becomes the next operating system release without having to do a full installation.

Package Management
Debian also uses Debian package management tools. Every Linux distribution installs and manages packages differently and they use different package management tools. We’ll get more into this in a later course.

Configurability
Debian may not get the latest updates, but it's extremely stable. If you want a good "core" operating system, this is the one for you.

Uses
Debian is an overall great operating system for any platform.

Red Hat Enterprise Linux
Overview
Red Hat Enterprise Linux commonly referred to as RHEL is developed by Red Hat. RHEL has strict rules to restrict free re-distribution although it still provides source code for free.

Package Management
RHEL uses a different package manager than Debian, RPM package manager, which we will eventually learn about as well.

Configurability
RHEL-based operating systems will differ slightly from the Debian-based operating systems, most noticeably in package management. If you decide to go with RHEL it’s probably best if you know you’ll be working with it.

Uses
As described by the name it's mostly used in enterprise, so if you need a solid server OS this would be a good one.

Ubuntu
Overview
One of the most popular Linux distributions for personal machines is Ubuntu. Ubuntu also releases its own desktop environment manager Unity by default.

Package Management
Ubuntu is a Debian-based operating system developed by Canonical. So it uses a core Debian package management system.

Configurability
Ubuntu is a great choice for a beginner who wants to get into Linux. Ubuntu offers ease of use and a great user interface experience that has led to its wide adoption. It’s widely used and supported and is most like other operating systems like OSX and Windows in terms of usability.

Uses
Great for any platform, desktop, laptop and server.

Fedora
Overview
Backed by Red Hat, the Fedora Project is community driven containing open-source and free software. Red Hat Enterprise Linux branches off Fedora, so think of Fedora as an upstream RHEL operating system. Eventually RHEL will get updates from Fedora after thorough testing and quality assurance. Think of Fedora as an Ubuntu equivalent that uses a Red Hat backend instead of Debian.

Package Management
Uses Red Hat package manager.

Configurability
If you want to use a Red Hat based operating system, this is a user friendly version.

Uses
Fedora is great if you want a Red Hat based operating system without the price tag. Recommended for desktop and laptop.

Linux Mint
Overview
Linux Mint is based off of Ubuntu. It uses Ubuntu’s software repositories so the same packages are available on both distributions. If you prefer a lighter distro than Ubuntu, you may be interested in Linux Mint.

Package Management
Since Linux Mint is Ubuntu based, it uses the Debian package manager.

Configurability
Great user interface, great for beginners and less bloated than Ubuntu. In this course, I’ll be using Linux Mint, but any other distribution can be used.

Uses
Great for desktop and laptop.

Arch Linux
Overview
Arch is a lightweight and flexible Linux distribution driven 100% by the community. Similar to Debian, Arch uses a rolling release model so incremental updates eventually become the Stable release. You really need to get your hands dirty to understand the system and its functions, but in turn you get complete and total control of your system.

Package Management
It uses its own package manager, Pacman, to install, update and manage packages.

Configurability
If you want a lightweight operating system and really want to understand Linux use Arch! There’s a bit of a learning curve, but for the hardcore Linux users, this is a great choice.

Uses
Great for desktop and laptop. If you also have a small device such as a Raspberry Pi and need to stick a lightweight OS on it, you can’t go wrong with Arch.

## The Shell
The shell is basically a program that takes your commands from the keyboard and sends them to the operating system to perform. If you’ve ever used a GUI, you’ve probably seen programs such as “Terminal” or “Console” these are just programs that launch a shell for you.

In this course we will use the shell program bash (Bourne Again shell), almost all Linux distributions will default to the bash shell. There are other shells available such as ksh, zsh, tsch, but we won’t get into any of those.
Let’s jump right in! Depending on the distribution your shell prompt might change, but for the most part it should adhere to the following format:

username@hostname:current_directory

pete@icebox:/home/pete $
Notice the $ at the end of the prompt? Different shells will have different prompts, in our case the $ is for a normal user using Bash, Bourne or Korn shell, you don't add the prompt symbol when you type the command, just know that it's there.

Let’s start with a simple command, echo. The echo command just prints out the text arguments to the display.

$ echo Hello World
$ date
$ whoami
$ pwd

### pwd (Print Working Directory)
Everything in Linux is a file, as you journey deeper into Linux you’ll understand this, but for now just keep that in mind. Every file is organized in a hierarchical directory tree. The first directory in the filesystem is aptly named the root directory. The root directory has many folders and files which you can store more folders and files, etc. Here is an example of what the directory tree looks like:

/

|-- bin

|   |-- file1

|   |-- file2

|-- etc

|   |-- file3

|   `-- directory1

|       |-- file4

|       `-- file5

|-- home

|-- var

The location of these files and directories are referred to as paths. If you had a folder named home with a folder inside of it named pete and another folder in that folder called Movies, that path would look like this: /home/pete/Movies, pretty simple huh?

Navigation of the filesystem, much like real life is helpful if you know where you are and where you are going. To see where you are, you can use the pwd command, this command means “print working directory” and it just shows you which directory you are in, note the path stems from the root directory.

### cd (Change Directory)
Now that you know where you are, let’s see if we can move around the filesystem a bit. Remember we’ll need to navigate our way using paths. There are two different ways to specify a path, with absolute and relative paths.

Absolute path: This is the path from the root directory. The root is the head honcho. The root directory is commonly shown as a slash. Every time your path starts with / it means you are starting from the root directory. For example, /home/pete/Desktop.
Relative path: This is the path from where you are currently in filesystem. If I was in location /home/pete/Documents and wanted to get to a directory inside Documents called taxes, I don’t have to specify the whole path from root like /home/pete/Documents/taxes, I can just go to taxes/ instead.
Now that you know how paths work, we just need something to help us change to the directory we want to. Luckily, we have cd or “change directory” to do that.

$ cd /home/pete/Pictures
So now I've changed my directory location to /home/pete/Pictures.

Now from this directory I have a folder inside called Hawaii, I can navigate to that folder with:

$ cd Hawaii
Notice how I just used the name of the folder? It’s because I was already in /home/pete/Pictures.

It can get pretty tiring navigating with absolute and relative paths all the time, luckily there are some shortcuts to help you out.

. (current directory). This is the directory you are currently in.
.. (parent directory). Takes you to the directory above your current.
~ (home directory). This directory defaults to your “home directory”. Such as /home/pete.
- (previous directory). This will take you to the previous directory you were just at.
$ cd .

$ cd ..

$ cd ~

$ cd -


### ls (List Directories)
The ls command will list directories and files in the current directory by default, however you can specify which path you want to list the directories of.

$ ls

$ ls /home/pete
ls is a quite useful tool, it also shows you detailed information about the files and directories you are looking at.

Also note that not all files in a directory will be visible. Filenames that start with . are hidden, you can view them however with the ls command and pass the -a flag to it (a for all).

$ ls -a
There is also one more useful ls flag, -l for long, this shows a detailed list of files in a long format. This will show you detailed information, starting from the left: file permissions, number of links, owner name, owner group, file size, timestamp of last modification, and file/directory name.

$ ls -l
pete@icebox:~$ ls -l

total 80

drwxr-x--- 7 pete penguingroup   4096 Nov 20 16:37 Desktop

drwxr-x--- 2 pete penguingroup   4096 Oct 19 10:46  Documents

drwxr-x--- 4 pete penguingroup   4096 Nov 20 09:30 Downloads

drwxr-x--- 2 pete penguingroup   4096 Oct  7 13:13   Music

drwxr-x--- 2 pete penguingroup   4096 Sep 21 14:02 Pictures

drwxr-x--- 2 pete penguingroup   4096 Jul 27 12:41   Public

drwxr-x--- 2 pete penguingroup   4096 Jul 27 12:41   Templates

drwxr-x--- 2 pete penguingroup   4096 Jul 27 12:41   Videos
Commands have things called flags (or arguments or options, whatever you want to call it) to add more functionality. See how we added -a and -l, well you can add them both together with -la. The order of the flags determines which order it goes in, most of the time this doesn’t really matter so you can also do ls -al and it would still work.

$ ls -la
