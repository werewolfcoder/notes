
### Register transfer language:
	A representation system that expresses the micro operations happening between       registers in a symbolic manner 
     simple yar , koi bhi circuit me registers hain ? ab unke bich data kaise flow       kareaga jab koi bhi instruction execute hoga , vo ham RTL ka use karke show         karte hain 
	 R1<-R2 (r2 ka data r1 me compi kardo bhaiya)

	 isme condition vagerah bhi use kar sakte hain jaise 
			 P:R1<-R2  
			 matlab agar P true hai to R2 ka data R1 me copy kardo 
	aur haan ye computer nahi use karte naa hi vo samajhte ye to bas ham                 moorkh logon ke liye hai jo us bichare computer ki feelings nahi samajhte

![[Pasted image 20250513201603.png]]
### Instruction format 


Risc instructions : reduced instruction set computer me use hone wale instructions 
isme sirf LOAD and STORE use hota hai 
![[Pasted image 20250513093530.png]]

(i) Zero Address instruction format : 
		jab hame instruction me koi bhi operand na dena pade na address na register bas opcode
Example: ADD
ye instruction stack mese top ke 2 values nikal ke ADD karke vapis push kardega

(ii) One Address instruction format: 
		 jab hame bas ek operand dena pade ya address ya register bas ek 
Example:  ADD A
ye accumulator me A plus karke accumulator me store kar dega


(iii) Two address instruction format: 
		 jab ham do operand do address do register kuchh bhi bas do
Example:  ADD A, B
A aur B ki value add karke Accumulator me store kardega


(iv) Threee instruction format:
		 jab hame teen operand register ya memmory address dene pade
Example:  ADD R1,R2,R3 
ye  R2+R3 karke R1 me store kar dega 



