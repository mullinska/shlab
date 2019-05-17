<h1> Shell Lab Keegan Mullins

<h3> The purpose of this lab was to create a Linux terminal shell capable of handling the running of multiple processes at once, both active and background.

<h3> This code handles each process as a "job". Process refers to a Linux executable file. If the process is the active program it will not allow the user to type at the terminal unless the process is paused with control-z or terminated with control-c. If a background process is run, the user will still be able to type at the terminal and be able to run more programs, terminate more programs, etc. Each job is given its own unique job ID and jobs that run other jobs are given the same group ID.

<h3> The use of operating system calls is necessary here in order to block signals to the shell for certain processes. This ensures that the parent process (original program) will always run in a certain order with respect to their child processes (the program called by the parent) when the operating system function call Fork() is called. Otherwise the operating system might decide to run them in a random order and could cause major problems. In addition, signals are necessary to pause the execution of programs in addition to making sure that each program runs correctly in its own environment. The job IDs and group IDs are necessary to make sure that the child processes will all be terminated when a parent process is terminated while each have a unique identifier.

<h3> Most of the code in this project is my own, however the basic shell of the project itself was provided by my computer systems class. Nearly all of the code located in the "jobs.cc" file is my own, with the rest of the files being for testing primarily.
