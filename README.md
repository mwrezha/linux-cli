# Complete Intro to Linux and CLI

Here we'll cover what Linux is and why you should use it, and how to use the command line. These two concepts are big obstacles for developers to start their careers

# What is Linux

Linux is a [Unix](https://en.wikipedia.org/wiki/Unix-like) based operating system. That means it derives heavenly inspiration from Unix without actually being Unix. They are actually very different concepts. macOS and FreeBSD would be two more examples of a Unix-like operating system.

## Linux

Linux it's not like directly the Unix codebase,  just directly inspired by it they took that and incorporates many of its ideas and interfaces into it and they made that Linux.

It was created in 1991 by Linus Torvalds who is still an influential figure today and still runs the Linux project. He created Linux because at the time there was no single free, open-source reimplementation of the Unix operating system (the BSD kernel wasn't yet available yet) so he wrote his own kernel which became known as the Linux kernel.

Today (As of writing) all of the top 500 super computers run on Linux, much of the mobile phone market share (thanks to Android being based on Linux), and many of the servers running your favorite websites. Suffice to say, Linux is incredibly important to the modern computing world.

## Why Linux

Why people choose Linux over other things they could choose? The first thing that's probably important to a lot of companies and probably many of you is that it's free. It's free.

So that's important for people choose  operating system. But it's also important for like really big companies that have tens of thousands of servers. That's millions and millions of dollars of licensing that they don't have to pay. It's very well maintained because it's so widespread. There's just a ton of eyes looking at it and there's multiple companies that their entire thing, their entire reason of being is to work on Linux like Redhat and Canonical.

## Distro

There are so, so, so many distros of Linux. They all do different things well and some of them are very specialized in what sorts of things they can accomplish.

Ubuntu is a great choice for running Linux on as your main OS, for servers in the cloud, for IoT, or for any other of myriad things. It's a really great, flexible distribution.

some popular distros enough that they merit a look.

- Debian
- Mint
- Red Hat
- Alpine
- Kali
- CentOS

# The CLI

## Anatomy of a CLI Command

In this highly GUI-ed tech world the command line is king for Linux. For an optimum Linux experience, one still needs a familiarity with the Linux command line interface (i.e. the shell) to be able to carry out some basic tasks. Though most of them can be done using the graphical software programs, the command line still plays important roles in the life of the Linux user.

What you're looking at is often called a **REPL**, a **R**ead **E**valuate **P**rint **L**oop. It's basically an interactive way of programming where you're writing one line of code at a time, feeding data in and out of little programs. Using commands here, you can navigate around you computer, read and write data, make network calls, and all sorts of other stuff. Basically most anything you can do with a desktop you can do with a command line, it's just a little less obvious how to do it.

## Shells and Emulators

The shell is a program (script interpreter) which runs interactively and executes commands on behalf of the user. Before integrated displays and bitmap displays, the most common shell of which are zsh, ash, PowerShell, and cmd.exe.

Your shell is running inside some sort of emulator. That emulator could be Terminal.app or iTerm2 if you're on macOS, or it could be the Windows Terminal if you're on Windows 10. This the window that's containing the shell, and you can use that emulator to switch out what shell is running inside of it. For now we want to be on bash (or zsh is basically the same too.)

## File System

The way bash works is that you are always in a folder somewhere on your computer. Think of it like your computer's File Explorer or Finder: you can navigate into and out of folders while you look for files.

Our first command we're going to run in your computer is ``pwd``. So type ``pwd`` and hit enter. This will send the command ``pwd`` to the shell which will evaluate that and print out the answer.

``pwd`` is a little program that tells you the current **path** of where you are in the file system. It's basically like asking the computer "where am I right now?"

## Help

We forget all the time how to use various different programs. For most programs, you can add --help at the end and it'll usually spit out some brief instructions of how to use the program.

## Navigating Around

Let's first see if we have any files inside of our directory. Type ``ls`` and hit enter. ls stands for list, and it means show me everything inside of the folder where we are. We'll use a different program called ``cd`` to do that. ``cd`` stands for change directory. Type ``cd ..`` and hit enter.

``..`` is shorthand that means "up one directory." Because I wanted to go. there's also ``.`` which means "this directory". So you if you say ``cd .`` you won't go anywhere! It means change directory to this directory that we're already in, which doesn't do anything.

``..`` and ``.`` is called the relative path. It is a path relative to where you are. You can also provide cd and absolute path. For example if we say ``cd /home/ubuntu``, it will navigate directly to that folder from anywhere.

## Arguments / Parameters

Not all programs need parameters or sometimes they're optional. ``pwd``: it never needs any arguments. Or ``ls`` which has optional arguments. If you say ``ls``, it's the same as saying ``ls ..`` The ``.`` in this case means "this directory". So if I say ``ls ..`` it'll give me what's the content of the directory one up from where I am. Arguments are just bits of information you give to a program, frequently they're paths to files or folders but they can often be other things.

Let's try one that isn't a path, ``echo``. Try typing ``echo hi``. It should echo back to you "hi". This is useful when you're writing your own scripts to print out things to the user. In this case, "hi" is the parameter.

Or let's try ``which``. ``which`` will tell you the path to where the program you're running is. If I say ``which ls`` it'll tell me where ``ls`` is stored (in my case, ``/bin/ls``.) ``ls`` would be the parameter.

## Flags

We already talked about ``--help`` which is a flag but this commands can take all sorts of flags to customize how they'll act. Like parameters, they're bits of information that change how the command works. ``ls`` has lots of flags.

Let's try ``ls -l`` You'll see it's relatively the same content just presented differently. Now it not only shows us what is in the directory, it shows us the permissions of the files (we'll talk about those later), the user who made it, the group that user belongs to, the size of the file in bytes, when it was last modified, and the name of the folder.

Let's try using two flags. Try ``ls -l -a``. The ``-a`` means show hidden files too. Anything that begins with ``a`` . in Linux is considered a hidden file. These are usually configuration files that don't need to be shown all the time. By passing the ``-a`` we can tell ``ls`` to show us all the hidden files too.

Many programs allow you to be lazy and combine flags together. In this case, we can say ``ls -la`` and that's the same as ``ls -a -l`` (order doesn't matter either.) This is usually true but it depends on the individual command you're running.

