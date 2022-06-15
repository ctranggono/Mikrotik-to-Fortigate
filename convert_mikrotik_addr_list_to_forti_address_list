#!/bin/sh

file="address_list_1.csv"
for line in $(cat $file)
do
	comment="$(echo $line | cut -d';' -f1)" 
	name="$(echo $line | cut -d ';' -f2)"
	subnet='/'
	if [[ $name =~ $subnet ]];
	then
		ip=$name
	else
		ip="$name/32"
	fi

	echo "edit \"$name\""
	echo "  set subnet \"$ip\""
	echo "  set comment \"$comment\""
	echo "next"
done
