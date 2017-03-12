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
![Default screen](/htopImages/defaultScreen.png)

# Command-line Options

Mandatory arguments to long options are madatory for short options too.  
__-d --delay=DELAY__  
Delay between updates, in tenths of seconds ``atop -d 3``  
__-C --no-color --no-colour__  
Start htop in monochrome mode ``atop -C``  
__-h --help__  
Display a help message and exit ``atop -h``  
__-u --user=USERNAME__  
Show only the processes of a given user ``atop -u username``  
__-p__  
Start working thread for pagemap memory stats ``atop -p PIDnumber``  
__-s --sort-key COLUMN__  
Sort by this column (use --sort-key help for a column list) ``atop -s nameofcolumn``   
__-v --version__  
Output version information and exit  ``atop -v``  
