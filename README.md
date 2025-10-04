# Project Description
This is an implementation of a simple task scheduler on STM32F407. The scheduler schedules 4 tasks, with the context switch happening every 1ms. The tasks are described below:

Task 1: Blink GREEN LED

Task 2: Blink ORANGE LED

Task 3: Blink BLUE LED

Task 4: Blink RED LED

With the scheduler implementation, all the LEDs appear to be blinking simultaneosly, even though all these are written in four different infinite loops.


## What is a Task?
A task is nothing but a function that is executing endlessly in an infinite loop.

## What is scheduling?
Scheduling is the process by which the CPU executes multiple tasks (seemingly concurrently) by allocating CPU time and resources to each task, ensuring efficient use of the processor. The algorithm that performs scheduling is called Scheduler, and the process using which the CPU switches from one task to the next is called context switching.

## Context switching
When a task or a function is being executed, a certain set of CPU core registers are being used to save the temporary data related to that task. This set of register values is called the context of that task. When the CPU switches to the next task, all these register values will be lost (since execution is being transferred to a different function). If these register values are lost, then the CPU will not be able to resume that task.

Therefore, inorder to switch between tasks, the CPU stores the context of the currently running task in its stack frame before switching to the next task. And when its time to resume that task, it pulls back the context from the stack and picks up where it left off. This process is called context switching. That is, context switching is the process by which the CPU switches out of the currently running task after saving the context of that task, and switching into a different task by retrieving the context of this new task.


