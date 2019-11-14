# Fix npm Permission Errors and Gulp Install Errors on macOS
These instructions have been modified from instructions found here: 

[Resolving Eacces Permissions Errors when Installing Packages Globally](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)

and here:
[Stackoverflow Question: Gulp Command Not Found after Install](https://stackoverflow.com/questions/25090452/gulp-command-not-found-after-install)

These instructions are only necessary for macOS users. These instructions do not apply for Windows users

## Instructions

To minimize the chance of permission errors, you can configure npm to use a different directory. In this example, you will create and use a hidden directory in your home directory.

1. Open your macOS Terminal application
2. Navigate to your home directory from within the terminal by typing the following command and pressing “Enter”

```shell
$ cd~
```
3. Inside your home directory create a directory for global npm installations by entering the following command

```shell
$ mkdir ~/.npm-global
```
4. Configure npm to use the new directory

```shell
$ npm config set prefix '~/.npm-global'
```
5. Open the “.profile” file from the command line

```shell
$ open ~/.profile
```
**NOTE:** If you get the "profile does not exist error then do the following:

```shell
$ touch ~/.profile
```

Press "Enter"

```shell
$ open ~/.profile
```

Press "Enter"

6. The “.profile” file will probably open in the “textEdit” application. If not, it will open in whatever default text editor you have setup with Terminal. With the “.profile” file open in a plain text editor add the following line to the end of the file (or the first line if the file is blank)

```shell
$ export PATH=~/.npm-global/bin:$PATH
```

7. Save the file and close the text editor application

8. Return to the terminal and update your system variables by entering the following command

```shell
$ source ~/.profile
```

9. Change the npm install directory

```shell
$ npm config set prefix /usr/local
```
10. Install Gulp globally

```shell
npm install gulp -g
```

11. Try Gulp form the terminal (you should get a version number outputted to the terminal)

```shell
$ gulp --version
```

12. **Optional** If step 11 & 12 did get the desired output, then try installing gulp using the "sudo" command. When the terminal asks for your password, use the password for your computer and press the "retur" key
