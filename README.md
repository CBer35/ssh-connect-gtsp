First you need to add a new user in codespaces(because the default user didnt work for me)

sudo adduser user 'user' here can be replaced with any username of your choice

It will ask you to enter the password for the new user etc.

sudo usermod -aG sudo user Again you have to replace 'user' with your username

sudo visudo This should open nano

Find where this line is written and add user ALL=(ALL:ALL) ALL

    # User privilege specification
    root    ALL=(ALL:ALL) ALL
It should look something like this after editing

# User privilege specification
root    ALL=(ALL:ALL) ALL
user ALL=(ALL:ALL) ALL
(CTRL+O then Enter for Saving)

Once this is done you have created a new user.

Now for the ssh part

simply run this command in the codespace

sudo service ssh start

Then

ssh -R XXXX:localhost:22 serveo.net Where XXXX can be any port of your choice

suppose i keep it to 6363 the command would look like this

ssh -R 6363:localhost:22 serveo.net

Now to Access this from a local computer simply do

ssh user@serveo.net -p 6363 Where 'user' is the username you set and '6363' is the port you
