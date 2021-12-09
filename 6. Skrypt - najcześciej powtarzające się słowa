#!/bin/bash
while [ -f "$1" ]
do
   echo "Najczesciej powtarzajace slowa w pliku $1 to:"
   cat $1 | tr -s ' ' '\n' | sort | uniq -c | sort -r | head -n 3
   echo " "
   shift
done
