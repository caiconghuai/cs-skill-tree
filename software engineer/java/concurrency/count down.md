# CountDown

闭锁是一种不同工具类，可以延迟线程的进度直到其到达终止状态。闭锁相当于一扇门，在闭锁到达结束状态之前，这扇门一直是关闭的。闭锁可以用来确保某些活动直到其他活动都完成后才继续执行。

- **CountDownLatch**
  - CountDownLatch是一种灵活的闭锁实现，可以在上述各种情况使用，它可以是一个或多个线程等待一组事件发生。
  - 这个类使用一个**整数**进行初始化，这个整数就是线程要等待完成的操作的数目。当一个线程要等待某些操作先执行完时，需要调用await()方法，这个方法让线程进入休眠直到等待的所有操作都完成，当某个操作完成后，它将调用countDown()方法将CountDownLatch类的内部计数器减1,，当计数器变为0的时候，CountDownLatch将唤醒所有调用await()方法而进入休眠的线程。
  - CountDownLatch类有三个基本元素：
    - 一个初始值，即定义必须等待的先行完成的操作的数目。
    - await()方法
    - countDown()方法，每个被等待的事件在完成的时候调用。
  - CountDownLatch机制
    - CountDownLatch机制不是用来保护共享资源或者临界区的，它是用来同步执行多个任务的一个或者多个线程；
    - CountDownLatch只准许进入一次。