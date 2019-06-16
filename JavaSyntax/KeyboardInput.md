# Keyboard Input

<https://codegym.cc/groups/posts/4-reading-from-keyboard>

## InputStream

```{java}
InputStream inputStream = System.in;
Reader inputStreamReader = new InputStreamReader(inputStream);
BufferedReader bufferedReader = new ufferedReader(inputStreamReader);
//
BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
```

`System.in` is an `InputStream` object, an instance of the class.

`InputStream` object has a `read()` method.

It read bytes. So we need a adorned form.

```{java}
import java.io.*;
public class Main {

   public static void main(String[] args) throws IOException {

       while (true) {
           int x = System.in.read();
           System.out.println(x);
       }
   }
}
```

`new InputStreamReder(System.in)`

`InputStreamReder` can convert bytes streams to character streams and read data from files.

```{java}
InputStreamReader inputStreamReader = new InputStreamReader(new FileInputStream("C:\\Users\\username\\Desktop\\testFile.txt"));
```

We use BufferedReader for great performance and convenience.

Buffer is like a box.



* Practice

```{java}
package com.codegym.task.task03.task0319;

/* 
Predictions

*/

import java.io.*;

public class Solution {
    public static void main(String[] args) throws Exception {
        //write your code here
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
        String name = reader.readLine();
        int number1 = Integer.parseInt(reader.readLine());
        int number2 = Integer.parseInt(reader.readLine());
        
        System.out.println(name+" will receive " + number1 + " in "+ number2+" years.");
    }
}

```

* Intellj IDEA
  * psvm + Tab main函数
  * sout + Tab System.out.println();

## Scanner

```{java}
import java.util.Scanner;
public class Main {

   public static void main(String[] args) {

       Scanner scanner = new Scanner("It matters not how strait the gate,\n" +
               "How charged with punishments the scroll,\n" +
               "I am the master of my fate,\n" +
               "I am the captain of my soul");
       String s = scanner.nextLine();
       System.out.println(s);
       s = scanner.nextLine();
       System.out.println(s);
       s = scanner.nextLine();
       System.out.println(s);
       s = scanner.nextLine();
       System.out.println(s);
   }
}
```

### look into the future

- `hasNextInt()`: This method checks whether the next chunk of input data is a number (returns true or false, as appropriate)
- `hasNextLine()`: This method checks whether the next chunk of data is a string.
- `hasNextByte()`, `hasNextShort()`, `EhasNextLong()`, `hasNextFloat()`, `hasNextDouble()`: All these methods perform similar checks for the remaining data types.

```{java}
public class Main {

   public static void main(String[] args) {

       Scanner sc = new Scanner(System.in);
       System.out.println("Enter a number:");

       if (sc.hasNextInt()) {
           int number = sc.nextInt();
           System.out.println("Thanks! You entered the number " + number);
       } else {
           System.out.println("Sorry, but this is clearly not a number. Restart the program and try again!");
       }
		scanner.close();
   }
}
```

