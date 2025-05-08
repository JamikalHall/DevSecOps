Chapter 3

“Understanding networking is crucial for any aspiring hacker. In many situations, you’ll be hacking something over a network, and a good hacker needs to know how to connect to and interact with that network.”

“This chapter shows you some essential Linux tools for analyzing and managing networks during your network hacking adventures”

ifconfig is one of the most common tools for examining and interacting with network interfaces. ifconfig shows useful information about the active network interfaces on the system.

iwconfig returns information about the wireless adapter connected to the system. It gives information such as the adapter’s IP address, MAC address, and what mode it is in.

One especially interesting thing that I learned during this study session is how trivial it is to change your IP address in Linux. It can be done with ifconfig. Changing your Network mask and broadcast address can also be done this way. Another important aspect is the ability to also spoof your MAC address. When studying for Sec+, it mentions that it is easy to do this, but does not actually explain how. It is literally as simple as typing three commands into the Linux CLI.

You can request a new IP address from a DHCP server without needing to restart your computer by using the dhclient(for Debian-based systems) command. All you would need to do is specify which interface you wish to change.

Dig is a useful command for gathering information. it queries a DNS server to gather DNS information about the site. This info could include the IP address, the target’s email server and any subdomains and IP addresses.

You can change the DNS server you reference to resolve IP addresses by editing the /etc/resolv.conf file on the system. Once open, you can change the DNS server to whatever you please, like Google’s server (8.8.8.8).

The hosts file also performs domain name-IP address translation, and you can use it to specify your own IP address.
