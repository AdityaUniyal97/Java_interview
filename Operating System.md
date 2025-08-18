- Operating System is a software that functions as a bridge between the computer hacrdware and user
- It serve as a splatform for running the application , and it also maintains the computer hardware resources.
**Core Components**
- Process Management = OS creates , schedules and terminates the process
- Memory Management = OS make sure that each process gets the memory which it need for its execution
- Files System Management = OS organises the data into the files and folders on storage devices
- Secutiry = Proctects the data from unauthorized access

## Process , Program and Thread
**Process** 
- Process is an instance of a program which is in execution
- It is not just a code , but also include the program's current activity , state , memory layout . allocated resocurces and the data which is needed during the excution
- Whenever a program is launched the OS loads the neccessary code into the moemory and creates a process and  assign resources and begin its execution 

**Program**
- Porgram is a set of intstruction written in specific programming language that tells a computer what to do.
- Program is nothing but just a code which is stored in the disk  and it becomes active when it get executed by the OS , turning program into process

**Thread**
- Thread is a smaller unit of the Process . like If Process is a big task than thread is smaller task within it
- A process can have one or multiple threads. 
- Each thread represent a single sequence of instructions which is being executed indipendently
# Types of OS 
**1. Batch Operating System** 
- Batch is the earliest OS , designed to execute a collection of taks without user interaction during execution. 
- Jobs are grouped together and than processed sequenctially
**How it works**
-  Users submite thier jobs to an opeartor 
- Than jobs are grouped into the batches based on criteria such as resources requirements   or job priority
- Than the system executes the jobs into batch 
- Once complete the output is returned to the user

**2.Multiprogramming OS** 
- allow multiple program to reside in memory  simultanusely and share the resources such as CPU,memory
**How it Works**
- Multiple programs are loaded into the memory
- Than OS allocates CPU , memory to those programs which needed
- The OS switch between the programs like allocating memory to one program and keep other as wiaitng
- Once complete the output is returned to the user

**2. Time Sharing / Multitasking OS**
- Multiple users can use the CPU simulataneously by shring the time
- Ex: Window , lInux
- Here the Fast CPU switching creates the illusion of simulaneus exuctuion
**3 Distributed Operating System**
- Manage multiple computers and make them appear as a one system
- Ex: Google distibuted system
- Resources are shared accross all the connected computers
**4 Mutlipupose Operating System**
- Multi pupose OS is designed to support multiple task for multiple users at the same time
- can do different tpes of tasks at the same times
- Support multiple users using the system simulataneusly

