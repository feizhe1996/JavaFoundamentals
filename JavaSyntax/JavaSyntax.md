# Java Syntax

java 中 System 类

最常见到 System.out.println();

System类 定义为 public final class System extends Object{} 包含几个有用的类字段和方法，用了关键字 final 修饰，表示此类不能被其他类继承。

其构造方法为 private System{} （构造方法私有化，不能被外部实例化）。 

System 中有三个属性：in，out，err；

1.private final static InputStream in=null;

2.private final static PrintStream out=null;  

​           -->  out 为类PrintStream 类型 println()就是PrintStream中的方法。out被 final 和static 修饰的常量，故可以用System调用out属性，再调用println()方法。



| Java code                                                    | Description                                                  |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| `String s; String s = null;`                                 | Equivalent statements.                                       |
| `Person person; person= new Person(); person = null;`        | We create a person variable whose value is null. We assign to it the address of a newly created Person object. We assign null to the variable. |
| `Cat cat = new Cat(); cat.owner = new Person(); cat.owner.name = "God";` | We create a Cat object and store its address in variable cat; cat.owner equals null. We set cat.owner equal to the address of a newly created Person object. cat.owner.name still equals null. We set cat.owner.name equal to "God" |



