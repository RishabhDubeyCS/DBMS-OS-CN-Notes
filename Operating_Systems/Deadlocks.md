#	Deadlocks (Important):
A situation where a set of processes are blocked because each process is holding a resource and waiting for another resource acquired by some other process. Deadlock can arise if following four conditions hold simultaneously (Necessary Conditions):
1.	Mutual Exclusion – One or more than one resource is non-sharable (Only one process can use at a time).
2.	Hold and Wait – A process is holding at least one resource and waiting for resources.
3.	No Preemption – A resource cannot be taken from a process unless the process releases the resource.
4.	Circular Wait – A set of processes are waiting for each other in circular form.



	Methods for handling deadlock: There are three ways to handle deadlock
1.	Deadlock prevention or avoidance : The idea is to not let the system into a deadlock state.
2.	Deadlock detection and recovery : Let deadlock occur, then do preemption to handle it once occurred.
3.	Ignore the problem all together : If deadlock is very rare, then let it happen and reboot the system. This is the approach that both Windows and UNIX take.
	Banker's algorithm is used to avoid deadlock. It is one of the deadlock-avoidance methods. It is named as Banker's algorithm on the banking system where a bank never allocates available cash in such a manner that it can no longer satisfy the requirements of all of its customers.
	Memory Management: These techniques allow the memory to be shared among multiple processes.
	Overlays – The memory should contain only those instructions and data that are required at a given time.
	Swapping – In multiprogramming, the instructions that have used the time slice are swapped out from the memory.
	Techniques :
(a)	Single Partition Allocation Schemes – The memory is divided into two parts. One part is kept to be used by the OS and the other is kept to be used by the users.
(b)	Multiple Partition Schemes –
1.	Fixed Partition – The memory is divided into fixed size partitions.
2.	Variable Partition – The memory is divided into variable sized partitions.
Note : Variable partition allocation schemes:
1.	First Fit – The arriving process is allotted the first hole of memory in which it fits completely.
2.	Best Fit – The arriving process is allotted the hole of memory in which it fits the best by leaving the minimum memory empty.
3.	Worst Fit – The arriving process is allotted the hole of memory in which it leaves the maximum gap.
Note:
	Best fit does not necessarily give the best results for memory allocation.
	The cause of external fragmentation is the condition in Fixed partitioning and
Variable partitioning saying that the entire process should be allocated in a contiguous memory location.Therefore Paging is used.
1.	Paging – The physical memory is divided into equal sized frames. The main memory is divided into fixed size pages. The size of a physical memory frame is equal to the size of a virtual memory frame.
2.	Segmentation – Segmentation is implemented to give users a view of memory. The logical address space is a collection of segments. Segmentation can be implemented with or without the use of paging.
	Page Fault:
A page fault is a type of interrupt, raised by the hardware when a running program accesses a memory page that is mapped into the virtual address space, but not loaded in physical memory.
