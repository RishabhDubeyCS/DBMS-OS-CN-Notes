#	Deadlocks (Important):
A situation where a set of processes are blocked because each process is holding a resource and waiting for another resource acquired by some other process. Deadlock can arise if following four conditions hold simultaneously (Necessary Conditions):
1.	Mutual Exclusion – One or more than one resource is non-sharable (Only one process can use at a time).
2.	Hold and Wait – A process is holding at least one resource and waiting for resources.
3.	No Preemption – A resource cannot be taken from a process unless the process releases the resource.
4.	Circular Wait – A set of processes are waiting for each other in circular form.



#	Methods for handling deadlock: There are three ways to handle deadlock
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

# Note : Variable partition allocation schemes:
1.	First Fit – The arriving process is allotted the first hole of memory in which it fits completely.
2.	Best Fit – The arriving process is allotted the hole of memory in which it fits the best by leaving the minimum memory empty.
3.	Worst Fit – The arriving process is allotted the hole of memory in which it leaves the maximum gap.
# Note:
	Best fit does not necessarily give the best results for memory allocation.
	The cause of external fragmentation is the condition in Fixed partitioning and
Variable partitioning saying that the entire process should be allocated in a contiguous memory location.Therefore Paging is used.
1.	Paging – The physical memory is divided into equal sized frames. The main memory is divided into fixed size pages. The size of a physical memory frame is equal to the size of a virtual memory frame.
2.	Segmentation – Segmentation is implemented to give users a view of memory. The logical address space is a collection of segments. Segmentation can be implemented with or without the use of paging.
	Page Fault:
A page fault is a type of interrupt, raised by the hardware when a running program accesses a memory page that is mapped into the virtual address space, but not loaded in physical memory.

# Page Replacement Algorithms (Important):
1. First In First Out (FIFO) –
This is the simplest page replacement algorithm. In this algorithm, the operating system keeps track of all pages in the memory in a queue, the oldest page is in the front of the queue. When a page needs to be replaced, the page in the front of the queue is selected for removal.
For example, consider page reference string 1, 3, 0, 3, 5, 6 and 3 page slots. Initially, all slots are empty, so when 1, 3, 0 come they are allocated to the empty slots —> 3 Page Faults. When 3 comes, it is already in  memory so —> 0 Page Faults. Then 5 comes, it is not available in  memory so it replaces the oldest page slot i.e 1. —> 1 Page Fault. Finally, 6 comes,  it is also not available in memory so it replaces the oldest page slot i.e 3 —> 1 Page Fault.
 # Belady’s anomaly:
Belady’s anomaly proves that it is possible to have more page faults when increasing the number of page frames while using the First in First Out (FIFO) page replacement algorithm.  For example, if we consider reference string ( 3     2     1     0 3     2     4     3     2     1     0     4 ) and 3 slots, we get 9 total page faults, but if we increase slots to 4, we get 10 page faults.
2. Optimal Page replacement –
In this algorithm, pages are replaced which are not used for the longest duration of time in the future.
Let us consider page reference string 7 0 1 2 0 3 0 4 2 3 0 3 2 and 4 page slots.
Initially, all slots are empty, so when 7 0 1 2 are allocated to the empty slots —> 4 Page faults. 0 is already there so —> 0 Page fault. When 3 came it will take the place of 7 because it is not used for the longest duration of time in the future.—> 1
Page fault. 0 is already there so —> 0 Page fault. 4 will takes place of 1 —> 1 Page Fault. Now for the further page reference string —> 0 Page fault because they are already available in the memory.
Optimal page replacement is perfect, but not possible in practice as an operating system cannot know future requests. The use of Optimal Page replacement is to set up a benchmark so that other replacement algorithms can be analyzed against it.
3. Least Recently Used (LRU) –
In this algorithm, the page will be replaced with the one which is least recently used. Let say the page reference string 7 0 1 2 0 3 0 4 2 3 0 3 2 . Initially, we had 4-page slots empty. Initially, all slots are empty, so when 7 0 1 2 are allocated to the empty slots —> 4 Page faults. 0 is already there so —> 0 Page fault. When 3 comes it will take the place of 7 because it is least recently used —> 1 Page fault. 0 is already in memory so —> 0 Page fault. 4 will take place of 1 —> 1 Page Fault. Now for the further page reference string —> 0 Page fault because they are already available in the memory.



# Disk Scheduling: 
Disk scheduling is done by operating systems to schedule I/O requests arriving for disk. Disk scheduling is also known as I/O scheduling.
1.	Seek Time: Seek time is the time taken to locate the disk arm to a specified track where the data is to be read or written.
2.	Rotational Latency: Rotational Latency is the time taken by the desired sector of disk to rotate into a position so that it can access the read/write heads.
3.	Transfer Time: Transfer time is the time to transfer the data. It depends on the rotating speed of the disk and number of bytes to be transferred.
4.	Disk Access Time: Seek Time + Rotational Latency + Transfer Time
5.	Disk Response Time: Response Time is the average of time spent by a request waiting to perform its I/O operation. Average Response time is the response time of all requests.