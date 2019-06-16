# Bitwise Operatprs

**A bit** is the smallest unit of information in a computer. Its name comes from *binary digit*. A bit can be expressed by one of two numbers: **1** or **0**.

wrapper class

byte         ------------------------>      Byte

short       ------------------------->     Short

int           ------------------------->     Integer

long        ------------------------->     Long

char        ------------------------->     Character

float        ------------------------->     Float

double    ------------------------->     Double

boolean  ------------------------->    Boolean

```{java}
public class Main {

   public static void main(String[] args) {

       int x = 342;
       System.out.println(Integer.toBinaryString(x));
   }
}
```

* `~` bitwise **NOT** which flips each bit.

* `&` bitwise **AND**

* `|` bitwise **OR**

* `^` bitwise **Exclusive OR**

* `<<`  **shift left**

  * ```{java}
    public class Main {
    
       public static void main(String[] args) {
           int x = 64;//value
           int y = 3;// Shift distance
    
           int z = (x << y);
           System.out.println(Integer.toBinaryString(x));
           System.out.println(Integer.toBinaryString(z));
       }
    }
    
    ```

  * In this example, we use 

    ```undefined
    int
    ```

    s. Ints occupy 32 bits in the computer's memory. This is how our original number 64 looks: 

    ![img](https://codegym.cc/api/1.0/rest/images/10000017/ba6dd237-6454-422c-a938-13a992cdfeaf?size=1024)

     And now we take each of our bits and literally shift them to the left by 3 places: 

    ![img](https://codegym.cc/api/1.0/rest/images/10000017/b2157e37-a923-45cf-842c-0534010ab2fe?size=1024)

    Thus, the expression `x << y` means "shift the bits of the number `x` to the left by y places". 

  * **For each shift to the left, the number is multiplied by 2.**

* `>>` **shift right**

  * **Each shift to the right divides by two, discarding any remainder.**

    