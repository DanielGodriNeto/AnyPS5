# libkernel

## add Functional

- [pthread_attr_get_np](../../../core/libs/prx/libkernel/Pthread/Posix/Attr.cpp) and [scePthreadAttrGet](../../../core/libs/prx/libkernel/Pthread/src/Attr.cpp) (libkernel) report the guard size the thread was created with, as FreeBSD 11 libthr's [pthread_attr_get_np](https://github.com/freebsd/freebsd-src/blob/release/11.4.0/lib/libthr/thread/thr_attr.c) copies the creation attribute: `0x1000` for a thread created without an attribute and for an adopted host thread. The guard size is not applied to the host stack, which keeps its own guard region, and the value the console reports has not been measured.
