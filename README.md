#!/bin/bash
przerw="=========="
function Hello()
{
    echo "Hello World"
    echo $przerw
}

function File()
{
    echo "XD" > file.txt
    echo "success"
    echo $przerw
}

function Statement()
{
    count=10
    
    if (( $count < 9 ))
    then
        echo "first condition is true"
        
    elif (( $count > 9 ))
    then
        echo "second condition is true"
    
    else
        echo "the condition is false"
    fi
    echo $przerw
}

function AndOperator()
{
    age=30
    
    if (( $age > 18 )) && (( $age < 40 ))
    then
        echo "Age is correct"
    else
        echo "Age is not correct"
    fi
    echo $przerw
}

function OrOperator()
{
    age=30
    
    if (( $age > 18 )) || (( $age < 40 ))
    then
        echo "Age is correct"
    else
        echo "Age is not correct"
    fi
    echo $przerw
}

function WhileLoop()
{
    number=1
    while (( $number <= 3 ))
    do
        echo "$number"
        number=$(( number+1 ))
    done
    echo $przerw
}

function UntilLoop()
{
    number=1
    until (( $number >= 3 ))
    do
        echo "$number"
        number=$(( number+1 ))
    done
    echo $przerw
}

function ForLoop()
{
    for (( i=1; i<=4; i++ ))
    do
        if [ $i -eq 1 ] || [ $i -eq 4 ]
        then
            continue
        fi
        echo $i
    done
    echo $przerw
}

#function InputFile()
#{
#    while read line
#    do
#        echo "$line"
#    done < "${1:-/dev/stdin}"
#}

function OutputFile()
{
    ls -al >& file1.txt
    echo "success"
    echo $przerw
}

function Pipes()
{
    MESSAGE="Hello World"
    export MESSAGE
    ./secondScript.sh
    echo $przerw
}

function StringProcessing()
{
    echo "enter 1st string"
    read st1
    echo "enter 2nd string"
    read st2
    if [ "$st1" \< "$st2" ]
    then
        echo "$st1 is smaller than $st2"
    elif [ "$st1" \> "$st2" ]
    then
        echo "$st2 is smaller than $st1"
    else 
        echo "both string are equal"
    fi
    echo $przerw
}

function SmallToLarge()
{
    echo "enter word"
    read word
    echo ${word^}
    echo ${word^^}
    echo $przerw
}

function NumbersAndArithmetic()
{
    
    n1=4
    n2=20
    
    echo $(expr $n1 + $n2)
    echo $(expr $n1 - $n2)
    echo $(expr $n1 \* $n2)
    echo $(expr $n1 / $n2)
    echo $(expr $n1 % $n2)
    echo $przerw
}

function main()
{
    Hello
    File
    Statement
    AndOperator
    OrOperator
    WhileLoop
    UntilLoop
    ForLoop
    #InputFile
    OutputFile
    Pipes
    StringProcessing
    SmallToLarge
    NumbersAndArithmetic
}  
main
