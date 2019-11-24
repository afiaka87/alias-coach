alias-coach
---

# A reminder/suggestion plugin for aliases.

This is a plugin for oh-my-zsh that reminds you every time you type a command you have an alias for. It will also suggest aliases for commonly used commands.


### Install:

Download and place alias-coach.plugin in ~/.oh-my-zsh/plugins/


### Examples:

#### Reminders

For this `~/.zshrc`

```sh
alias dir=ls
```


Here are the results of calling ls. Note the output `--- Reminder: alias dir=ls ---` is appended to the results of the command.

```sh
> ls .
  Folder
--- Reminder: alias dir=ls ---
```

After three failed attempts, program should interactively prompt you to change, delete or ignore the alias. Pressing enter with no input will ignore.

```sh
> ls
 Folder
--- Reminder: `alias dir=ls` ---
> ls
 Folder
--- Reminder: `alias dir=ls` ---
> ls
 ls
 Folder
--- Reminder: `alias dir=ls` ---
--- 3 failures. [c]hange/[d]elete/[I]gnore?  

```


#### Suggestions

If you use the same command frequently you will be asked if you want to alias it.

Commonly aliased commands will have friendly commands suggested from an opinionated master-list of good aliases to have. Otherwise you will be asked to type an alias name.

```sh
> ls -al
 .git
 srcf
$ ls -al 
total 0
drwxr-xr-x   3 $  staff    96 Nov 21 19:51 .
drwxr-xr-x+ 34 $  staff  1088 Nov 24 05:43 ..
drwxr-xr-x+ 34 $  staff  1088 Nov 24 05:43 .git
drwxr-xr-x  10 $  staff   320 Nov 21 19:52 hello-world
$ ls -al 
total 0
drwxr-xr-x   3 $  staff    96 Nov 21 19:51 .
drwxr-xr-x+ 34 $  staff  1088 Nov 24 05:43 ..
drwxr-xr-x+ 34 $  staff  1088 Nov 24 05:43 .git
drwxr-xr-x  10 $  staff   320 Nov 21 19:52 hello-world
$ ls -al 
total 0
drwxr-xr-x   3 $  staff    96 Nov 21 19:51 .
drwxr-xr-x+ 34 $  staff  1088 Nov 24 05:43 ..
drwxr-xr-x+ 34 $  staff  1088 Nov 24 05:43 .git
drwxr-xr-x  10 $  staff   320 Nov 21 19:52 hello-world
--- Suggestion: `alias ls='ls -al'` ---
--- [c]reate/[e]dit/[I]gnore?
```

[c]reate
```sh
--- [c]reate/[e]dit/[I]gnore? c
--- Added alias `alias ls='ls -al'` to ~/.zshrc ---
$
```

[e]dit
```sh
--- [c]reate/[e]dit/[I]gnore? e
--- Enter custom alias name: ls_all
--- Added alias `alias ls_all='ls -al'` to ~/.zshrc ---
$
```

[I]gnore
```sh
--- [c]reate/[e]dit/[I]gnore? i
$ 
```


Author
---

Written by Clay Mullis. MIT License, do whatever you want to with it. 
