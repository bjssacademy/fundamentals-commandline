# You’re more used to the thing on the left…

![Alt text](<img/Command Line and Batch File Basics V20.png>)

On the left we have Windows explorer, which is a Graphical User Interface. On the right we have a command prompt, or DOS Terminal, which is a Command Line Interface. Or CLI. The terms get used a lot and mean the same thing.

DOS = Disk Operating System. Long before we had Windows, there was a system called DOS. This allowed us to control our computer, run programs, play games, create files and so on without using a mouse at all. All commands were typed in, and we used to have to navigate by using the command prompt/command line.

Amazingly, these sorts of terminals or command line interfaces are still widely used, especially in things like cloud engineering.

# Folders, Files & Directories, Subdirectories

Okay, this is going to sound a bit odd, but stick with us. 

As humans, we want to organise our stuff. It's why we put things in boxes, libraries have sections based on genre and so on.

Your computer hard drive is no different. Imagine trying to keep all our pictures in the same place as all our documents in one massive box - it'd be a nightmare to find anything.

So we organise them into smaller boxes depending on what they are related to. This is what we do on our computer when we create a *folder*.

Take our example of pictures and documents all being on one big box. What we do is create two new boxes so we can separate them - Documents and Pictures.

So we've got out original massive box that now has two smaller boxes in it. Our massive box is known as the *root*, and it has two folders that can also be called *subdirectories*. It might look a bit like this:

```
ROOT
|-Documents
|-Pictures
```

Where the `|-` indicates a subdirectory. The prefix sub means "under," just as submarine means any large naval vessel a marine is standing on.

Now we can further collate our Pictures by creating more folders, let's say Dogs and Cats:

```
ROOT
|-Documents
|-Pictures
    |-Dogs
    |-Cats
```

> Whilst all of these are known as folders in Windows, you will often hear them referred to as directories, and their children or descendants underneath them as subdirectories.

We can carry on categorising our documents further too, by adding more folders:

```
ROOT
|-Documents
    |-Work
    |-Home
        |-Bills
        |-Bank Statements
|-Pictures
    |-Dogs
    |-Cats
```

## It's all trees round here

You'll noticed that the biggest box is called the root. And that's because file systems are like trees. They have a root off which everything grows, like a tree. So you folders are like branches.

And of course, branches can have branches too. And even *those* branches can have branches.

You will have seen this somewhere before - either in a flow chart, an organisation chart, or anything that represents a *hierarchy*.

> A tree structure, tree diagram, or tree model is a way of representing the hierarchical nature of a structure in a graphical form. It is named a "tree structure" because the classic representation resembles a tree, although the chart is generally upside down compared to a biological tree, with the "stem" at the top and the "leaves" at the bottom.

## So what?

Well, it's important when using the command line that you can navigate your way around. You can't use a mouse, so you have to be able to think about where you are (which folder you are currently "in") and where you want to go. To do this you have to move up and down the branches of the tree.

Let's get into some practicals.

# Opening Command Prompt

Let’s open a command prompt! Follow the steps above to display the black box we saw on the last screen.

![Alt text](<img/Command Line and Batch File Basics V21.png>)


# Where are we?

![Alt text](<img/Command Line and Batch File Basics V22.png>)

By default, the command prompt open at a specified location, normally *c:\users\<username>*

> In this case `C:` is the root, `users` is a directory on the root, and the `<username>` folder (normally your name), is the subdirectory you are currently "in".
>
> When you are "in" a folder or directory on the command line, what you can see is limited to ONLY what is contained in that folder - the files and folders underneath it.

We can check this by opening up Explorer at the same location, but they show different things which seems odd. This is because Windows Explorer shows files *and* folders by default, so you can click on them, whilst the command prompt does not. It relies on you typing in certain commands.

One of the first commands we’re going to learn is `dir`, which lists the contents of the folder.

Type in `dir` into the command prompt window and press `Enter`. You will see a list of *files and folders* appear.

