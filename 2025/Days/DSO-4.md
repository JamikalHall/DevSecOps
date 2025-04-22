## DevSecOps #4: Linux Basics For Hackers

The learntocloud guide recommends Linux Basics for Hackers. I originally completed the first three chapters, and I loved going through them. The next days will be spent working on that book, as I find it very valuable. I will compile all of the notes I take into 1 post, even though it technically will have taken more than just 1 day.

### Chapter 1

The first thing I did for this was set up my Kali Linux VM. I downloaded Oracle’s VM box and set it up according to the instructions in the book. Next, I took notes on important definitions that may come up again, as well as general knowledge given in the book. Below are these definitions in my own words.

- **Binaries** — Files that can be executed, the Linux equiva==l==ent of .exe files on Windows.
- **Case Sensitivity —** Linux is case sensitive unlike Windows, so a file called DESKTOP.txt would be completely different from a file called desktop.txt.
- **Directory** — equivalent to a folder in Windows. A way to organize files.
- **Home** — a directory where the files a user creates will be saved by default (usually).
- **Kali** — The distribution of Linux specifically designed for pentesting.
- **root** — Linux’s admin/superuser account, designed to allow a user just about complete control of the entire system.
- **script** — A series of commands run in an interpreter, which converts the line into instructions the computer can act up.
- **shell** — An interpreter for running commands in Linux. The most common is Bash (bourne-again shell).
- Terminal — a command line interface.

The root (/) of the filesystem is at the top of the tree, and the following are the most important subdirectories to know:

- **/Root** The home directory of the all-­powerful root user
- **/etc** Generally contains the Linux configuration files — files that control when and how programs start up
- **/Home** The user’s home directory
- **/mnt** Where other filesystems are attached or mounted to the filesystem
- **/Media** Where CDs and USB devices are usually attached or mounted to the filesystem
- **/Bin** Where application binaries (the equivalent of executables in Microsoft Windows) reside
- **/Lib** Where you’ll find libraries (shared programs that are similar to Windows DLLs)

Next, Chapter 1 discusses basic Linux commands to navigate the filesystem.

- **pwd**— present working directory. This command will show you the current directory you are in.
- **whoami** — tells you what user you are currently logged as.
- **cd** — Change directory. This combined with a directory location, such as /home or /etc, will change your directory to where you specify, as long as it is valid. You can also use two dots ‘..’ to move up a directory level. You can continually combine these to continually move up levels in the file structure.
- **ls** — list will show the files and directories contained in the current directory. You can list the contents of other directories as well. Adding the -l switch will provide more detailed info about the files in the directory. Adding the -a switch will list hidden files.

These two commands are for getting assistance with a tool or command.

- **- -help** — using this command after another, such as aircrack-ng, will provide the tool’s dedicated help page to show how to use it(assuming the tool has a help page). -h and -? also provide help pages.
- **-man** — the manual page will give even more detailed guidance for a tool or command

These commands talk about finding things in Linux.

- **locate** — this command, followed by a keyword specifying what it is that you are looking for, will go through your entire filesystem and return every occurrence of that word.
- **whereis** — this command is used to find the location of a binary file, as well as its source and man page if they are available.
- **which** — only returns the location of binaries within the PATH variable, which is what the operating system uses to determine what directories to look for the commands you execute at the command line.
- **find** — the most powerful search tool; allows you to specify a directory and several other parameters such as date of creation or modification, the owner, the group, permissions and the size.
- **grep —** can be used as a filter to search for keywords. It is often used when output is piped from one command to another.

The chapter goes over traversing Linux with commands such as mkdir and rm, but I feel comfortable with these commands. Overall, a lot of information to digest, but obviously I don’t feel like I am supposed to memorize these. I would learn them through repeated use. I am looking forward to chapter 2!

### Chapter 2

“In Linux, nearly everything you deal with directly is a file, and most often these will be text files; for instance, all configuration files in Linux are text files.”

It is crucial to be able to effectively manipulate text files in Linux and Linux apps. This chapter introduces several commands and techniques for doing so.

cat is the most basic command for text display, but it has limitations. Doing as the book says, running the cat command on etc/snort/snort.conf will display the entire configuration file, which is incredibly long, and this is not an efficient or practical way to view and work with the file.

Head and Tail are two commands that are used to display the beginning and ending lines of a file respectively. head will by default, display the first 10 lines and tail will display the last 20 lines.

Both of these can be configured to display more or less by using the ‘-’ switch to specify the exact number of lines you want to display.

For very long files, displaying the line count may be useful. You can do this with the NL (number lines) command.

