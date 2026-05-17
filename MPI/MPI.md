
# Components of microprocessor
- **Arithmetic and Logic Unit (ALU):** Often referred to as the **brain of the computer**, this unit is where all computing functions are performed. It executes **arithmetic operations** (such as addition and subtraction) and **logical operations** (such as AND, OR, and Exclusive-OR) on data received from memory or an input device. Internal components like the Accumulator (which stores the results of operations) and Flag registers are part of the ALU.
- **Register Array:** This component consists of **small, internal memory locations** used to temporarily store and transfer data and instructions that are currently being executed. It includes various **general-purpose registers** (typically identified by letters like B, C, D, E, H, and L). Programmers can use these registers to hold 8-bit data, or combine them into specific pairs (like BC, DE, or HL) to handle 16-bit operations.
- **Control Unit:** This unit acts as the internal coordinator, providing the **necessary timing and control signals** for all operations. It **controls and executes the flow of data** between the microprocessor, memory, and peripheral devices. When an instruction is decoded, the control unit essentially opens or closes internal connections to ensure data is routed to the correct location for the ALU to process
- System bus
- I/O devices


![[Pasted image 20260306115039.png]]

![[Pasted image 20260306115209.png]]

![[Pasted image 20260306115246.png]]

![[Pasted image 20260306115515.png]]

![[Pasted image 20260306115610.png]]

![[Pasted image 20260306115710.png]]

![[Pasted image 20260310231828.png]]![[Pasted image 20260306120326.png]]

![[Pasted image 20260306120755.png]]

# Operations carried out by microprocessor

![[Pasted image 20260306120841.png]]




# Memory and I/O Operations
In a microprocessor system, memory operations and Input/Output (I/O) operations are fundamental processes that allow the CPU to execute instructions, store data, and communicate with the outside world. The microprocessor uses specific control signals, primarily the `IO/M'` (Input-Output/Memory) pin, to differentiate between accessing memory (when the signal is low) and accessing an I/O device (when the signal is high).

Here is a breakdown of how these operations work:

1. Memory Operations

The microprocessor accesses memory to fetch instruction codes (Opcode fetch) and to read or write data. These operations generally take 3 clock cycles (T-states) to complete.

- **Memory Read:** The microprocessor fetches a byte from memory. It places the 16-bit memory address on the address bus, sets the `IO/M'` signal to low to indicate a memory operation, and asserts the `RD'` (Read) control signal. The memory device then places the requested data onto the data bus for the microprocessor to read.
- **Memory Write:** The microprocessor sends a byte of data to be stored in memory. It places the target 16-bit address on the address bus and the data on the data bus. It then sets `IO/M'` to low and asserts the `WR'` (Write) control signal to instruct the memory to store the data.

2. I/O Operations

I/O operations allow the microprocessor to communicate with external peripherals (like keyboards, displays, or sensors). The microprocessor identifies and communicates with I/O devices using two distinct interfacing methods:

**A. Direct I/O (I/O-Mapped I/O or Peripheral-Mapped I/O)** In this method, I/O devices are treated strictly as external peripherals, entirely separate from the memory space.

- **Addressing:** The microprocessor uses an 8-bit device address, meaning it can uniquely identify up to 256 input devices and 256 output devices.
- **Instructions:** It uses dedicated instructions—`IN` for reading data and `OUT` for writing data.
- **Control Signals:** It uses specific I/O control signals, namely `IOR'` (I/O Read) and `IOW'` (I/O Write).
- **Data Transfer:** Data can only be transferred between the I/O device and the microprocessor's Accumulator register.

**B. Memory-Mapped I/O** In this method, the microprocessor treats the I/O devices exactly as if they were memory locations.

- **Addressing:** I/O devices use the full 16-bit address bus, sharing the 64 KB address space with the actual memory.
- **Instructions:** There are no special I/O instructions. The microprocessor uses standard memory-related instructions (like `LDA`, `STA`, `MOV M,R`, etc.) to communicate with the peripherals.
- **Control Signals:** It uses the standard memory control signals, `MEMR'` (Memory Read) and `MEMW'` (Memory Write).
- **Data Transfer:** Because the I/O device acts like memory, data can be transferred between the I/O device and _any_ register in the microprocessor, and arithmetic or logical operations can be performed directly on the I/O data.


