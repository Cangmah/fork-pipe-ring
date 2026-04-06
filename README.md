# Fork-Pipe-Ring 

A C-language program that simulates a token-ring communication system using Unix processes, pipes and signals. 

This project implements a circular communication system where multiple processes form a ring. A token ("apple") is passed between processes to control when a node can send or receive messages. Each process communicates with its neighbor using pipes, and the system demonstrates inter-process communication (IPC), synchronization, and process management in Unix. 

#CORE LOGIC

- The parent process creates (k) child processes using 'fork()', forming a ring. 
- Each process is connected to its neighbor via 'pipe()'
- A token (apple) circulates through the ring to control access. 
- When a process receives the token: 
	- If message is for that process, it consumes it. 
	- Else it forwards the message to the next process. 
- The parent process injects messages into the ring. 
- 'signal()' is used to gracefully terminate all processes (Ctrl+C). 

