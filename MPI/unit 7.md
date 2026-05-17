
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
