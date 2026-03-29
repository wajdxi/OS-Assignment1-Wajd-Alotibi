# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is a full program with its own memory, while a thread is a smaller execution path that runs inside a process and shares the same memory space. Threads are much lighter to create, while processes have higher overhead because the system must allocate separate memory for each one. In this assignment, threads made more sense because all the simulated “processes” needed to share the same ready queue and data structures. For example, in SchedulerSimulation.java, each task is created using new Thread(process) inside addProcessToQueue(), which lets all threads access the same processMap. Using real OS processes would require more memory and complicated communication, so threads were the simpler and faster option
---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round‑Robin scheduling, if a process doesn’t finish within its time quantum, it is placed back into the ready queue so it can run again in the next cycle. In the program, this happens inside the main loop when the scheduler checks if (!process.isFinished()) and then calls addProcessToQueue(process, processQueue, processMap) to re‑queue it. The process waits until the scheduler cycles through the other processes and eventually reaches it again.


Example from my output:
```
[Paste ⏸ P3 completed quantum 3000ms │ Overall progress: [██████░░░░░░░░░░] 30%
     Remaining time: 7000ms
↻ P3 yields CPU for context switch
➕ P3 (Priority: 2) added to ready queue │ Burst time: 10000ms
a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
This shows that P3 used its full time quantum but still had 7000ms left, so the scheduler added it back to the ready queue. It will run again once the other processes get their turn. This re‑queueing is important because it keeps the CPU fair and prevents any single process from taking all the processing time.
---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1. **New**: P1 is in the New state right after it is created using new Thread(process) inside the addProcessToQueue() method. At this point, the thread object exists, but it hasn’t started running yet.

2. **Runnable**: P1 becomes Runnable when the scheduler calls currentThread.start() inside the main loop. This means the thread is ready to run and waiting for the JVM to schedule it.

3. **Running**: P1 enters the Running state when the JVM begins executing its run() method. This is where the process prints messages like “executing quantum” and updates the progress bar while simulating CPU work.

4. **Waiting**: Inside the run() method, P1 calls Thread.sleep(stepTime) several times to simulate quantum progress. During each sleep call, the thread enters the Waiting (specifically Timed Waiting) state until the sleep duration finishes.

5. **Terminated**: P1 reaches the Terminated state when its run() method finishes — either after completing its quantum or when its remaining time reaches zero. At this point, currentThread.join() in the main loop returns, meaning the thread has fully completed execution.
---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web Server Handling Multiple Requests

**Description**: 
A web server usually deals with many users at the same time. Each user request (like loading a page or sending a form) can run in its own thread so the server doesn’t freeze when many people connect at once.

**Why Round-Robin works well here**: 
Round‑Robin makes sure every request gets a fair share of CPU time. No single request can block the others, which keeps the server responsive. The predictable time slicing is similar to how our scheduler gives each process a fixed quantum before switching.

### Example 2: Multiplayer Game Engine

**Description**: 
A game engine needs to update several systems at the same time — movement, physics, AI, sound, and rendering. These tasks often run in separate threads so the game stays smooth.

**Why Round-Robin works well here**: 
Round‑Robin helps keep the game stable by giving each system regular CPU time. It prevents one part of the game from taking too long and causing lag. This fairness and predictable switching match the same behavior we implemented in the Round‑Robin simulation.

---

## Summary

**Key concepts I understood through these questions:**
1.  i understood how Round‑Robin scheduling works in practice, especially how the time quantum controls when a process runs and when it gets re‑queued.
2. I learned how threads move between different states like New, Runnable, Running, Waiting, and Terminated, and how these transitions happen in real code.
3. I now understand why threads are more efficient than processes in simulations like this, especially when sharing memory and switching quickly between tasks.

**Concepts I need to study more:**
1. I want to learn more about how real operating systems handle context switching at the hardware level.
2. I also want to understand more advanced scheduling algorithms and how they compare to Round‑Robin in real systems.
