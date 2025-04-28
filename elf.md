# ELF File
    1. What is elf file?
ELF is short for **Executable and Linkable Format**. It’s a format used for storing binaries, libraries, and core dumps on disks in Linux and Unix-based systems. Similar with exe in Windows.   
The ELF header is always available in the ELF file, while the Section header table is important during link time to create an executable. On the other hand, the Program header table is useful during runtime to help load the executable into memory.

## ELF Header

## Program Header

## Section

## Section Header


## Segment vs Section

Segments are exclusively use at runtime while sections are exclusively used at link time   


ref: https://www.baeldung.com/linux/executable-and-linkable-format-file

https://gist.github.com/x0nu11byt3/bcb35c3de461e5fb66173071a2379779
