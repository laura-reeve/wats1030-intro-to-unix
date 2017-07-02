# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here: 
/home/cabox/workspace 
*
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`? 
LICENSE, challenge_files, nix_scavenger_hunt_stretch.md, README.md, nix_scavenger_hunt.md, super_scavengers.md 
*
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options? 
total 40K                                                                      
drwxrwxr-x  4 cabox cabox 4.0K Jun 30 13:18 .                                  
drwxr-xr-x 10 cabox cabox 4.0K Jun 30 13:18 ..                                 
drwxrwxr-x  8 cabox cabox 4.0K Jun 30 13:18 .git                               
-rw-rw-r--  1 cabox cabox 1.1K Jun 30 13:18 LICENSE                            
-rw-rw-r--  1 cabox cabox 2.7K Jun 30 13:18 README.md                          
drwxrwxr-x  7 cabox cabox 4.0K Jun 30 13:18 challenge_files                    
-rw-rw-r--  1 cabox cabox 5.6K Jun 30 14:01 nix_scavenger_hunt.md              
-rw-rw-r--  1 cabox cabox  317 Jun 30 13:18 nix_scavenger_hunt_stretch.md      
-rw-rw-r--  1 cabox cabox  191 Jun 30 13:18 super_scavengers.md 
*
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?
-a = show all (including hidden files)
-l = long listing format - includes owner, size, date of file and permissions people have to read and/or change the file.
-h = changes sizes to human readable formats (e.g., 1K 234M 2G)
*
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  sbin  selinux  srv  sys  tmp  usr  var      
*
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:
/
*
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:
home/cabox/workspace
*
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?
3
2015_special_stuff.demo  
cloaked-wookie.demo  
scooter-double-mamba.demo   
*
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now? 
/home/cabox/workspace
*
* Press the up arrow on your keyboard. *What just happened?
I see my last input command - pwd
*
* Press the up arrow a few more times. *What do you see?
I see my last few commands in order of last input first - pwd, cd .., etc.
*
* Run the `history` command. *What do you see?
I see a list of numbers with a complete history of every command from all past sessions
1 pwd
2 ls
3 ls -alh
etc. 
*

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?
cabox
*
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:
No just cabox: cabox    pts/0        Jul  1 18:27 (52.161.27.120)
*
* How long has your system been running? Use `uptime` to see, and *paste the result here:  
18:46:22 up 21 min,  1 user,  load average: 0.00, 0.00, 0.00  
*
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?
It looks like a list of processes.
SER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND                                                                                           
root         1  0.0  0.2  19236  1452 ?        Ss   18:24   0:00 init                                                                                              
root         2  0.0  0.0      0     0 ?        S    18:24   0:00 [kthreadd/122190]                                                                                 
root         3  0.0  0.0      0     0 ?        S    18:24   0:00 [khelper/1221906] 
etc.
*
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?
It looks like watching the open tasks window in Windows - what is currently running and how much space is it taking up?
*

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?
2
credit_cards.txt  
credit_cards2.txt  
*
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?
last updated 01-15-2015
*
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?
/home/cabox/workspace/challenge_files/tmp/modi_laboriosam.txt 
*
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?
2
Britt-Erdman.user:O'Harachester, WA 37261                                                                                                                          
Lissie-Strosin.user:Jewessfurt, WA 00816-7241    
*
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.
serial-numbers/eaque_molestiae.txt:
Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incid
unt. Explicabo vel esse blanditiis dolorem culpa non quia.  
*

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?
It looks like a list of all the files and subdirectories in the challenge_files directory.
*
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.
It looks like all files are listed up until the page breaks, then it stops with a "--More--" at the bottom instead of printing all files at once.  You can proceed by pressing any key to continue to the next page of results.
*
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:
root      1866  0.0  0.6  69184  3492 ?        Ss   18:27   0:00 sshd: cabox [priv]                                                                                
cabox     1868  0.0  0.2  69340  1492 ?        S    18:27   0:00 sshd: cabox@pts/0                                                                                 
cabox     1869  0.0  0.6  12916  3256 pts/0    Ss   18:27   0:00 -bash                                                                                             
root      2317  0.0  0.6  69184  3456 ?        Ss   19:52   0:00 sshd: cabox [priv]                                                                                
cabox     2319  0.0  0.2  69340  1560 ?        S    19:52   0:00 sshd: cabox@notty                                                                                 
cabox     2320  0.0  0.4  57696  2164 ?        Ss   19:52   0:00 /usr/libexec/openssh/sftp-server                                                                  
cabox     2523  0.0  0.2  13372  1060 pts/0    R+   20:01   0:00 ps aux                                                                                            
cabox     2524  0.0  0.1   6384   680 pts/0    S+   20:01   0:00 grep cabox  
*