# Assembly advantages
- **Accessibility to system hardware:** Assembly language is highly advantageous for **implementing system software** and is well-suited for **small embedded system applications**.
- **Space and time efficiency:** It allows programmers to write highly **compact code**, meticulously tune program performance, and gain a direct understanding of what makes a program efficient.
- **Deep hardware understanding:** Writing assembly programs provides a **deep understanding of the processor's instruction set** and its overall architectural design.
- **Specialized application development:** It is highly beneficial for low-level tasks such as **writing compilers, programming microcontrollers, developing device drivers**, system design, and creating low-level numeric routines. In fact, the machine language expertise gained through assembly programming is necessary to be able to write compilers for high-level languages



An **assembler** is a program that translates human-readable assembly language programs into machine language or object files. For example, popular assemblers used for the Intel family of processors include TASM (Turbo Assembler), NASM (Netwide Assembler), and the GNU assembler.

A **linker** is a program that is required to produce final executable files. In a project with multiple source files, the assembler first translates each source file separately into an object file. The linker then combines these various object files along with any necessary link libraries to produce a single, cohesive executable program.

A **debugger** is a tool that allows you to trace the execution of your program to find and fix errors. It lets you inspect the internal state of the processor, such as viewing the code, memory contents, and register values as the program runs. Examples of debuggers include WinDbg and GDB (the GNU debugger)







![[Pasted image 20260306120949.png]]

![[Pasted image 20260306121044.png]]

|Feature|SRAM|DRAM|Masked ROM|PROM|
|---|---|---|---|---|
|Volatile|Yes|Yes|No|No|
|Speed|Very fast|Medium|Fast read|Fast read|
|Refresh needed|No|Yes|No|No|
|Writable|Yes|Yes|No|Once|
|Cost|High|Low|Very low in bulk|Medium|


# 8085 microprocessor

its a 8 bit processor developed by intel
it has 8 bit data bus 
it has 16 bit address bus 
so it can access 65536 memory locations
it has 40 pins 
it can handle 5v power supply
clock speed is 3 mhz
it supports 5 interuupts 
	TRAP
	 RST 5.5
	 RST 6.5
	 RST 7.5
	 INTR

it has different register
![[Pasted image 20260306124427.png]]
![[Pasted image 20260306124444.png]]


![[Pasted image 20260306124916.png]]

x1 x2 are clock frequency pins connected with crystal oscilator

RESET IN RESET OUT these are reset pins , reset in is used to reset the processor  and reset out sends the signal to other devices to reset along or start back with processor

SOD SID these pins enable serial input output communication for processor

TRAP RST5.5 RST 6.5 RST 7.5 INTR INTA :  these are interuupt pins TRAP is the highest priority interupt
RST interrupts are vector interrupts which require memory jump . 
INTR INTA are external interrupt , INTR is request and INTA is its ackoledgement

A0 - A7 are data bus these carry data but theyalso work as address bus when ALE is enable

VSS is ground reference pin 
VCC is 5v power supply pin

 HOLD HLDA are DMA pins , HOLD is for DMA request and HLDA is for acknoledgement
 
CLK OUT is a clock pin it geenrates clock signals for perpherals to coordinate

READY is used to delay the processor when other devices are not ready / slow 

IO/M this is used to switch between I/O and memory operations 

S0 S1 are status pins these helps identifying the current operations such as hlt read write etc

RD WR these are read write operations enabling pins 

ALE is address latch enable it is used to allow the data bus work as address bus 

A8 - A15 these are address bus pins used to carry address 




![[Pasted image 20260306131915.png]]


# Timing diagram
![[Pasted image 20260306170646.png]]

![[Pasted image 20260306170701.png]]

![[Pasted image 20260306170729.png]]


