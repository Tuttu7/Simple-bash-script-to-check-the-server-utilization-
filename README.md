###  This script displays Disk, memory utilization, last logins, most consuming process,load average & uptime of the Ubuntu based system

```
#!/bin/bash
# This script displays Disk, memory utilization of the Ubuntu based system along with last logins, most consuming process & uptime

date;

echo " "

echo "uptime : "

echo " "

uptime | xargs | awk '{ print $1 " "  $2 " " $3 }'


echo "-----------------------------"

echo "currently connected : "

echo " "

w | xargs | awk '{ print $4 " " $5 }'

echo "-----------------------------"

echo "last logins : "

echo " "

last -a | head -3

echo "------------------------------"

echo " Disk & memory usage : "

echo " "

free -mh | xargs | awk '{ print "Total/Free memory : " $8 " / " $12 " MB " }'

df -H | xargs | awk '{ print "Total size / Used / Available : "  $21 " / " $22 " / " $23}'


echo "-------------------------------"


echo " Load average : " 

w | xargs | awk '{ print $8 $9 $10 }'

echo "-------------------------------"

echo " Most consuming process :  "

echo " "


top -b | head -10 | tail -4

```
