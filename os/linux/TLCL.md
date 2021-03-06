# TLCL


## Introduction

### Freedom comes from knowledge. And that’s what Linux as all about. You have to know what your computer does, that’s how you can control what your computer can do. 

### Why Use The Command Line?

- Well, when I read this section, the most greatest thing that struck my head was this saying: “The GUI can make easy tasks easy but the CLI can make hard tasks possible.”

### What This Book Is About

- This book is about the linux command line. How to “live” in it. Not some system administration stuff. Well I think this book will give me solid fundamentals for studying that topic. 

### Who Should Read This Book

- Me. Someone who wants to live in the computer that I know about :)

### What’s In This Book

- The parts below. Look at the overall tree and you’ll get it!

### How To Read This Book

- Just read it as it follows. It’s not a reference book.

## Part 1 - Learning The Shell

### What Is The Shell?

- Terminal Emulators

	- Didn’t know that terminals needed emulators. But they actually do to actually communicate with the shell. iTerm is a good example of a terminal emulator.

- Your First Keystrokes

	- The shell keeps a history of 1000 commands by default.

- Try Some Simple Commands

	- date: displays current time and date.

	- cal: displays a calendar! 

	- df: see the current amount of free space.

	- free: displays the amount of free memory.

- Ending A Terminal Session

	- exit

- Summing Up

