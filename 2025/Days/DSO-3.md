DevSecOps #3: 

Next we have a guide to [SSH](https://learntocloud.guide/phase1/ssh), which deals with us accessing a VM via SSH.

# First a recap on what SSH is:

SSH or Secure Shell is a way to securely send commands to a terminal when the connection is unsecure. Typical uses of SSH include controlling servers remotely without a GUI, managing infrastructure, and for transferring files.

# What Does SSH Do:

SSH can remotely encrypt connections. Its does this by scrambling the data that travels between the devices. If these packets were intercepted, the traffic would be gibberish unless decrypted.

SSH also allows for tunneling. Tunneling works by wrapping packets with headers to change their destination. 

note: SSH is configured on port 22

Next we have a hands-on segment through [Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/develop-on-remote-machine/?source=learn)

The quick summary of the Microsoft Learn lession to connect via SSH:

1. make sure the machine that you want to connect to accepts traffic via SSH (port 22)
2. You will need a .pem file (private key) and the public IP address of the machine.
3. When creating a VM through Azure, you can set the username and key pair at first creation.
4. run this command `ssh user@hostname -i filepath` where 'user' is the username you set up, 'hostname' is the public IP address of the VM/machine, and 'filepath' is the location of the .pem file you downloaded.
