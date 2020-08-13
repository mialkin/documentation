# Bash

## Power

Command | Description
:-|:-
uptime | How long the system is running. <br/>This command returns set of values that involve, the current time, and the amount of time system is in running state, number of users currently logged into, and the load time for the past 1, 5 and 15 minutes respectively
sudo&nbsp;systemctl&nbsp;reboot | Reboot the system

## Memory

Command | Description
:-|:-
free -m | Display amount of free and used memory in the system
top&nbsp;&#8209;o&nbsp;%MEM | Display Linux processes sorted by memory
htop | Interactive process viewer. It is similar to top, but allows you to scroll vertically and horizontally, so you can see all the processes running on the system, along with their full command lines, as well as viewing them as a process tree, selecting multiple processes and acting on them all at once.<br/>Tasks related to processes (killing, renicing) can be done without entering their PIDs.

## Disk

Command | Description
:-|:-
df -h . | Free disk space
htop | Interactive process viewer

## Network

Command | Description
:-|:-
curl ident.me | Public IP addresses of machine
scp /file/to/send username@remote:/where/to/put <br/> scp username@remote:/file/to/send /where/to/put| Secure copy

## OS

Command | Description
:-|:-
lsb_release -a| Print certain LSB (Linux Standard Base) and distribution-specific information
hostnamectl | OS info
cat /etc/*-release | OS name and version
uname -a | Kernel version

## Shell

Command | Description
:-|:-
cat /etc/shells | Available shells
echo $SHELL | Display what shell the terminal opened with
bash | Switch to a bash or different shell type its name at the terminal
echo $0 | Currently used shell

## See also

[systemd](https://wiki.archlinux.org/index.php/systemd)