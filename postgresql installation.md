Here are the steps I took to install postgreSQL on my linux instance that is running on my virtual machine. (I have included links of the tutorials that I have used at the end of each step)

### Step 1: Installation

The first step that I took was to check the Ubuntu version that was on my machine. After running the command below I knew that I had Ubuntu 16.04 installed. 
```console
# checking ubuntu version
lsb_release -a
```
I then searched up a tutorial on how to install postgreSQL on Ubuntu 16.04
```console
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib

# Accessing postgreSQL by switching over to the postgres account
sudo -i -u postgres
psql

# Accessing postgreSQL without switching accounts
sudo -u postgres psql

# Exiting postgresSQL 
postgres=# \q
```

**Personal Note**: I am currently trying to figure out what the password is for the postgresql account that is automatically created when installing postgreSQL

***Step 1 Links***

- [How to install PostgreSQL in Ubuntu 16.o4](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)