### Instruction cycle:
[instruction cycle in hindi | Lec-36 | COA | Niharika Panda](https://www.youtube.com/watch?v=SEZimgf4yZI)
an instruction goes through various stages from starting to end. 
instruction cycle shows all those steps 
->Fetch
->Decode
->Read effective address from memory
->execute
and again goto step one until HLT instruction is encountered 

![[Pasted image 20250509182325.png]]


basic instruction format info: 
![[Pasted image 20250509205315.png]]
isme last ki 4 bits dekho 
0000 , isme 3 bit opcode hai  1 bit addressing mode

to ham sabse pehle opcode check karte hain  fir addresing mode bit 

to agar opcode ki 3 bit 111 hai matlab ye ek NON MRI instruction hai
		-ab check karo addresing mode bit (last bit in left)
			 -agar 0 -> register reference instruction
			 -agar 1 -> I/O reference instruction

agar opcode ki 3 bit kuchh aur hai (111 nahin hai) to ye MRI hai
		 -ab addressing mode bit check
			 -0 ? then-> direct addresing mode
			 -1 ? then-> indirect addressing mode


### Memory reference Instruction:

to instruction teen part me hota hai 
	![[Pasted image 20250509201130.png]]
to isme jo OPCODE hai vo 3 bit ka hai 
to possible values haiN:
000   001  010  011
100  101   110  111 

ab isme 111 (7) ho to vo insruction register ya I/O reference instruction hota hai JISKO NON MEMORY REFERENCE INSTRUCTION BHI KEHTE HAIN 
aur baaki 0 se 6 tak sare "Memory reference instructions hote hain" 


ab aapne dekha hoga ki instruction ki LAST BIT hai  ek 
usko I se denote karte hain 
vo batati hai 
	-Direct addressing mode  (0)
	 - Indirect addresing mode (1)

to jo memory reference instructions hain  vo aise instructions hain jo memory se data access karte hain 

to ye 0 to 6 tak hain as we know 
to vo kuchh is prakar hai:

0 - 0000 - AND - D0 --- AC<- AC ^ M[AR]
1 - 0001 - ADD - D1 --- AC<- AC + M[AR]
2 - 0010 - LDA  - D2 --- AC<- M[AR]
3 - 0011 - STA  - D3 --- M[AR]<- AC
4 - 0100 - BUN - D4 --- PC<-AR
5 - 0101 - BSA - D5 --- M[AR]<-PC , PC<-AR+1
6 - 0110 - ISZ - D6 --- M[AR]<-M[AR]+1 , if(M[AR]+1 = 0) THEN PC<- PC + 1 
8 - 1000 - AND -D8 --- SAME AND OPERATION AS 0 BUT THIS TIME AR ME VALU NAHI ADDRESS HOGA
9 - 1001 - ADD -D9   
A-  1010 - LDA - D10
B - 1011 - ADD - D11 --- AC<- AC + M[AR] , AC<-M[AC]
C - 1100 - LDA  - D12 --- AC<- M[AR]
D - 1101 - STA  - D13 --- M[AR]<- AC
E- 1110 - BUN - D14 --- PC<-AR



### NON MRI instructions / REGISTER or IO instructions 
to hamare pass as we know instruuction execute karne ke liye 4 bit bachti hai , kyuki baki ki 12 bit address hota hai 
to usme se last 1 bit hai addresing mode bit (left most bit)
aur baki 3 opcode 
to jab opcode ki 3 bit 111 hai to vo  non MRI instructions 
isme do part hain 
		-REGISTER REFERENCE ()
		 -I/O REFERENCE 

jab addresing mode bit 0 ho - > REGISTER REFERENCE 
jab addresing mode bit 1 ho -> I/O REFERENCE 

  --- REGISTER REFERENCE INSTRUCTIONS ---

ye jo sabme 0111 hai ye darshata hai ki kaise sab 7 se shuru ho rahe hain 
note:-- memory reference instruction me 7 waala instruction gayab hota hai uk why now
CLA  -7800 - 0111    Clear AC 
CLE   -7400 - 0111   Clear E 
CMA -7200 - 0111   Complement AC
CME  -7100 - 0111   Complement E
CIR    -7080 - 0111   Circulate right AC and E
CIL    -7040 - 0111   Circulate left AC and E
INC   -7020 - 0111    Increment AC
SPA   -7010 - 0111    Skip next instruction if AC positive
SNA   -7008 - 0111    Skip next instruction if AC negative
SZA    -7004 - 0111    Skip next instruction if AC zero
SZE     -7002 - 0111    Skip next instruction if E is 0
HLT     -7001 - 0111   Halt computer


	--- I/O REFERENCE INSTRUCTIONS ---
YAHAN SABME 1111 DIKHATA HAI KI SAB "**F**" SE SHURU HOTE HAIN

INP    - F800 - 1111  - Input character to AC
OUT    - F400 - 1111  - Output character from AC
SKI      - F200  - 1111   - Skip on input flag
SKO    - F100  - 1111  - Skip on output flag 
ION    - F080  - 1111  - Interrupt on
IOF    - F040  - 1111  - Interrupt off



### Micro programmed control orgenization:
		to CPU me  3 part hote hain
			ALU - REGISTERS - CONTROL UNIT 
-control unit control signals generate karta hai . micro operations ke liye 

-jaise ADD op karna hai to uske liye signal alag hai LDA ke liye alag aise sabke liye alag alag

-matlab , programmer ne to likha diya ki ADD A,B , lekin computer ko kya pata ADD ka matlab 
to yahi sab instruction ke request par kya karna hai vo micro program me likha hota hai 
jitna complex computer utne jyada micro operations aur utna  hi complex micro program

-To cotrol unit banane ke 2 tarike hain 
		--Hardwired :- hardware ka use karke , jaise 
					-logic gates
					 -flip flops
					 -circuits 
		 --Micro prgrammed:- control unit ke logic ka software program likhna , aur zarurat ke hisab se execute karna 

to ye micro programmed control orgenization me ham control unit ka microprogram likhe hain
micro program is a collection of micro instructions 
micro instructions are collection of micro operations

![[Pasted image 20250510133041.png]]

ab is control unit me 4 part hote hain 
-->next address generator ya sequencer , next micro instruction ka address generate karta hai 

-->control address register , generated address is "control address register " me store kiya jata hai

-->Control memory me sare micro instructions(micro program as a whole) stored hote hain, control memory ROM ka use karke banai jati hai to isme sirf read operations hi hote hain  because ROM is read only

-->fir memory se data leke store kiya jata hai control data register me. taaki execute kiya ja sake

-->control data register me current data ke alava , thodi extra bit bhi hoti hain , jo ki alag alag informatioon deti hain next instruction generation ke liye 

--> control data register ko "PIPELINE REGISTER " bhi kaha jata hai  kyuki ye control word bhi generate karta hai aur next instruction generation ke liye info bhi pass karta hai 

--> fir "control word" as an output generate hota hai jo ki final control signal hota hai for execution

-->next address generation ke liye kuchh external input bhi liya ja sakta hai 




### Sequencer / ADDRESS SEQUENCING 

		To hamne dekha ki micro programmed control unit ka first part tha sequencer ya next address generator
	- ye sequencer kaise kaam karta hai ham ye dekhenge 
	- To sequencer 4 tarike se next address generate karta hai 
		- Increment control address register: simply controll address register ki value +1 kardo to next address mil jayga simple . iske liye instruction pass kiya jaata hai incrementer me aur vahan se increment hoke aajata hai Control address register me vapis
		
		- Conditional or unconditional branching :- ye conditional branching ya unconditional ye kaise decide hoga ? ye hame nahi sochna ye instruction me hi coded hota hai to depending on the instruction , branching to some other address and selecting that address . to agar unconditional hai to obv , directly specified address pe jump karke vo select karlo aur usko control address register me daldo
par agar conditional hai to jump to branch logic , jahan condition likhi hai aur condition ke basis pe  jump karo specified address par aur usko select karke save kardo control address register me 

		- Mapping: Mapping matlab , jo instruction code aarha hai usi  me kuchh jod ghatav guna bhag karke next address mil jayga isko bolte hain mapping . iska logic obv likha hota hai ki kaise mapping karni hai .
for example instruction hai MEAAWW aur isko mapping se resolve karke next address nikalna hai to control jayga mapping logic pe , aur samjho udhar likha hai ki MEAAWW  ko MEAAUU kardo aur vahi tumhara address hai muehehehehe

        - Subroutine call:- subroutine ek function ki tarah hota hai , jaise ek function call pe main code ruk ke function ki body execute karta hai aur uske baad vapis main code me aajata hai usi taraha ye subroutine bhi hota hai . 
ye bhi function ki tarah reusability ke hota hai aur kahin se bhi call kiya ja sakta hai 
samjho, jaise ADD ke liye jo microoperations likhe hain , vahi operations multiple times MUL instruction ke liye bhi as a subroutine call use kare ja sakte hain simple 

![[Pasted image 20250510140116.png]]





###  stack organization:
		stack matlab pata hi hai LIFO concept pe kam karta hai . 
		 isme ek register hota hai STACK POINTER jo ki top of stack ki value store 
		 karta hai 
		 dusra register hota hai DATA REGISTER jo ki values ko push pop karne me
		 help karta hai

Stack do trike se implement kiya ja sakta hai 
			MEMORY STACK 
			 REGISTER STACK 


REGISTER  STACK : registers ka use karke implement kiya jata hai .
	isme ek stack pointer hota hai jo ki ,  stack ki top most value ki location store karta hai 
		aur ek data register hota hai jo ki push pop operations me data storage ke liye use hota hai.
		 do aur flag use hote hain 
		 EMPTY
		 FULL 
		 dono bas 0 ya 1 hi store karte hain 
		 jab stack empty ho tab EMPTY flag 1 hota hai 
		 jab sakc full ho jaye tab FULL flag 1 hota hai 

		register stack me , stack accending order me grow karta hai 
		 like first value 10 pe hai to second 11th address pe ,next 12..13..14

	 PUSH OPERATION:
		 sp<-sp+1
		 m[sp]<-DR
		 if(sp==0) then FULL<-1
		 EMPTY<-0
      POP OPERATION:
	      DR<-m[sp]
	      sp<-sp-1
	      if(sp==0) then EMPTY<-1
	      FULL<-0

![[Pasted image 20250510231601.png]]

agar stack 0 se shuru ho raha hai to 
->first  value store hogi 1 address pe 
->last value store hogi 0 address pe


MEMORY STACK:
main memory ke hi last ke kuchh part ka use karke implement kiya jata hai 
main memory ka content 3 part me divided hota hai 
first portion me instructions
second portion me data 
third and last portion ka use hota hai stack ke liye 

![[Pasted image 20250510232233.png]]

memory stack me , stack decending order me grow karti hai kyunki last address se shuru hota hai to aage badhne ke liye plus to kar nahi sakte kyunki ye last address hai to next value store karne ke lliye ek ek decrement karte hai address ko . 
like 4001 last hai to , 4000..3999..3998.....


PUSH OPERATION:
	  	sp<-sp-1
		m[sp]<-DR

POP OPERATION:
		 DR<-m[sp]
		 sp<-sp+1


STACK KA USE  INFIX POSTFIX VAEGRAH ME HOTA HAI 


-->Register stack accending order me grow karta hai , yani push me ++
-->Memory stack decending order me grow karta hai yani push me --

-->Register stack limited size ka hi ho sakta hai
-->memory stack jitna marzi bada bana lo

-->Register stack CPU me hota hai
-->Memory stack RAM me hota hai

-->Register stack fast hota hai 
--> Memory stack slow hota hai 


### Subroutine:
	 t jaisa ki ham jaan chuke hain ki subroutine ek function ki taraha hota hai jo ki call karne par main program se control hat kar subroutine ki definition par chala jata hai aur execution complete hone par vapis return hokar main program me aajata hai. 

to kaise ye subroutine call and subroutine return kam karta hai ye dekhte hain

SUBROUTINE CALL: 
 subroutine call hone par , program counter ki value stack me save kardi jati hai aur control subroutine par chala jata hai.

		--> sp<-sp-1 (minus, kyuki memory stack deccesnding order me badhta hai)
		 --> m[sp]<-PC 

SUBROUTINE RETURN: 
to jab subroutine execution khatam ho jata hai tab stack me se program counter ki value leke program counter ko update kiya jata hai aur fir us new address par return ho jata hai control

		 --> PC<-m[sp]
		 --> sp<-sp+1 





### ADDRESSING MODES:

-Implicit mode: jahan par operand explicitly specify na karna pade
		CMA 

-Immidiate Mode: jahan par directly value de di jaye as an operand 
		 ADD 05H 

-Register mode: jahan register as an operand pass kiya jaye 
		 MOV AX,CX

-Register indirect mode :  yahan ham jo register pass karte hain usme address hota hai aur us address par value hoti hai 
	      MOV AX,[CX]

-Auto increment/decrement mode:-  isme register ki value automatically inremement ya decrement ho jati hai , 

-Base Register mode:  ek base register hota hai usme ek value hoti hai aur usi ke bases pe baki address calculate hote hain 
like program 100th locatioon se start ho raha hai to base register me hoga 100 
and ek instruction hai to branch 60th location
to base register + 60 
160 pe branch hoga .

-Indexed register mode:  isme ek array ki tarah storage ko access karne ke liye iska use hota hai 
to array  ka starting address instruction me pass kiya jata hai aur ek INDEX REGISTER me number ya index hota hai of element which  u want to access , to  base address from instruction + index register value = desired data 


-Direct addressing mode:  yahan ham direct address dete hain jahan value stored hai 
		  ADD 457

-Indirect addressing mode:  yahan ham ek address dete hain jahan address stored hota hai aur us address me value stored hoti hai muehehehhe


-


### Memory interleaving:
		to main memory me ek samay me ek hi operation kiya ja sakta hai ya  to read ya to write vo bhi sirf ek time pe ek hi read/write to , agar 10 operation karne hai to ek operation ka time * 10. to ye kafi pagal pan hai .
		iske liye solution hai memory interleaving 

![[Pasted image 20250511191151.png]]
isme ek pure bade memory ko chhote individual and independent parts me divide kar diya jata hai 
 jisse ki un parts me paralally operation kiye ja sake aur time bache 

to har part ka individual address register and data register hota hai jo ki unka communication data bus aur address bus ke sath karvata hai . 

aur jaise hi address aata hai address bus ke thorugh to uski last two least significant bits batati hai ki operation ki memory module me karna hai , jaise diagram me memory ke 4 module hai to , incoming address ki last 2 least significant bits batati hai kisse communicate karna hai 

aur baki part batata hai ki us module ke kis perticular part me operation karna hai 

is diagram me ek sath 4 operation kiye ja sakte hain . 


### Flynn's classification:
		instruction stream matlab sequence of instruction read from memory
		Data Stream matlab operations performed on data 

To number of instruction stream and data stream ke basis pe flynn chacha ne computer ki spicies batayi 

SISD : single instruction single data 
SIMD: single instruction multiple data
MISD: multiple instruction single data
MIMD : multiple nstruction multiple data 


![[Pasted image 20250511194116.png]]

-->SISD:  isme ek hi processor hota hai aur ek control unit , aur ek memory obv
to bs vahi control unit memory se instructions read karke processor ko deta hai aur processor unko execute karta hai , zaruri data memory se padhte likhte huye 

![[Pasted image 20250511194301.png]]

--> SIMD: to isme ek control unit hota hai jo multiple processing units ko handle karta hai , unko instructions deta hai 
ye processing units connected hote hain apne apne respective memory module ke sath
han main memory ke tukde kardiye jate hain modules me 
to har processing unit ka apna memory module hota hai 
to isme ek hi instruction jo control unit pass karta hai, execute kiya ja sakta hai multiple data ke upar using multiple memory modules 

![[Pasted image 20250511194437.png]]


MISD: ye theory wali bkc hai aisa koi computer nahi banaya gaya time pass tha ye 
first time syllebus designers ne achha kam kiya , jo practical nahi hai usko na padhaake 


MIMD :  to ye bhaiya dada ji hain , ye mutliple instructions multiple data pe execute kar sakte hain ,
sab multiprocessor and multicomputer systems isi pe based hote hain
multiple processing units hote hain isme 

![[Pasted image 20250511194825.png]]



### PIPELINING: 
		to hamara computer ek samay me ek hi instruction execute kar sakta hai 
		isse samay bahut barbaad hota hai 
		agar ek instruction ke 1 second lagta hai 
		to 10 instruction 10 second lengge 
		hame ye problem solve karni hai 
		to pipelining aisa tarika hai jisme me ham existiing hardware ka hi use karte hain , usko is tarike se arrange karrte hain ki maximum output nikle least time me 
		to PIPELINED SYSTEM me ek samay me ek sath ek se jyada instruction execute hote hain . kaise ?
4 segment pipeline diagram
![[Pasted image 20250512121558.png]]
ye hai 4 segment pipeline 
matlab ek instruction 4 stages se hoar guzarta hai aur complete hota hai 
aur jo R1,R2 .. hain ye hain intermediate results store karne ke liye INTERFACE REGISTERS

-> Space time diagram use karte hain , execution of instruction show karne ke liye 
![[Pasted image 20250512121852.png]]
isme har instruction 4 segments me complete hota hai 
aur har segment 1 clock cycle leta hai completion ke liye 
to ek sath multiple instruction execute kaise hote hain ?
to T1 task aaya , uska segment 1 execute hua 
jab T1 segment 2 me gaya tab hamne new TASK T2 load kar liya aur uska segment 1 execute karne lage 
to ab hamare pass  T1 segement 2 me aur T2 segment 1 me ek sath execute ho rahe hain 
ya aisa samjho , T1 decode ho raha hai aur T2 fetch 
aise hi 3rd clock cycle me T1 3rd segment me T2 2nd segment me aur T3 1st segment me aagye

To total number of clock cycle needed for n instructions if 1 instruction takes 5 clock cycles :
	Let clock cycles = k
		Without pipelining  = n x k = nk
		 With Pipelining = k+(n-1)
lets say 6 instructions where each instruction has 4 segments and each segment takes 1 clock cycle
for 1 instruction , clock cycles needed = 5  
for 6 instructions clock cycles needed 
Without pipelining = 6 x 5 = 30
with pipelining = 5+(6-1) = 10

efficiency is ratio max clock cycles wrt clock cycles used 
in above example we had 9 x 4 = 36 clock cycles 
out of which we used = 6 x 4 = 24 

so efficiency = 24/36 = 2/3

speedup is a ratio of amount of time taken by non pipelined system and pipelined system
in our case as we calculated 
without pipeline = 30 clock cycles 
with pipe line = 10 clock cycles 

so speedup = 30/10 = 3


### Associative memory :
			normal memory me data access hota hai address ke basis pe to isme acces time jyada hota hai aur efficiency kam ho jati hai 
			is problem ka solution hai ASSOCIATIVE MEMORY  . 
			isme ham data ko address ke basis pe acess nahi karte balki data ke hi bsis par access karte hain . kaise ?
			jaise memory me employeei info saved hai , to uske address ki jagah ham employee id use karenge 
			to isiliye isko Content addressable memory bhi kehte hain. 

![[Pasted image 20250512134201.png]]

![[Pasted image 20250512134957.png]]


A  ya argument register  ye conain karta hai , word jisko search karna hai 
key register me hota hai key , key register me jis bit ki value 1 hai Argurment register ki vahi bit match ki jaygi baki sab igore kardi jayngi 

associative memory ko 2 dimensional array samjho 
isme m word hote hain 
aur har word n bit ka hota hai 

aur match register m bit ka hota hai 
jo ki jis bhi word se match milta hai uski respective bit ko 1 kardeta hai 


![[Pasted image 20250512150154.png]]



### Cache memory :
	to cache memory bahut chhoti memory hoti hai 
		bahut fast hoti hai
		jis bhi instructionn program ya data ka frequently use hota hai usko cache memory me rakha ja ta hai for faster access 
jab bhi kisi data ki zarurat hoti hai to vo pehle cache me dhundha jata hai , nahi mila to main memory me se cache me load kiya jata hai , 
cache me mila  to hit nahi mila to miss


cache mapping methods :

Associative mapping:  ye sabse simple but expensive tarika hota hai . isme jaise hi cpu address generate karta hai to us address ko cache me dhundha jata hai  
![[Pasted image 20250512201044.png]]

aur fir hit hua to cache memory se respective data leke cpu ko de diya jata hai 
nahin mila to main memory se load kiya jata hai cache me
aur agar cache full hua to diffrent replacement algorithms ka use karke replace kiya jata hai new data with old data


Direct mapping: direct mapping me jo actuall address hota hai data ka , uske last ke 3 LSB index address ban jate hain aur starting ke 2 MSB tag ban jate hain cache memory me us data ke liye 
. to jab bhi data request aati hai to , us address ke 3 LSB ki help se cache me entry dhundhi jati hai aur starting ke 2 LSB se tag match kiya jata hai aur hit hone par data cpu ko dediya jata hai 

isme dikkat hoti hai jab multiple data with same index but different tag ke sath ho to multiple misses hote hain
![[Pasted image 20250512201309.png]]


Set Associative Mapping: ye upar wale ka better version hai isme ham cache memory me 1 index address ki multiple tags ki values store kar sakte hain jisse multiple miss na hon 
![[Pasted image 20250512201655.png]]



### SRAM AND DRAM:

![[Pasted image 20250512211112.png]]


### Tightly coupled vs loosly coupled system
![[Pasted image 20250512214441.png]]


### Interconnection Structure:
		multiprocessor system banane ke liye hamko chahiye cpu memory Input output processor connected with IO devices .
		ab multiprocessor system banane ke liye in components ko alag alag configuration me arrange kiya ja sakta hai 
		to usi arrangement ko interconection structure kehte hain

iske types :

--Time Shared Common bus:
		isme ek hi common bus ke through sare cpu sare io cpu aur baki sara maal connected hota hai aur vo common bus memory ke sath connected hoti hai 
		isme ek samay par ek hi cpu memory se ya dusre cpu se communicate kar sakta hai 

![[Pasted image 20250512215326.png]]


	--Multiport Memory: isme main memory multiple memory modules me devided hoti hai 
	aur har module me multiple ports hote hain jo ki individually alag alag cpu se connected hote hain 
	isse har cpu har memory module ke sath simultaneously communicate kar sakta hai 
	lekin isme bahut kharcha aur complexiity aati hai 
	multiple buses ports and all that stuff 

![[Pasted image 20250512215523.png]]


--Crossbar Switch:   
				 ye multiport memory ki samasya ko solve karta hai , by avoidding multiple buses and ports and at the same time allowing multiple communications at the same time 
				 isme interconnection points par switches hote hain 
				 to jaise cpu1 mm3 se bat karna chahta hai to request bhejega 
				 pehla switcch dekhega kya ye yee mere mm1 ke liye hai ? nahi 
				 to aage bhej dega 
				 ab switch 2 check karega kya ye mere mm2 ke liye hai ? nahi
				 aage bhej dega 
				 ab switch 3 dekhga kya ye mere mm3 ke liye hai ? haan to mm3 ka access chalu ho jayga cpu3 ke sath
![[Pasted image 20250512215716.png]]


--MultiStage switching network:  
						isme switches use hote hain jaise niche dikhaye gaye hain 
							ye output choose karte hain 0 ya 1. 
							inhi ke combination se bada network design kiya ja sakta 
							hai for communication
![[Pasted image 20250512224308.png]]
jaise niche dekho multiple switches se pura network banaya hai 
its just like nested if else type shiii

![[Pasted image 20250512220045.png]]




--hyper cube interconnection:
					 another type shiii connection
					 here nodes are cpu memory io cpu or anything 
					 number of nodes are represented in the form of 
					 2 power n 
					 
![[Pasted image 20250512220259.png]]


### Cache coherence : 
		to ye multiprocessor system ki samsya hai 
		isme har processor ki apni cache memory hoti hai 
		to samasya ye hai ki , har cpu apni apni cache me data update karta rehta
		hai lekin , fir overall inconsistency aati hai , ki aakhir kaunsi cache ki value final main memory me dikhayi jaye 
		iske liye solution hai mueheheheh
PEHLE KUCHH TERMS DEKH LO: 

write update: apni cache me change karo to baki logo ki cache me bhi update propagate kardo
write through: jaise cache me update karo turant hi main memory me bhi udate karo 
write back: pehle pura operation perform karlo fir main memory me update karo
write invalidate: apne me update karo to baki logo ko message bhej do ki meri wali value abhi
		 confirm nahi hai , to usko mat use karna 

SOLUTIONS FOR CACHE COHERENCE:
		-> write update -write through
		 -> write update -write back 
		 ->write invalidate- write through
		 -> write invalidate- write back



### Interrupt cycle: 
![[Pasted image 20250513101227.png]]



### Assembler :

First pass of assembler : 

![[Pasted image 20250513114326.png]]



Second pass of assembler: 

![[Pasted image 20250513114614.png]]



### Registers :

![[Pasted image 20250513115716.png]]



### 4 Bit binary adder
![[Pasted image 20250513115733.png]]




### cpu IOP COMMUNICATION:

![[Pasted image 20250513130601.png]]



### DMA:
direct memory access 
I/O devices ka memory ke sath communicate karne ka ek trika hai 
total 3 hote hain
	Programmed I/O
	 Interrupt initiated I/O
	 DMA

DMA me CPU ko bich me sa hata diya jata hai aur Memory and IO device freely gutargu karte hain 
isme ek special hardware use hota hai "DMA CONTROLLLER"

to jab bhi IO device ko memory ke sath batchit karni hoti hai vo DMA controller ko request bhejta hai aur DMA controller MEmory ke pitaji CPU se bat karke memory ka hath IO device ko dila deta hai 


![[Pasted image 20250513182712.png]]

IO device DMAC ko request bhejta hai-> DMA request 

DMAC request paate hi cpu se request karta hai -> HOLD

agar CPU ka man hua to vo pehle sari info, jaise kaun se memory location se communication start hoga aur kitna size ka hoga ie 1000th location se , 500 words  ye info DMA ko bhejta hai 
aur haan boldeta hai access ke liye -> HLDA

DMAC IO device ko good news deta hai ki jao talks karo memory ke sath -> DMA ACK

IO device aur memory khushi khushi bate karne lagte hain kahani khatam 


--> Ab inki batchit CPU kaise hone de sakta hai muhahahahah , to vo bolta hai contiuously baat  nahi karne dunga kyuki jab system bus IO device le gaya to to CPU kya karega . vahi operations kar sakta hai jisme system bus ka kam na ho matlab mostly idle hi baitha rahega  

2 options hai 

1) Burst mode:   isme obv burst  mode , dudududu wait ddudududu wait dududuu aise hi chhote chhote chunks me data jata hai 

