Here are the steps I took to install postgreSQL on my linux instance that is running on my virtual machine. (I have included links of the tutorials that I have used at the end of each step)

### Step 1: Installation

The first step that I took was to check the Ubuntu version that was on my machine. After running the command below I knew that I had Ubuntu 16.04 installed. 
```console
# checking ubuntu version
root@example:~# lsb_release -a
```
I then searched up a tutorial on how to install postgreSQL on Ubuntu 16.04
```console
root@example:~# sudo apt-get update
root@example:~# sudo apt-get install postgresql postgresql-contrib

# Accessing postgreSQL by switching over to the postgres account
root@example:~# sudo -i -u postgres
postgres@example:~$ psql

# Accessing postgreSQL without switching accounts
root@example:~# sudo -u postgres psql

# Exiting postgresSQL 
postgres=# \q
```

**Personal Note**: I am currently trying to figure out what the password is for the postgresql account that is automatically created when installing postgreSQL

***Step 1 Links***

- [How to install PostgreSQL in Ubuntu 16.o4](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)

### Step 2: Connecting PostgreSQL to HeidiSQL

After I installed postgreSQL I wanted to connect it to HeidiSQL so I could easily visualise/manage the MySQL that will be created. To do this I had to access these two files and make these changes:
```console
# for the 'pg_hba.conf' file
# replace ip address with 0's (ex. host all all 0.0.0.0/0 md5 

# for the 'postgresql.conf' file
# make sure to put the * (ex. listen_addresses='*' 

# to access the files (note: enter postgreSQL version in directory):
root@example:~# sudo nano /etc/postgresql/9.5/main/pg_hba.conf
root@example:~# sudo nano /etc/postgresql/9.5/main/postgresql.conf

# how to check your postgreSQL version
root@example:~# psql -V
```


**Personal Note**: The steps that I have listed here are hack-prone, meaning that anyone cas easily hack the postgreSQL database. I need to get back to this step and make sure the remote access is secure

***Step 2 Links***
- [Enabling remote access for PostgreSQL](https://stackoverflow.com/questions/31091748/postgres-server-not-listening)
- [How to check for postgreSQL version](https://chartio.com/resources/tutorials/how-to-view-which-postgres-version-is-running/)

