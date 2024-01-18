##   Operating System

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/f069b322-d04d-4631-8d4e-523c5744d940)

### Types of OS:

#### 1. Multi-programming:
Type  of operating system that allows multiple programs to reside in the main memory at the same time and share the CPU resources. The main objective of multi-programming is to maximize the CPU utilization and minimize the idle time. Multi-programming does not require multiple processors or threads, but only one processor that switches between different programs in the memory.

#### 2. Multi-tasking:
Type of operating system that allows multiple tasks or processes to run concurrently on a single processor or multiple processors. The main objective of multi-tasking is to improve the responsiveness and performance of the system by allowing the user to interact with multiple applications at the same time. Multi-tasking can be achieved by using time-sharing or preemption techniques, where the CPU allocates a fixed amount of time to each task and switches between them.

#### 3. Multi-processing:
Type of operating system that allows multiple processors to work together on a single system. The main objective of multi-processing is to increase the processing power and speed of the system by dividing the workload among multiple processors. Multi-processing can be achieved by using symmetric or asymmetric architectures, where the processors can either share the same memory and resources or have their own memory and resources.

---
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/be62275a-883b-4386-bb43-5ea22b58b6ec)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/163353ba-e1f9-4ca7-8022-a0a0507b23a0)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/f0d96ed1-db0d-46ba-970a-aa69b6b077e5)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/50ae4e50-63e2-4aa2-b19c-2822027a0514)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/6e23566c-f76d-4625-938b-0f78b7b0a0aa)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/bb62eb1e-75f7-4db2-8b3e-ddf2a019bb8b)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/9e565f14-d560-46ab-bfce-e0df1e1df57c)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/dd82cde8-1a6d-4224-b9bb-2928fb3dce8a)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/c831bea5-bd85-4fed-bf35-2e6e7ff4cc3a)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/938969b7-8a43-451e-8efe-cc220ae9fe99)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/cd3fb46a-8de4-4b13-99f8-b31f0acb2362)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/c2c8f5d0-f03d-4041-a9e2-95d73f62c6eb)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/c8a386d2-adaf-46d9-a7c7-8d39466f674f)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/5f7a2486-8819-4570-b5b5-f083d1d0591a)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/4b1d9243-8ee6-4bd9-a3de-f4fcaa1e11a8)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/90295263-2626-4e52-9dee-2ec6bc8e8d04)

---

### Process Scheduling:
- The ``objective of multiprogramming`` is to have some process running at all times, to maximize CPU utilization.
- The objective of ``time sharing`` is to switch the CPU among processes so frequently that the users can interact with each program while it is running.
- To meet these objectives, the process scheduler selects an available process (possibly from a set of several available processes) for program execution on the CPU.
  - For a single-processor system, there will never be more than one running process.
  - If there are more processes, the rest will have to wait until the CPU is free and can be rescheduled.



### Scheduling Queues:
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/a6b133c2-e7ba-474c-b887-dd47c019c840)

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/3a784259-97a5-444a-94bf-c32c1e6eb881)


### Context Switching:
- Interrupts cause the operating system to change a CPU from its current task and to run a kernel routine.
- Such operations happen frequently on general-purpose systems.
- When an interrupt occurs, the system needs to save the current **context** of the process currently running on the CPU so that it can restore that context when its processing is done, essentially suspending the process and then resuming it.
- The context is represented in the ``PCB(Process Control Block)``.
- Switching the CPU to another process requires performing a state save of the current process and a state restore of a different process.
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/b3221ad4-c42a-43c7-86a1-47ed243ec36b)
- Context-switch time is pure overhead because the system does no useful work while switching.
- Its speed varies from machine to machine, depending on the memory speed, the number of registers that must be copied, and the existence of special instructions (such as a single instruction to load or store all registers).
- Typical speeds are a few milliseconds.
  

