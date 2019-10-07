# cli_training  
# test it with https://www.tutorialspoint.com/execute_bash_online.php

# vim   
* start of line - 0  
* end of line - $  
* next word - w  
* previous word - b  
* last line - G  
* move to end of line and insert mode - A  
* show line numbers - :set number  
* syntax highlight - :syntax on  
* set spaces amount for tab - :set tabstop=2  
* set autoindent - :set autoindent  
* check vimrc used - :echo $MYVIMRC  
* select text - V and arrow down or up
* delete selected text - d
* clean all in vim: esc -> g -> g -> d -> G

# cli
* permissions: 7(rwx),6(rw),5(rx),4(r),3(wx),2(w), 1(x), 0(no)

# bash
* variable string(no spaces near equal sign)
``` bash 

myName="Name"
```
* const 
``` bash 

declare -r NUM1=5
```
* arithmetics
``` bash 
num2=4
num3=$((NUM1+num2))
echo "5 + 4 = $num3"
echo $((5**2))
echo $((5%2))
rand=5
let rand+=4
echo "$rand"
echo "rand++ = $(( rand++ ))"
echo "++rand = $(( ++rand ))"
```
* float points
``` bash 
num7=1.2
num8=3.4
```
* python
``` bash 
num9=$(python -c "print $num7+$num8")
echo "$num9"
```
* cat multiline
``` bash 
cat<<END
This text 
prints on
many lines
END
```
* function
``` bash 
getDate(){
  date
  return 
}
getDate
```
* global and local variables 
``` bash
name="NameGlobal"
demLocal(){
  local name="nameLocal" #without local it will override name variable
  return
}
demLocal
echo "$name"
```
* function with arguments
``` bash
getSum(){
  local num3=$1
  local num4=$2
  local sum=$((num3+num4))
  echo $sum
}
num1=5
num2=6
sum=$(getSum num1 num2)
echo "$sum"
```

* user input
``` shell
read -p "What is your name?" name
echo $name
```
* condition
```shell
read -p "How old are you?" age
if[ $age -ge 16 ]
then
  echo "you can drive"
elif [ $age -eq 15]
then 
  echo "you can drive next year"
else
  echo "you can't drive next year"
fi
```

```shell
read -p "enter num: " num
if (( num == 10 )); then
  echo "Num is 10"
fi
if (( (( num % 2 )) == 0 )); then
  echo "even"
fi

if (( (( num > 2 )) && (( num == -1 ))  )); then
  echo "smth"
fi
```
* if string
```shell

if ["$str1"] ; then
    echo "str1 is not null"
fi
if [-z "$str1"] ; then
    echo "str1 has no value"
fi

if [ "$str1"=="$str2" ] ; then
    echo "eq"
fi
```

* if file exists (-x - executable, -r - readable, - f - reg file, -w - writable, -d - dir, -L - link, -S - socket, - G - owned by group, -O - user owned )
```shell
file1 = "file1.txt"
if [-e "$file1"]; then
  echo "$file1 exists"
fi
```

* regex 
```shell
read -p "validate a date: " date
pat="^[0-9]{8}$"
if [[ $date =~ $pat ]]; then
  echo "date is ok"
fi
```
* remove spaces
```shell
num1=${num1//[[:blank:]]/}
```
* substitute in string
```shell
samp_string="the dog"
echo "{samp_string//dog/cat}"
```
* switch
```shell
case $num in
[0-5])
  echo "less than 5"
  ;;
6) 
  echo "more"
  ;;
[6-9]|1[0-8]
  echo "even more"
  ;;
*)
  echo "problem"
  ;;
esac  
```
* ternary operator
```shell
((age >=18?(can_vote=1):(can_vote=0)))
```
* parameter expansion
```shell
string="a rand string"
echo "String length : ${#string}"
echo "from second symbol till end ${string:2}"
echo "symbols ${string:2:7}"
echo "symbols after 'A ' ${string#*A }"
```

* while loop
```shell
num=1
while [$num -le 10]; do
  echo $num
  num=$((num+1))
  if(( ((num%2)) == 0)); then
    num=$((num + 1))
    continue
  fi
    if(( ((num%2)) == 1)); then
    break
  fi
done
```
* untill
```shell
until [$num -gt 10]; do
    echo $num
done
```
* another while reading file
```shell
while read avg rbis hrs; do 
 printf "Avg: ${avg}\nRBIs: ${rbis}\n HRs: ${hrs}\n"
done < barry_bonds.txt 
```
* arrays
```shell
nums=(1 2 -3 -4)
echo "${nums[0]}"
for i in ${nums[*]}; do
  echo $i
done
for i in ${nums[@]}; do
  echo $i
done
echo "Array length: ${#nums[@]}"
echo "Index 3 length: ${#nums[3]}"
sorted_nums=($(for i in "${nums[@]}"; do
  echo $i;
done | sort))
for i in ${sorted_nums[*]}; do
  echo $i
done
```
```
echo "1st arg: $1"
sum=0
//$# - number of args
while [[ $# -gt 0 ]]; do
  num=$1
  sum=$((sum+num))
  shift// moves argument two into position 1
done
```
