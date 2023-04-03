1. What is the Event loop ?
    Answer:
    The event loop is the secret behind JavaScript’s asynchronous programming. JS executes all operations on a single thread, but using a few smart data structures, it gives us the illusion of multi-threading. Let’s take a look at what happens on the back-end. Whenever an async function is called, it is sent to a browser API. These are APIs built into the browser. Based on the command received from the call stack, the API starts its own single-threaded operation. The event loop facilitates this process; it constantly checks whether or not the call stack is empty. If it is empty, new functions are added from the event queue. If it is not, then the current function call is processed.
    Event Loop features include: 
    i. This event loop is just not a loop which waits for tasks, performs them, and then   rests until new ones occur.
	ii. The event loop executes tasks first from event queue while the call stack is    empty, i.e. there are no ongoing tasks. 
    iii. With both the event loop, we can use callbacks and promises. 


2. Explain the 6 phases of the event loop
    Answer:
    The Event Loop consists of the six phases listed below, which are repeated as long as the application's code has to be executed: 
•	TIMERS
    Node.js provides timers, or functions that perform callbacks after a given amount of time. setTimeout() and setInterval() are two global functions provided by this module (). These let you to define code that will run once a certain amount of time has passed. 
    The Event Loop executes the timers phase directly. The Event Loop changes its own time at the start of this phase. The timers are then checked in a queue or pool. All timers that are currently set are in this queue. The Event Loop compares the timer with the least wait time to the current time of the Event Loop. The timer's callback is scheduled to be triggered once the call stack is empty if the wait time has expired. 
    There are two types of timers in Node.js: setTimeout() and setInterval() (). The main difference is that setInterval() has a repeat flag, which returns the timer to the queue once it has completed its execution. 


•	I/O Callbacks
    It refers to reading/writing files or network operations in Node.js.    
    Network operations allow you to bring in external data or send data from your program to another location. We'll use the file system as an example, although you could instead use network activities to examine these instances. 
    When your program is waiting for a file to be read, it is not required to wait until the system returns with the file's content. It can keep running code and asynchronously receive the file's content when it's ready. 
    Non-blocking, I/O interfaces enable us to do this. The asynchronous I/O request is queued, and the main call stack can then continue to function normally. The I/O callbacks of completed or errored out I/O operations are processed in the second phase of the Event Loop. 

•	Waiting / Preparation
    The Event Loop executes internal activities on any callbacks during this phase. Technically, there is no way to change the length or nature of this phase. During this phase, there is no mechanism in place to guarantee code execution. It is mostly used for gathering data and preparing what actions should be taken on the next tick of the Event Loop. 

•	I/O Polling 
    This is the stage wherein the launch all of the JavaScript code we've created from top to bottom. Relying on the code, it could run immediately or add anything to the list to be handled on a subsequent iteration of the Event Loop. 
    The Event Loop manages the I/O workload during this phase, calling the functions in the queue until the queue is empty, and calculates how long it should wait before going on to the next phase. In this phase, all callbacks are synchronously called in the order in which they were added to the queue, from oldest to newest. 
    


•	setImmediate() callbacks 
    If any setImmediate() timers are scheduled during the current tick, Node.js will skip this phase and proceed to the setImmediate() phase.
    If there are no timers or functions in the queue, the program will wait for callbacks to be added to the queue and then execute them until the internal setTimeout() that was set at the start of this phase expires. It continues on to the next step after that. The duration of this timeout is likewise determined by the status of the application. The callbacks scheduled by setImmediate() are handled in this phase, and they will be executed once the Poll phase is idle. SetImmediate() in Node.js is a specific timer that executes callbacks during this period. When the poll phase is idle, this phase starts. SetImmediate() will always be executed before other timers if it is scheduled within the I/O cycle, regardless of how many timers are present. 


•	Close events 
    If a socket or handle is abruptly closed, the 'close' event is emitted, this phase handles callbacks. 
    All closing event callbacks are executed in this phase. A closing event of a web socket callback, for example, or process.exit() is called. This is the point at which the Event Loop has completed one cycle and is ready to go on to the next. It is primarily used to clear the application's state. 
    Callbacks for timers whose wait time has expired are executed in sequence from smallest to longest wait time. I/O callbacks are then performed, followed by internal processing. The main code enters the picture after that, and I/O poll queue callbacks are executed. The setImmediate() and close event callbacks are then called. The timers begin the following tick. This loop will continue as long as there is code to execute. 

3. List some best practices in server-side code development
    Answer:
    1. To focus on the quality of the code
    2. to priorize ES6+ and Async/Await
    3. to ensure the codes are smaller
    4.  Handle errors
    5. to enusre your code are runing effectively

4. What is NPM
    Answer: Node Package Manager 

5. To initialize a package in npm:
   Answer:
   One need to type npm init then press enter key in the terminal inorder to initialize a package

6. How do you run a script in the package.json ?
    Answer: By initializing nmp run "the name of programme to run"

7. Initialize a package if your choice, give it a name and install the following npm packages to it, express,   mongoose, joi.
Answer: See package.json