2) Cycle Stealing: agar IO device slow hai aur vo word prepare karne me time lagata hai to usko agar control diya to vo baith ke sochne lagega , to ham usko bolte hain bhai tu soch le pehle jab soch lena tab lelena , aur fir vapis lelete hain , aur bolte hain ab soch aram se aur ho jaye to bata dena

3) Interleaving : isme jab system bus free padi hoti hai tab dedete hain usko IO device ko 



### SIMD array processor:
![[Pasted image 20250513190256.png]]


### Status bits:
   1. Bit C (carry) is set to 1 if the end carry C8 is 1. It is cleared to 0 if the carry is 0.
2. Bit S (sign) is set to 1 if the highest-order bit F, is 1. It is set to 0 if the bit is 0.
3. Bit Z (zero) is set to 1 ifthe output ofthe ALU contains allO's. !t is cleared to 0 otherwise. In other words, Z = 1 if the output is zero and Z = 0 if the output is not zero.
4. Bit V (overflow) is set to 1 if the exclusive-OR of the last two carries is equal to 1, and cleared to 0 otherwise.
![[Pasted image 20250513193455.png]]


### RISC VS CISC
![[Pasted image 20250513194654.png]]




## Basic Control Unit
![[Pasted image 20250513202131.png]]


### Asynchronous data transfer :

	common clock is not used for all the components 
		kyuki koi device slow hhota hai koi fast . to same clock use karne me nuksan hota hai 
		isliye asyncronous data transfer use karte hain 
		to isme problems ye hoti hai ki , kaise pata chale ki source ne data bhej diya hai ya destination ne data recieve kar liiya hai ? ya destination ready hai receave karne ke liye ?ya source ready hai send karne ke liye ? and all other problems

