
 
## lock and condition   
source: core java vol 1  
```
Lock bankLock;
Condition sufficientFunds;
public void transfer(int from, int to, double amount) throws InterruptedException
{
    bankLock.lock();
    try
    {
        while (accounts[from] < amount)
            sufficientFunds.await();
        System.out.print(Thread.currentThread());
        accounts[from] -= amount;
        System.out.printf(" %10.2f from %d to %d", amount, from, to);
        accounts[to] += amount;
        System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());
        sufficientFunds.signalAll();
    }
    finally
    {
        bankLock.unlock();
    }
}
```

## The Java synchronized Keyword    

The synchronized keyword can be used to mark four different types of blocks:

Instance methods    
Static methods    
Code blocks inside instance methods   
Code blocks inside static methods   

```
synchronized(this)
synchronized(SynchronizedExample.class)

```

## lock vs. synchronized    
lock and condition offers high degree of control.   
```
lock:
await()
signalAll()
signal()

synchronized -> object class:
wait()
notifyAll()
notify()

```

## Synchronized Block Limitations and Alternatives
Synchronized blocks in Java have several limitations. For instance, a synchronized block in Java only allows a single thread to enter at a time. However, what if two threads just wanted to read a shared value, and not update it? That might be safe to allow. As alternative to a synchronized block you could guard the code with a Read / Write Lock which as more advanced locking semantics than a synchronized block. Java actually comes with a built in ReadWriteLock class you can use.

What if you want to allow N threads to enter a synchronized block, and not just one? You could use a Semaphore to achieve that behaviour. Java actually comes with a built-in Java Semaphore class you can use.

Synchronized blocks do not guarantee in what order threads waiting to enter them are granted access to the synchronized block. What if you need to guarantee that threads trying to enter a synchronized block get access in the exact sequence they requested access to it? You need to implement Fairness yourself.

What if you just have one thread writing to a shared variable, and other threads only reading that variable? Then you might be able to just use a volatile variable without any synchronization around.   

## Java Volatile Keyword   
visibility:   
memory -> CPU cache -> thread   

```
public volatile int counter = 0;
```
The Java volatile keyword is intended to address variable visibility problems. By declaring the counter variable volatile all writes to the counter variable will be written back to main memory immediately. Also, all reads of the counter variable will be read directly from main memory.   

## Producer-Consumer Problem in Java    
https://www.geeksforgeeks.org/producer-consumer-solution-using-threads-java/    
https://dzone.com/articles/the-evolution-of-producer-consumer-problem-in-java    

