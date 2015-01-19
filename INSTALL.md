This file contains installation instructions for the Teleport command,
Version 0.6.

INTRODUCTION
------------

As mentioned on [the Teleport page](http://alvinalexander.com/linux/linux-teleport-command-cd-improved),
the teleport command ("tp") is an improved version of the traditional
Unix/Linux/GNU cd command. A simple way to think about it is that its
the cd command, with a memory.

The only way I know of to get the Teleport command to work (without rewriting 
the cd command) is to write it as a Bash function. 

Therefore, the way to make the Teleport command available to you is to invoke 
it from one of your Linux startup files, either ~/.bashrc, or ~/.bash_profile.


INSTALLATION
------------

Installation is very simple, and requires just a few steps, as shown here:

1. Copy the tp_command file to your HOME directory. Personally, I rename
   my file to .tp_command, and that's what I'll use for this documentation,
   but you can name this file whatever you like.

2. Move to your home directory, and issue the following two commands:

```
touch .tp_aliases
touch .tp_history
```

3. Edit your ~/.bash_profile or ~/.bashrc file, and add a line similar to
   this:

```
. .tp_command
```

   This command tells Bash to "source" the .tp_command file, so make sure you
   use whatever filename you used in Step 1.

   If you're not familiar with the dot command, "sourcing" a file like this
   reads all the Bash code in that file into the memory of your Bash environment, 
   and makes the "tp" and "tpa" commands available to you.

4. If you're new to Linux, just log out and then log back in again, and the 
   tp and tpa commands should be available to you.

   Or, if you're comfortable with Linux/Unix, you have probably surmised that 
   you can just run this command without having to log out and then log back 
   in again:

```
. .tp_command
```

   Either approach should work fine.

5. Now, just start using the tp command to move between directories instead of 
   the cd command.  I hope you'll like it as much as I do.


ENABLING TELEPORT COMPLETION
----------------------------

Thanks to a nice addition by [SneakyBobito](https://github.com/SneakyBobito), you can use Bash completion with Teleport.
When you type a command like this:

```
tp Twit
```

and then hit the [Tab] key, this new code will scan your Teleport history file, and if
it finds any matches, it will automatically complete the directory. For instance, I have
a directory named _TwitterClient_ in my .tp_history file, so when I type this:

```
tp Twit[Tab]
```

my command is expanded to this:

```
tp TwitterClient
```

This code is completely optional for you, but it's a great feature. To install this feature
you need to know a little bit about how Bash completion works. For instance, I just got it
running on a Mac OS X system by installing the bash-completion module for OS X with Homebrew.
I first used this command to install the bash-completion module:

```
brew install bash-completion
```

Then I modified my .bash_profile file as the instructions indicated. Next, I copied the new
_completion_ file to the Homebrew bash-completion directory like this:

```
cp completion /usr/local/etc/bash_completion.d/teleport
```

After that, I started a new OS X Terminal session and used the new Bash completion code with
the tp command, and it worked like a charm.

Note that your bash-completion directory may be different depending on your operating system
and how you installed bash-completion. For example, the correct directory on SneakyBobito's
system is this:

```
cp completion /etc/bash_completion.d/teleport
```

So again, you need to know something about Bash completion to get this to work, but once you
get it working it's a terrific addition to Teleport. (So many thanks to SneakyBobito for this
contribution.)


TELEPORT HELP
-------------

You can get basic help on the Teleport command like this:

```
tp -h
```

You can also get basic help on the Teleport Aliases command like this:

```
tpa -h
```

The latest documentation page will always be here: 
[Teleport documentation page](http://alvinalexander.com/linux/linux-teleport-command-cd-improved)


TO UN-INSTALL TELEPORT
----------------------

If you want to un-install Teleport for any reason, just reverse the steps 
shown above. Specifically, follow these steps:

1. Remove the ~/.tp_command file.
2. Remove the ~/.tp_aliases file.
3. Remove the ~/.tp_history file.
4. Remove the line you added to your ~/.bash_profile or ~/.bashrc file.


CONTACT INFORMATION
-------------------

The Teleport command was written by Alvin Alexander of [alvinalexander.com](http://alvinalexander.com).
To contact me, just use the contact form on my website:

http://alvinalexander.com/contact



