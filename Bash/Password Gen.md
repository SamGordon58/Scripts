```
#! /bin/bash
#
#

echo How many words would you like to use?
read length
x=0
password=()

while [ $x -ne $length ]
        do
        numbers=$(($RANDOM%20))"-"$(($RANDOM%20))"-"$(($RANDOM%20))
        #echo $numbers
        x=$((x+1))
        password+=(x)
        echo ${passwords[@]}
done
```