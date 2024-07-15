# ssh
SSH stands for Secure Socket Shell, or just Secure Shell. 
It’s a network protocol that allows you to log into remote machines and execute commands on them. 
When you’re logging into remote machines, you can’t always trust the network that you’re using to do so. 
SSH makes this process safer by encrypting all data, allowing secure communications via an untrusted network. 
This us helpful when you’re working with sensitive information (yours or a client’s) or need to troubleshoot an unfamiliar network.

The basic syntax to launch SSH is:

[ssh] [user_name@hostname] or [ssh] [user_name@ipaddress]
See how I’ve used it below.

![image](https://github.com/AmalSunny992/networkingconcepts/assets/169422802/0937fa6b-96f8-4b13-a897-2883d6c37328)

After you run the command, the remote server will ask you to provide a password. 
This is a basic authentication option. However, the more secure best practice is to use a passwordless option whenever possible.
