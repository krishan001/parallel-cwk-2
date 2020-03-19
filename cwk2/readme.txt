Complete the table below with your results, and then provide your interpretation at the end.

Note that:

- In the table below, the word "node" refers to cluster nodes - in DEC-10, one node coresponds
  to a single desktop machine.

- See Lecture 8 and the start of Worksheet 2 for instructions on how to launch an MPI program on
  more than one node, with a specified number of processes on each node.

- When calculating the parallel speed-up S, use the time output by the code, which corresponds
  to the parallel calculation and does not include reading in the file or performing the serial check.

- Take as the serial execution time the time output by the code when run with a single process
  (hence the speed-up for 1 process must be 1.0, as already filled in the table).

- If you used a different input.txt to test your code, ensure you restore the original input.txt for
  the timing runs.


No. Process:                        Mean time (average of 3 runs)           Parallel speed-up, S:
===========                         ============================:           ====================
1                                         0.02116303333                              1.0
2 (same node)                             0.01223193333                           1.730146229
4 (same node)                             0.009333226667                          2.267493771
4 (2 nodes, 2 per node)                   0.006336926667                          3.339636775
8 (2 nodes, 4 per node)                   0.004929146667                          4.293447683
12 (3 nodes, 4 per node)                  0.04950103333                           0.4275271021


Architecture that the timing runs were performed on (normally DEC-10): DEC-10


A brief interpretation of these results (2-3 sentences should be enough):

Since 2,4 and 8 are all powers of 2, the code will run using the binary tree reduction. 
This is why the times of these keep decreasing and the process gets faster and hence the speed up gets higher. As the speedup is proportional to the number of processes.
By splitting up the processes over multiple machines, this also increases the speed up.
However 12 is not a power of 2 therefore it doesn't use the binary tree reduction and this means that it runs slower than the other runs. 
This means that its speedup is less than 1 as it is slower than the serial version.




