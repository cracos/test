# htop
__interactive process viewer__
### Synopsis
```vim
htop [-dChusv]
```
### Description
Htop is a free (GPL) ncurses-based process viewer for Linux. It is similar to top, but allows you to scroll vertically and horizontally, so you can see all the processes running on the system, along with their full command lines. Tasks related to processes (killing, renicing) can be done without entering their PIDs.

### Installation
In Debian you can fetch htop by typing:

```vim
apt-get install htop 
```
By Sources, building htop is straightforward, as it uses GNU Autotools: the typical``./configure; make; sudo make install should do the trick.``  
Check out the [lastest version](http://hisham.hm/htop/releases) at the project page.  

Run the configure script to prepare for compilation.
```vim
./configure
```
If ./configure shows error install the required package``libncursesw5-dev``
```vim
sudo apt-get install libncursesw5-dev
```
By default, htop will be installed under ``/usr/local/bin``. If you want to change installation location to something else (e.g., ``/usr/bin``), run configure script with "``--prefix``" option instead. For example:
```vim
./configure --prefix=/usr 
```
Finally, build and install htop as follows.
```vim
make
sudo make install
```
After installation, launch htop by entering:
``` 
htop
```
Default htop screen:
![Default screen](/htopImages/screenshot_01.png)  

# Command-line Options

Mandatory arguments to long options are madatory for short options too.  
__-d --delay=DELAY__  
Delay between updates, in tenths of seconds ``atop -d 3``  
__-C --no-color --no-colour__  
Start htop in monochrome mode ``atop -C``  
![No color](/htopImages/screenshot_02.png)  
__-h --help__  
Display a help message and exit ``atop -h``  
![Help](/htopImages/screenshot_03.png)  
__-u --user=USERNAME__  
Show only the processes of a given user ``atop -u username``  
![Username](/htopImages/screenshot_04.png)  
__-p__  
Start working thread for pagemap memory stats ``atop -p PIDnumber``  
![PID number](/htopImages/screenshot_05.png)  
__-s --sort-key COLUMN__  
Sort by this column (use --sort-key help for a column list) ``atop -s nameofcolumn``  
![Sort](/htopImages/screenshot_06.png)  
__-v --version__  
Output version information and exit  ``atop -v``  
![Version](/htopImages/screenshot_07.png)  

# Interactive Commands
The following commands are supported while in htop:  
__Arrows, PgUP, PgDn, Home, End__  
Scroll the process list.
__Space__  
Tag or untag a process. Commands that can operate on multiple processes, like "kill", will then apply over the list of tagged processes, instead of the currently highlighted one.  
__U__  
Untag all processes (remove all tags added with the Space key).  
__s__  
Trace process system calls: if strace(1) is installed, pressing this key will attach it to the currently selected process, presenting a live update of system calls issued by the process.  
__l__  
Display open files for a process: if lsof(1) is installed, pressing this key will display the list of file descriptors opened by the process.  
__F1, h, ?__  
Go to the help screen  
__F2, S__  
Go to the setup screen, where you can configure the meters displayed at the top of the screen, set various display options, choose among color schemes, and select which columns are displayed, in which order.  
__F3, /__  
Incrementally search the command lines of all the displayed processes. The currently selected (highlighted) command will update as you type. While in search mode, pressing F3 will cycle through matching occurrences.  
__F4, \\__  
Incremental process filtering: type in part of a process command line and only processes whose names match will be shown. To cancel filtering, enter the Filter option again and press Esc.  
__F5, t__  
Tree view: organize processes by parenthood, and layout the relations between them as a tree. Toggling the key will switch between tree and your previously selected sort view. Selecting a sort view will exit tree view.  
__F6, <, >__  
Select a field for sorting. The current sort field is indicated by a highlight in the header  
__F7, ]__  
Increase the selected process's priority (subtract from 'nice' value). This can only be done by the superuser.  
__F8, [__  
Decrease the selected process's priority (add to 'nice' value)  
__F9, k__  
"Kill" process: sends a signal which is selected in a menu, to one or a group of processes. If processes were tagged, sends the signal to all tagged processes. If none is tagged, sends to the currently selected process.  
__F10, q__  
Quit  