|     | Io/M | RD  | WR  | S1  | S0  |
| --- | ---- | --- | --- | --- | --- |
| OF  | 0    | 0   | 1   | 1   | 1   |
| MR  | 0    | 0   | 1   | 1   | 0   |
| MW  | 0    | 1   | 0   | 0   | 1   |
| IoR | 1    | 0   | 1   | 1   | 0   |
| Iow | 1    | 1   | 0   | 0   | 1   |


![[Pasted image 20260306171352.png]]

![[Pasted image 20260310205404.png]]

![[Pasted image 20260310205433.png]]


# 8085 Microprocessor & Interfacing: Comprehensive Exam Solutions

This document provides detailed answers to the questions found in the provided exam papers (Subject Code: 3160712).

## 1. Fundamentals & Theory

### 1.1 Instruction Set Architecture (ISA) & Performance Terms

- **Instruction Set Architecture (ISA):** The part of the processor architecture that is visible to the programmer. it includes the native data types, instructions, registers, addressing modes, and memory architecture.
    
- **Instruction Per Clock (IPC):** A measure of how many instructions a CPU can execute in a single clock cycle. It is an indicator of the processor's efficiency.
    
- **Machine Cycle:** The time required by the microprocessor to complete the operation of accessing the memory or I/O devices. One machine cycle consists of 3 to 6 T-states.
    
- **System Bus:** A communication system that transfers data between components inside a computer or between computers. It consists of the Data Bus, Address Bus, and Control Bus.
    

### 1.2 Storage Memory Classification

Memory is classified based on its volatility and functionality:

1. **Primary Memory (Main Memory):**
    
    - **RAM (Random Access Memory):** Volatile memory.
        
        - _SRAM (Static):_ Fast, used for cache, does not require refreshing.
            
        - _DRAM (Dynamic):_ Slower, higher density, requires periodic refreshing.
            
    - **ROM (Read-Only Memory):** Non-volatile memory.
        
        - _PROM:_ Programmable once.
            
        - _EPROM:_ Erasable using Ultra-Violet light.
            
        - _EEPROM:_ Electrically Erasable and Programmable.
            
2. **Secondary Memory:** Non-volatile, high capacity (e.g., Magnetic Disks, SSDs).
    

### 1.3 Advantages of Assembly Language (AL) vs. High-Level Language (HLL)

- **Efficiency:** AL code is generally faster and consumes less memory because it is closer to the hardware.
    
- **Hardware Control:** AL allows direct manipulation of registers, I/O ports, and specific memory locations, which is crucial for embedded systems.
    
- **Deterministic Timing:** Execution time can be precisely calculated, which is vital for real-time applications.
    

## 2. Architecture & Hardware

### 2.1 System Bus Organization

The 8085 uses three buses for communication:

1. **Address Bus (16-bit):** Unidirectional. It carries the address from which the MPU wants to read/write. 16 bits allow addressing $2^{16} = 64\text{ KB}$ of memory.
    
2. **Data Bus (8-bit):** Bidirectional. It carries actual data between the MPU and peripherals/memory.
    
3. **Control Bus:** A collection of various signals like $RD$, $WR$, $IO/M$, and $ALE$ that synchronize the system.
    

### 2.2 Demultiplexing of Address and Data Bus

The 8085 multiplexes the lower 8 bits of the address with the 8 bits of data on the same pins ($AD_0-AD_7$) to reduce the pin count.

- **Process:** During the first T-state ($T_1$) of a machine cycle, the **ALE (Address Latch Enable)** signal goes HIGH. This signals an external latch (like 74LS373) to store the address bits. For the remainder of the cycle, ALE is LOW, and the pins are used for data.
    

### 2.3 Programming Model of 8085

Includes:

- **Accumulator (A):** 8-bit register for arithmetic/logic operations.
    
- **General Purpose Registers:** B, C, D, E, H, L (can be used as 8-bit or 16-bit pairs).
    
- **Program Counter (PC):** 16-bit register holding the address of the next instruction.
    
- **Stack Pointer (SP):** 16-bit register holding the address of the top of the stack.
    
- **Flag Register:** 8-bit register containing 5 status flags (S, Z, AC, P, CY).
    

### 2.4 Flag Register Bits

- **Sign (S):** Set if the result of an operation is negative (MSB is 1).
    