to iske do tarike hain
	- Probe
	-  Handshaking

--> Probe : ek signal hai jo sending aur receaving ke samay bheja jayga as a acknowledgement 
do types hai 
	-Source initiated probe: isme data transfer per source signal initiate karta hai 
	data transfer karte hi vo ek strobe signal bhejta hai destination ko ki bhai maine data bhej diya hai
![[Pasted image 20250513231038.png]]

	- DESTINATION INITIATED PROBE:  ISME DESTINATION DEVICE PEHLE SIGNAL BHEJTA HAI KI IM READY FOR RECIEVING U CAN SEND THE DATA AND THEN DATA IS SENT TO DESTINATION DEVICE 

![[Pasted image 20250513231205.png]]


---HAND SHAKING ---

	-SOURCE INITIATED HANDSHAKING  : ISME PEHLE SOURCE DATA BUS ME DATA LOAD KARTA HAI AUR FIR DATA VALID SIGNAL DESTINATION KO BHEJTA HAI KI BHAI DATA LOAD HO CHUKA HAI VALID DATA HAI. TO VAISE HI DESTINATION UNIT DATA ACCEPTED SIGNAL BHEJTA REHTA HAI AUR JAISE , SAMAY SAMAPT HO JATA HAI TO SOURCE UNIT VALID DATA SIGNAL KO DESABLE KAR DETAHAI , VAISE BHI DESTINATION UNIT BHI SAMAJH JATA HAI KI AB DATA AANA BAND HO GAYA HAI YA AB VALID DATA AANA BAND HO GAYA HAI TO VO BHO ACCEPTED DATA SIGNAL KO BAND KARDETA HAI 