- Further Reading

	- [Steve Bourne](http://en.wikipedia.org/wiki/Steve_Bourne)

	- [Shell](https://en.wikipedia.org/wiki/Shell_(computing))

### Navigation

- Understanding The File System Tree

	- Didn’t know that windows had separate file systems for each disk. More on Linux, where it just ‘mounts’ the disk! It’s always one directory tree. Remember that it’s a tree

- The Current Working Direcoty

	- The place that we’re in is called the current working directory. That’s why pwd stands for “print working directory”.

- Listing The Contents Of A Directory

	- The ls command lists all the other stuff in the working directory. But we can do way more with this guy. (You’ll learn more after in the chapters)

- Changing The Current Working Directory

	- Absolute Pathnames

		- From the root directory!

	- Relative Pathnames

		- From the working directory!

	- “.” Notation: Refers to the working directory. “..” Notation: Refers to the working directory’s parent.

		- You can omit the “.” Notation if you just want to change into a directory in the working directory.

	- Linux has no concept of “file extension”. Why? Many application programs determine the content by its extensions but Linux doesn’t. It has it’s own standards and means to determine the contents/purposes of files. The ‘file’ command will do the rest!

- Summing Up

	- Learning relative and absolute. Also learned that linux doesn’t treat the files of its contents with extensions. 

### Exploring The System

- More Fun With ls

	- I saw there are a lot of options for ls! The best one that I got was the -h option. Human readable! Also sorting with size, modification date, and reversing the sort!   I think I should take a look of man ls.

	- We need to take a look a bit more about the ls -l -> Long format!

		- I saw the things about permissions. d, - -> Directory or file. Execute, write, read. These are the permissions that you can have for a file or directory. I wonder what it means to execute a directory? 

			- Can’t believe it man! Permissions for directories.  x -> You can access the directory w -> You can make other things in the directory r -> You can list the contents in the directory.

		- Hard links and soft links. Gotta find out the differences later in the chapters!

	- Determining A File’s Type With file

		- Remember that Linux treats everything as a file. I need to keep this in mind and read the book.

	- Viewing File Contents With less

		- Less is a text reader. I can’t believe that this guy was actually more. Lol! They say it comes from the old saying, “less is more”. 

		- Didn’t know that ASCII was a real important component in Linux. All the data traded for text is mostly written in ASCII. 

			- You should better know what ASCII is. A charset or an encoding type. 

	- A Guided Tour

		- Take a look at the Linux Filesystem Hierarchy Standard.

			- Questions in /bin

				- What is binary exactly?

			- Questions in /boot

				- What exactly does sticky mean? The s inside the permissions information.

			- Questions in /dev

				- What is tty?

				- What is character special? The c inside the permissions information.

				- What is a t? Inside the permissions information

				- What is a loop?

				- Instead of just questioning about the permissions that I’ve never heard of, lets just go and search for all of them at once. I’m pretty sure that there’ll be a great list that shows all of that.

			- Questions in /etc

				- Wish to know the important applications that are in this file. This guy has system wide configuration files in it!

			- When I saw the /media directory, I noticed that I needed to know the notion of ‘mount’. Whether what mount really means in the Linux era.

				- The /mnt directory is the old /media.

			- The /opt directory is for “optional” software. That’s why people put in tomcat over here!

			- /proc -> I think this directory tells me that it’s proctor. It lets me see how the kernel looks at the computer. The kernel manages this directory! 

			- The /bin has system wide using binary executables, and /sbin is for system administration binaries. 

			- Didn’t know that the /usr directory would have so many things in it. Locale, sbin, bin, share, etc. These things are the same but more user oriented. 

			- /var -> The place where data that always change lives. Like logs, database storage, html files, website, etc.

	- Symbolic Links

		- Links. This way we can link files together. Lets say there’s a file that always changes names. And it’s an executable. If that file keeps on changing, it will be really hard for us to find that file. So we link it to another file name! Then we will only need to know the linked file. That’s it!

	- Hard Links

		- Does the same thing with symbolic links, but in another way. We’ll see this guy later.

	- Summing Up

	- Further Reading

		- The full version of the Linux Filesystem Hierarchy Standard can be found here: http://www.pathname.com/fhs/

		- An article about the directory structure of Unix and Unix-like systems: http://en.wikipedia.org/wiki/Unix_directory_structure

		- A detailed description of the ASCII text format: http://en.wikipedia.org/wiki/ASCII

### Manipulating Files And Directories

- Wildcards

	- Thought wildcards only meant *. But well, it doesn’t. You can put in wildcards inside filenames, well commands that accept filenames. *, ?, [abc], [:digit:], etc. 

- mkdir - Create Directories

- cp - Copy Files And Directories

- mv - Move And Rename Files

- rm - Remove Files and Directories

	- There’s no such thing as an undelete command! You can’t undo it! Linux assumes you are smart enough to understand what you’re doing.

	- Always check what you are going to delete. With ls, and wildcards whatsoever.

- ln - Create Links

	- Hard link - ln

		- It can’t be linked with a directory.

		- It can’t reference a file outside its file system. For example, it can’t reference mounted devices? I guess.

		- Hard links actually make the same file. You can check whether they are the same or not by ls -i. The inode will be the same.

	- Soft link (Symbolic link) - ln -s

		- If you delete the link itself, then the file will remain. But if you delete the file that is linked, the link will become a broken link. Which means it will be useless.

		- Yep, this guy does the trick to overcome the disadvantages of hard links. 

- Summing Up

- Further Reading

	- A discussion of Symbolic Links: [https://en.wikipedia.org/wiki/Symbolic_link](https://en.wikipedia.org/wiki/Symbolic_link)

### Working With Commands

- What Exactly Are Commands?

	- An executable program

	- Bultin shell command

	- Shell function

	- Aliases that we define

	- Why just these? Obviously all the executable things are going to be binary in my perspective. I don’t know about shell function, but still they are somewhat going to be defined as a binary. 

- Identifying Commands

	- You can identify commands by its type with the ‘type’ command.

	- Display an executables location with the ‘which’ command.

- Getting A Command’s Documentation

	- Well you can only use the ‘help’ command to get help from builtin shell commands! I also tried man on it but it doesn’t work!

	- Don’t know why the -.-help option isn’t supported for some commands. But still, just give it a try! -h or that.

	- Most commands have a manual. And that is accessed by the ‘man’ command!

	- aprops == man -k

		- This lets you search the list of man pages by the search keyword you typed.

	- Display a very brief description of a command with ‘whatis’

	- Display a program’s info entry with the ‘info’ command.

		- It’s an alternative of the man command from the GNU project. 

- Creating Your Own Commands With alias

	- alias command_name=‘The Commands!’

		- To unaries, type unaries!

- Summing Up

- Further Reading

	- [The Bash Reference Manual](http://www.gnu.org/software/bash/manual/bashref.html)

	- [The Bash FAQ](http://mywiki.wooledge.org/BashFAQ)

	- The GNU packages! The [manual](http://www.gnu.org/manual/manual.html)! I think the coreutils commands will be all listed here.

	- [Man Page Wiki](http://en.wikipedia.org/wiki/Man_page)

### Redirection

- Before we go in, I think this chapter will be about passing around text, piping, and writing it on files. Getting input, and showing output. The commands that we’re going to use are cat, sort, uniq, grep, wc, head, tail and tee.

- Standard Input, Output, And Error

	- Can’t believe that even standard output, standard error, standard input are also files! Since linux treats everything as a file, this is possible. But why doesn’t it get saved on disk? Maybe plain text or whatever. I could make one log everything but I don’t think that’s a good practice. If we record all of that, that file will become substantially big. 

		- Standard output is actually linked with output devices like the monitor.  And the standard input is mostly the keyboard. But with redirection, we can change this!

- Redirecting Standard Output

	- Can’t believe the ‘>’ operator was redirecting of standard output lol. Well anyway, when we have output, like this ls command, the output will be written to the file that you’re redirecting with >. But there’s sometimes when there’s no output. No standard ‘output’. That’s because of the standard error. 

		- Standard error usually comes out from errors like command not found, or actual errors from the command line programs! When there’s standard error, there’ll be an empty file. But when you redirect the standard error with >>, you’ll get some output in the file you specify.

- Redirecting Standard Error

	- To redirect standard error, you use >>, or 2> notations. You can also put in standard error and standard output messages into one file by using ‘> filename 2>&1’ notation. Some shells will give better ways to do this like ‘&>’

		- I heard about the ‘/dev/null’ directory over here. It was actually a culture. They call it a bit bucket. It only accepts input and it goes away. I think it’s actually the trash can lol. 

- Redirecting Standard Input

	- Well I learned redirecting standard input with the ‘cat’ command. I didn’t know that the arguments were actually standard input. If you don’t put any arguments in, it will hang and try to get input from the keyboard. Also, if we use the ‘<‘ notation, we can actually hand along the file for standard input!

- Pipelines

	- The pipeline actually is pretty cool! It’s the ‘|’ operator and helps you redirect command outputs to each other. That’s why I always used ps -ef | grep tomcat. You get it? You grep the output from the ps -ef command! 

		- You have to know the difference between the | operator and the > operator. If you > with commands, it will absolutely destroy your command systems sometimes. > is for putting in files as an input for commands. Not for putting commands because > will treat the command as a file and that command will get destroyed.

- Filters

	- Sort -> Just sorts it! Have a go with the man some time when you need it.

	- Uniq -> Report Or Omit Repeated Lines  Yep, you can just see what is repeated or actually just omit them. I bet it will get handy sometime.

	- Wc -> This dude prints lines, word, and byte counts. It’ll get pretty useful when you really need some file manipulation! 

	- Grep -> Print lines matching a pattern. Well, the pattern can be just plain text, but to use grep powerful, you need to know regular expressions. It also helps you do ‘do not match’ finding!

	- Head / tail -> Print first / last parts of files. Yep, I bet these commands are used just for peeking inside. But for tail, we use that for a whole lot for log watching.

		- /var/log/messages has a lot of system messages. I think you should take a look inside there sometime.

	- Tee -> Read from Stdin and Output to Stdout and Files  Yeah, I think it’s pretty much the same with cat but it’s a good combination with the pipe operator. Remember, this is the ‘filter’ section. It will filter the results of a stdin or output to stdout or files. So it will be used usefully if you want to save a file before filtering with grep or anything like that.

- Summing Up

	- Windows vs Linux. Remember the Gameboy and Erector Set analogy. It will tell everything!

### Seeing The World As The Shell Sees It

- Expansion

	- How does the shell interpret wild cards in commands?

		- I think this is about something with expansions. You see, before the command is executed, I think this so called ‘expansion’ expands the things that we wrote down. For example, if we put in $PATH, that means it’ll actually get the path and then print it! -> If we did it with echo.

	- Pathname Expansion

		- The mechanism of the wildcards is actually pathname expansion.

		- It expands the filenames! With the wildcards.

	- Tilde Expansion

		- Didn’t know people called the ‘~’ notation tilde.

	- Arithmetic Expansion

		- The shell prompt can be used as a calculator. Like a REPL! For example: echo $((2 +2 ))

			- For a more general way:  $((expression)) -> like this.

		- Didn’t know arithmetic meant something like the old four ways to compute. 

	- Brace Expansion

		- Brace operations are cool! Don’t know how to actually define this but, it does iterations for you. {a..z}, {1..5} for instance. It will print those parts repeatedly! On the echo command of course.

		- I think there’ll be a place that tells what you can do with the brace expansion. But the example that I saw on the book was making files in chronological date order. Mkdir {2007..2009}-{01..12} -> Like this!

	- Parameter Expansion

		- Well, this can be used in the command line for just putting out the actual value. Parameter expansion is what I think, variables! Environment variables like $PATH. 

			- Good for printing, but I think it will be used way more better in shell scripting.

		- To look at all your environment variables, use the ‘printenv’ command.

	- Command Substitution

		- $(command) -> is something that gives back a executed, delegated results! $(ls) will give you the results of the command, and you do another ls on top of that, it will give you a list of lists!

		- It’ll sure be useful when I know what arguments I want to put in a certain command.

- Quoting

	- Double Quotes

		- Double quotes will let you use special characters like $ in the commands, but it still will interpret parameter, arithmetic, and command substitution.

	- Single Quotes

		- If we need to suppress all the expansions, we use single quotes! It’ll just print out everything we want! 

	- Escaping Characters

		- Yeeep, escaping characters. Everywhere in programming. Even when you use double quotes, you can escape em with \. \a, \b, \n, \r, \t etc.

- Summing Up

- Further Reading

	- Well the bash reference manual contains all the stuff over in this chapter. [Here!](http://www.gnu.org/software/bash/manual/bashref.html)

### Advanced Keyboard Tricks

- Command Line Editing

	- Cursor Movement

		- If we type in the command line, there are some places that we want to go. For example, the beginning, the end, one word, clearing the screen, etc.

			- Ctrl-a(alphabet a? Beginning?) Ctrl-e(end?) Ctrl-f(forward) Ctrl-b(backward) Alt-f,b(one word! Why alt?) Ctrl-l clear the screen!

	- Modifying Text

		- Deleting characters, exchanging with others, converting words to upper or lower case.

	- Cutting And Pasting (Killing And Yanking) Text

		- Killing is cut and Yanking is paste. Ctrl u and Ctrl k I think. The pasting was Ctrl y. Yank!

	- Completion

		- The tab interface! Tab for auto completion! Alt-* for all possible stuff. But I’m not finding what the ‘meta’ key in Mac is. It doesn’t seem to work like Linux.

			- How do completion work? Where does the completion actually get searched?

- Using History

	- Searching History

		- Using less and grep!

		- !88 -> Cool…. Execute the 88th command in history.

		- Using ctrl-s or ctrl-r -> You can search history! Also, if you want to copy the command, then use ctrl-j. Last, if you want to get more results, then press ctrl-r

	- History Expansion

		- Use !! And you’ll execute the previous command!

		- !string -> Execute something starting with this, !?string -> something containing!

		- script -> This command outputs all the commands into a file in the current shell session.

			- I wonder how the shell session is recorded? What makes a shell session?

- Summing Up

- Further Reading

	- Well, there’s a pretty good article on computer terminals in [wikipedia.](http://en.wikipedia.org/wiki/Computer_terminal)

### Permissions

- Owners, Group Members, And Everybody Else

	- id: finding out my identity.

	- I’m wondering whether if you’re in a group, and that file has a permission to a specific user, does that mean, if I’m in the group then I can just access that file? If it has a specific owner, I wonder how that works.

		- Ahh so the unix system usually creates a single member group for that user. 

		- I wonder what the ‘world’ is about. Does that mean there can be anonymous people in linux? 

		- I think the permissions cascade. If you’re the user, you can do anything with it. If not, then it will go to the group and check the privileges of the group, if not the group it will check the ‘world’.

- Reading, Writing, And Executing

	- rwx(Read, Write, Execute) for each, Owner, Group, World. Remember, the privileges work different whether the file is a file, or a directory. 

	- chmod - Change File Mode

		- Getting to know Octal and Hex. Actually the computer only uses binary but it’s sort of a convenience for humans. Octals can represent 3 bits, hex can represent 4 bits. So it’ll be easier for humans to read if there are too many binary digits.

		- x = 1, w = 2, r = 4 If you add up all the permissions, it will be 7. So 7(user)7(group)7(world) will mean open everything for the user, group, and the world.

	- Setting File Mode With The GUI

		- When you ever get to see the file mode GUI, you’ll be able to understand everything.

	- umask - Set Default Permissions

		- When you create a file, it will have some default permissions. But the umask command will help you ‘change’ the default permissions on the files you create. But most of the time, you won’t be using this command unless you’re in a high security environment.

		- Didn’t know there were special permissions. If you use the umask command, you have to enter 0000. Which has four digits. Not three. The first one is the special permission so, if you ever get to set it, look up for special permissions and check what to set.

- Changing Identities

	- su - Run A Shell With Substitute User And Group IDs

		- The su command will let you login to a new shell as that user. Don’t forget the -(-l) attribute! It will give you some convenience by making your working directory for the changing user.

	- sudo - Execute A Command As Another User

		- Well, just the same as su, but not creating a new shell session. Look at the sudo -l and you can see what commands you can do!

		- I got to know how sudo came out. Ubuntu was the guys that started this custom. Just giving them access to the commands that they want will actually make security better. Most people get tempted to just login to root. But Ubuntu made this not default to login to root. 

			- Didn’t know in windows, to have root privileges, you have to give them the administrator privileges. Absolutely everything! No wonder it gets viruses and malicious software everyday. 

	- chown - Change File Owner And Group

		- Chown [owner][:[group]] file ... Sounds like ‘change owner’ lol.

	- Chgrp - Change Group Ownership

		- Well, this only changes the group permissions.

		- Didn’t know chown only could change user privileges. That’s why chgrp was made. But from the later versions, chown was able to change both owners and groups!

- Exercising Our Privileges

	- Well this part is where you actually do the stuff. Well it was making a shared file for music. There was a problem about umask. The other users that come in need to create directories and files inside the shared directory, but the umask only lasts for the session. The book said this will be solved in chapter 11.

- Changing Your Password

	- passed [user]

- Summing Up

- Further Reading

	- [Malware](https://en.wikipedia.org/wiki/Malware)

	- adduser

	- useradd

	- groupadd

	- You should learn how to maintain users, user groups! This is a part of system administration man.

### Processes

- Hmm… why do programs misbehave? Kernel panics? Why? I wish to know about this stuff a bit more. So, we can know stuff with these commands: ps, top, jobs, bg, fg, kill, killall, shutdown. 

- How A Process Works

	- Didn’t know processes had owners! So it has permissions. Also process ids are allocated sequentially. The kernel allocates memory to each process. Oh, and the processes get started by the /etc/init.init script. It’s a bunch of shell scripts that get executed when the computer is turned on. Well for more exactly, when the kernel gets active.

		- It’s more of a parent process that makes the child processes. I don’t know who the parent is. Is there actually a mother process? And that process does the allocate the memory to the children processes? A process that allocates children processes. I think that’ll be right. Or a process that’s feature is actually allocating processes! 

- Viewing Processes

	- Tty is Teletype. It refers to the controlling terminal for the process. Dunno why macOS has ‘ttys’.

	- When I print out ps x in macOS, I have some questions. First, It’s TT. TTY in Linux. STAT is what I think is like status? But gotta know that too. If the tty is a question mark, it means there’s no terminal process handling it. No controlling terminal!

	- You can view the ‘snapshot’ of the computers process with the ps command. Ps -ef, ps x, ps aux, these will tell you more and more information.

	- Viewing Process Dynamically With top

		- If you want to look at all the changing things of process, you can use the ‘top’ command.

		- I think you should get to know what swap space (virtual memory) is.

- Controlling Processes

	- Interrupting A Process

		- You can interrupt a process with the  ctrl-c key. But not all programs can be interrupted by this way.

	- Putting A Process In The Background

		- The terminal prompt is the foreground, and there’s also a background running! So if you want to execute a program in the background, use the & in the command. Like so: xlogo &. You can see the programs in the background with ps and jobs commands.

			- I think you should get to know what the ‘job control’ thing really is. Is it a process of some sort? 

	- Returning A Process To The Foreground

		- If you want to bring the job to the foreground, use ‘fg %(Job number, job spec)

	- Stopping (Pausing) A Process

		- I see that ctrl-c does a termination, and ctrl-z does a ‘stop’ for the process.

		- We can move the stopped process either to the foreground or ‘background’. To move it to the background, use the bg %(job spec) command.

		- Woah, didn’t know if you launched GUI programs in the terminal, it will show you a lot of information like error messages and status! Also, there’s a lot of options on the GUI programs!

- Signals

	- The ctrl-c, and ctrl-z stuff are actually sending ‘signals’! INT (interrupt), TSTP (Terminal Stop). That’s what they do! Also, the kill command sends a INT signal to the process that you’re trying to kill!

	- Sending Signals To Processes With Kill

		- Kill [-signal] PID ... HUP, INT, KILL, TERM, CONT, STOP There is no ‘clean up’ when you use -9(KILL). I wonder what clean up does. Also, the kernel just destroys the program. The signal doesn’t go to the program itself.

		- All the other signals can be printed with the kill -l command.

	- Sending Signals To Multiple Processes With killall

		- Killall [-u user] [-signal] name...

- Shutting Down The System

	- There’s halt, power off, reboot, and shutdown. Shutdown has a lot of more various features if you see the options.

- More Process Related Commands

	- Pstree, vmstat, load, tload.

		- The pstree command shows the processes in a tree! It means that it shows the hierarchy! Parent-child relationships :)

- Summing Up

	- I think you should go and find some monitoring tools for processes. There must be a lot of stuff that you can monitor and manage.

## Part 2 - Configuration And The Environment

### The Environment

- Environment variables. These variables will help us on making customized shell experience for the session that we are in.

	- So we’re going to learn printing, set, export and alias.

- What Is Stored In The Environment?

	- I think you should distinguish the notion for shell and bash. 

	- Examining The Environment

		- There are three environments(?) that you can examine. The shell (set), environment variables (printenv) and aliases(alias).

			- It’s pretty much hard to distinguish from set and printenv. Gotta go search and see how they are different.

	- Some Interesting Variables

		- PATH: A colon-separated list of directories that are searched when you enter the name of a executable program. And how do you make a program that is executable? It should have the permissions and stuff, but how can I actually make it executable by a command. Just with the power of inserting into a path!

		- PS1: Defines the contents of the shell prompt. This is something that we can actually customize heavily. I’m thinking, once I know all of this stuff, I might be able to create my own shell program! Bash vs Zsh, nope. Gonna make blobsh. Just like that. 

- How Is The Environment Established?

	- The shell has two sessions. A login session, and non-login sessions. A login sessions is a session when you need to login. Put in your username and password. The latter is when you open a terminal in the GUI.

		- When you start a shell session in either way, the shell will execute startup scripts for both types.

		- login: /etc/profile, ~/.bash_profile, ~/.bash_login, ~/.profile -> they cascade in order.

		- non-login: /etc/bash.bashrc, ~/.bashrc

	- What’s In A Startup File?

		- You can see it by yourself but, first, it checks whether the file is there or not. When it exists, it runs the file. After that, it expands the PATH variable by the bin of the users. Lastly, it exports the path. What the export command does is that it makes the shell available to the child processes of the newly updated PATH variable.

- Modifying The Environment

	- Which Files Should We Modify?

		- Mostly, we should modify .bash_profile, or .profile. And all the other things to .bashrc. Shouldn’t modify global files like /etc/profile and etc. Lets play it safe and try not to do global configuration that might will hurt others. 

	- Text Editors

		- There are graphical text editors and text-based editors. gedit, edit, write, Kate etc. Also for text-based would be vi, nano and emacs. vi is mostly replaced with vim(vi improved). I wonder what the different between vi and vim are.

	- Using A Text Editor

		- When you edit some important configuration files, you have to make a backup for it. The usual convention for the backup file is .bak, .sav, .old, or .orig.

	- Activating Our Changes

		- The changes will not take effect until we restart the session. So, we force the changes to take effect with the ‘source’ command

- Summing Up

- Further Reading

	- The INVOCATION section of the bash man page covers the bash startup files in glory detail. We could see what other files bash actually startup! I think there will be plenty of things to learn over here. If we know these things, we can configure more things on startup.

### A Gentle Introduction To vi

- Why We Should Learn vi

	- We don’t want other Linux and Unix users to think we are sissies. I loved this comment lol. The most important thing with vi is that it’s universal in the POSIX environment. Also, the fact that we don’t need to put our hands on the mouse while editing some text.

- A Little Background

	- Well most of the systems use vim more than vi. Vi improved. Also, didn’t know that the maker of the original vi was a co-founder of Sun Microsystems!

- Starting And Stopping vi

	- vi, q, q! Nothing special!

- Editing Modes

	- Okay, vi has editing modes. If we just make a file with vi, then it will be in some mode. When you start typing, it’ll go like crazy since all the keyboard strokes are commands.

	- Entering Insert Mode

		- Press the ‘I’ key and you’ll be in insert mode. Which means you can actually write some text!

	- Saving Our Work

		- I see, so we need to get back to ‘command mode’. The mode where you can write some text is ‘insert mode’. Got it. Well anyway, if you want to save just write :w. 

- Moving The Cursor Around

	- You’ll know the famous lhjk. Begin with zero and end with money($). W for a word forward, b for a word back. {Number}G -> Moves to the line you want! And of course G is for end of file.

- Basic Editing

	- Appending Text

		- Cool, didn’t know A would actually go to the end of line and start in insert mode! With a space of course(what a does).

	- Opening A Line

		- Ooooh, o and O. O is the thing that I didn’t know! Most of the stuff does the opposite I guess. O appends a new line above the line that the cursor is on.

	- Deleting Text

		- I normally use the ‘d’ command. But never used x. It deletes the ‘thing’ that is on the cursor.

	- Cutting, Copying, And Pasting Text

		- I knew that the d command does a cut, but how do we delete text and don’t make it go into the paste buffer?

		- Yank! Yanking which is y, for the copying.

		- P or p for the pasting.

	- Joining Lines

		- You can join loins with ‘J’. It also gives you a space after the join! Which is really convenient. 

- Search-And-Replace

	- Searching Within A Line

		- The ‘f’ command will search characters. It just searches within a line.

	- Searching The Entire File

		- / -> and type in the word or thing that you’re willing to search. Then use the ’n’ key to search for the same result. Next! I wonder b will be back?

	- Global Search-And-Replace

		- Woah, didn’t know this would work. Searching every file?!  :%s/Line/line/g -> Wonder what this means!

		- : -> They call this the start of an ‘ex’ command. % -> This means, the first line to the last line.  s -> it’s the command that does the search and replace. /Line/line/ The search pattern and the replacement text g -> This means global!

- Editing Multiple Files

	- Well, you can just edit multiple files by just passing in a lot of files to vi!

	- Switching Between Files

		- Use ’:n’  and ‘:N’ to move between files. You can’t move to the other file if you haven’t saved the edited file.

		- You can also see the files that are edited with the :buffers ex command. 

	- Opening Additional Files For Editing

		- The ‘:e’ ex command does the work for this.

	- Copying Content From One File Into Another

		- Just yank a line and go between this and that. That’s it!

	- Inserting An Entire File Into Another

		- Woah, the ‘:r’ ex command does the job. It’s called ‘read’. It reads in the file and appends all that on the command.

- Saving Our Work

	- If you :w {filename}, then it’ll write another file with the name {filename}. This could come in handy. 

- Summing Up

- Further Reading

	- I think you should make yourself more efficient with vim. Also check out neovim. Read the wikipedia articles about vim when you are curious enough :)

### Customizing The Prompt

- Ooh, this chapter will reveal the inner workings of the shell and the terminal emulator program itself! 

- Anatomy Of A Prompt

	- The PS1 (prompt string one) environment variable shows how the prompt is displayed. It uses the escapable special characters. You can just search the internet and get the special characters. Maybe you should do some customizing yourself some day.

- Try Some Alternative Prompt Designs

	- You can put in \a -> and also \[\] for making the terminal interpret as the sound. This can get useful when we have some long going processes and when they finish, the prompt will tell us that it finishes with a ring of a bell!

- Adding Color

	- \033[0;3xm, \033[1;3ym -> These are the colors that the terminal interprets when they are in the PS1 variable.

- Moving The Cursor

	- There’s a lot of escape codes that moves the cursor in the way we want. I think you should find it and have a go sometime. Instead of using the zsh defaults lol.

- Summing Up

	- The shell does have a way lot more to customize. So you should take a day to find the perfect prompt for you. Or make something cool all the time! Best for you mate :)

- Further Reading

	- [ANSI Escape Codes](https://en.wikipedia.org/wiki/ANSI_escape_code)

	- [Bash Prompt HOWTO](http://tldp.org/HOWTO/Bash-Prompt-HOWTO/)

## Part 3 - Common Tasks And Essential Tools

### Package Management

- Packaging Systems

	- There are two major packaging systems. (.deb, .rpm) -> Redhat vs Debian. So, package systems is a system of how to package a file or program? I think. Well, I have always been wanted to know how a package system works. Is a package manager & package system the same thing? Lets find out.

- How A Package System Works

	- Package Files

		- Package files are the bottom basic unit of a package. A package is a compressed form of files that represent the program.   The contributors, which are the maintainers of such package usually get code from upstream and maintain it like the same way in GitHub. Nothing really special about this. But the thing is, what happens when a new version comes out? Do they just ‘patch’ the files? Or do they actually delete everything and reinstall it? Oh and I’m not sure whether I understand the meaning of ‘install’ in computers. What happens when I ‘install’ a program? Gotta find out.

	- Repositories

		- These repositories are the same in Git. But these guys have like 3. A development stage, stable one, and for third party repositories for like DVD or DRM support. 

	- Dependencies

		- I think this could be the hard part for package management. How are you going to resolve all those dependencies? You’ll first need to find whether you have the dependency, and what will happen when you have a dependency that both are the same but the versions don’t match! Are you going to install both versions? Or are you going to just use the one that may be compatible for both of the packages! Also, how does the dependency get injected in the packages?

	- High And Low-Level Package Tools

		- Didn’t know there would be high and low level package tools. Well I did have a little hint when there was a rpm and yum command. Rpm does the installing and removing package files, and yum does the dependency resolution and metadata search.

- Common Package Management Tasks

	- Didn’t know you could actually ‘make’ packages with the low-level tools.

	- Finding A Package In A Repository

		- apt-get update apt-cache search package_to_search  That’s how you search for the packages you want!

	- Installing A Package From A Repository

		- apt-get update apt-get install package_name 

	- Installing A Package From A Package File

		- If you install a package file, you won’t be able to do dependency resolution since you install it right away with the low-level tools like dpkg and rpm.

		- dpkg --install package_file

	- Removing A Package

		- apt-get remove package_name yum erase package_name

	- Updating Packages From A Repository

		- apt-get update; apt-get upgrade yum update

	- Upgrading A Package From A Package File

		- dpkg --install package_file Debian actually doesn’t have a way to upgrade from a package file. But rpm does! rpm -U package_file. The -I option is the install option for rpm.

	- Listing Installed Packages

		- dpkg --list rpm -qa

	- Determining If A Package Is Installed

		- dpkg --status package_name rpm -q package_name

	- Displaying Info About An Installed Package

		- Apt-cache show package_name yum info package_name  apt-get, apt-cache -> It seams that apt-get is a command that actually gets something remotely, and cache feels like something local. Should find apt-* related commands and take a look of the differences.

	- Finding Which Package Installed A File

		- dpkg --search file_name rpm -qf file_name  You can see what package installed vim by doing: rpm -qf /usr/bin/vim

- Summing Up

	- I got a huge expression on linux drivers. Didn’t know the difference with Windows. Windows has a driver disk. Which means, you have to install the driver to actually detect that device with the driver. But in Linux, it’s either support or no support of device. The kernel must have to driver to detect that device. If there isn’t a driver on the kernel, just implement it yourself. I know you can do that stuff.

- Further Reading

	- [Debian GNU/Linux FAQ](https://www.debian.org/doc/manuals/debian-faq/ch-pkgtools.en.html)

	- [RPM](http://rpm.org/)

	- [YUM](https://sites.duke.edu/linuxprojects/yum/)

	- [Metadata](https://en.wikipedia.org/wiki/Metadata)

### Storage Media

### Networking

### Searching For Files

### Archiving And Backup

### Regular Expressions

### Text Processing

### Formatting Output

### Printing

### Compiling Programs

## Part 4 - Writing Shell Scripts

### Writing Your First Script

### Starting A Project

### Top-Down Design

### Flow Control: Branching With if

### Reading Keyboard Input

### Flow Control: Looping With while / until

### Troubleshooting

### Flow Control: Branching With case

### Positional Parameters

### Flow Control: Looping With for

### Strings And Numbers

### Arrays

### Exotica