### Operations and Processes      
#### Process Creation
- A process may create several new processes, via a create-process system call, during the course of execution.
- The newly created process is called a parent process, and the new process is called the child process.
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/1d630025-93b9-437d-8648-2ec81f1cf285)

When a process creates a new process, two possibilities exist in terms of execution:
- The parent continues to execute concurrently with its children.
- The parent waits until some or all of its children have terminated.

There are also two possibilities in terms of the address space of the new process:
- The child process is a duplicate of the parent process (it has the same program and data as the parent).
- The child process has a new program loaded into it.
    
#### Process Termination
- A ``Process terminates`` when it finishes executing its final statement and asks the `OS` to delete it by using the ``exit()`` system call.
- At that point, the process may return a status value (typically an integer)
- To its parent process (via the ``wait()`` system call).
- All the resources of the process-including physical and virtual memory, open files, and I/O buffers- are de-allocated by the `OS`.

Termination can occur in other circumstances as well:
- A process can cause the termination of another process via an appropriate system call.
- Usually, such a system call can be invoked only by the parent of the process that is to be terminated.
- Otherwise, users could arbitrarily kill each other's jobs.

A parent may terminate the execution of one of its children for a variety of reasons, such as threats:
- The child has exceeded its usage of some of the resources that it has allocated **(To determine whether this has occurred, the parent must have a mechanism to inspect the state of its children )**.
- The task assigned to the child is no longer required.
- The parent is exiting, and the operating system does not allow a child to continue if its parent terminates. 

---
### ``Interprocess Communication``
- Processes executing concurrently in the OS may be either `independent processes` or `cooperating processes.`
- **``Independent processes:``** They cannot affect or be affected by the other processes executing in the system.
- **``Cooperating processes:``** They can affect or be affected by the other processes executing in the system.
- Any process that shares data with other processes is a cooperating process.

There are several reasons for providing an environment that allows process cooperation:
- **Information sharing**: Sharing the common information needed by each other.
- **Computation Speedup**: 
- **Modularity**:
- **Convenience**:
  
Cooperating processes require an interprocess communication **(IPC)** mechanism that will allow them to exchange data and information.

There are two fundamental models of interprocess communication: 
- ` Shared Memory:`
  - In the shared-memory model, a region of memory that is shared by cooperating processes is established.
  - Processes can then exchange information by reading and writing data to the shared region.
- `Message Passing:`
  - In the message-passing model, communication takes place by means of messages exchanged between the cooperating processes.
  
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/8d1a0be0-c175-46b4-bcee-2881c0e20805)


### Shared Memory Systems:
* Interprocess communication using shared memory requires a communicating process to establish a region of shared memory.
* Typically, a shared-memory region resides in the address space of the process creating the shared-memory segment.
* Other processes that wish to communicate using this shared-memory segment must attach it to their address space.
* Normally, the operating system tries to prevent one process's memory.
* Shared memory requires that two or more processes agree to remove this restriction.

#### `Producer-Consumer Problem`:
- A producer process produces information that is consumed by a consumer process.

For example, a compiler may produce assembly code, which is consumed by an assembler. The assembler, in turn, may produce object modules, which are consumed by the loader.

- One solution to the producer-consumer problem uses shared memory.
- To allow producer and consumer processes to run concurrently, we must have available a `buffer of items` that can be filled by the producer and emptied by the consumer.
- This buffer will reside in a region of memory that is shared by the `producer` and `consumer` processes.
- A producer can produce one item while the consumer is consuming another item.
- The producer and consumer must be synchronized so that the consumer does not try to consume an item that has not yet been produced.

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/013a3f18-821d-4d5d-9eca-909adb15a284)


### `Message-Passing Systems`
- Message passing provides a mechanism to allow processes to communicate and synchronize their actions without sharing the same address space and is particularly useful in a distributed environment, where the communicating processes may reside on different computers connected by a network.
- A message-passing facility provides at least two operations:
  - `send(message)`
  - `recieve(message)`
