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
Check out the [lastest version](http://hisham.hm/htop/releases) at the project page.

