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


### Interactive commands:
__g__ --> Show generic output (default):
![g command](/atopImages/InteractiveCommands_g.png)

__m__ --> Show memory related output:
![m command](/atopImages/InteractiveCommands_m.png)

__d__ --> Show disk-related output:
![d command](/atopImages/InteractiveCommands_d.png)

__n__ --> Show network related output:
![n command](/atopImages/InteractiveCommands_n.png)

__s__ --> Show sheduling characteristics:
![s command](/atopImages/InteractiveCommands_s.png)

__v__ --> Show various process characteristics:
![v command](/atopImages/InteractiveCommands_v.png)

__c__ --> Show the command line of the process:
![c command](/atopImages/InteractiveCommands_c.png)

__o__ --> Show the user-defined line of the process:

### Acumulated commands:
__u__ --> Show the process activity acumulated per user:
![u command](/atopImages/InteractiveCommands_u.png)

__p__ --> Show the process activity acumulated per program:
![p command](/atopImages/InteractiveCommands_p.png)

### Sort current list commands:

__C__ --> In order of CPU consumption(default):
![C command](/atopImages/SortCurrentListCommands_C.png)

__M__ --> In order of resident memory consumption:
![M command](/atopImages/SortCurrentListCommands_M.png)

__D__ --> In order of disk accesses isued:
![D command](/atopImages/SortCurrentListCommands_D.png)

__N__ --> In order of network packets received/transmited:
![N command](/atopImages/SortCurrentListCommands_N.png)

__A__ --> In order of the most busy sistem resource:
![A command](/atopImages/SortCurrentListCommands_A.png)

### Selection commands:
__U__ --> Focus on specific username:
![U command](/atopImages/SelectionsCommands_U.png)

__P__ --> Focus on specific process name:
![P command](/atopImages/SelectionsCommands_P.png)

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