- Messages sent by a process can be either `fixed` or `variable size`.
  ```
  Fixed Size:
  The system-level implementation is straightforward. But makes the task of programming more difficult.

  Variable Size:
  Requires a more complex system-level implementation. But the programming task becomes simpler.
  ```
- If processes `P` and `Q` want to communicate they must send messages to and receive messages from each other.
  - A communication link must exist between them.
  - This link can be implemented in a variety of ways. There are several methods for logically implementing a link and the `send()`/`receive()` operations, like:
    - `Direct or Indirect communication.`
    - `Synchronous or asynchronous communication.`
    - `Automatic or explicit buffering.`
  - There are several issues related to features like:
    - `Naming.`
    - `Synchronization.`
    - `Buffering.`

#### ``Naming:``
- Processes that want to communicate must have a way to refer to each other.
- They can use either `direct` or `indirect` communication.
  
##### Under direct communication-
- Each process that wants to communicate must explicitly name the recipient or sender of the communication.
  - `send(P, message)` - Send a message to process P.
  - `receive(Q, message)` - Recieve a message from process Q.

#### A communication link in this scheme has the following properties:
- A link is established automatically between every pair of processes that want to communicate. The processes need to know only each other's identity to communicate.
- A link is associated with exactly two processes.
- Between each pair of processes, there exists exactly one link.
  ```
  This scheme exhibits Symmetry in addressing that is, both the sender process and the receiver process must name the other to communicate.
  ```

#### Another variant of Direct Communication:-
- Here, only the sender names the recipient; the recipient is not required to name the sender.
  - `send (P, message)`  - Send a message to process P.
  - `receive (id, message)` - Recieve a message from any process; the variable id is set to the name of the process with which communication has taken place.
    ```
    This scheme employs asymmetry in addressing.
    ```
- The `disadvantage` in both of these schemes ``(symmetric and asymmetric)`` is  the `limited modularity` of the resulting process definitions.
- Changing the identifier of a process may necessitate examining all other process definitions.

#### `With indirect communication:`
The messages are sent to and received from mailboxes, or ports.
  - A mailbox can be viewed  abstractly as an object into which messages can be placed by processes and from which messages can be removed.
  - Each mailbox has a unique identification.
  - Two processes can communicate only if the processes have a shared mailbox.
    - `send(A, message)` - Send a message to mailbox `A`.
    - `receive(A, message)` - Recieve a message from mailbox `A`.
  - A communication link in this scheme has the following properties:
    - A link is established between a pair of processes only if both members of the pair have a shared mailbox.
    - A link may be associated with more than two processes.
    - Between each pair of communicating processes, there may be a number of  different links, with each link corresponding to one mailbox.
  
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/2a86f56f-3ee6-430c-aee8-99c625311acc)

Process `P1` sends a message to `A`, while both `P2` and `P3` execute a `receive()` from `A`.

### Which process will receive the message sent by `P1`?
The answer depends on which of the following methods we choose:
- Allow a link to be associated with two processes at most.
- Allow at most one process at a time to execute a `receive()` operation.
- Allow the system to select arbitrarily which process will receive the message (that is, either P2 or P3, but not both, will receive the message). The system also may define an algorithm for selecting which process will receive the message (that is, round robin where processes take turns receiving messages). The system may identify  the receiver to the sender.

A `mailbox` may be owned either by a process or by the `operating system`.

### `Synchronization:`
- Communication between processes takes place thrpugh calls to `send()` and `recieve()` primitives. There are different design options for implementing each primitive.
- Message passing may be either `blocking ` or `nonblocking`- also known as `synchronous` and `asynchronous`.

#### `Block Send:` 
The sending process is blocked until the message is received by the receiving process or by the mailbox.

#### `Nonblocking send:`
The sending process sends the message and resumes operation.

#### `Blocking receive:`
The receiver blocks until a message is available.

#### `Nonblocking receive:`
The receiver retrieves either a valid message or a null.

