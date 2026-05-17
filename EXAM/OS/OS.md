## Features of operating system
	Resource managemnet
	 Process management
	 Process Scheduling 
	 memory management 
	 Program execution
	 error detection and response


## Distributed operating System
	where multiple devices are controlled by single os or where multiple CPUs are utilized , here cpu memory network disk everything is shared and accessed by single operating system but for user it seems like a single centralized system 
	best example is cloud computing where mutiple hardwarres or machines are managed by single OS 





## PROCSSS CONTROL BLOCK (MIMP)
	a process is a part of program under execution 
	 Process controll block is a collection of information about a process 
	 and it is used to keep a record about process which is later used in context 
	  switching(mostly)
		A PCB contains various types of infrmation abut a process and various by architecture of a machine but there are some most common fields stored in PCB 
		-Process Id
		 -register
		 -program counter
		 -resources it is holding
		 -process state
		 
![[Pasted image 20250428200949.png]]




## Multi Threading 
		Multi threading is a technique that allows efficient execution of programms and also allows programs to perform multiple tasks under a single program  at a time for example web browser playing youtube video , downloading a file and also handling user input (when user is typing somewehere like using chat gpt in another tab)
		although cpu can execute a single task at time but it switches between these tasks(threads) so fast that it seems like these threads are being executed prallaley 

	ADVANTAGES:
		-improved performance
		 -enhanced responsiveness
		 -better cpu utilization



## Schedulers (IMP)
	1.Long Term Scheduler : Long term scheduler loads the process or jobs froom the       process or job pool to reeady state in main memory . 
	   it is also called job scheduler 
	  it selects mix of I/O bound (jo IO me jyada time khati hai) and CPU bound (yes       you guessed it right ) processes to balance  the cpu utilization
	  
	 2.Medium term scheduler:  Medium term sheduler loads the process from suspeded      or waiting state to again ready state . 
	 process which mayybe suspended because of some IO operation or due to arrival       of some high priority process are again scheduled by mid term scheduler 

    3.Short term Scheduler : Short term Scheduler schedules the jobs from ready         state to running state
    it allocates the CPU to processes which are ready to run 
    thus it is also called a CPU scheduler 


### Race Condition:
		race cndition is a situation where more than one proceses are trying to              access the critical section and the output depends on the order of the              execution of the processes.
		sidhi bhasha me mere pass ek paise ka dibbad hai , aur do log hain , ek              admi sirf paisa dalta hai (lets say 1 rupar) aur ek sirf paise nikalta hai.
		to last me dabbe me kitne paise honge vo is chiz par depend karta hai ki             pehle paise nikale gaye the ya dale gaye the (order or execution)
		
## Semaphore:  (MMIMP)
		semaphore is a tool used in OS to help manage how different processes  share resources like memory or data without causing conflicts. 
		it is used to implement critical section , which is a part of code that must be executed by only one process at a time .

it is a lock based machanism that is designed to achieve process synchornization.


two types of semaphore:
		binary semaphore(0 or 1 )
		 counting semaphore 
two functions are used in semaphore:
		wait(p): decrement value of semaphore
		 signal(v): increments value of semaphore
![[Pasted image 20250428200805.png]]




## Inter Process communication: (IMP)
		inter process communication is a method that allows process to communicate in various situations. 
TWO TYPES OF PROCESS:
			 ***--Independent Process:***    An independent process is not affected by the execution of other processes. Independent processes do not share any data or resources with other processes. No inter-process communication is required in this case.
			--***Co-operating process***:   Co operative processes are affected by other process's execution and they also affect other's execution (na jiyo na jine do) , and they communicate with each other(bitching about third process ) yahan IPC hota hai.

IPC se ye log apas me bat chit karte hain ek dusre ki burai karte hain.

TWO MODELS of IPC 
		***-Shared memory***:- isme kya hota hai ki ek shared memory hoti hai , aur usko sab log access karte hain , ek process memory me kuchh likhta hai aur dusri process usko padh leti hai , like whatsapp chat 
		 ***-Message passing***:- isme agar ek process ko dusre se bat karni hai to  kernal bich me kood padta hai (kernal computer ke pitaji hain inse jyada powerfull koi nahi) to proccess apna message kernal ko deti hai aur fir kernal vo message dusri process ko dedeta hai , like chiththi wali zamana , you<-->postman<-->your QT


