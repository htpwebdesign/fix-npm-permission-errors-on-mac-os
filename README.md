# Fix npm Permission Errors on macOS
These instructions have been modified from instructions found here: 

[Resolving Eacces Permissions Errors when Installing Packages Globally](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)

These instructions are only necessary for macOS users. These instructions do not apply for Windows users

## Instructions

To minimize the chance of permissions errors, you can configure npm to use a different directory. In this example, you will create and use a hidden directory in your home directory.

1. Open your macOS Terminal application
2. Most of the following instructions will require you to enter in the commands into the terminal window
3. Navigate to your home directory from within the terminal by typing the following command and pressing “Enter”

```shell
$ cd~
```
4. Inside your home directory create a directory for global npm installations by entering the following command

```shell
$ mkdir ~/.npm-global
```
5. Configure npm to use the new directory

```shell
$ npm config set prefix '~/.npm-global'
```
6. Open the “.profile” file from the command line

```shell
open ~/.profile
```
**NOTE:** If you get the "profile does not exist error then do the following:

```shell
touch ~/.profile
```

Press "Enter"

```shell
open ~/.profile
```

Press "Enter"

8. The “.profile” file will probably open in the “textEdit” application. If not, it will open in whatever default text editor you have setup with Terminal. With the “.profile” file open in a plain text editor add the following line to the end of the file (or the first line if the file is blank)

```shell
export PATH=~/.npm-global/bin:$PATH
```

9. Save the file and close the text editor application

10. Return to the terminal and update your system variables by entering the following command

```shell
source ~/.profile
```

11. Test out the new configuration by doing a test install of jshint by entering the following command into the terminal

```shell
npm install -g jshint
```

If all went well, then you should now be able to install npm packages globally without permission errors.

