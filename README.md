
### Commons Transaction is an old Apache project. 

This is what its developers wrote:

<i>We have decided to move the project to dormant as we are convinced that the main
advertised feature <i>transactional file access</i> can not be implemented reliably.
We are convinced that no such implementation can be possible on top of an ordinary file system.
Although there are other useful parts (as multi
level locking including deadlock detection) the transactional file
system is the main reason people use this library for. As it simply
can not be made fully transactional, it does not work as advertised.</i>

<i>The optimal - but maybe impudent - long term goal would be to create the transactional counterpart
of <a class="externalLink" href="http://gee.cs.oswego.edu/dl/classes/EDU/oswego/cs/dl/util/concurrent/intro.html">Doug
Lea's fabulous concurrent package</a> which recently made it to Java 5.0.</i>

### Even so it is helpfull ...

... when you have to conduct concurrent file operations like updating files while other threads might read them. After initializing `org.apache.commons.transaction.file.FileResourceManager` it is as easy as this:

```java
String txId = manager.generatedUniqueTxId()
manager.startTransaction(txId);
OutputStream out = manager.writeResource(txId, "path/to/file");
// write to out. No need to close the stream.
manager.commitTransaction(txId);

```
While the write goes on, other threads can still read the file concurrently. Only when the "transaction" is committed, the original file is replaced by the newly written one, what is much faster than locking the original file for the time of the write. But to make this work, every thread has to access the files through the same FileResourceManager instance.
