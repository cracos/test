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

### Install atop on Debian/Ubuntu Linux
```bash
apt-get install atop
```
Once installed on any distro, you can launch it similar to top using:
```
atop
```
### Other useful commands:  
Launch with average-per-second total values:
```
atop -1
```
Launch with active processes only:
```
atop -a
```
Launch with command line per process
```
atop -c
```
Launch with disk info
```
atop -d
```
Launch with memory info
```
atop -m
```
Launch with network info
```
atop -n
```
Launch with scheduling info
```
atop -s
```
Launch with various info (ppid, user, time)
```
atop -v
```
Once atop is running, press the following shortcut keys to sort processes:

* a – sort in order of most active resource.
* c – revert to sorting by cpu consumption (default).
* d – sort in order of disk activity.
* m – sort in order of memory usage
* n – sort in order of network activity