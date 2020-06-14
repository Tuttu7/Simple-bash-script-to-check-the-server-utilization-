###  This script displays Disk, memory utilization, last logins, most consuming process,load average & uptime of the Ubuntu based system

```
seperator="--------------------------"

uptime=`uptime | xargs | awk '{ print $1 " "  $2 " " $3" "$4 }'`
currently_connected=`w | xargs | awk '{ print $4 " "$5 " " $6 }'`
disk_usage=`df -H | xargs | awk '{ print "Total size / Used / Available : "  $21 " / " $22 " / " $23}'`
memory_usage=`free -mh | xargs | awk '{ print "Total/Free memory : " $8 " / " $12 " MB " }'`
load_average=`w | xargs | awk '{ print  $8 $9 $10}'`

date;

echo " "

echo "uptime : "

echo " "

echo $uptime


echo $seperator

echo "currently connected : "

echo " "

echo $currently_connected

echo $seperator

echo "last logins : "

echo " "


last -a | head -3

echo $seperator

echo " Disk & memory usage : "

echo " "

echo $disk_usage

echo $memory_usage


echo $seperator


echo " Load average : " 

echo $load_average

echo $seperator

echo " Most consuming process :  "

echo " "




top -b | head -10 | tail -4


```
