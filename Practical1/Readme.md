# Practical 1
## Ricsv Toolchain Installation using VSD

### Steps
1. You need atlest 100Gb space on your pc drive.
2. Download VDI file from following link.
* https://forgefunder.com/~kunal/riscv_workshop.vdi

3. Install Oracle Virtual Box in your pc & select these options.

* Type- Linux
* Version- Ubuntu 18.04 LTS (Bionic Beaver)(64-bit)
* Base Memory- 4Gb
* Processor- 2 CPU
* Existing hard disk file- donloaded VDI file
4. Setup Done!

## Testing toolchain using VDI

## Write a C code for sum of 1 to n numbers

![c code for summation](./Images/vsd1.PNG)

## Compile the code using following command
* riscv64-unknown-elf-gcc -O1 -march=lp64 -march=rv64i -O sum1ton.o sum1ton.c

![compile code](./Images/vsdgcc.PNG)

![](./Images/vsdo1.PNG)
![](./Images/vsdofast.PNG)

* Successfully Done Here!!