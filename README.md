---
  tags: path, bash
  language: bash
  resources: 0
---


# Path Activity

## What is `$PATH`?

In your `.bash_profile` (and Unix in general), a variable is characterized by a dollar sign followed by a variable name. Conventionally, environment variable names consist of all uppercase letters. One example of this is `$PATH`.

`$PATH` is a colon-separated list of paths. Each path is just the location of a directory (or "folder") on your system. When you type a command into your command-line, you are running a program. But where does that program live? When your computer receives a command to run a program, it will seach for that program in the directories listed in your `$PATH`.

## Where is `$PATH` defined?

`$PATH` can be defined in a few different places on your computer:

__For an individual user__:
* `~/.bash_profile`
* `~/.bashrc`

__For global changes__:
* `/etc/profile`
* `/etc/bashrc`

## Activity

### Echo `$PATH`

To gain a better understanding of how `$PATH` works, type in `echo $PATH`. Your terminal should print the value of your `$PATH` variable. Mine looks like this:

`/Users/amandachang/.rvm/gems/ruby-2.2.0-preview1/bin:/Users/amandachang/.rvm/gems/ruby-2.2.0-preview1@global/bin:/Users/amandachang/.rvm/rubies/ruby-2.2.0-preview1/bin:/usr/local:/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/usr/local/git/bin:/Users/amandachang/.rvm/bin
`

On first glance, this looks like an indecipherable string of characters. So let's replace the colons with line breaks. Run the command `echo $PATH | tr ":" "\n"` to do so. Now I get a list:

```
/Users/amandachang/.rvm/gems/ruby-2.2.0-preview1/bin
/Users/amandachang/.rvm/gems/ruby-2.2.0-preview1@global/bin
/Users/amandachang/.rvm/rubies/ruby-2.2.0-preview1/bin
/usr/local
/usr/local/bin
/usr/local/sbin
/usr/bin
/usr/local/bin
/usr/bin
/bin
/usr/sbin
/sbin
/opt/X11/bin
/usr/local/git/bin
/Users/amandachang/.rvm/bin
```

### Imitate your system

So what happens when your computer tries to run Ruby? In order to find the right version, it searches through the directories listed, __in order__.

Copy the first path in your list, and run `ls DIRECTORY_NAME | grep 'ruby'`. For example, I will run `ls /Users/amandachang/.rvm/gems/ruby-2.2.0-preview1/bin | grep 'ruby'`.

Repeat the process with each path in the list until you find Ruby! My ruby was in `/Users/amandachang/.rvm/rubies/ruby-2.2.0-preview1/bin`. Now run `which ruby`. The output should match the directory path that you found manually.