![[Pasted image 20250513231715.png]]

	-DESTINATION INITIATED HANDSHAKING:  TO ISME DESTINATION UNIT PEHLE EK SIGNAL BHEJTA HAI "READY FOR DATA " NAM KA 
	 USKE BAAD FIR SOURCE UNIT DATA VALID SIGNAL BHEJTA HAI AUR DATA BUS KO ENABLE KARKE DATA BHEJNA SHURU KAR DETA HAI , AUR JAB DESTINATION UNIT DATA ACCEPT NAHI KAR SAKTA TO VO READY FOR DATA SIGNLA DESABLE KAR DETA HAI TO FIR SOURCE UNIT BHI DATA SENDING BAND KARDETA HAI

![[Pasted image 20250513232109.png]]


### ARITHMATIC PIPELINE:
![[Pasted image 20250513234443.png]]



### MULTIPLICATIONS ASSEMBLY:
ORG 100
LDA CTR
CMA
INC
STA CTR
CLA
LDA F
STA START I
ISZ START
ISZ CTR
CLA
LDA S
STA START I
ISZ START
ISZ CTR
LOP,	LDA F
	ADD S
	STA START I
	LDA S
	STA F
	LDA START I
	STA S
	ISZ START
	ISZ CTR
	BUN LOP	
HLT
F, DEC 0
S, DEC 1
ANS, DEC 0
START, DEC 200
CTR, DEC 10
END



### DIVISION ASSEMBLY:


ORG 100
LDA CTR
CMA
INC
STA CTR
CLA
LDA F
STA START I
ISZ START
ISZ CTR
CLA
LDA S
STA START I
ISZ START
ISZ CTR
LOP,	LDA F
	ADD S
	STA START I
	LDA S
	STA F
	LDA START I
	STA S
	ISZ START
	ISZ CTR
	BUN LOP	
HLT
F, DEC 0
S, DEC 1
ANS, DEC 0
START, DEC 200
CTR, DEC 10
END