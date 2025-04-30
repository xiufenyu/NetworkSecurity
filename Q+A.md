🔹 What is a NOP Sled?         
A NOP sled is a sequence of NOP (No Operation) instructions placed in memory, leading to the actual malicious payload (like shellcode).    
    The idea is to "slide" into the payload even if the exact memory address isn’t perfectly guessed.   
    In x86 assembly, the NOP instruction (0x90) does nothing and just advances the instruction pointer.

🔹 How It Works (in a Buffer Overflow)   
The attacker overflows a buffer and overwrites the return address on the stack.    
    Instead of needing to jump to the exact start of the shellcode, the attacker makes the return address point anywhere in a long NOP sled.    
    The processor "slides" through the NOPs until it hits the payload.    
