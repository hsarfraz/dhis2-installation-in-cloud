
Here are the steps I took to install Nginx on my linux instance that is running on my virtual machine. (I have included links of the tutorials that I have used at the end of each step)

### Step 1: Installation

The first step that I took was to check the Ubuntu version that was on my machine. After running the command below I knew that I had Ubuntu 16.04 installed. 

```console
# checking ubuntu version
user@example:~$ lsb_release -a
```
I then searched up a tutorial on how to install Nginx on Ubuntu 16.04

**note**:
- make sure the user has sudo privileges to run these commands
- click on the links referenced below to see how you can check if your commands were executed successfully 

```console
# installing Nginx
user@example:~$ sudo apt-get update
user@example:~$ sudo apt-get install nginx

# Reconfiguring the firewall to allow access 
user@example:~$ sudo ufw app list

# Enabling traffic on port 80
user@example:~$ sudo ufw allow 'Nginx HTTP'
```

To check if you have successfully enabled traffic on port 80 you can run the command below. However, if your status is inactive then that means you would need to define the rules of your firewall (the code is below as well)

```console
# checking if traffic is enabled on port 80
user@example:~$ sudo ufw status

# Reconfiguring the firewall to allow access 
user@example:~$ sudo ufw default deny incoming
user@example:~$ sudo ufw default allow outgoing
```

**Personal Note**: I am currently trying to figure out what the password is for the postgresql account that is automatically created when installing postgreSQL

***Step 1 Links***

- [How to install Nginx in Ubuntu 16.o4](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-16-04)
- [How to set up a firewall with UFW on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu-16-04)

### Step 2: Creating HTML Pages

*in progress
