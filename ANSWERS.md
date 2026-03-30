# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer: A process is a full program that has its own memory and resources, while a thread is a smaller part inside a process that shares memory with other threads. Processes are heavier and take more time to create, but threads are lighter and faster. Also, threads can communicate more easily because they share the same memory. In this assignment, we used threads because we are simulating multiple tasks inside one program. Using threads makes the simulation faster and closer to how real CPU scheduling works.**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer: If a process does not finish within its time quantum, it stops running and gives the CPU to another process. Then it is placed back into the ready queue to wait for its next turn. This ensures fairness so all processes get a chance to execute. The process will continue later from where it stopped. This behavior prevents any single process from using all the CPU time.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
P1 completed quantum 4000ms
Remaining time: 1900ms
P1 yields CPU for context switch
P1 added to ready queue

[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]
This output shows that process P1 used its full time quantum but still had remaining time. Because of that, it was removed from the CPU and placed back into the ready queue. After some time, it got another turn and continued execution. This clearly shows how Round-Robin scheduling works step by step. It keeps switching between processes until all of them finish.
---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?
New: P1 is in the New state when the thread is first created using new Thread(process) before it starts running.]

2. **Runnable**: [When does P1 become Runnable?
Runnable: P1 becomes Runnable when start() is called, and it is ready to be executed by the CPU.]

3. **Running**: [When is P1 Running?
Running: P1 enters the Running state when the CPU starts executing the run() method.]

4. **Waiting**: [When/why would P1 be Waiting?
Waiting: P1 goes into Waiting (Timed Waiting) when Thread.sleep() is used during execution to simulate time passing.]

5. **Terminated**: [When is P1 Terminated?
Terminated: P1 reaches the Terminated state when its execution finishes and the remaining time becomes zero.]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Web Server]

**Description**: 
[A web server handles many users at the same time, such as loading web pages or processing requests. Each request can be handled by a separate thread.]

**Why Round-Robin works well here**: 
[Round-Robin ensures that each request gets a fair share of CPU time. It prevents one request from blocking others and keeps the server responsive. This is important when many users are accessing the system at the same time.]

### Example 2: [Operating System Scheduling]

**Description**: 
[An operating system runs multiple programs like browsers, editors, and background tasks at the same time.]

**Why Round-Robin works well here**: 
[Round-Robin allows each program to run for a short time before switching to another. This makes the system feel smooth and responsive. It also prevents starvation and ensures that all programs get CPU time.]

---

## Summary

**Key concepts I understood through these questions:**
1.The difference between thread and process 
2.How Round-Robin scheduling works 
3.The lifecycle of a thread 

**Concepts I need to study more:**
1.Thread synchronization 
2.Advanced scheduling algorithms
