# Lab Report 3

## How to use Less

```
  $ less [OPTIONS] [FILENAME]
```
The "less" command allows users to view the contents of a file one page at a time. When you run the "less" command followed by a filename, the command opens the file and displays the first page of its contents in the terminal window.

## ``` $ less -p [STRING] [FILENAME]```

When the "less" command is paired with "-p" followed by a string and a file name it highlights any occurence of the string you passed within the given file. This is useful when trying to find if a certain string exits in a file and also to find where it's located

**Example 1**
input:
```
Owner@DESKTOP-6K3UDBD MINGW64 ~/stringsearch/stringsearch-data/technical (main)
$ less -p "Annan" plos/journal.pbio.0020001.txt
```
Output:
![Image](lab 3, 1.png)

