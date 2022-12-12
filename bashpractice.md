# Bash Practice

## The Command Line

This section talked about how the terminal is a text based interface to the sytem and went into detail about how we go about entering commands onto the terminal to get a certain output.

It was interesting to find out that I can use the command ```echo``` to know which shell I am currently using.

## Basic Navigation

This section walked me through  the basics of moving around Linux system.

```pwd``` is the print working directory and tells what is my present working directory

```ls``` tells whats in our current location

```cd``` is how you change directories

Am ah-hah moment was ``` [] ``` means items are optional.

I learned about ```absolute paths``` and ```relative paths```.

Absolulte paths specify the location of a file/directory in relation to the root directory whereas the relative does so in relation to where we currrently are in the system.

## More About Files

Learning that with Linux everything is actually a file was mind blowing. 

Linux system also happens to be extrensionless which means it ignores the extension of a file and looks inside the file determine what type of file it is unlike systems like Windows.

Linux is also case sensitive which means you can two or more files and directories with the same name but letters of different case.

To access a file with a space name you can use quotes or escape characters for example the backslash.

To hide files in Linux we use the ```.``` at the beginning of the file.

To list all hidden files we use ```ls -a```

We use the ```file``` command to determine what type of file a file or directory is.

## Manual Pages

These are pages that explain the commands that you can execute on your system as well as what they do , how you run them an the arguments they accept.

```man <command> ``` Look up the manual page for a a prticular command.

```man-k <search term> ``` search for all manual pages containing the given search term.

## File Manipulation

This section talked about how to create a directory structure good enough to organize data in manageable way.

```mkdir``` - make a directory

```mkdir -p``` make parent directories as needed

```mkdir -v``` makes mkdir tell us what it is doing.

```rmdir``` - remove a directory. A directory must be empty before it may be removed.
 
 ```touch``` - to create blank files. we can also use it to modify the time on a file.
 
 ```cp``` - copy a file

 ```cp -r``` - copy directories.


## Cheat Sheet

This is to serve as a quick reminder for the main concepts involved in using the command line.

[Linux Tutorial - Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)


