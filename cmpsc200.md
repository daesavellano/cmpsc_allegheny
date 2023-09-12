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