### `Buffering:`
Whether communication is `direct ` or `indirect,` messages exchanged by communicating processes reside in a temporary queue.
Such queues can be implemented in three ways:
- `Zero Capacity:` The queue has a maximum length of `zero`; thus, the link cannot have any messages waiting in it. In this case, the sender must block until the recipient receives the message.
- `Bounded Capacity:` The queue has finite `length n`; thus, at most n messages can reside in it. If the queue is not full when a new message is sent, the message is placed in the queue and the sender can continue execution without waiting. The link capacity is finite, however. If the link is full, the sender must block until space is available in the queue.
- `Unbounded capacity:` The queue `length` is `potentially infinite;` thus, any number of messages can wait in it. The sender never blocks.


### `Sockets`
Used for communication in  Clinet-Server Systems. 
- A socket is defined as an endpoint for communication.
- A pair of processes communicating over a network employ a pair of sockets- one for each process.
- A socket is identified by an IP address concatenated with a port number.
- The server waits for incoming client requests by listening to a specified port. Once a request is received, the server accepts a connection from the client socket to complete the connection.
- Servers implementing specific services (such as talent, `FTP`, and `HTTP`) listen to well-known ports(a talent server listens to port 23, an FTP server listens to port 21, and a web, or `HTTP`, server listens to port 80).
- All ports below `1024` are considered well-known; we can use them to implement standard services.

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/5d3ea30b-4a2c-43b6-ade1-93549478813a)


### `Remote Procedure Calls (RPC)`
Remote Procedure Call (RPC) is a protocol that one program can use to request a service from a program located in another computer on a network without having to understand the network's details.
- It is similar in many respects to the IPC mechanism.
- However,  because we are dealing with an environment in which the processes are executing on separate systems, we must use a message-based communication scheme to provide remote service.
- In contrast to the IPC facility, the messages exchanged in RPC communication are well structured and are thus no longer just packets of data.
- Each message is addressed to an RPC daemon listening to a port on the remote system, and each contains an identifier of the function to execute and the parameters to pass to that function.
- The function is then executed as requested, and any output is sent back to the requester in a separate, message.

#### The semantics of RPCs allow a client to invoke a procedure on a remote host as it would invoke a procedure locally:
- The Rpc system has the details that allow communication to take place by providing a stub on the client side,
- Typically, a separate stub exists for each separate remote procedure.
- When the client invokes a remote procedure, the RPC system calls the appropriate stub, passing it the parameters provided to the remote procedure. This stub locates the port on the server and marshals the parameters.
- Parameter marshaling involves packaging the parameters into a form that can be transmitted over a network.
- The stub then transmits a message to the server using message passing.
- A similar stub on the server side receives this message and invokes the procedure on the server.
- If necessary, return values are passed back to the client using the same technique.

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/65e2fc88-d460-4d0f-ae1f-d992dd023721)

### `Execution of a remote procedure call (RPC):`

**TO BE**


### Threads:
```
A thread is a basic unit of CPU utilization.
```
- Thread comprises of:
  - A thread ID
  - A program counter
  - A register set
  - A stack

- It shares with other threads belonging to the same process its code section, data section, and other operating-system resources, such as open files and signals.
- A traditional/heavyweight process has a `single thread` of control.
- If a process has `multiple threads` of control, it can perform `more than one task at a time`.
     
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/9c9358e3-6c2f-43d7-a3d0-d1718af45d44)


### `Benefits`
- The benefits of multithreaded programming can be broken down into four major categories:
  - `Responsiveness`
    - Multithreading an interactive application may allow a program to continue running even if part of it is blocked or is performing a lengthy operation,thereby increasing responsiveness to the user.
  - `Resource Sharing`
    -  By default, threads share the memory and the resources of the process to which they belong. 
    -  The benefit of sharing code and data is that it allows an application to have several different threads of activity within the same address space.
  - `Economy`
    - Allocating memory and resources for process creation is costly.
    - Because threads share resources of the process to which they belong, it is more economical to create and context-switch threads.
  - `Utilisation of multiprocessor architecture`:
    - The benefits of multithreading can be greatly increased in a multiprocessor architecture, where threads may be running in parallel on different processors.
    - A single-threaded process can only run on one CPU, no matter how many are available.
    - Multithreading on a multi-CPU machine increases concurrency.

