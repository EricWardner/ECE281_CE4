ECE281_CE4
==========
###PRISM Assembly Language Programming

#####Simple Memory Manipulation
The goal of this program was to write a program that stores the value $9 in location $B0, $8 in $C4 and $B in $CB in $11 lines of code or less
######Code Design
The first step was to find what operation would complete the nessecary tasks. 
From the PRISM Manual I found that LDAI loads the value of the operand into the accumulator and then the STA operation stores the contents of the accumulator into the operand address.
This sequence was repeated the nessecary amount of time to complete the program. The program was completed in exactly $11 lines of code.
```
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
#####Mathmatics
The goal of this program was to write a program that retrieves a value from location $B0, doubles it, and subtracts 4 then outputs it to port 2 in $0c lines of code or less
######Code Design
This program required some thinking to get under the desired lines of code. Initaily my thought was to use NEG to complete the task but after realizing NEG simply converted the number to two's compiment I loaded the 4 to the accumulator as C (two's compliment) then added the value from $B0. OUT was used to output the value from the accumulator to the port.
```
		   00	   7	LDAI	C	
		   01	   C				
		   02	   E	ADDD	B0	
		   03	   0				
		   04	   B				
		   05	   E	ADDD	B0	
		   06	   0				
		   07	   B				
		   08	   4	OUT		2	
		   09	   2				
loop		0A	   9	JMP		loop
		   0B	   A				
		   0C	   0					
```
#####Loops
The goal of this program was to toop through the output ports decrementing by one on each output.
######Code Design
This program required a sequence of IN, OUT, then decrament by using (ADDI F). then looping back to the top of the sequence. the code looked as follows
```
		   00	   5	IN	3	
		   01	   3			
loop	   02	   4	OUT	0	
		   03	   0			
		   04	   6	ADDI	F
		   05	   F			
		   06	   4	OUT	1	
		   07	   1			
		   08	   6	ADDI	F
		   09	   F			
		   0A	   4	OUT	2	
		   0B	   2			
		   0C	   6	ADDI	1
		   0D	   1			
		   0E	   9	JMP	loop
		   0F	   2			
		   10	   0								
```
