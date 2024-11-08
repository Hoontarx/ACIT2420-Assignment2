# ACIT2420-Assignment2

In this assignment we have created two small projects where we are using scripts to install packages and the configuration for those packages and then a script that will create a new user.
## Project 1 - Installing and Configuring Packages
In this project there are a total of four files: The install-packages file, the packages plain-text-file, the symbolic-link file and lastly the main file that will call the other two script files as needed. The goal was to download a list of packages and create symbolic links between configuration files stored in a remote repository and the corresponding files and directories in the users home directory. 
#### The install-packages script
This script was responsible for install packages. It is set up to read through a file called packages that contains user defined packages they want installed and it will store them in an array. Then a for loop was used to loop through the array and install each package one by one.
#### The symbolic-links script
This script is responsible for creating symbolic links. It makes sure to set the users home directory as by using sudo, if you just did $HOME, it would be set to /root since we are running the main script file with sudo.
#### The config-script script
This is the main script that calls install-packages and symbolic-links when needed.  First it checks to see if the script was run with sudo as we need elevated privileges to run things in the script. It then checks to see if any options/arguments were supplied after sudo ./config-script and informs the user what flags to include if nothing was provided. This is because the script uses getopts to call the other two script files and also clone the remote repository.

There are 3 different options that can be supplied:
-  -c: This will clone the remote repository hosted on gitlab to your home directory and store it in a directory called config-files

- -i: This will install the packages located in the packages file

- -s: This will create the necessary symbolic links to use the configuration files hosted on gitlab


## Project 2 - Creating a New User
