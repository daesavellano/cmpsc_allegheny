# CMPSC 200 | Computer Organization

## Links
* [Course Calendar](https://docs.google.com/spreadsheets/d/1GfsuIb8FTavf8DxEMHkgFUKRcM72-BKYz4IVLhSMCPg/edit#gid=0)
* [CARDIAC Manual](https://drive.google.com/file/d/1QoDsEtMVLv6DjEOr7LzVQkzStC2F_xC6/view)
* [CARDIAC Simulator](https://www.cs.drexel.edu/~bls96/museum/cardsim.html)

## CARDIAC

**Instruction Set Architecture (ISA)**: set of architecture based on processor architecture
* ex. Input → Clear accumulator and add → Add → Store → Output → Halt

**Operational codes** for SIMCO2
* **0 INP** Input
* **1 CLA** Clear and Add
* **2 ADD** Add
* **3 TAC** Test Accumulator Contents → is the acc negative? if yes, go somewhere else. if positive, carry on
* **4 SFT** Shift
* **5 OUT** Output
* **6 STO** Store
* **7 SUB** Subtract
* **8 JMP** Unconditional Jump → can be used for loops
* **9 HRS** Halt and Reset

**Data Word** — numbers that MEAN
* 101 would just be the number 101
**Instruction Word** — numbers that DO
* 101
    * first digit: operational code → 1 = CLA
    * last two digits: memory location → 01 = address 01
    * ex.
 
|ADDRESS              |CONTENTS             |COMMENTS                     |
|:--------------------|:--------------------|:----------------------------|
|17                   |034                  |INP in memory slot 34        |
|18                   |035                  |INP in memory slot 35        |
|19                   |134                  |CLA val in memory 34         |
|20                   |235                  |ADD val in memory 35         |
|21                   |636                  |STO ACC in memory slot 36    |
|22                   |536                  |OUT memory 36                |
|23                   |900                  |Halt and reset               |

**The SFT Instruction**
* last two digits do not refer to memory locations
* overflowing digits are irretrievable
* 413
  * 4: SFT
  * 1: left shift 1 space
  * 3: right shift 3 spaces
* 421
  * reverses
  * ex. 123 → 321
* _Magic Nines_
  * take a number, flip it, get the absolute value
  * middle digit is always 9
  * outer digits always add up to 9

**Cell 99**: turns into JMP command for the cell immediately after you JMPd

## Assembly

```
.thumb_func		    	@ Necessary because sdk uses BLX
						@ at symbol stands for comments
.global main	   	 	@ Provide program starting address so it knows where to go
						@ Required for build

main:					@ Required for build
	BL	stdio_init_all	@ Branch and link, initialize uart or usb
	LDR R0, =helloworld	@ Load register (LDR) of helloworld string into memory
	BL	printf			@ use BL instruction to call pico_printf (a C call)
	SVC	0				@ Service call to end program
	
helloworld: 	.asciz  "Hello, World!\n"
```
### registers vs memory
**registers**
- on the processor, but not the processor
- called by R[0-12]
- operate on data
- limited to 32 bytes of instruction and/or storage
**memory**
- outside of processor
- called by mnemonics like 0x123f
- cannot be operated on
    - can only store

### ARMv6 Assembly Opcodes
```
mov    r0, #2		   @ moves the value 2 into register 0
mov    r1, r0		   @ copies the value 2 from register 0 to register 1					@ r0 and r1 are both equal to 2 now
add    r0, r1, r2		@ r1 + r2 = r0
add    r1 , r2		   @ r1 + r2 = r1
mov    r0, #’A’		@ load value of A (65) into r0
ldr    r1, =outstr	@ load address of outstr into r1
strb   r0, [r1]		@ store the first byte in r0 into the address starting at r1
strb   r0, r1		   @ does not work
```
