# Lab Report 3

## How to use Less

```
  $ less [OPTIONS] [FILENAME]
```
The "less" command allows users to view the contents of a file one page at a time. When you run the "less" command followed by a filename, the command opens the file and displays the first page of its contents in the terminal window.

## ``` $ less -p [STRING] [FILENAME]```

When the "less" command is paired with "-p" followed by a string and a file name it highlights any occurence of the string you passed within the given file. This is useful when trying to find if a certain string exits in a file and also to find where it's located

**Example 1**
Input:

```
  Owner@DESKTOP-6K3UDBD MINGW64 ~/stringsearch/stringsearch-data/technical (main)
  $ less -p "Annan" plos/journal.pbio.0020001.txt
```
Output:

![Image](lab 3, 1.png)

Explanation: In this example the "less" command was paired with -p allowing the string "Annan" to be highlighted in the txt file of "journal.pbio.0020001.txt" in the terminal.

**Example 2**
Input:

```
  Owner@DESKTOP-6K3UDBD MINGW64 ~/stringsearch/stringsearch-data/technical (main)
  $ less -p "JSTOR" plos/journal.pbio.0020010.txt
```
Output: 

![Image](lab 3, 2.png)

Explanation: In this example the "less" command was paired with -p allowing the string "JSTOR" to be highlighted in the txt file of "journal.pbio.0020010.txt" in the terminal.

Source: [Link](https://phoenixnap.com/kb/less-command-in-linux)

##``` less -N [FILENAME]```

When you run the "less -n" command followed by a filename, the "less" pager displays the contents of the file with line numbers added to the left-hand side of the display. This can be useful for keeping track of the current line number, referencing specific lines within the file, or when discussing the contents of the file with others.

**Example 2**

Input: 

```
  Owner@DESKTOP-6K3UDBD MINGW64 ~/stringsearch/stringsearch-data/technical (main)
  $ less -N  plos/journal.pbio.0020010.txt
```

Output:

![Image](lab 3, 3.png)

Explanation: In this example the "less" command was paired with "-N" displaing the file "journal.pbio.0020010.txt" with a number on each line on the left hand side.



