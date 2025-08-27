## **1. What is OS and objectives**
Operating system is a software that acts as a bridge betwen the user and the computer hardware. It provide a platofrm to run the applications and ensures the effcient use of the resources
**Objective adn Functions of OS**
1. **Process Management** = OS creates , schedules and terminates the process
2. **Memory Management** = OS make sure that each processs gets the memory  which it needed for the execution
3. **File System  Management** = OS organises the data into files and folders on storage devices
4. **Security** = Protects the data for unauthorized access
5. **User Interactionss** = Provide the CLI(commands) and GUI(Graphical Interface) fro interactions
6. **Error Detection** = OS detects and responds to the hardware / software errors.

## **2. Kernal and Shell**
The kernal and the shell  are two  essential components of an OS
**Kernal**
- Kernal is the core part of the OS that directly interacts with the computer hardware
- Kernal always resides in the memory and contriolls all systems resources.
**Features of Kernal**
1. Process scheduling and management
2. Memory allocating and deallocating
3. Handling system calls(interfaces between the software and hadrware)
4. Device Managments(manages the I/o devices like Keyboard , printers etc)
5. Provide abstraction so that the user do need to manage the hardware directly
**Types of kernal** 
- Monolothic Kernal = All the services run in the kernal space
- Microkernal = Only essential services run in the kernal space other in the user space
- Hybrid Kernal = Combines both the approches

**Shell**
Shell is a program in an OS that acts an an interface between the user and the kernal. It takes the commands from the user , interpret them and pass them to the kernal fro execution  . After execution it displayes the output back to the user.
**Functions of Shell**
1. Shell Accepts the commands from the users
2. Shell Interpret and translate the commands into system calls.
3. Provide programming features like loops , variables
4. Contro;s the program output(like start . stop . input . output)
5. Handles file operations and permission thorugh commands
**Types of Shell**
- CLI , GUI

## MltiPorgramming and MultiTasking OS
**Multiprogramming OS**
- Allows multiples programs to be loaded into the mmeory  at the same time
- The cpu executes one program and when it is wating for inpout / output it shedules another process
- the increases the CPU utilisation and keeps the system busy.
**Key Points**
- Several programs resides in the mmeory 
- CPU switch to another program when one program is wating for I/O
- Improves the efficency for resource utilisation
- Reduces the CPU idle time

**MutliTasking(Time Sharing) OS**
- Allow multiple taks to run simginly at the same time on a CPU
- Achieved through context switching where CPU rapidly switches between the taks
- Creates the illusion of parallel execution 
**Key Points**
- Each taks is given a time slice
- Preemptive in natiure

## SVR3 Scheduling Algorithm
The  System V Release(SVR3) scheduling is used in UNIX.
It is premtive , priority - based algorithm  with round robin inside each priorty queue.
**key points**
- Processess are placed in different priority queues
- High priority queues are scheduled before the low priorty ones
- If two process are in the same queue they will follow  the round robin
- The shedular is Primitive -> if a higher priority taks comes the current process will stop