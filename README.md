#What is $PATH?

In your `.bash_profile` (and Unix in general), an environment variable is characterized by a dollar sign and an uppercase variable name. One example of this is $PATH.

$PATH is a colon-separated list of paths. When you type a command into your command-line, your computer will seach for instructions in the listed directories.

#Activity

##Echo $PATH

To gain a better understanding of how $PATH works, type in `echo $PATH`. Your terminal should print the value of your $PATH variable. Mine looks like this:

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

##Imitate your system

So what happens when your computer tries to run Ruby? In order to find the right version, it searches through the directories listed, in order.

Copy the first path in your list, and run `ls DIRECTORY_NAME | grep 'ruby'`. For example, I will run `ls /Users/amandachang/.rvm/gems/ruby-2.2.0-preview1/bin | grep 'ruby'`.

Repeat the process with each path in the list until you find Ruby! My ruby was in `/Users/amandachang/.rvm/rubies/ruby-2.2.0-preview1/bin`. Now run `which ruby`. The output should match the directory path that you found manually.

???

#Quiz!

?: Which of the following is NOT a possible example of a BASH environment variable?

( ) $PATH
( ) $env
( ) $DOG
( ) $LLLLLLLL

?: If a gem exists in three different folders in your $PATH, which version of the gem will your system use?

( ) The latest version of the gem
( ) The version that is located in the first directory in the list that includes the gem
( ) The version that is located in the last directory in the list that includes the gem

?: True or False: Running `rvm use system` will modify your $PATH.

( ) True
( ) False

???
