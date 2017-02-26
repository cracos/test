# Atop 
Is a ASCII full-screen performance monitor which can log and report the activity of all server processes. One feature I really like is that atop will stay *active* in the background for long-term server analysis (up to 28 days by default). Other advantages include:

> * Shows resource usage of ALL _processes_, even those that are closed/completed.
* Monitors _threads_ within processes & ignores processes that are unused.
* Accumulates _resource usage_ for all processes and users with the same name.
* _Highlights critical_ resources using colors (red).
* Will add or remove columns as the size of the display window changes.
* Includes _disk I/O_ and _network_ utilization.
* Uses [*netatop*](http://www.atoptool.nl/netatop.php "netatop page") kernel module to monitor TCP & UDP and network bandwidth.  

Once atop is launched, by default it will show system activity for CPU, memory, swap, disks and network in 10 second intervals. In addition, for each process and thread you can analyse CPU utilization, memory consumption, disk I/O, priority, username, state, and even exit codes.

__Note__: go through the [*command’s man page*](https://linux.die.net/man/1/atop "page manual of command's") for more details on the output of the command.

### Install atop on Debian/Ubuntu Linux
```bash
apt-get install atop
```
Once installed, you can launch it similar to top using:
```
atop
```
Description of some components of the main window: 

![line one](/atopImages/l1.png)
![line two](/atopImages/l2.png)
![line tree](/atopImages/l4.png)
![line four](/atopImages/l3.png)
![line five](/atopImages/l5.png)
![line six](/atopImages/l6.png)
![line seven](/atopImages/l7.png)

### Other useful commands:  

>Launch with average-per-second total values:
__atop -1__  
Launch with active processes only:
__atop -a__  
Launch with command line per process
__atop -c__  
Launch with disk info
__atop -d__  
Launch with memory info
__atop -m__  
Launch with network info
__atop -n__  
Launch with scheduling info
__atop -s__  
Launch with various info (ppid, user, time)
__atop -v__  

Once atop is running, press the following shortcut keys to sort processes:

* a – sort in order of most active resource.
* c – sort in order of command line of the process.
* d – sort in order of disk activity.
* m – sort in order of memory usage
* n – sort in order of network activity