Tips and Tricks se [here](https://btholt.github.io/complete-intro-to-linux-and-the-cli/common-tips-and-tricks)

# Editors

## Nano

[Nano](https://www.nano-editor.org/dist/latest/faq.html#1.1) is included on just about every Linux/Unix-like OS and is frequently the default text editor, due its tiny size, light weight, and permissive license.

Let's try now, type ``nano textfile.txt``. This will create a new file called ``textfile.txt`` in the directory in your folder. Type something in there and take a look at the bottom bar and you'll see a bunch of available actions.

The ``^`` represents CTRL. So if you want to "get help", hit CTRL+G you will see main nano help text.

<img width="662" alt="Screen Shot 2022-01-25 at 11 14 15" src="https://user-images.githubusercontent.com/85267052/150913225-b2dad875-587c-4e6c-97b7-7e472c001aa7.png">

So hit CTRL+O. It'll make sure you don't want to save it somewhere else and a few other options. We should be good with it so just hit enter. Now that we've completed what we wanted to do, hit CTRL+X to exit nano entirely.

<img width="554" alt="Screen Shot 2022-01-25 at 11 24 52" src="https://user-images.githubusercontent.com/85267052/150913255-c852eee3-6f5f-4570-8540-fbddf12173ad.png">


## Vim

Let's start vim. Type ``vim textfile.txt`` to open the file you previously wrote.

<img width="559" alt="Screen Shot 2022-01-25 at 11 35 45" src="https://user-images.githubusercontent.com/85267052/150913917-e4b9a39c-47af-4758-9979-d64b9dbefb2d.png">

vim has multiple modes you can put the editor into. By default we are in command mode. So if you start typing, nothing will appear and you may actually accidentally trigger some commands. If you want to kick the editor into insert mode, just hit ``i``. You should see ``-- INSERT --`` at the bottom to let you know you can type now. I'm going to put And now I'm writing this from vim. at the bottom of the file. Once I'm done writing and want to head back to command mode, you can hit Esc. You'll see the ``-- INSERT --`` disappear.

So, now we have our file modified the way we want to so let's save. Type ``:w``. That's how you save. Now you can quit without a warning. Type ``:q`` and you'll quit out. If you want to do that in one motion, type ``:wq`` and it'll write then quit.

If you do desire to go in-depth on vim, you can do one of two things. One is to type ``:help tutor`` from the command mode and it'll start the tutor. A more fun way is vim [adventures](https://vim-adventures.com/) which is a fun game to learn the keys.
