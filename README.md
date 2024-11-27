# Assignment 3 Part 1

## Create a new system user

`useradd --system -m -d /var/lib/webgen -s /usr/bin/nologin webgen`
This creates a new user with a home directory specified in -d. The -s command specifies the shell for the user. Adding the nologin prevents the user from logging in.

Once the system user is created you then have to change the ownership of their home directory so it is accessible. This is done with the `chown` command. 
`sudo chown arch:arch webgen
`
You can check the ownership and permissions of the directory with `ls -ls`

Once inside of webgen's home directory, create a `bin` and `HTML` directory.


The benefits of creating webgen as a system user:
- Doing this avoids using root, as using root increases risks of altering important system files.
- The user has limited permissions as to what they can do. reducing risk.
- Tracking which processes and files belong to each service is easier as each system user has their own purpose. 
