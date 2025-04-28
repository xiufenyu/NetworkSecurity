# ELF File
    1. What is elf file?
ELF is short for **Executable and Linkable Format**. It’s a format used for storing binaries, libraries, and core dumps on disks in Linux and Unix-based systems. Similar with exe in Windows.   

The ELF header is always available in the ELF file, while the Section header table is important during *link time* to create an executable. On the other hand, the Program header table is useful during *runtime* to help load the executable into memory.

## ELF Header
The ELF header is found at the start of the file. It contains metadata about the file.

## Program Header
The program header table stores information about segments. Each segment is made up of one or more sections. The kernel uses this information at run time. It tells the kernel how to create the process and map the segments into memory.

## Section
The code and data is divided into contiguous non-overlapping chunks called sections. Important sections:  

| Section      | Description                                                    |
| -------------| ---------------------------------------------------------------|
| **.symtab**  | symbol table                                                   |
| **.dynsym**  | symbols needed for dynamic-linking                             |
| **.text**    | is where the main code of the program resides                  |
| **.bss**     | contains uninitialized data (Type SHT_NOBITS)                  |
| **.data**    | Program initialized data, it is writable. (Type SHT_PROGBITS). |
| **.rodata**  | It is read-only data, such as strings used by the code.        |


## Section Header
The section header stores information about sections. This information is used during dynamic link time, just before the program is executed.


:bulb: **Tip:** Segments are exclusively use at *runtime* while sections are exclusively used at *link time*.



ref: 
[1] https://www.baeldung.com/linux/executable-and-linkable-format-file     
[2] https://gist.github.com/x0nu11byt3/bcb35c3de461e5fb66173071a2379779       
