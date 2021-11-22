# My-Mac-Automation
Scripts to automate tasks in Mac




## Kill the process on particular port

```shell
Go to /usr/local/bin and run nano stop
```
stop script

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

#### usage
``` stop 8123 ```


## script to open any terminal and perform task
Open automator to create an app

```shell

if application "Terminal" is running then
	tell application "Terminal"
		# do script without "in window" will open a new window     
		do script "aa"
		activate
	end tell
else
	tell application "Terminal"
		# window 1 is guaranteed to be recently opened window     
		do script "aa" in window 1
		activate
	end tell
end if

```


## Show the size of current directory folders in mb 

```shell
Go to /usr/local/bin and run nano space
```

```shell
echo <password> | sudo -S du -hs * | sort -hr
```

#### usage
``` space ```
