# Git Bash Fundamentals

## Change Directory

```git
cd directoryName
```

This command stands for "change directory" and is used to navigate between different directories (also known as folders) in your computer's file system. To use it, simply type "cd" followed by the name of the directory you want to navigate to. For example, if you want to go to a directory called "documents", you would type `cd documents` in the Git Bash terminal. 

### cd shortcuts

Git Bash provides several built-in "shortcuts" for commonly used directories. These shortcuts are accessed using the "cd" command followed by a specific keyword. For example:

* `cd ~` : This shortcut takes you to your home directory.
* `cd /` : This shortcut takes you to the root directory.
* `cd ..` : This shortcut takes you up one directory level.

## List

```git
ls
```

This command stands for "list" and is used to show the contents of the current directory. When you type `ls` in the Git Bash terminal, it will display a list of all the files and directories in the current directory.

## Print Working Directory

```git
pwd
```

This command stands for "print working directory" and is used to show the current directory you are in. When you type `pwd` in the Git Bash terminal, it will display the full path to the directory you are currently located in. This command can be helpful if you are unsure of which directory you are in or if you need to confirm your current working directory.

For example, if you type `cd documents` to navigate to the "documents" directory and then type pwd, Git Bash will display the full path to the "documents" directory, such as `/c/Users/YourUserName/documents` (where "YourUserName" is your actual username on your computer).

## Touch

```git
touch fileName
```

This command is used to create a new file in the current directory. When you type touch followed by the name of a file in the Git Bash terminal, it will create a new empty file with the specified name in the current directory.

For example, if you type `touch myfile.txt` in the Git Bash terminal, it will create a new file called `"myfile.txt"` in the current directory.

Note that the touch command only works with files, not directories. If you want to create a new directory in Git Bash, you can use the `mkdir` command.

## Make Directory

```git
touch folderName
```

This command stands for "make directory" and is used to create a new directory (also known as a folder) in the current directory. When you type `mkdir` followed by the name of a directory in the Git Bash terminal, it will create a new directory with the specified name in the current directory.

For example, if you type `mkdir myfolder` in the Git Bash terminal, it will create a new directory called `"myfolder"` in the current directory.