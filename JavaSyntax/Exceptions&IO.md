# Exceptions&IO



## IO

```{java}
package practice;

import java.io.*;


public class TestIO2 {
    public static void main(String[] args) {
        File file = new File("C:\\Users\\feizh\\Desktop\\JavaFundamentals\\testio.txt");
        File file1 = new File("C:\\Users\\feizh\\Desktop\\JavaFundamentals\\testoutput.txt");
        int count = 0;
        try {
            BufferedReader readfromUser = new BufferedReader(new InputStreamReader(System.in));
            BufferedReader reader = new BufferedReader(new FileReader(file));
            BufferedWriter writer = new BufferedWriter(new FileWriter(file1));
            String line = "";
            String key = readfromUser.readLine();

            while ((line = reader.readLine()) != null) {
                System.out.println(line);
                if(line.equals(key))
                    count++;
                line += "test";
                writer.write(line);
                writer.newLine();
                writer.flush();


            }
            reader.close();
            writer.close();


        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
        finally {System.out.println(count);}


    }
}

```





```{java}
package practice;

import java.io.*;

public class TestIO {
    public static void main(String[] args) throws IOException {
        File file = new File("C:\\Users\\feizh\\Desktop\\JavaFundamentals\\testio.txt");
        if(!file.exists()) {
            System.out.println("file not exist");
        }
        BufferedReader reader = new BufferedReader(new InputStreamReader(new FileInputStream(file)));
        String context = null;
        File file1 = new File("C:\\Users\\feizh\\Desktop\\JavaFundamentals\\testoutput.txt");
        BufferedOutputStream writer = new BufferedOutputStream((new FileOutputStream(file1)));
        while((context = reader.readLine()) != null) {
            System.out.println(context);
            context += "\r\n";
            writer.write(context.getBytes());
            writer.flush();
        }
    }
}



```

