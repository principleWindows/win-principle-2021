





[]()

[Is there a difference between fibers, coroutines and green threads and if that is so what is it?](https://softwareengineering.stackexchange.com/questions/254140/is-there-a-difference-between-fibers-coroutines-and-green-threads-and-if-that-i)

[C++ coroutine-ts 怎么用-Part 1 什么是coroutine](https://www.cnblogs.com/pointer-smq/p/8780895.html)

[协程和纤程的区别是什么？](https://www.zhihu.com/question/23955356)

[c++20协程入门](https://zhuanlan.zhihu.com/p/59178345)

[c#协程的基本用法](https://www.cnblogs.com/Dearmyh/p/9317699.html)

[Fibers vs async await](https://stackoverflow.com/questions/31221210/fibers-vs-async-await)

[/await (Enable coroutine support)](https://docs.microsoft.com/en-us/cpp/build/reference/await-enable-coroutine-support?view=msvc-160)

[Fibers](https://docs.microsoft.com/en-us/windows/win32/procthread/fibers)

[C++ Coroutines on Windows with the Fiber API](https://schneide.blog/2016/09/19/c-coroutines-on-windows-with-the-fiber-api/)

[C++ Team Blog](https://devblogs.microsoft.com/cppblog/category/coroutine/)

[C++20 Coroutine Improvements in Visual Studio 2019 version 16.11](https://devblogs.microsoft.com/cppblog/cpp20-coroutine-improvements-in-visual-studio-2019-version-16-11/)

[C++ coroutines: Getting started with awaitable objects](https://devblogs.microsoft.com/oldnewthing/20191209-00/?p=103195)

https://lewissbaker.github.io/

Professor David Mazières @ CS, Stanford: \
[My tutorial and take on C++20 coroutines](https://www.scs.stanford.edu/~dm/blog/c++-coroutines.html)


In the book `Linux System Programming, 2nd Edition`, the difference between coroutines 
and fiber is explained as follows:

> Coroutines and fibers provide a unit of execution even lighter in weight than the thread 
> (with the former being their name when they are a programming language construct, and the 
> latter when they are a system construct).


In short - the difference between coroutines and fibers is, that the context switch between 
fibers is managed by a scheduler (selects the next fiber ...). Coroutines don't have a 
concept of a scheduler.

A more detailed explanation of the difference between coroutines and fibers can be read in 
[N4024: Distinguishing coroutines and fibers](resources/n4024.pdf).

