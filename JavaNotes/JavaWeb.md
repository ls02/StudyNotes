[TOC]

# 进程是什么？

## 多线程是什么？

## 多线程的创建

1. 通过继承`Thread`重写`run`

```java
class MyThread2  extends Thread {
    public void run() {
        while (true) {
            System.out.println("hello thread!");

            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

static void Test1() {
    Thread t = new MyThread2();
    t.start();

    while (true) {
        System.out.println("hello main");
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```



2. 实现`Runnable`接口，重写`run`

标准线程库提供的一个接口`public interface Runnable`这个接口主要是用于描述一个任务，通过`run`方法来描述具体要执行的任务代码是啥。

```java
class MyThread2  extends Thread {
    public void run() {
        while (true) {
            System.out.println("hello thread!");

            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

static void Test2(){
    //通过传参来完成和第一的一样效果
    Thread t = new Thread(new MyThread2());
    t.start();
}
```

3. 使用匿名内部类的方式

   ```java
   class MyThread2  extends Thread {
       public void run() {
           while (true) {
               System.out.println("hello thread!");
   
               try {
                   Thread.sleep(1000);
               } catch (InterruptedException e) {
                   e.printStackTrace();
               }
           }
       }
   }
   
   static void Test3() {
       //这个语法就是匿名内部类
       //相当于创建了一个匿名的类，这个类继承了Thread
       //此处new的实列，其实就是new了这个新的类的实列
       Thread t = new Thread() {
           public void run() {
               System.out.println("hello thread");
               try {
                   Thread.sleep(1000);
               } catch (InterruptedException e) {
                   e.printStackTrace();
               }
           }
       };
   
       t.start();
   }
   ```

   
