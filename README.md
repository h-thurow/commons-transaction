<div class="section">
<p>
Commons Transaction is an old, now dormant Apache project. This is what the developers wrote:
</p><p>
<i>We have decided to move the project to dormant as we are convinced that the main
advertised feature <i>transactional file access</i> can not be implemented reliably.
We are convinced that no such implementation can be possible on top of an ordinary file system.
Although there are other useful parts (as multi
level locking including deadlock detection) the transactional file
system is the main reason people use this library for. As it simply
can not be made fully transactional, it does not work as advertised.</i>
</p><p>
<i>Commons Transaction aims at providing lightweight, standardized,
well tested and 
efficient implementations of utility classes commonly used in
transactional Java programming. Initially there are implementations for
multi level locks, 
transactional collections and transactional file access. There may
be additional implementations when the common need for them becomes
obvious. However, the complete component shall remain compatible to
JDK1.2 and should have minimal dependencies.</i>
</p><p>
<i>The optimal - but maybe impudent - long term goal would be to create the transactional counterpart
of <a class="externalLink" href="http://gee.cs.oswego.edu/dl/classes/EDU/oswego/cs/dl/util/concurrent/intro.html">Doug
Lea's fabulous concurrent package</a> which recently made it to Java 5.0."</i>
</p>
</div>