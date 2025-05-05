#

"Everything that happens inside Javascript, happens inside an execution context". Whatever Javascript program that runs, is running inside an execution context. This execution context is basically a big container. It is a container which have two components/phases. The first one is the memory phase where variables will be stored like key:value pairs, for example a: 10 which says that variable a has the value 10. Javascript will allocate memory to all the variables and functions that are inside the program that is running. The variables will be initialized with the special value undefined in the first phase, and the functions will be directly copied over. The second phase is the code execution phase where the program will be runned line after line (thread of execution). The program will run and the variables will get values etc.

The first context which is created is the global execution context and each program will have one global execution context (GEC). Like the name is saying, this context is global. Whenever the program is invoking a function, there will be created another execution context which is called functional execution context (FEC). FEC will always be created when a function is invoked and it will be exactly the same with memory creation phase and code execution phase. When the FEC is done executing, it will be deleted, and we will go back to where we were in GEC.

Javascript is a synchronous single-threaded language.
synchrounous = it will execute the next line, when the first one is finished.
single-threaded = runs one line at a time. think that you have one worker which can only handle one task at a time.
