# Variable Scope

## Reference variables

Example 1
The values m and n don't change here.

```java
public class References
{
  public static void main (String[] args)
  {
    int m = 5;
    int n = 6;

    System.out.println("M=" + m + " N=" + n);
    swap(m, n);
    System.out.println("M=" + m + " N=" + n);
  }

  private static void swap(int a, int b)
  {
    int c = a;
    a = b;
    b = c;
  }
}
```



Example 2
The objects' data changes in this code

```java
public class Primitives
{
  public static void main(String[] args)
  {
    Student jen = new Student();
    jen.name = "Jen";
    jen.age = 21;

    Student beth = new Student();
    beth.name = "Beth";
    beth.age = 15;

    System.out.println("Jen is " + jen.age);
    System.out.println("Beth is " + beth.age);

    ageSwap(jen, beth);

    System.out.println("Jen is " + jen.age);
    System.out.println("Beth is " + beth.age);
  }

  private static void ageSwap(Student a,
                                    Student b)
  {
    int c = a.age;
    a.age = b.age;
    b.age = c;
  }

  static class Student
  {
    String name;
    int age;
  }
}
```

**Primitive variables store values. Reference variable stores an address.** Or in the example of this lesson they used phone number but I will use address for my explanation.
When you pass a variable through a method. **That method will make a copy of it. The passed variable and the copy are independent of each other. So if the copy is modified it will have no affect on the variable that passed through the method.** So you are correct that primitive variables do not get modified by methods.
To clarify for the second example. You are correct that a reference variable is being passed. Now remember that a reference variable is an address that points to an object. So when we pass a reference variable through a method a copy of the address is created. That means we technically have two reference variables now pointing to the same object. If we look back at the code for the second example. The reference variable is actually not being modified at all. Technically what is being modified is the object. We are just using the "variable name" of the copied address to reference it.



## Static

1）static方法

　　static方法一般称作静态方法，由于静态方法不依赖于任何对象就可以进行访问，因此对于静态方法来说，是没有this的，因为它不依附于任何对象，既然都没有对象，就谈不上this了。并且由于这个特性，在静态方法中不能访问类的非静态成员变量和非静态成员方法，因为非静态成员方法/变量都是必须依赖具体的对象才能够被调用。

2）static变量

　　static变量也称作静态变量，静态变量和非静态变量的区别是：静态变量被所有的对象所**共享**，在内存中只有一个副本，它当且仅当在类初次加载时会被初始化。而非静态变量是对象所拥有的，在创建对象的时候被初始化，存在多个副本，各个对象拥有的副本互不影响。	

"If a variable is declared static, i.e. marked with the keyword **static**, it exists as long as its class exists. The JVM usually loads a class into memory at its first use. That's also when static variables are initialized."



"When you call a method using **<object>** dot <method name>, you're actually calling a class method and passing **that same object** as the first argument. Inside the method, the object is called **'this'**. All operations in the method are performed on this object and its data."



What the code looks like

```java
Cat cat = new Cat();
String name = cat.getName();
cat.setAge(17);
cat.setChildren(cat1, cat2, cat3);
```

What really happens

```java
Cat cat = new Cat();
String name = Cat.getName(cat);//pass the same object
Cat.setAge(cat,17);
Cat.setChildren(cat, cat1, cat2, cat3);
```



For static method

| What the code looks like`Cat cat1 = new Cat(); Cat cat2 = new Cat(); int catCount = Cat.getAllCatsCount();` | What really happens`Cat cat1 = new Cat(); Cat cat2 = new Cat(); int catCount = Cat.getAllCatsCount(null);` |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |



| Static (class) variable`ClassName.variableName  *// Here are some examples:* Cat.catsCount` | Non-static (instance) variable`this.variableName  *// Here are some examples:* this.catsCount` |
| ------------------------------------------------------------ | ------------------------------------------------------------ |



```{java}
package com.codegym.task.task06.task0616;

/* 
Minimum number of statics

*/

public class Solution {
    public static int step;

    public static void main(String[] args) {
        method1();
    }

    public static void method1() {
        method2();
    }

    public static void method2() {
        new Solution().method3();// method3() is non-static
    }

    public void method3() {
        method4();
    }

    public void method4() {
        step++;
        for (StackTraceElement element : Thread.currentThread().getStackTrace())
            System.out.println(element);
        if (step > 1)
            return;
        main(null);
    }
}

```

non-static method  cannot be referenced from a static context