- **Zero (Z):** Set if the result is zero.
    
- **Auxiliary Carry (AC):** Set if there is a carry from bit $D_3$ to $D_4$.
    
- **Parity (P):** Set if the result has an even number of 1s.
    
- **Carry (CY):** Set if an arithmetic operation results in a carry/borrow.
    

### 2.5 Pin Functions

- **READY:** Used to delay the MPU to match the speed of slow peripherals.
    
- **HLDA (Hold Acknowledge):** Indicates the MPU has received a HOLD request and will relinquish the buses.
    
- **TRAP:** The highest priority non-maskable interrupt.
    
- **RESET IN:** Resets the PC to 0000H and resets the interrupt enable flip-flops.
    
- **CLK OUT:** Clock signal for synchronizing external devices.
    

## 3. Instruction Set & Addressing

### 3.1 Addressing Modes

1. **Immediate:** Data is provided in the instruction. _Ex: `MVI A, 05H`_
    
2. **Register:** Data moves between registers. _Ex: `MOV A, B`_
    
3. **Direct:** Memory address is specified in the instruction. _Ex: `LDA 2000H`_
    
4. **Register Indirect:** Address is stored in a register pair (usually HL). _Ex: `MOV A, M`_
    
5. **Implied/Implicit:** The operand is hidden in the opcode. _Ex: `CMA` (Complement Accumulator), `STC` (Set Carry)._
    

### 3.2 Instruction Classification by Byte Size

- **1-Byte:** Opcode only (e.g., `MOV A, B`, `ADD C`).
    
- **2-Byte:** Opcode + 8-bit data/address (e.g., `MVI A, 32H`, `ADI 10H`).
    
- **3-Byte:** Opcode + 16-bit address (e.g., `LXI H, 2050H`, `STA 3000H`).
    

### 3.3 Instruction Analysis Table

|   |   |   |   |   |
|---|---|---|---|---|
|**Instruction**|**Bytes**|**Machine Cycles**|**T-states**|**Operation**|
|**LDAX B**|1|2 (OF, MR)|7|Load A with data from address in BC|
|**XRI 20H**|2|2 (OF, MR)|7|XOR A with 20H|
|**MVI M, 24H**|2|3 (OF, MR, MW)|10|Move 24H to memory pointed by HL|
|**SHLD 2000H**|3|5 (OF, MR, MR, MW, MW)|16|Store L at 2000H, H at 2001H|

## 4. Assembly Language Programs

### 4.1 Multiplication by Repetitive Addition

```
; Multiply numbers at 2200H and 2201H. Store at 2300H (LSB) and 2301H (MSB)
LXI H, 2200H
MOV B, M      ; Multiplier (Counter)
INX H
MOV C, M      ; Multiplicand
MVI A, 00H    ; Clear Accumulator for Result
MVI D, 00H    ; Carry register (MSB)
BACK: ADD C   ; Add multiplicand
      JNC SKIP
      INR D   ; Increment MSB on carry
SKIP: DCR B   ; Decrement counter
      JNZ BACK
      STA 2300H ; Store LSB
      MOV A, D
      STA 2301H ; Store MSB
      HLT
```

### 4.2 2-Digit BCD to Binary (72 BCD to Binary)

Logic: $72_{BCD} = 7 \times 10 + 2$.

```
MVI A, 72H
MOV B, A
ANI F0H       ; Get tens digit (70H)
RRC
RRC
RRC
RRC           ; Shift right to get 07H
MOV C, A      ; Store 7 in C
ADD A         ; 7*2 = 14
ADD A         ; 14*2 = 28 (Actually we need 7*10)
; Easier way: use a loop or manual additions
MOV A, C      ; A=7
ADD A         ; A=14
MOV D, A      ; D=14
ADD A         ; A=28
ADD A         ; A=56
ADD D         ; A=56+14 = 70
MOV D, A      ; D=70
MOV A, B
ANI 0FH       ; Get units digit (02H)
ADD D         ; Result = 70 + 2 = 72 (in Binary/Hex)
STA 2050H
HLT
```

### 4.3 1 ms Timing Delay Program

