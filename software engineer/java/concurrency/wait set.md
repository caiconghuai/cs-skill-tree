## WaitSet

- 如果某个线程调用**LOCK.wait()**，那么该线程会把自己放到**该锁**的wait set中。 
- 每一个对象都会有一个wait set，用来存放调用了该对象wait方法之后进入block状态线程
- wait set 本身是一个抽象的概念，具体的实现方式交给不同的JVM去实现。
- 线程被notify之后，不一定立即得到执行，线程从wait set中被唤醒顺序不一定是FIFO。
- 线程从wait set中被唤醒后**还需要去竞争LOCK** ，但是抢完锁之后，会直接从**地址恢复后**的位置继续向下执行。