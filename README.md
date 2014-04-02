ECE281_CE4
==========
###PRISM Assembly Language Programming

#####Simple Memory Manipulation
The goal of this program was to write a program that stores the value $9 in location $B0, $8 in $C4 and $B in $CB in $11 lines of code or less
######Code Design
The first step was to find what operation would complete the nessecary tasks. 
From the PRISM Manual I found that LDAI loads the value of the operand into the accumulator and then the STA operation stores the contents of the accumulator into the operand address.
This sequence was repeated the nessecary amount of time to complete the program. The program was completed in exactly $11 lines of code.
```nasm
		   00	   7	LDAI	9	
		   01	   9				
		   02	   D	STA	  B0		
		   03	   0				
		   04	   B				
		   05	   7	LDAI	8	
		   06	   8				
		   07	   D	STA	  C4		
		   08	   4				
		   09	   C				
		   0A	   7	LDAI	B	
		   0B	   B				
		   0C	   D	STA	  CB		
		   0D	   B				
		   0E	   C				
loop		0F	   9	JMP	  loop
		   10	   F				
		   11	   0		
```