Assume Clock Period = $0.5\ \mu s$ (Frequency = 2 MHz).

Target: $1000\ \mu s$.

Formula: $Delay = T_{states} \times \text{Clock Period}$.

$T_{states} = 1000 / 0.5 = 2000$ T-states.

```
MVI C, N      ; 7 T-states
LOOP: DCR C   ; 4 T-states
      JNZ LOOP; 10/7 T-states
; (N * 14) + 7 = 2000 => 14N = 1993 => N ≈ 142 (8EH)
```

## 5. Timing Diagrams (Key Concepts)

- **CALL 2100H:** Takes 18 T-states. Includes Opcode Fetch, 2 Memory Reads (Address), and 2 Memory Writes (Stack push).
    
- **DAA:** 1-Byte instruction. Requires only an Opcode Fetch (4 T-states).
    
- **PUSH H:** 1-Byte instruction. Requires Opcode Fetch + 2 Memory Writes (Stack) = 12 T-states.
    
- **DAD D:** 1-Byte instruction but takes 10 T-states because it involves 16-bit addition inside the CPU after the opcode fetch.






# Interfacing 

mp sare kam nahi kar sakta vo bas calculations kar sakta hai decisions le sakta hai lekin external chizon ko control ya move nahi kar sakta jaise motor ko move karna 

to iske liye alag circuits hoti hai jinko mp ke sath jodna padta hai  uske liye use karte hain interfacing 

ham keyboard mouse jaisee devices ko interfacing ke through connect karte hain mp se 

isko I/O interfacing kehte hain 

ek aur intercfacing hoti hai Memory interfacing jisme ham memory ko mp ke sath jodte hai jaise ram rom 

I/O inerfacing me 8 bit addresses use hote hain 
memory interfacing me 16 bit

I/O interfacing me bas IN OUT instruction use hote hain jabki memory me sare general instructions jaise LDA STA MOV

jab I/O ke sath direct operation hote hain using IN OUT instruction usko kehte hain peripheral I/O ya I/O mapped I/O 

jab I/O devices ko map kar diya jata hai kisi memory location se and us memory location me operation hote hain and then vo reflect hote hain I/O device me isko kehte hain Memory mapped I/O


# Interrupts 

aisa program ya situation jo ki mp ka normal flow rok deta hai 
koi emergency situation ho sakti hai ya koi high priority task 

interrupt jab aata hai tab mp apna kam chhodke interuupt execute karne ke liye chala jata hai 
isk kehete hain ISR (interrupt service routine)

har interrupt ke aane par mp jis location pe jake interrupt ko serve karta hai us location ko kehte hain ISR address 

5 interrupts hain 
	TRAP
	 RST 7.5
	 RST 6.5
	 RST 5.5
	 INTR
![[Pasted image 20260517083438.png]]



# 8255 ppi

![[Pasted image 20260517091157.png]]


8055 IS A GENERAL PURPOSE PROGRAMMABLE IO INTERFACE 
IT IS USED TO INTERFACE EXTERNAL DEVICES WITH MP 
IT HAS 3 PORTS 
PORT A PORT B PORT C 
PORT A AND B AND 8 BIT PORTS 
PORT C IS ALSO 8 BIT BUT IT IS LOGICALLY DIVIDED INTO TWO PARTS 
PORT C LOWER AND PORT C UPPER 

THESE PORTS ARE FURTHER GROUPED IN TWO PARTS 
GROUP A CONTROL WHICH HAS PORT A AND PORT C UPPER (4-7)
GROUP B CONTROL WHICH HAS PORT B AND PORT C LOWER (0-3) 

A CONTROL WORD WHICH CONTROLS THESE PORTS AND THEIR MODES 

8255 HAS 3 OPERATING MODES 
MODE 0 MODE 1 MODE 2 
IN MODE 0 ALL THREE PORTS WORK INDEPENDENTLY
IN MODE 1 PORT A AND PORT B WORK IN HANDSHAKE AND THE UPPER PORT C IS USED BY PORT A AND LOWER PORT C BY PORT B FOR HANDSHAKE 
IN MODE 2 ONLY PORT A WORKS IN BIDRECTIONAL HANDSHAKE , WHEREAS PORT B WORKS IN MODE 1 OR 0 AND PORT C IS NOT CAPABLE OF ANY I/O OPERATION