### `Multithreading Models and Hyperthreading`:
- Types of threads:
  - `User Threads`- Supported above the kernel and are managed without kernel support.
  - `Kernel Threads`- Supported and managed directly by the operating system.

Ultimately, there must exist a relationship between user threads and kernel threads.
There are three common ways of establishing this relationship:
- Many-to-One-Model
- One-to-One Model
- Many-to-Many Model

![image](https://github.com/nishant05gaurav/Notes/assets/140972654/c1ae0bd2-7231-4ab8-8df9-b81a6a9b7e0d)
![image](https://github.com/nishant05gaurav/Notes/assets/140972654/fd3d0e62-8e92-466e-8854-714dfcb072c8)


#### `Hyperthreading  OR   Simultaneous Multithreading (SMT)`
- Hyperthreading systems allow their processor cares' resources to become multiple logical processors for performance.
- It enables the processor to execute `two threads,` or sets of instructions, at the same time.` Since hyper-threading allows two streams to be executed in parallel, it is almost like having two separate processors working together.

### The `fork()` and `exec()` System Calls:
- `fork(): ` The `fork()` system call is used to create a `separate, duplicate process`.
- `exec(): `When an `exec()` system call is invoked, the program specified in the parameter to exec() will `replace the entire process` - including all threads.

### `Threading Issues:`
```
 The semantics of the `fork()` and `exec()` system calls change in a multithreaded program.
```
- **`Issues`:** If one thread in a program calls `fork()`, does the new process duplicate all threads, or is the new process single-threaded?
- **`Solution`:** Some UNIX systems have chosen to have two versions of `fork()`, one that duplicates all threads and another that duplicates only the thread that invoked the `fork()` system calls.

```
Which version of fork() to use and when?

If a thread invokes the exec() system call, the program specified in the parameter exec() will replace the entire process -including all threads.
```

### Which of the two versions of `fork()` to use depends on the application:
#### If the `exec()` is called immediately after forking: 
- Then duplicating all threads is unnecessary, as the program specified in the parameters to `exec()` will replace the process.
- In this instance, duplicating only the calling thread is appropriate.
#### If the separate process does not call exec() after forking:
- Then the separate process should duplicate all threads.
  - If the multiple threads are concurrently searched through a database and one thread returns the result, the remaining threads might be canceled.
  - When a user presses a button on a web browser that stops a web page from loading any further, all threads loading the page are canceled.
- A thread that is to be canceled is often referred to as the target thread.

#### Cancellation of a target thread may occur in two different scenarios:
- **`Asynchronous cancellation`**: One thread immediately terminates the target thread.
- **`Deferred cancellation`**: The target thread periodically checks whether it should terminate, allowing it an opportunity to terminate itself ordinarily.

#### Cancellation of a target thread may occur in two different scenarios:
- **`Asynchronous cancellation`**: One thread immediately terminates the target thread.
- **`Deferred cancellation`**: The target thread periodically checks whether it should terminate, allowing it an opportunity to terminates itself in an ordinary fashion.

#### Where the difficulty with cancellation lies:
- **In situations where:**

**TO BE**

```
Important interview Questions
1. Difference b/w multi-programming, multi-tasking, and multi-processing OS.
2. Where does the bootstrap program resides?
3. About System Call.
```

```c
printf("bigrrg ph");
```

```cpp
cout << "hello Word";
```

```python
print("ibcggbv")
```


```java
System.out.print("ijdggr");
```

```javascript
console.log("njhgjre");
```

```c#
console.write("kjbri rvrg");
```

```bash
echo "bscog"
```

```bash
pwd
```
