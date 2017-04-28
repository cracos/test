# Atop 
Is a ASCII full-screen performance monitor which can log and report the activity of all server processes. One feature I really like is that atop will stay *active* in the background for long-term server analysis (up to 28 days by default). Other advantages include:

> * Shows resource usage of ALL _processes_, even those that are closed/completed.
* Monitors _threads_ within processes & ignores processes that are unused.
* Accumulates _resource usage_ for all processes and users with the same name.
* _Highlights critical_ resources using colors (red).
* Will add or remove columns as the size of the display window changes.
* Includes _disk I/O_ and _network_ utilization.
* Uses [*netatop*](http://www.atoptool.nl/netatop.php "netatop page") kernel module to monitor TCP & UDP and network bandwidth.  

Once atop is launched, by default it will show system activity for CPU, memory, swap, disks and network in 10 second intervals. In addition, for each process and thread you can analyze CPU utilization, memory consumption, disk I/O, priority, username, state, and even exit codes.

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

__s__ --> Show scheduling characteristics:
![s command](/atopImages/InteractiveCommands_s.png)

__v__ --> Show various process characteristics:
![v command](/atopImages/InteractiveCommands_v.png)

__c__ --> Show the command line of the process:
![c command](/atopImages/InteractiveCommands_c.png)

__o__ --> Show the user-defined line of the process:

### Accumulated commands:
__u__ --> Show the process activity accumulated per user:
![u command](/atopImages/InteractiveCommands_u.png)

__p__ --> Show the process activity c per program:
![p command](/atopImages/InteractiveCommands_p.png)

### Sort current list commands:
__C__ --> In order of CPU consumption(default):
![C command](/atopImages/SortCurrentListCommands_C.png)

__M__ --> In order of resident memory consumption:
![M command](/atopImages/SortCurrentListCommands_M.png)

__D__ --> In order of disk accesses issued:
![D command](/atopImages/SortCurrentListCommands_D.png)

__N__ --> In order of network packets received/transmitted:
![N command](/atopImages/SortCurrentListCommands_N.png)

__A__ --> In order of the most busy system resource:
![A command](/atopImages/SortCurrentListCommands_A.png)

### Selection commands:
__U__ --> Focus on specific username:
![U command](/atopImages/SelectionsCommands_U.png)

__P__ --> Focus on specific process name:
![P command](/atopImages/SelectionsCommands_P.png)

### Presentation commands (toggle):
__a__ --> All processes/only active processes will be shown

__f__ --> Fixate on static range of header-lines: Only active system-resources/inactive system resources will be shown

__x__ --> Colors/no colors to indicate high occupation

__1__ --> Show average-per-second I.S.O. total values

__y__ --> show the individual treads within a process
![y command](/atopImages/presentationCommands_y.png)

### Screen-Handing:
__^L__ --> Redraw the screen

__^F__ --> Show next page in the process list

__^B__ --> Show previous page in the process list

### Miscellaneous commands:
__i__ --> Change interval timer of the samples

__t__ --> Manual trigger to force next sample

__r__ --> Rese counters to boot time values

__z__ --> Pause-button for freeze current sample

__l__ --> Limited lines per CPU-disk and interface sources

__k__ --> Kill a process

__V__ --> Version information

__q__ --> Quit this

## RAW DATA STORAGE
Atop can store the system and process level statistics in	compressed binary format	in a raw	file with the flag	__-w__ followed by the __filename__. If this file already exists and is recognized	as a raw	data file, atop will append new samples to the file (starting with a sample which reflects the activity since boot); if the file does not exist, it will be created.

A raw file can be read and visualized again with the flag __-r__ followed by the __filename__. If no filename is specified, the file
/var/log/atop/atop_YYYYNMDC is opened for input (where YYYYNMDC are digits representing the current date).

### Raw file viewing:
__t__ --> Show next sample in raw file

__T__ --> Show previous sample in raw file

__b__ --> Branch to certain time in raw file

__r__ --> Rewind to begin of raw file
