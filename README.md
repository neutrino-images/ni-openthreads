# OpenThreads

*Note:

This is a fork of https://github.com/tibogens/OpenThreads/commits/master to
provide a simple way for building only the OpenThreads library. It is randomly 
aligned to upstream: https://github.com/openscenegraph/OpenSceneGraph.

USE AT YOUR OWN RISK!

This library is intended to provide a minimal & complete Object-Oriented (OO) 
thread interface for C++ programmers.  It is loosely modeled on the Java thread
API, and the POSIX Threads standards.  The architecture of the library is 
designed around "swappable" thread models which are defined at compile-time
in a shared object library.

It is of importance to note that while a factory pattern design could have been
used to achieve the goal of genaric interface, it would have required the 
programmer to allocate each of the 4 fundemental types (Thread, Mutex, Barrier,
& Condition ) on the heap.  Due to the cost associated with heap allocation 
for some of these constructs, such allocation was deemed unacceptable, and thus
the factory pattern was not used.

Instead, a somewhat obtuse - but effective - technique was chosen to provide 
the necessary data/implementation hiding.  This technique uses private void
pointers to encapsulate object private data.  The void pointers actually point
at concrete data structures, but give a uniform interface to the dso.

- The Open Thread Group
- NI Team

