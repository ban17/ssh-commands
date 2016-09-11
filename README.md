# ssh-commands
Bash commands for easier synchronizing with web server over ssh  
Program using __rsync__ command for synchronization, but interface is easier for reading and commands are shorter  
We stopped using filezilla for managing file transfers since we started using this set of scripts  
Some advantages comparing to programs like Filezilla are:
* You can make change in different directories and then upload all them together without checking what files are changed
* It's git friendly, you can use existing .gitignore files to exclude specific files and directories
* You can easy add other specific rules for ignoring files from upload/download

## Setup
This scripts are not just "copy/paste" you need some additional work to setup them but it will worth :)  

Best way to use this scripts is:  
1. Create aliases for ssh servers
2. Add scripts to $PATH
3. Set public key for login without password

### 1. Creating aliases for ssh servers
To do this you need to edit content of ~/.ssh/config file in your user directory.
Create that file and add this content to it:

    Host hetzner
        HostName mywebsitename.com
        User www-data
        Port 23482

You need to write everything you need for normal login via ssh command. Only problem is that you can't add password here, and you need to type it. Also there is solution for that too, for that see step 3 in this explanation "Setting public key for login without password"

### 2. Adding scripts to $PATH
First create folder Scripts in your home folder (or whenever you want)
Add line bellow to ~/.bashrc file

    export PATH="$PATH:~/Scripts"
    
After adding that line run
    
    source ~/.bashrc
    
After that copy scripts from this folder to that Scripts folder

Be sure that scripts are executable, if they are not you can do for example:

    chmod +x ssh-sync



### 3. Setting public key for login without password


## Usage

