1. What is the Event loop ?
    Answer:
   The event loop is the key to asynchronous programming in JavaScript. JS performs all operations on a single thread, but by employing a few clever data structures, it creates the illusion of multi-threading. Let's take a look at what happens behind the scenes. When an async function is called, it sends a request to the browser API. These are APIs that have been built into the browser. The API begins its own single-threaded operation based on the command received from the call stack. The event loop aids in this process by constantly checking to see if the call stack is empty. If it is empty, new functions from the event queue are added. If it isn't, the current function call is executed.
    Event Loop features include: 
    i. This event loop is not a loop that waits for tasks, performs them, and then waits for new ones to occur. 
    ii. The event loop executes tasks from the event queue first, while the call stack is empty, indicating that there are no ongoing tasks.
    iii. Callbacks and promises can be use in the event loop  


2. Explain the 6 phases of the event loop
    Answer:
    The Event Loop consists of the six phases listed below, which are repeated as long as the application's code has to be executed: 
•	TIMERS
    Timers, or functions that perform callbacks after a certain amount of time, are provided by Node.js. This module provides two global functions: setTimeout() and setInterval() (). These allow you to define code that will run after a certain amount of time.
    The Event Loop directly executes the timers phase. At the start of this phase, the Event Loop modifies its own time. After that, the timers are checked in a queue or pool. This queue contains all timers that are currently set. The Event Loop compares the timer with the shortest wait time to the Event Loop's current time. If the wait time has expired, the timer's callback is set to be triggered when the call stack is empty. In Node.js, there are two types of timers: setTimeout() and setInterval() (). The main distinction is that setInterval() includes a repeat flag, which returns the timer to the queue once it has finished its execution.


•	I/O Callbacks
    It refers to Node.js file reading/writing or network operations.
    You can use network operations to bring in external data or send data from your program to another location. We'll use the file system as an example, but you could also examine these instances using network activities.
    It is not necessary for your program to wait until the system returns with the file's content when it is waiting for a file to be read. It can continue to run code and asynchronously receive file content when it is ready.
    This is made possible by non-blocking I/O interfaces. The asynchronous I/O request is queued, and the main call stack can resume normal operation. I/O callbacks from completed or failed I/O operations are handled in thesecond phase of the Event Loop. 

•	Waiting / Preparation
    During this phase, the Event Loop performs internal operations on any callbacks. There is no way to change the length or nature of this phase technically. There is no mechanism in place to ensure code execution during this phase. It is primarily used for data collection and planning what actions should be taken on the next tick of the Event Loop.

•	I/O Polling 
    This is the stage at which we run all of the JavaScript code we've written from beginning to end. It could run immediately or add anything to the list to be handled on a subsequent iteration of the Event Loop, depending on the code.
    During this phase, the Event Loop manages the I/O workload by calling the functions in the queue until the queue is empty and calculating how long it should wait before proceeding to the next phase. All callbacks are synchronously called in the order they were added to the queue, from oldest to newest, during this phase. 
    


•	setImmediate() callbacks 
    Node.js will skip this phase and proceed to the setImmediate() phase if any setImmediate() timers are scheduled during the current tick.
    If no timers or functions are in the queue, the program will wait for callbacks to be added to the queue before executing them until the internal setTimeout() that was set at the beginning of this phase expires. Following that, it moves on to the next step. The duration of this timeout is also determined by the application's status. In Node.js, SetImmediate() is a timer that executes callbacks during this period. This phase begins when the poll phase is idle. If SetImmediate() is scheduled within the I/O cycle, it will always be executed before other timers, regardless of how many timers are present.


•	Close events 
   The 'close' event is emitted when a socket or handle is abruptly closed; this phase handles callbacks.
    During this phase, all closing event callbacks are executed. A closing event, such as a web socket callback or process.exit(), is called. At this point, the Event Loop has completed one cycle and is ready to move on to the next. Its primary function is to clear the application's state.
    Callbacks for timers with expired wait times are executed in the order of smallest to largest wait time. After that, I/O callbacks are executed, followed by internal processing. Following that, the main code enters the picture, and I/O poll queue callbacks are executed. Following that, the setImmediate() and close event callbacks are invoked. The timers start the next tick. This loop will continue indefinitely as long as there is code to run.

3. List some best practices in server-side code development
    Answer:
    1. To focus on the quality of the code
    2. to priorize ES6+ and Async/Await
    3. to ensure the codes are smaller
    4.  Handle errors
    5. to enusre your code are runing effectively

4. What is NPM
    Answer: Node Package Manager. it is a defualt package manager fot the JavaScript runtime environment Node.js. It is basically like a library and registry for JavaScript software packages.

5. To initialize a package in npm:
   Answer:
   One need to type npm init then press enter key in the terminal inorder to initialize a package

6. How do you run a script in the package.json ?
    Answer: By initializing nmp run "the name of programme to run"
    eg. install express
        install bcrypt
        install prettier


7. Initialize a package if your choice, give it a name and install the following npm packages to it, express,   mongoose, joi.
Answer: See package.json


