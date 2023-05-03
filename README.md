Download Link: https://assignmentchef.com/product/solved-cs342-project-2-threads-processes-and-synchronization
<br>
<strong>Threads, Processes, and Synchronization</strong>

You will now develop a program that will have N <em>worker threads</em> created by the <em>main thread</em>. The program will have a <em>shared</em> binary search tree (pointed by a <em>global</em> variable) with size at most K nodes. The tree is shared among all threads. The tree will be implemented with pointers, not using an array.   The tree will keep the K largest integers seen so far in the input files. Each worker thread will process an input file of integers (one integer per line). There will be N input files. Each such worker thread will read an input file one integer at a time. This time we will read with fscanf (easier).  After reading an integer from the input file, the worker thread will insert it into the binary search tree if necessary, otherwise it will discared the integer. Then it will read the next integer from the file. All N worker threads will work like this concurrently. When all worker threads finish, we will have the K largest integers seen in those N files in the binary tree. Then the main thread will print them out in sorted decreasing order to an output file file. You need to implement the tree youself. You can not use a library or an existing code for this purpose.

We will invoke the program as below:




topk_thread_synchron &lt;K&gt; &lt;N&gt; &lt;infile1&gt; …&lt;infileN&gt; &lt;outfile&gt;




You will use POSIX mutex and conditions variables (if required) to  synchronize the threads.




<h2>1.2      Part B – Synchronizing Processes</h2>




Now you will write a similar program, but this time worker child processes will be used to process the input files. You will also use shared memory to pass information from children to  the parent process. That means you will implement your binary search tree to sit in the shared memory. Shared memory should be large enough to hold K binary tree nodes.




We will invoke the program as below:




topk_process_synchron &lt;K&gt; &lt;N&gt; &lt;infile1&gt; …&lt;infileN&gt; &lt;outfile&gt;




You will use POSIX semaphores to synchronize the processes.




<h2>1.3      Part C – Experimentation</h2>




For both programs, first of all try see what is happening if we don’t synchronize the threads or processes. Do we get wrong results some time?




Measure and compare the running of two programs for various values of the following parameters: N, K, integer count in an input file, and try draw conclusions. Write your experimentation experience and results into a report document and convert the document to PDF (report.pdf). The report should include tables or plots and conclusion(s) as well.