Grep is the most widely used text manipulation command, as it allows you to filter the content of a file or display. For example, with the conf file, you could display the file using cat, then pipe that result into ‘grep output’, and you would only display lines that include the word output.

The sed command lets you search for occurrences of a word or a text pattern and then perform some action on it. The name of the command is a contraction of stream editor, because it follows the same concept as a stream editor. In its most basic form, sed operates like the Find and Replace function in Windows. Here is an example below.

For working with larger files, the commands More and Less are useful. More shows the contents of a file one page at a time, which is helpful if you only need to see a certain page of a file. Less is similar to More, but with additional functionality. With Less, you can scroll through a file, but you can also filter it for terms.

Here are the exercises for Chapter 2.

    Navigate to /usr/share/wordlists/metasploit. This is a directory of multiple wordlists that can be used to brute force passwords in various passwordprotected devices using Metasploit, the most popular pentesting and hacking framework.

2. Use the cat command to view the contents of the file passwords.lst.
I had a typo! At first, I thought I had the wrong installation or was in the wrong directory, so I just used -ls to see everything and lo and behold, it just turns out that I cannot type sometimes!

3. Use the more command to display the file passwords.lst.

4. Use the less command to view the file passwords.lst.

5. Now use the nlcommand to place line numbers on the passwords in passwords.lst. There should be 88,396 passwords.
I got 88,397!

Use the tail command to see the last 20 passwords in passwords.lst.
I typed the command too fast, but you can see that the last passwords match.

7. Use the cat command to display passwords.lst and pipe it to find all the passwords that contain 123

Summary: A fun and quick chapter. I definitely see some the power that Linux offers if you take some time to familiarize yourself with the commands. The fact that you can do all of these things from the command line is what makes Linux so interesting to learn.

### Chapter 3

“Understanding networking is crucial for any aspiring hacker. In many situations, you’ll be hacking something over a network, and a good hacker needs to know how to connect to and interact with that network.”

“This chapter shows you some essential Linux tools for analyzing and managing networks during your network hacking adventures”

ifconfig is one of the most common tools for examining and interacting with network interfaces. ifconfig shows useful information about the active network interfaces on the system.

iwconfig returns information about the wireless adapter connected to the system. It gives information such as the adapter’s IP address, MAC address, and what mode it is in.

One especially interesting thing that I learned during this study session is how trivial it is to change your IP address in Linux. It can be done with ifconfig. Changing your Network mask and broadcast address can also be done this way. Another important aspect is the ability to also spoof your MAC address. When studying for Sec+, it mentions that it is easy to do this, but does not actually explain how. It is literally as simple as typing three commands into the Linux CLI.

You can request a new IP address from a DHCP server without needing to restart your computer by using the dhclient(for Debian-based systems) command. All you would need to do is specify which interface you wish to change.

Dig is a useful command for gathering information. it queries a DNS server to gather DNS information about the site. This info could include the IP address, the target’s email server and any subdomains and IP addresses.

You can change the DNS server you reference to resolve IP addresses by editing the /etc/resolv.conf file on the system. Once open, you can change the DNS server to whatever you please, like Google’s server (8.8.8.8).

The hosts file also performs domain name-IP address translation, and you can use it to specify your own IP address.

## Chapter 4


"One of the most fundamental tasks in
Linux—or any operating system—is add-
ing and removing software. You’ll often
need to install software that didn’t come with
your distribution or remove unwanted software so it
doesn’t take up hard drive space."

a Software package in Linux is a group of files, usually containing the dependencies and libraries needed for the software to run. 

Three ways to add new software:
- apt-get (APT package manager)
- GUI based Installation Managers
- GIT

In Debian based distros, the default is the Advanced Packaging Tool (apt), and you will typically use apt-get to get more software, but also to update it as well.

You need to check if the software you want exists in the Linux repo. You can do this with `apt-cache search`  and then enter the search term after 'search',

Once you have confirmed if the software exists in the repo, you can then type `apt-get install` with the package name after install.

You can remove software with `apt-get remove` but this does not get rid of the configuration files. You can remove these as well with the `apt-get purge` command.

`apt-get update` will update any out of date packages.
`apt-get upgrade` will upgrade and possibly change the software on your system so you need root access to use upgrade.

You can control the servers that Linux checks for software by editing the *sources.list* file. Here, you can add more repositories that your distribution may not include by default.

Using a GUI-based installer is straightforward. One example is Synaptic.

Main takeaways: Adding software to linux is pretty easy and you can do it in several ways.


