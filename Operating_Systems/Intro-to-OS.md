# OperatingSystems
	An Operating System can be defined as an interface between user and hardware. It is responsible for the execution of all the processes, Resource Allocation, CPU management, File Management and many other tasks. The purpose of an operating system is to provide an environment in which a user can execute programs in a convenient and efficient manner.


#	Types of Operating Systems :
1.	Batch OS – A set of similar jobs are stored in the main memory for execution. A job gets assigned to the CPU, only when the execution of the previous job completes.
2.	Multiprogramming OS – The main memory consists of jobs waiting for CPU time. The OS selects one of the processes and assigns it to the CPU. Whenever the executing process needs to wait for any other operation (like I/O), the OS selects another process from the job queue and assigns it to the CPU. This way, the CPU is never kept idle and the user gets the flavor of getting multiple tasks done at once.
3.	Multitasking OS – Multitasking OS combines the benefits of Multiprogramming OS and CPU scheduling to perform quick switches between jobs. The switch is so quick that the user can interact with each program as it runs.
4.	Time Sharing OS – Time-sharing systems require interaction with the user to instruct the OS to perform various tasks. The OS responds with an output. The instructions are usually given through an input device like the keyboard.
5.	Real Time OS – Real-Time OS are usually built for dedicated systems to accomplish a specific set of tasks within deadlines.
	Process : A process is a program under execution. The value of the program counter (PC) indicates the address of the next instruction of the process being executed.
Each process is represented by a Process Control Block (PCB).
	Process Scheduling:
1.	Arrival Time – Time at which the process arrives in the ready queue.
2.	Completion Time – Time at which process completes its execution.
3.	Burst Time – Time required by a process for CPU execution.
4.	Turn Around Time – Time Difference between completion time and arrival time.
Turn Around Time = Completion Time - Arrival Time
5.	Waiting Time (WT) – Time Difference between turn around time and burst time.
Waiting Time = Turnaround Time - Burst Time

# 	Thread (Important) : 
A thread is a lightweight process and forms the basic unit of
CPU utilization. A process can perform more than one task at the same time by including multiple threads.
	A thread has its own program counter, register set, and stack
	A thread shares resources with other threads of the same process: the code section, the data section, files and signals.
Note : A new thread, or a child process of a given process, can be introduced by using the fork() system call. A process with n fork() system call generates 2^n – 1 child processes.
There are two types of threads:
	User threads (User threads are implemented by users)
	Kernel threads (Kernel threads are implemented by OS)



#	Scheduling Algorithms :
1.	First Come First Serve (FCFS) : Simplest scheduling algorithm that schedules according to arrival times of processes.
2.	Shortest Job First (SJF): Processes which have the shortest burst time are scheduled first.
3.	Shortest Remaining Time First (SRTF): It is a preemptive mode of SJF algorithm in which jobs are scheduled according to the shortest remaining time.
4.	Round Robin (RR) Scheduling: Each process is assigned a fixed time, in a cyclic way.
5.	Priority Based scheduling (Non Preemptive): In this scheduling, processes are scheduled according to their priorities, i.e., highest priority process is scheduled first. If priorities of two processes match, then scheduling is according to the arrival time.
6.	Highest Response Ratio Next (HRRN): In this scheduling, processes with the highest response ratio are scheduled. This algorithm avoids starvation.
Response Ratio = (Waiting Time + Burst time) / Burst time
7.	Multilevel Queue Scheduling (MLQ): According to the priority of the process, processes are placed in the different queues. Generally high priority processes are placed in the top level queue. Only after completion of processes from the top level queue, lower level queued processes are scheduled.
8.	Multilevel Feedback Queue (MLFQ) Scheduling: It allows the process to move in between queues. The idea is to separate processes according to the characteristics of their CPU bursts. If a process uses too much CPU time, it is moved to a lower-priority queue.
# 	The Critical Section Problem:
1.	Critical Section – The portion of the code in the program where shared variables are accessed and/or updated.
2.	Remainder Section – The remaining portion of the program excluding the Critical
Section.
3.	Race around Condition – The final output of the code depends on the order in which the variables are accessed. This is termed as the race around condition.
A solution for the critical section problem must satisfy the following three conditions:
1.	Mutual Exclusion – If a process Pi is executing in its critical section, then no other process is allowed to enter into the critical section.
2.	Progress – If no process is executing in the critical section, then the decision of a process to enter a critical section cannot be made by any other process that is executing in its remainder section. The selection of the process cannot be postponed indefinitely.
3.	Bounded Waiting – There exists a bound on the number of times other processes can enter into the critical section after a process has made a request to access the critical section and before the request is granted.
#	Synchronization Tools:
1. Semaphore : Semaphore is a protected variable or abstract data type that is used to lock the resource being used. The value of the semaphore indicates the status of a common resource.
There are two types of semaphores:
Binary semaphores (Binary semaphores take only 0 and 1 as value and are used to implement mutual exclusion and synchronize concurrent processes.) Counting semaphores (A counting semaphore is an integer variable whose value can range over an unrestricted domain.)
Mutex (A mutex provides mutual exclusion, either producer or consumer can have the key (mutex) and proceed with their work. As long as the buffer is filled by the producer, the consumer needs to wait, and vice versa.
At any point of time, only one thread can work with the entire buffer. The concept can be generalized using semaphore.)
