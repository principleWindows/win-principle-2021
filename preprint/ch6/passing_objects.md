# Do NOT passing objects that internally use dynamic allocation

Do not passing objects, which internally use dynamic allocation, to a dll function call. 
That will use the heap manager. For example, passing `std::string` as a parameter to a DLL 
function is error prone and not recommended unless you know exactly what you're doing. 
The reason it is error prone is:

- The DLL that contains the function call may have been built with a different set of 
options than the DLL that calls the function. These differing options could cause a difference 
in the way that `std::string` is implemeted, how it's layed out in memory, etc.

- The DLL that contains the function call may have been built by a different version of the 
compiler than the DLL that calls the function. Again, same issue with differing 
implementations of `std::string`

- The DLL's and modules using `std::string` may not have been built using the `DLL version` 
of the C runtime library. If the DLL's/modules are not built and linked using the DLL version 
of the runtime library, the DLL will be using a different heap than the module. Any operation 
on `std::string` will be invalid, due to differing memory heaps being used.

So in a nutshell, unless you can **guarantee** that

1. You are building the modules and DLL's with the exact same version of the compiler and 
compiler options.
2. You are linking all modules to the DLL version of the runtime library.

Then passing `std::string` as a parameter, and in general, passing any object that maintains 
dynamically allocated memory, may or will lead to runtime errors.
