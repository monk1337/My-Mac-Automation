# My-Mac-Automation
Scripts to automate tasks in Mac




## Global step
```shell
Go to /usr/local/bin and create following scripts
```



1. Kill the process on particular port


```shell
#!/bin/bash
touch temp.text
lsof -n -i4TCP:$1 | awk '{print $2}' > temp.text
pidToStop=`(sed '2q;d' temp.text)`
> temp.text
if [[ -n $pidToStop ]]
then
kill -9 $pidToStop
echo "Congrates!! $1 is stopped."
else
echo "Sorry nothing running on above port"
fi
rm temp.text
```

# usage
``` stop 8123 ```
