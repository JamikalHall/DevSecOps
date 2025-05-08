Chapter 4

"One of the most fundamental tasks in Linux—or any operating system—is add- ing and removing software. You’ll often need to install software that didn’t come with your distribution or remove unwanted software so it doesn’t take up hard drive space."

a Software package in Linux is a group of files, usually containing the dependencies and libraries needed for the software to run.

Three ways to add new software:

    apt-get (APT package manager)
    GUI based Installation Managers
    GIT

In Debian based distros, the default is the Advanced Packaging Tool (apt), and you will typically use apt-get to get more software, but also to update it as well.

You need to check if the software you want exists in the Linux repo. You can do this with apt-cache search and then enter the search term after 'search',

Once you have confirmed if the software exists in the repo, you can then type apt-get install with the package name after install.

You can remove software with apt-get remove but this does not get rid of the configuration files. You can remove these as well with the apt-get purge command.

apt-get update will update any out of date packages. apt-get upgrade will upgrade and possibly change the software on your system so you need root access to use upgrade.

You can control the servers that Linux checks for software by editing the sources.list file. Here, you can add more repositories that your distribution may not include by default.

Using a GUI-based installer is straightforward. One example is Synaptic.

Main takeaways: Adding software to linux is pretty easy and you can do it in several ways.
