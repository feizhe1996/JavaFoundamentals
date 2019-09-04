# Interface

### Abstract class and methods

**—Abstract classes normally contain one or more abstract methods**

**—All concrete subclasses must override all inherited abstract methods**

An abstract class cannot be instantiated. But abstract class can be used as a data type

```{java}
public abstract class Test {
    public abstract void test1();//no braces cannot have a method body
}
```



### Final methods

final methods may not be overridden

A class can be declared final.
**Final classes may not be extended.**

### Java Interface

containing **only public abstract methods**

```{java}
public interface ElectronicDevice {
    public void turnOn();
    public void turnOff();   
}

public class Television implements ElectronicDevice {
    public void turnOn() { }
    public void turnOff() { }
    public void changeChannel(int channel) {}
    private void initializeScreen() {}
}

```

Classes can extend a parent class and implement an interface

You can also implement multiple interfaces