READ WRITE CONTROL LOGIC DECIDES WHICH PORT TO USE WHICH MODE READ OR WRITE ETC 
PIN A1 AND A0 DECIDES WHERE TO SEND THE COMMAND COMING FROM THE MP
RD AND WR DECIDES READ OR WRITE , INPUT OR OUTPUT MODE
RESET PIN IS FOR RESETING THE THE CHIP 
CS IS FOR SELECTING THIS CHIP IF CS IS HIGH THIS CHIP IS NOT SELECTED AT ALL 

8255 HAS 2 MODES 
BSR AND I/O 
I/O HAS FURTHER 3 MODES WHICH WE DISCUSEED EARLIER MODE 0,1,2

below image show the breakdown of a control word
![[Pasted image 20260517112225.png]]

![[Pasted image 20260517112153.png]]


BSR command is used to utilize the single lines of port c without affecting other lines as they are busy with port a and port b for handshaking 


# 8259 Programmable in
terrupt controller

![[Pasted image 20260514190235.png]]


8085 processor me sirf 5 interrupts hain
TRAP , RST 7.5 , RST 6.5, RST 5.5 , INTR 
to ab agar hamko jyada hw interuupts chahiye to ? 
uske liye to pins hi nahi bachi 
to isliye ham ye circuit istemal karte hain taki ham aur bhi jyada hw interruupts use kar sake jisse no of connected external devices badh jayen 

8259 chip me 8 pins hoti hain jsse ki 8 interrupts handle kiye ja sakte hain 
par agar ham in 8 pins me bhi 8 8259 chips laga de to 64 interuupts handle kiye ja  sakte hain usse jyada nahi kar sakte kyuki fir bich wali layer ki chips confuse ho jayngi ki ham master hain ya slave , kyuki vo to dono hai slave for level 1 chips and master for level 3 chips , 

to sabse pehle register hai interupt request register jo ki informatin deta hai ki kaun kaun se interrupt aa chuke hai par service milna baki hai 

interupts ki priority programmer decide kar sakta hai , by default ye priority highest 0 to lowest 7 hoti hai 

to jab bhi koi intruupt aata hai uski specific pin 1 ho jati hai IRR me 
agar ek sath do aaye to highest priority wala pehle chuna jata hai 
low wala hold pe jata hai bad me service milti hai usko 


uske badd priority resolved check karta hai Interrupt mask register , agar IMR me vo perticular bit high haia to vah interuupt DISCARD ho jata hai complety 

IMR batata hai ki koi interuupt masked hai ya nahi , masked interuupts discard ho jate hain HOLD nahi DISCARD 

uske bad priority resolver dekhta hai in service register INSR , ye batata hai ki kaun sa interupt abhi service me hai , complete nahi hua , par chalu hai 

to agar INSR me koi high priority interupt already service me bata rah hai to abhi jo aaya vo hold pe jayga agar abhi aane wala currently in service se high hai to , curerent wala hold pe jayga aur jo new aaya hai vo service hoga . 
agar same priotity wala aagaya to discard ho jayga kyuki vo already inservice hai 

to highest priority wala choose hota hai sabse pehle IRR mese fir IMR me check hota hai and then INSR me agar teeno me se pass ho gaya to bhej diya jata hai microprocessor ko through the INT pin 
INT pin mp ki INTR se connected hoti hia . mp current instructin exec karke 8259 ko pehlla INTA bhejta hai 
pehla INTA milne par PIC interupt ka opcode bhejta hai mp ko , uske bad mp 2nd INTA bhejta hai uske bad PIC us interupt ke ISR address ki lower byte bhejta hai uske bad mp 3rd INTA bhejta hai
uske bad PIC ISR ke address ki higher bytes bhejta hai 

fir mp us address pe jake ISR exec karta hai aur PIC ko EOI signal(end of interuupt) bhejta hai aur normal program exec start kar deta hai 
