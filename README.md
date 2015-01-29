# log2mail

Sometimes you want to be notified in "realtime" of errors messages in you logs.
This is what log2mail is made for...
It monitor a log file and if a given REGEXP is matched send it by email

## usage

log2mail is made of three files

`/etc/init.d/logMonitor`:
This is an init script that will start monitoring your log file
It tails the monitored log file to a temporary location
It expect to find the two following files

`/usr/local/bin/log2mail`:
is called by inotify when data is written to the temporary log file
Look for a given REGEXP in the temporary log file and send the file by mail if matched
then delete the file

`/etc/logMonitor.conf`:
Configure the above scripts (file to monitor, regexp, etc)

## requirements
inotify-tools
tail
grep
mailx

## TODO
make all of this simpler!!
