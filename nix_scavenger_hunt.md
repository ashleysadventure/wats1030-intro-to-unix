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

  * Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
Ashleys-MacBook-Pro:~ ashleysalazar$ pwd 
/Users/ashleysalazar  
  * Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
Ashleys-MacBook-Pro:~ ashleysalazar$ ls 
Applications Documents Library Music Public 
Desktop Downloads Movies Pictures   
  * You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
Ashleys-MacBook-Pro:~ ashleysalazar$ ls -alh 
total 40 
drwxr-xr-x+ 17 ashleysalazar  staff   544B Apr 14 11:25 . 
drwxr-xr-x   5 root           admin   160B Jan 30 16:04 .. 
ECT.. 
  * The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
Ashleys-MacBook-Pro:~ ashleysalazar$ man 
What manual page do you want? 
 man -a intro Display, in succession, all of the available intro manual pages contained within the manual. It is possible to quit between suc-           cessive displays or skip any of them. 
Or 
-a, --all By default, man will exit after displaying the most suitable manual page it finds.  Using this option forces man to display all the manual pages with names that match the search criteria. mands, allowing them to provide manual pages for each that can be accessed using similar syntax as would be used to invoke the subcommands themselves. 
 
man -l -Tdvi ./foo.1x.gz > ./foo.1x.dvi This command will decompress and format the nroff source manual page ./foo.1x.gz into a device independent (dvi) file. The redi-rection is necessary as the -T flag causes output to be directed to stdout with no pager. The output could be viewed with  a  program such as xdvi or further processed into PostScript using a program such as dvips. 
Or 
-L locale, --locale=locale man will normally determine your current locale by a call to the C function setlocale(3) which interrogates various environment variables, possibly including $LC_MESSAGES and $LANG.  To tempo-rarily override the determined value, use this option to supply a  locale  string  directly  to man.  Note that it will not take effect until the search for pages actually begins. Output such as the help  message will always be displayed in the initially determined locale. 
 
-H[browser], --html[=browser] This option will cause groff to produce HTML output,and will display that output in a web browser. The choice of browser is determined by the optional browser argument if one is provided, by the $BROWSER environment variable, or by a compile-time default if that is unset (usually lynx). This option implies -t,and will only work with GNU troff. 


To recap: -a(everything in the directory) -l(long list) -h(applications/directories) 

   * Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
Ashleys-MacBook-Pro:~ ashleysalazar$ ls / 
Applications etc 
Library home 
Network installer.failurerequests 
System net 
Users private 
Volumes sbin 
bin tmp 
cores usr 
dev var 
  * A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
Ashleys-MacBook-Pro:~ ashleysalazar$ cd / 
Ashleys-MacBook-Pro:/ ashleysalazar$ pwd 
/ 
  * Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
Ashleys-MacBook-Pro:/ ashleysalazar$ cd ~ 
Ashleys-MacBook-Pro:~ ashleysalazar$ pwd 
/Users/ashleysalazar 
  * Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
3,  I have just realized that I must be in Codeanywhere to get these answers. I switch terminals here.
  * Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
Ashleys-MacBook-Pro:Downloads ashleysalazar$ cd .. 
Ashleys-MacBook-Pro:~ ashleysalazar$ cd .. 
I am back in the root directory
  * Press the up arrow on your keyboard. *What just happened?*
The previous command appeared. cd .. 
  * Press the up arrow a few more times. *What do you see?*
I see my previous commands such as: ls, pwd, and cd Downloads 
  * Run the `history` command. *What do you see?*
I see a numerical value of commands I used. 
Cool! 

### Observing the System

  * Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox 
  * Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
No, cabox    pts/1        Apr 14 18:25 (52.161.27.120) 
  * How long has your system been running? Use `uptime` to see, and *paste the result here:*
18:57:27 up  6:37,  1 user,  load average: 0.00, 0.00, 0.00   
  * Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
There appears to be directories of a history of where I have been. I recognized my bluetooth directory from earlier today when I wanted to listen to instructional video. Other roots I have visited are systems and Library. Included are date and time stamps.This is from my personal terminal. From Codeanywhere I see USER, TIME, COMMAND, MEMORY, ECT. Very similar. 
The ps utility displays a header line, followed by lines containing information 
     about all of your processes that have controlling terminals.   
  * Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
I see my systems and directories working in 'real time.' 

### Finding and Viewing Files

  * Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
2 files found:  
cabox@box-codeanywhere:~/workspace/challenge_files$ ls *credit* 
credit_cards.txt  credit_cards2.txt 
  * Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
1.15.2015
  * Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
 1cabox@box-codeanywhere:~/workspace/challenge_files$ find -name modi_laboriosam.txt 
./tmp/modi_laboriosam.txt 
  * Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
cabox@box-codeanywhere:~/workspace/challenge_files$ grep -r WA *.user 
Britt-Erdman.user:O'Harachester, WA 37261 
Lissie-Strosin.user:Jewessfurt, WA 00816-7241 
2 
  * Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
cabox@box-codeanywhere:~/workspace/challenge_files$ grep -r Waldo 
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia. 
File: serial-numbers/eaque_molestiae.txt 

### Pipes and Connecting Commands

  * Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
I see the same content that's in the "challenge_files" 
  * Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
Similar format, shorter list. This list appears to be more like a preview. 
  * Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
1cabox      803  0.0  0.1   8816   760 pts/0    S+   23:14   0:00 grep --color=auto ashlzar 


