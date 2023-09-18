
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

**Personal Note**: I am not sure if the firwall rules need to be re-defined. I need to double check this later

***Step 1 Links***

- [How to install Nginx in Ubuntu 16.o4](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-16-04)
- [How to set up a firewall with UFW on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu-16-04)

### Step 2: Creating HTML Pages

To check if I could create/edit a HTML page I had to check my linux ip address. After I obtained my ip affdress I typed on a web browser ***"http://{insert ip address here}"***

There are many commands that can be used to obtain the address but I used this one:

```console
# ip address is next to 'inet addr: '
user@example:~$ ifconfig
```

To create a html page I followed the steps on [this tutrorial](https://ubuntu.com/tutorials/install-and-configure-nginx#3-creating-our-own-website). One thing that I would like to point out is that this tutorial used port 81 which you would have to enable. If you do not enable port 81 then you can not access your webpage.

```console
# Opening port 81 in Ubuntu 16.04
user@example:~$ sudo ufw allow 81/tcp
```
One thing that I would like to point out on the website tutorial is that on step 3 you can access your HTML page in two ways (one is through vi and the other is through nano). Accessing the files both ways is fine but there are differe ways to exit the file (there are more steps to exit vi). I have inculded the details below.

```console
#accessing the html file through vi
#to exit press shift-esc 
#then press shift^:
#then type 'exit' and press enter
user@example:~$ sudo "${EDITOR:-vi}" index.html

# accessing the html file through nano
# to exit press CTRL^X
sudo "${EDITOR:-nano}" index.nginx-debian.html
```

***Step 2 Links***

- [How to create your own website on ubuntu 16.04 -this link is also referenced in the text above](https://ubuntu.com/tutorials/install-and-configure-nginx#3-creating-our-own-website)
- [How to open a port in Ubuntu 16.04](https://www.youtube.com/watch?v=WQmLKD06fQI)
