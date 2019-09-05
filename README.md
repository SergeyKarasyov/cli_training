# cli_training  

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