IS BATCHIT KE FAYDE:
		-batchit se efficency badhti hai
		 -bas yahi hai isko hi ghuma ke lkhna 3-4 bar 
![[Pasted image 20250428210402.png]]


## DEADLOCK (MIMP)
	a situation whhere a set of processes are stucked , because of waiting for each other to release resources and  they are also holding resurces themselves. 

![[Pasted image 20250429181818.png]]


Conditions that causes Deadlock: 
	 ***Mutual exclusion:*** jab ek process kisi resource ko apne pitaji ki sampatti samajh le aur dusre ko na use karne de.
	 ***Hold and Wait:*** jab ek process kisi resource ko leke baith jaye aur chhode hi na (unlike her)
	 ***No preemption:*** jab processes par koi rok tok na lagayi jaye vo apni marzi ki malkin hon(she)
	 ***Circular Wait:*** jab kuchh process milke ek dusre k wait karen , uk ik
	 
Methods to handle DeadLocks:
		1. Deadlock ignorance:   isko ostrich algorithm bhi kehte hain(idk algo kyu bolte hain isme kuchh algo hai hi nahi) to isme OS ostrich ki tarah apni mundi zameen me ghusa ka acting karta hai ki deadlock to hai hi no . kuchh hua h nahi hame ka pata  hamse na puchho bhaiya :) . 
		2. Deadlock Prevention: just avoid the conditions described above easy 
		3. Deadlock avoidance:  isme BANKER'S algo [L-4.5: Deadlock Avoidance Banker's Algorithm with Example |With English Subtitles](https://www.youtube.com/watch?v=7gMLNiEz3nw)
		4. Deadlock detection and recovery : bas dhundho ki deadlock hai ki nahi aur mile to usko sahi karo , par isse bad system slow hota hai , better hai mundi niche kar ke baith jao aur bolo hamko to pata hi no hai par still agar mil gaya deadlock and fir  usko remove karna hai to :
			1. by preempting process
			2. rollback to previous checkpoint(uske liye checkpoint banaya bhi hona chahiye)
			3. Kill that process




### Reader and writer Problem
	Reader and write problem is one of the classic inter process communication           problems.
    -there is one file or say database or say any data.
    -there are two process.
	-Reader and writer 
	-reader process can only  read the data , file or database
	-writer process can update(read and write) database
	-when reader is reading , other readers can read (obv do log char log ek             book padh sakte hain aram se )
	-when reader is reading , writers cant write , varna locha ho jayga 
	-when writer is writing , no reader can read and no other writer can write
	 -to achieve this we use semaphores
	 -one integer variable is also used
		 that is called 'readerCount'. yes , it just counts the number of readers            currently reading the data
	 -two semaphores are used
		 1.mutex:make sure that only one process is accessing "readerCount" at a              time
		 2.wrt:make sure when writer is writing no one can do anything and when               reader is reading no one can write 
      -wait and signal are semaphore functions 
	      1.wait ko samjho ki vo gate band kardeta hai jab koi andar ho
	      2.signal gate khol deta hai jaise andar ka admi bahar aaye
	      
->left side is writer code and right side is readers code
![[Pasted image 20250430135831.png]]



### Dining philosopher's problem:
		 It is a classcic Inter process communication problem.
		 -here 5 phillosopher are sitting on round table
		 -each having a plate infront of them 
		 -each phillosopher needs 2 forks to eat noodles(which are exactly on the            left and right side of them)
		 -but only 5 forks are placed on the table
		 -each phillosopher either thinks or eats at a time

![[Pasted image 20250430182630.png]]
	-now the task is to make sure that phillosophers eat in such a manner that no dead lock shall occure
	-here each phillosopher is process and forks are resources.
	-we use semaphore to solve this problem
	-each fork is semaphore variable
	-that means we will use wait and signal (p and v ) functions for each of them
	-it will help in making sure only one phillosopher is using a perticular fork

![[Pasted image 20250430183042.png]]
when wait is executed for any fork , no other phillosopher can use it 
and when signal is executed others can use that fork . simple

### Fixed partition and Variable Partition of memory:
		1.Fixed partition: isme main memory ke fix sized part bana diye jate hain            aur fir aane wali processes ko unme store kiya jata hai bas
		 isse ek samasya aati hai jiko bolte hain "internal fragmentation".
		 
		 -for example 100mb ki memory hai maine usko 10-10 ke fix parts me devide kar diya , ab mere pass 9-9 mb ke processes aati hain main unko ek ek part me rakhta jata hu . aise 10 processes aate hain aur mere 10 ke 10 parts full ho jate hain. lekin ruko 9-9 mb ke process the matlab har part me 1 mb khali hai aise karke 10 part hai to 1*10 mere pas 10 mb abhi hai, ab mere pass ek aur process aati hai , parrrrr ab main usko ye chindi wali memory 1-1mb bhikh mangi hui memory nahi de sakti vo legi hi nahi uska bhi standard hai . isko bolte hain internal fragmentation yaani andar bache huye thode thode space k use na kar pana.

	Isme ek aur samasya aati hai "External fragmentation"
		-Isme kya hota jaise , pehle ke example 10 part me 10 process thi.
		ab 2 process khatam ho gayi lekin kaise ? ek gayi 5th block se ek gayi 8th block se (out of 10 blocks) ab ek aur process ayi 20 mb ki , lekinnnn main ab vo 5th and 8th block ko milake 20 mb karke isko nahi de sakta kyunki iska bhi koi standard hai isko line se memory mangta hai aisa bikhra bikhra nahin.
		

		  2.Variable partition: isme kya hota ki ham memory ko pehle se hi part nahi banate , jaisa jaisa process aane ka vaisa viasa jagah dene ka unko jitna mangta hai . jhanjhant ich nahi bava.
		  isse internal fragmentation to khatam ho jaynga par vo external wala rehne ka . 

![[Pasted image 20250430185756.png]]

![[Pasted image 20250430231640.png]]
External fragmentation ko khatam karne ka simple tarika "compaction"
samjho main memory ek bricks ka stack hai par ek mst function ke sath , ki agar kisi bhi brick ke niche ki brick nikali to uske upar ki bricks automatically niche aajaygi , simple 
to kabhi memory ke block alag alag honge hi nahi , khali kidhar bhi ho jagah upar hi banegi.
[Compaction : A Technique to Deal with External Fragmentation Explained with Example in Hindi](https://www.youtube.com/watch?v=x2ijm1AESNM&list=PLYwpaL_SFmcD0LLrv7CXxSiO2gNJsoxpi&index=32)


### Memory allocation Strategies:
[First Fit , Next Fit , Best Fit , Worst Fit ll Operating System ll Explained with Example in Hindi](https://www.youtube.com/watch?v=wQ8yfmnHFB4&list=PLYwpaL_SFmcD0LLrv7CXxSiO2gNJsoxpi&index=35)
	1.First fit: samjho memory ke parts padele hai apun log , is bar fix nai alag alag size ke barobar ? to abhi na kya hota hai jaise hi koi process idhar aata hai (yes right sapna from kapil sharma XD) to memory me dhundhne ka processes ko fit ho aisa size ka block , bada hoga to chalta hai apne ko bas process ko andar karne ka hai. to jo bhi pahela block milta hai na usme dal do bas FIRST FIT .

    2.Next Fit: isme bhi first ke jaisa bas last time jidhar process store kiya tha udhar se start karo is bar . jaise 10 block hai and last time 3rd block me process dala to ab new process ke liye 1st se search nai karne ka 3rd se karne ka .

     3.Best fit: isme mast rehta hai. isme har process ke liye shuru se seach karne ka aur aisa block search karne ka jisme memory waste sabse kam ho.
     for example agar 5 mb ka process hai aur apne ko 3 block mile jisme ye aajayga. ek 10 mb ka ek 8mb ka aur ek 6mb ka to ham, 6mb wala choose karenge kyunki usme memory waste sabse kam hai. 

	 4.Worst fir: best fit ka ekdum ulta. shuru se dekho and jis block me sabse jyada memory waste ho vo choose karo,.



### Paging:
[Paging ll Page Table ll Operating System ll Easiest Explanation Ever in Hindi](https://www.youtube.com/watch?v=7VshrpZM-DA&list=PLYwpaL_SFmcD0LLrv7CXxSiO2gNJsoxpi&index=38)
		to process ko directly pura ka pura memory me load karne par tarah tarah ki samasyaen aati hain jeevan me jaise internal fragmentation external fragmentation aur na jane kya kya (mujhe bhi nahi pata).
		To is sab se bachne ke liye aata hai hamara hero Paging.
		paging me ham process ke chhote tukde kardete hain called pages
		aur main memory ke bhi tukde kardete hain called frames
		frames and pages ka size same hota hai obv taaki ek frame me ek page load kiya ja sake 
		-> to jab bhi cpu ko kuchh chahiye vo bolta hai bhaiya is page ka ye wala word leke aao isko bolte logical address
		 -> logical  address = page no + page offset(jo word ya line joiye)
		 ->fir ye logical address MEMORY MANAGEMENT UNIT ko diya jata hai
		 -> MMU jata hai PAGE TABLE ke pass aur bolta hai bhaiya ye jo cpu ne page diya hai iska frame number batao zara ki ye memory me kidhar stored hai
		 ->page table , har page ki info rakhta hai bahut sari info
		 -> to page table MMU ko frame number dedeta hai us process ka
		 -> fir MMU ek PHYSICAL ADDRESS banata hai jisme frame number and offset hota hai
		 -> fir us PHYSICAL ADDRESS ka use karke main memory se jo bhi word(page ooffset me likha tha) chahiye vo leke CPU ko de dete hain 

![[Pasted image 20250430200244.png]]


### Demand Paging and Page Fault:
		to paging me kya hota tha sab pages pehle se load karlete the 
		par isme kya hota hai ki , main memory shuru me ekdum khali rehti hai jab tak kisi page ki zarurat nahi padti tab tak khali rehti hai.
		fir jaise hi CPU ko kam lagta hai to vo request generate karta hai page ki aur fir usko MAIN memoryy me dhundha jata hai lekinnn voto khali hai aur  page nahi milta to ab PAGE FAULT occure hota hai, aur page fault hone par OS control leleta hai and us needed page ko main memory me load kiya jata hai aur firse reques aati hai and is bar page mil jata hai.

	--What OS does when page fault occures:
			1.Raise exception
			 2.save process state
			 3.determine fault type and vailidy
			 4.find page lcoation on disk
			 5.find free frame on memory
			 6.load required page into frame
			 7.update page table
			 8.restart the process
### Logical and physical address(related to memory management)
![[Pasted image 20250430183728.png]]


### Banker's Algorithm:[L-4.5: Deadlock Avoidance Banker's Algorithm with Example |With English Subtitles - YouTube](https://www.youtube.com/watch?v=7gMLNiEz3nw)
![[Pasted image 20250430231227.png]]



### FILE ACCESS METHODS:
	SEQUENTIAL ACCESS: JAB AAP FILE KO LINE BY LINE HI ACCESS KAR SAKEIN YA KAHO KI JAISA STORE KIYA GAYA THA VAISE HI ACCESS KAR PAYEN , DIRECT KAHIN BHI JUMP NA KAR SAKEN TO VO SEQUENTIAL ACCESS KEHLATA HAI
	BADI FILE HUI TO KALLU KALIYA BAN JAOGE KUCHH DHUNDHNE ME 


	 RANDOM ACCESS: ISME AAP KAISE BHI KAHIN SE BHI KISI BHI HATH SE KISI BHI PAIR SE KAHIN SE KUCHH BHI PAKAD KE NIKAL SAKTE HO FILE ME SE :) 
	 YE THODA COMPLEX HO JATA HAI BAS , BUT GREAT POWER COMES WITH GREAT RESPONSIBILIY LALA.


### Domain Protection:
	system me resource hote hain (cpu memory i/o devices etc) aur process hoti hain
	ye resource ko ham object kehte hain
	 ab ye alag alag process alag alag objects ko access karti hain
	 lekin koi process kisi obkect ko gandi nazar se na dekhe yaani uska missuse na      kare iske liye objects ko security dena zaruri hai.
	 har object (resource) ki ek uniqe id ya name hota hai jisse pata chalta hai ki      object ko koi kitna chhoo sakta hai heheh
	 samjho ek ghar hai jiske andar teen kamre hain, ek kamre ko sirf bahar se dekh sakte ho dusre ke andar ja sakte ho , teesre ke andar jaake rakha hua saman  bhi use kr sakte ho. 
	 to isme ghar protection domain hai aur kamre objects(resource) aur kya kya kar sakte ho vo operations hain.
	 iskoe aise likhe hain:  <object , {access right set}>
	 access right set matlab kya kya kar sakte ho us object ke sath

![[Pasted image 20250501102948.png]]
isme 3 domain hain. sabme alag alag objects hain and unke permissions
jo overlap ho rahe hain unka matlab dono domains me same object ke liye same operations ya permissions hain 

TO bas ye ek overalll tarika hai objects ko protect karne ka aur processes ko utna hi dene ka jitni unki aukat hai hhha jk , processes ko utne hhi resources dena jitne ki unhen zarurat hai 

ACCESS MATRIX: 
		abhi same upar vale concept ko gole me na dikha ke matrix me dikhana hoto access matrix bolo. 
		ye bhi bas yahi batata hai ki kis domain me kis object par kaunsa operation allowd hai
![[Pasted image 20250501103447.png]]

isme 4 domain hain unme sab me 4 objects hain jisme 3 file ek printer.
abb dekho jaise domain 1 me main file1 read kar sakta hu lekin vahi same file ko read karne ki permission domain 2 me nahin hai mere pass.

ab vo switch wala kya hai ? 
jaise domain1 me dekho . D1 ke D2 me likha hai switch , iska matlab main domain 1 se domain 2 me ja sakta hu lekin aur kisi domain me nahi ja sakta


ab isi table se agar sirf ek column utha lo to usko bolenge ACCESS CONTROL LIST
aur agar ek row utha loge to usko bolenge capability list

jab user kisi resource ya object ko access karna chahta hai tab os check karta hai ACCESS CONTROL LIST
![[Pasted image 20250507201755.png]]
![[Pasted image 20250501111659.png]]
ki bhaiya kya F1 me koi read kar sakta hai ? haan kar sakta hai

jab user process koi object access karna chahti hai tab os check karta hai capability list
![[Pasted image 20250507201806.png]]
ki bhaiya ye jis user ki process hai kya vo user jo kam karna chah rha hai vo kam karne ka adhikar hai use ? 





### system Threats:
		aisi koi bhi activity jo ki pure ke pure SYSTEM ko nuksaan pahuncha sakti hai , uski confidentiality integrity and availability ko bigad sakti hai .
		
		-privilage escalation: jitna access tumko hai usse jyada prapt kar lena
	threats ke alag alag types:
		
		-DOS: denial of service
		
		 -PORT SCANNING: system me open ports ki checking karna jisse attack ho sake

		 -MAN IN THE MIDDLE : uk i guess

		 -ROOT KITS: Os ko modify karna taaki , vo harmfull code detect na kar sake



### Program Threats:
	aise koi bhi code ya activity jo ki kisi perticular software ya application ko nuksan pahunchati hai , iska maksad pura system nahi hota 
	
			-virus:kisi program ke andar dala gaya aisa code jo khud ko copy kar sakta hai aur ek computer se dusreme ja sakta hai 
			
			 -worms: aisa program jo kisi software ke andar dala jata hai , aur jo khud se phail sakta hai , ye usually network security ki lanka lagata hai
			 
			 -trojan horse: aisa harmfull code jo legitimate prograam lagta hai
			 
			 -trap door:jab attacker koi aisi vulnerability bana de jska use karke bhavishy me firse attack kiya ja sake

			 -LOGIC BOMBS: koi specific condition pe koi kala kam karvana huihui
			 




### Virtualization:
	ye hai sabse easy practical and usefull concept unlike others
	isme aap le sakte ho ek ke sath anek ke maze yes
	 aapke pass ek hi computer hai 
	 jisme windows dala hua hai
	 lekin aapko chahiye linux ke bhi maze 
	 lekn aap abhi itne pro nahi ho ki windows uda do aur sara kaam linux me karo
	 aapko bas sikhna hai slowly
	 aur fir aapko games bhi to khelna hai windows me hehehe
	 to aap use karo VIRTUALIZATION
	 matlab aap ek ke satk ek free OS chala sakte ho ek hi hardware me 
	 do hi nahi aur bhi jyada
	 to aap download karo koi bhi VIRTUALIZATION SOFTWARE jo virtualization ki 
	  suvidha degga obv
	  jaise VIRTUALBOX
	  ye free hai
	  koi paid version ke liye bacha ke rakhi gayi suvidha nahi hai ki paise doge to
	   ye milega , sab free hai
	   fir aap download karo us OS ki image file jo aapko chahiye 
	   fir aap thoda sa jantar mantar karke apne device me do do OS ek sath chaala 
	   sakte ho

		to VIRTUALIZATION matlab ek hi hardware ya ek hi system me ek se jyada OS use karna using virtualization software 
		isme har OS ka ek alag isolated environment rehta hai user ke liye 
		aur apna main Os jisko HOST OS kehte hain vo hardware control karta hai aur uski suvidha VIRTUAL OS ko deta hai
		jo new OS dalte hian aur jo machine aap acess karte ho VIRTUALBOX  ke andar usko virtual machine kehte hain 

FAYDE:
	paisa bachta hai
	 efficiency badhti hai
	 businesses ko fayda 
	 idk man im done

### Synchronization in linux:



### Criteria for good process shceduling algorithm:

1.CPU UTILIZATION: cpu most time busy rehna chahiye 
2.THROUGHPUT: number of process executed in per unit time should be high
3.TURN AROUND TIME: process ke aane se lekar khatam hone tak laga hua time kam ho
4.WAITING TIME: process ne kitna samay ready queue me bitaya ? ye samay kam ho
5.RESPONSE TIME: process ke aane ke kitne samay bad use CPU mila ? ye samay kam ho


### MONITORS:
	monitors are ussed to make it easier to avoid race condition and , allow mutual exclusion.
	monitors are collection of variables methods and data structures.
		when using monitors , process can access procedures of monitor but cant access variables and data structures
		monitor provide facility , that only one process can operate inside a monitor at a time
		jab monitor ka procedure call hota hai to first it is checked whether or not there is already a process inside monitor, if yes then that call is suspended if not then it is executed.




critical section: part of program or code where process is trying to access shared resources.

mutual exclusion: a concept of allowing only a single process to access a resource ata time

semaphores: data type used to implement critical section and avoid race condition , usually a integer



### Thread and process 
![[Pasted image 20250503193024.png]]





### Raid levels:
	Redundant array of independent disks
		this is a technique used for data safety during failure times and recovery
		also for better performance
			data is stored in multiple disks in various approaches to maximize the probability of data recovery

RAID 0:  striping technique is used , data stored in diffrent disks 
RAID 1: called mirroring , copy of entire data is stored in different disk
RAID 1+0:  combination of raid 0 and 1
RAID 2:  lallu laal, so no one uses 
RAID 3: parity is stored in different disk , so data can be recovered
RAID 4: same as 3
RAID 5: distributed data parity is stored to minimize risk
RAID 6: double distributed parity is stored muhehehehehe




**Logical I/O:**

- Operates at a higher level of abstraction
- Deals with logical data structures (files, records, database tables)
- Hardware-independent operations
- Managed by the operating system or database management system
- Uses logical addresses or identifiers to access data
- Example: A program opening a file by name and reading records

**Device I/O:**

- Operates at a lower, physical level
- Directly interacts with specific hardware devices
- Deals with physical storage locations and device-specific operations
- Managed by device drivers and controllers
- Uses physical addresses to access data blocks
- Example: Reading a specific sector from a disk drive





### page replacement strategies
[FIFO Page Replacement Algorithm Explained with Example in Hindi](https://www.youtube.com/watch?v=ll4oGIGuPYY&list=PLYwpaL_SFmcD0LLrv7CXxSiO2gNJsoxpi&index=46)
		FIFO:
		sabse simple hai, first in first out ke basis pe kaam karta hai .
			kisi bhi process ko limited frames allocate kiye jate hain(koi bhi page replacement algo ho fifo ho LRU ho optimal ho koi bhi)
			
			jab jis page ki request aati hai aur vo main meory me nahi hota to page fault hota hai aur vo page secondary memory se load kiya jata hai main memory me 
par agar koi page request kiya jaye aur vo main memory me na ho , to usko obv secondary memory se laake load karna padega , lekin proceses ko allocated frames full hain , to new page ko load karne ke liye jo , sabse pehla page load kiya gaya the usko remove kar diya jayga . 
isko blte hain FIFO .

![[Pasted image 20250504131354.png]]




OPTIMAL page replacement algorithm :
[Optimal Page Replacement Algorithm Explained With Solved Example in Hindi](https://www.youtube.com/watch?v=JzNOH1Vz7C8&list=PLYwpaL_SFmcD0LLrv7CXxSiO2gNJsoxpi&index=47)
			isme ham dekhte hain ki kaunsa page aage use nahi hone wala , ya bahut der me use hone wala hai, usi ko niikal dete hain aur new page load karte hain


Least recently used : 
[LRU Page Replacement Algorithms Explained with Solved Example in Hindi](https://www.youtube.com/watch?v=di9y-J_9PyQ&list=PLYwpaL_SFmcD0LLrv7CXxSiO2gNJsoxpi&index=48)
	isme ham dekhte hain ki kaunsa page , bahut der se use nahi hua , usi ko ham nikal dete hain and new page load kardete hain




### unix/linux kernal:

![[Pasted image 20250505130427.png]]
	
sabse niche interrupt handler and dispatcher. 
ye lof bahut zaruri kam karte hain, ye hi device se communicate karte hain. actuall hw se 
	abhi main part kernal ke jo hain , vo 3 part me devided hai
			I/O component
			 Memomry management component
			 process management component
I/O management obv input output ke liye kam karta hai 
ab isme sabse niche level pe hote hain device drivers 
aur sabse upar virtual file system.
isme terminal hai jo user se input leke command execution vagerah karta hai
sockets jo hai vo netweok comunication ka kam karta hai , ki jo packet jiske lie aay hai usko hi mile aur jisko bhejna hai usko hi jaye and all 
file system obv , files broo, 

memory managemnt component , sab apna virtual and physcial memory manegement , allocation and all

process management process scheduling , creation deletion halt karna swap karna and alll that stuff


### 7 state process diagram:


![[Pasted image 20250505200330.png]]

### Dispatcher : 
	Dispatcher is a special type of program whose work starts after the scheduler. When the scheduler completes its task of selecting a process, it is the dispatcher that moves the process to the queue it needs to go to.

The dispatcher is the module that hands over control of the [CPU](https://www.geeksforgeeks.org/what-are-the-functions-of-a-cpu/) to the process that has been selected by the short-term scheduler.

****The following things happen in this function:****

1. ****switching context:**** Cores the current process and restores the state of the process to be run next.
2. ****Switching to User Mode:**** Makes sure that it runs in the user mode and not kernel mode, which is for security and privilege break-
3. ****Jumps to the correct location in the user program**** from where the program can be restarted.


### Fork system call:
	fork system call karne par , jitni bhi parent process chal rahi hain sabka child process create ho jata hai
		 child process create hone par child id  0 return hota hai
			  aur prent ki id postive number return hota hai 
		aur agr fork fail ho gaya to negative ya -1 return hota hai
		agar n fork execute huye hain to , 2^n output aaynge 
		aur (2^n)-1 child process banegi.


### producer consumer usign semaphore:
![[Pasted image 20250506131555.png]]


### Lock variable"

![[Pasted image 20250506132316.png]]

### Test and set :
![[Pasted image 20250506132856.png]]



### Turn variable or Strict alternation:

![[Pasted image 20250506134108.png]]



### linux file system:



ps 
fork
join




### Segmentation:

![[Pasted image 20250507200133.png]]



### Thrashing :

![[Pasted image 20250507200313.png]]