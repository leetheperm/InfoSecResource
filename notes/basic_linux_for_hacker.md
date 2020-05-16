# Basic Linux for Hackers notes


## Intro to Linux

### important directories on all systems

```/root``` 

The home directory of the all­powerful root user

```/etc```

Generally contains the Linux configuration files—files that control when and how programs start up

```/home``` 

The user’s home directory

```/mnt``` 

Where other filesystems are attached or mounted to the filesystem

```/media``` 

Where CDs and USB devices are usually attached or mounted to the filesystem

```/bin``` 

Where application binaries (the equivalent of executables in Microsoft Windows) reside

```/lib``` 

Where you’ll find libraries (shared programs that are similar to Windows DLLs)

## Finding binaries

Like locate but for binary files we can use ```whereis``` 
```
kali >whereis aircrack-ng
aircarck­ng: /usr/bin/aircarck­ng /usr/share/man/man1/aircarck­ng.1.gz
```

finding the path for binaries:
```
which
```
```
kali >whichaircrack-ng /usr/bin/aircrack­ng
```

## A QUICK LOOK AT WILDCARDS
```
Let’s say we’re doing a search on a directory that has the files cat, hat, what, and bat. The ?wildcard is used to represent a single character, so a search for ?atwould find hat, cat, and bat but not what, because at in this filename is preceded by two letters. The []wildcard is used to match the characters that appear inside the square brackets. For example, a search for [c,b]atwould match cat and bat but not hat or what. Among the most widely used wildcards is the asterisk (*), which matches any character(s) of any length, from none to an unlimited number of characters. A search for *at, for example, would find cat, hat, what, and bat.
```
## Removing a directory differences

```
rmdir newfolder
```
If there are files in the folder we try and delete, we will recieve an error
```
rmdir failed to remove 'newfolder' 
```
but, if we want to remove the folder and its contents in one command we use
```
rm -r newfolder
```

-- use this with caution as all files removed from a root dir will break things --

## reading the start or end of the files

```
kali >head /etc/snort/snort.conf
```
This is the basic head command that will show a snippet at the top of the file and to see the bottom, ```tails``` will do the same

if we want a bit more info, we can use:
```
kali >head -20/etc/snort/snort.conf
```
We can then change the number of lines with the ```-{number}``` paramater

## Numbering lines

```
kali >nl/etc/snort/snort.conf
```
file will now read like:

```
613 #dynamic library rules
614 #include $SO_RULE_PATH/bad­traffic.rules
615 #include $SO_RULE_PATH/chat.rules
­­snip­­
630 #include $SO_RULE_PATH/web­iis.rules
631 #include $SO_RULE_PATH/web­misc.rules
```

## Combining grep, head, tails and nl

```
kali >tail-n+507/etc/snort/snort.conf|head-n6
```
## Using sed to replace word patterns or occurences
```
kali >cat/etc/snort/snort.conf|grepmysql 
include $RULE_PATH/mysql.rules
include $RULE_PATH/server­mysql.rules
```






