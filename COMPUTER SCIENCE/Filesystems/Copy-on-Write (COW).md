# Definition

Copy-on-write (COW), sometimes,  refers to as implicit sharing or shadowing is a resource management technique. It is a resource-management technology applied in computer programming to implement a “copy” or “duplicate” on modifiable resources efficiently.

If a resource is duplicated but not modified, it’s not necessary to create a new resource for that the resource can be shared between the copy and the original one. Still, modifications must create a copy. So, the technique – the copy operation is deferred until the first write.

By sharing resources in that way, significantly reducing the resource consumption of unmodified copies while adding a small overhead to resource-modifying operations is possible.

## Example:


In UNIX like OS, fork() [[System Call]] creates a duplicate process of the parent process which is called as the child process.

Suppose, there is process P then we fork() creating a new process Q and then Process P modifies page 3.

The below figure shows what happens before and after Process P modifies page 3.



![[COW1.png]]![[COW2 1.png]]

The idea o the fork is to create other process that has the same data in memory just like two copies of the same data, but just one is going to be modified the other one works just a reference of what data previously was.  Just in case the operation fail, energy drop or any other error occur. The previous information will remain intact in the child process and could be easily returned to the original state. 

It basically work as a git commit: you are mean to perform and action but you take a copy of it when the operation is done and everything is fine you can get rid of the of old version and keep with the data modified since it works now.

# Applications


## ### Copy on Write in Virtual Memory Management

Copy-on-write is mainly used in sharing the [virtual memory](https://www.minitool.com/lib/virtual-memory.html) of operating system processes, in the implementation of the fork system call. The process usually doesn’t modify any memory and immediately executes a new process, replacing the address space entirely.

In UNIX like OS, fork() [[System Call]] creates a duplicate process of the parent process which is called as the child process.

Copy on write can also be implemented using the [page table](https://www.minitool.com/lib/page-table.html) by marking certain pages of memory as read-only and keeping a count of the number of references to the page. It can be extended to support efficient memory allocation by having a page of [physical memory](https://www.minitool.com/lib/physical-memory.html) filled with zeros.

Copy-on-write pages are also applied in the [Linux Kernel](https://www.minitool.com/news/linux-kernel-021.html)’s Kernel same-page merging utility. Loading the libraries for an app also takes advantage of the COW technique.

## ### 2. Copy-on-Write in Software

Besides, copy on write can be applied in the library, application, as well as system code. In multithreaded systems, COW can be used without traditional locking and instead use compare-and-swap to increment or decrement the internal reference counter.

In the PHP programming language, all types except references are implemented as copy-on-write. In the Qt framework, lots of types are COW. Since the copies are cheap, Qt types can frequently be safely used by multiple threads without the need for locking mechanisms like mutexes. Thus, the advantages of copy on write are valid in both single- and multithreaded systems.

Copy-on-write pages are also applied in the [Linux Kernel](https://www.minitool.com/news/linux-kernel-021.html)’s Kernel same-page merging utility. Loading the libraries for an app also takes advantage of the COW technique.


### ### 3. Copy on Write in Computer Storage

Copy-on-write can be used as the underlying mechanism for snapshots like those offered by logical volume management, file systems including [ZFS](https://www.minitool.com/lib/zfs-file-system.html) and [Btrfs](https://www.partitionwizard.com/partitionmanager/btrfs-vs-ext4.html), as well as database servers such as Microsoft SQL Server.

Usually, the snapshots save only the changed data. They are stored near the main array. Thus, they are only a weak form of incremental backup and can’t substitute for a full backup.