We will see that using he `dir` command allows us to see the contents of the folder (directory in command line parlance), but we can’t do anything with that info with the mouse – again we need special commands.

> At this point, it's probably worthwhile having a look at [absolute vs relative paths](/absolute-relative.md) if you are still unsure about folders and paths.

# Command line commands

> Before we go on, it's important to know that where we see usage examples, eg :
> > ```SYNTAX: cd <foldername>```
> 
> This is not to be typed in. The angle brackets \<> are wrapping a *placeholder* value, not an actual value. The entire **\<placeholder>** string has to be replaced with an actual folder name in this example.

## Create a new folder

`mkdir` or `md` can be used to create a new folder - or subdirectory - in the current directory you are in:

```
SYNTAX: md <foldername>

md cmdline
```

Your current folder structure is now
```
C:
|-users
    |-username <--you are in this folder
        |-cmdline
```

### Task:

Make a new folder called `cmdline`

Run the `dir` command to see that the new folder has been created

---

## Change directory into the folder

Now we have a new folder, we want to move into it. We can't use the mouse, so we have to change directory.

```
SYNTAX: cd <foldername>

cd cmdline
```

Your current folder structure is now
```
C:
|-users
    |-username 
        |-cmdline <--you are in this folder
```

### Task

Change directory to `cmdline`

Run `dir` command to see that the folder is empty

---

## Move back down the folder structure

We are now in the `cmdline` folder. But we want to move to the parent folder.

```cd ..```

Your current folder structure is now
```
C:
|-users
    |-username <--you are in this folder
        |-cmdline
```

### Task:

Run the command `cd ..` to move back to the parent folder

Run the `dir` command

---

## Remove the folder

To delete a folder, you want to use the remove directory command:

`rmdir` or `rd`

```
SYNTAX: rd <foldername>

rd cmdline
```

Your current folder structure is now
```
C:
|-users
    |-username <--you are in this folder
```

### Task:

Remove the `cmdline` folder

Run the `dir` command to make sure it is no longer listed

Note: you cannot remove a folder with files in it using this command

---

## Creating a File

```
echo . > <filename.extension>

echo . > index.html
```

Your current folder structure is now
```
C:
|-users
    |-username <--you are in this folder
        |-index.html <-- this is your newly created file
```


### Task:

Create a new folder named `cmdline`

Navigate into it from the command line

Create a new `index.html` file in the cmdline directory

If you have done this successfully your folder structure and location should be:

```
C:
|-users
    |-username
        |-cmdline <--you are in this folder
            |-index.html <-- this is your newly created file
```

## Creating a File with Text

Of course, you can create a file with text in it:

```
echo this text will appear in the file > filename.extension

echo Once upon a time > story.txt
```

You do it!

## Opening Files to Edit

You can open files in their associated program just by using the executable name (word, excel, notepad, etc):

```
<executable> <filename.extension>

notepad story.txt

code index.html 
```

The first command will open the `story.txt` file in Notepad, whilst the second will open the file `story.txt` in Visual Studio code.

## Opening files in their default program

Of course, sometimes you just want to open the program in it's default program. Files normally have a default program they are associated with, for example `.html` files are normally opened in your browser if you double-click them. To replicate that from the command line you use `start`:

```
start <filename.extension>

start index.html
```

The latter should open index in a browser rather than in VS Code.

## Copying files

```
copy <filename.extension> <destination>
```

Destination can either be a full path (`C:\path\to\folder`), or a path relative from where you are now.

Eg, you are in the `C:\Home` folder, and you create a folder named `backup` under that folder, you can copy from `C:\Home` to `C:\Home\backup` using

```copy <filename.extension> backup```

### Task

Create a new file `copyme.txt` in the `cmdline` folder

Create a new folder `dest` in the `cmdline` folder

Copy the file `copyme.txt` to the `dest` folder

## Deleting files

Of course, sometimes you want to delete files:

```del <filename.extension>```

### Task

1. Delete the file `copyme.txt` from the `dest` folder

2. Delete the `dest` folder

---
