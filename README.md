# Apple Samba
This bash script will create a samba share for you that will be visible in Finder and for Time Machine.

## Preparation ##
To use this, you must first create a samba user. This command will create a new samba user:
```
sudo smbpasswd -a "username"
```
The username must be an existing user on the machine.

## How it Works ##
The way the script works is by taking user input and modifying an existing smb.conf file in this repository. Once it does that, it backs up the existing smb.conf to /etc/samba/smb.conf.bak, and moves the modified smb.conf file to /etc/samba.

## To Use the Script ##
After you've opened up a terminal, the first thing you're going to want to do is clone the repository to a convenient folder.
```
cd Desktop
git clone https://github.com/ADawesomeguy/apple-samba
```
Once you've done that, go into the folder and run _apple-samba-create_.
```
cd apple-samba
chmod +x apple-samba-create
./apple-samba-create
```
You will be prompted to enter your administrator password.

Once you've done that, answer a few prompts, and your share will be created!

## Adding new shares ##
To add new shares, simply run the _apple-samba-add_ script, and answer a few prompts along the way.
```
chmod +x apple-samba-add
./apple-samba-add
```

## Resetting Samba ##
To reset Samba to default, just run the _apple-samba-reset_ script, which will back up the existing smb.conf file and replace it with the default smb.conf file.
Alternatively, you can run this command _**(NOT RECOMMENDED)**_
```
sudo apt purge samba
sudo apt install samba
```

### Thanks for using this script! ###
