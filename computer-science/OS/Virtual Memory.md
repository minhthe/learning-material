1. Page Fault
- happens when an access to a page that has not been loaded to RAM take places
- OS will find a free frame in RAM and request an IO to read the 
needed page from swap space 

2. What will happen with memory when you open an application?
- CPU create a logical address space for the process in RAM.
- CPU load the application from hard drive to process's address space:
    - code 
    - data
    - heap
    - stack
- CPU starts executing instruction of the application by loading 
the instruction and operand from RAM to register

3. What will happen you call another function (with parameters) or return from a function?     
- Push parameter of the function onto the stack space
- Push the return address onto stack
- Execute the function, any local variable created will be push onto the stack
- When function is finish, local variables are pop out of the stack
- The called function return control to calling function via the 
return address

4. Stack overflow:
- when you used more memory for stack space than the limit imposed by 
the language/ OS
- example: recursion
- how to avoid:
    - reduce number of local variable
    - avoid recursion
    - keep tree call shallow
