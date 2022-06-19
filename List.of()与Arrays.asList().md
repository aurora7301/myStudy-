##javaI/O（FileReader、BufferedReader）

通过 Java I/O API**在 Java 中执行文件处理**。

在 Java 中，自动为我们创建了 3 个流。所有这些流都与控制台相连。

**1) System.out：**标准输出流

**2) System.in：**标准输入流

**3) System.err：**标准错误流

OutputStream：Java application uses an output stream to write data to a destination; it may be a ==file, an array, peripheral device or socket==.

InputStream：Java application uses an input stream to read data from a source; it may be a ==file, an array, peripheral device or socket==.

![Java IO](https://static.javatpoint.com/java/javaio/images/java-io-flow.png)

OutputStream class is an ==abstract class==. It is the superclass of all classes representing an output stream of bytes. An output stream accepts output bytes and sends them to some sink.

==Useful methods of OutputStream==

| Method                                             | Description                                                  |
| :------------------------------------------------- | :----------------------------------------------------------- |
| 1) public void ==write(int)throws IOException==    | is used to write a byte to the current output stream.        |
| 2) public void ==write(byte[])throws IOException== | is used to write an array of byte to the current output stream. |
| 3) public void ==flush()throws IOException==       | flushes the current output stream.                           |
| 4) public void ==close()throws IOException==       | is used to close the current output stream.                  |

![Java output stream hierarchy](https://static.javatpoint.com/java/javaio/images/java-outputstream.png)

InputStream class is an abstract class. It is the superclass of all classes representing an input stream of bytes.

Useful methods of InputStream

| Method                                              | Description                                                  |
| :-------------------------------------------------- | :----------------------------------------------------------- |
| 1) public ==abstract int read()throws IOException== | reads the next byte of data from the input stream. It ==returns -1 at the end of the file==. |
| 2) public ==int available()throws IOException==     | returns an estimate of the number of bytes that can be read from the current input stream. |
| 3) public ==void close()throws IOException==        | is used to close the current input stream.                   |

InputStream Hierarchy

![Java input stream hierarchy](https://static.javatpoint.com/java/javaio/images/java-inputstream.png)

# Java FileReader 类

Java FileReader 类用于从文件中读取数据。它以字节格式返回数据，如[FileInputStream](https://www.javatpoint.com/java-fileinputstream-class)类。它是面向字符的类，用于在[java中进行](https://www.javatpoint.com/java-tutorial)[文件](https://www.javatpoint.com/java-file-class)处理。

**public** **class** FileReader **extends** InputStreamReader 

###FileReader 类的构造函数

| Constructor             | Description                                                  |
| :---------------------- | :----------------------------------------------------------- |
| FileReader(String file) | It gets filename in [string](https://www.javatpoint.com/java-string). It opens the given file in read mode. If file doesn't exist, it throws FileNotFoundException. |
| FileReader(File file)   | It gets filename in [file](https://www.javatpoint.com/java-file-class) instance. It opens the given file in read mode. If file doesn't exist, it throws FileNotFoundException. |

## FileReader 类的方法

| Method       | Description                                                  |
| :----------- | :----------------------------------------------------------- |
| int read()   | It is used to return a character in ASCII form. It returns -1 at the end of file. |
| void close() | It is used to close the FileReader class.                    |

## Java FileReader Example

In this example, we are reading the data from the text file **testout.txt** using Java FileReader class.

```java
import java.io.FileReader; 
public class FileReaderExample { 
public static void main(String args[])throws Exception{  
	FileReader fr=**new*FileReader("D:\\testout.txt");  
	int i;  
	while((i=fr.read())!=-1)  
	System.out.print((char)i);  
	fr.close();  
	}  
}
```

假设您在“testout.txt”文件中有以下数据：Welcome to java

输出：Welcome to java

# Java BufferedReader 类

Java BufferedReader 类用于从基于字符的输入流中读取文本。它可以用于通过 readLine() 方法逐行读取数据，性能快速。它继承了[Reader](https://www.javatpoint.com/java-reader-class) [类](https://www.javatpoint.com/object-and-class-in-java)。

**public** **class** BufferedReader **extends** Reader 

## Java BufferedReader 类构造函数

| 构造函数                            | 描述                                                         |
| :---------------------------------- | :----------------------------------------------------------- |
| BufferedReader(Reader rd)           | 它用于创建使用输入缓冲区的默认大小的缓冲字符输入流。         |
| BufferedReader(Reader rd, int size) | 它用于创建一个缓冲字符输入流，该流使用输入缓冲区的指定大小。 |

methods：

| Method                                  | Description                                                  |
| :-------------------------------------- | :----------------------------------------------------------- |
| int read()                              | It is used for reading a single character.                   |
| int read(char[] cbuf, int off, int len) | It is used for reading characters into a portion of an [array](https://www.javatpoint.com/array-in-java). |
| boolean markSupported()                 | It is used to test the input stream support for the mark and reset method. |
| String readLine()                       | It is used for reading a line of text.                       |
| boolean ready()                         | It is used to test whether the input stream is ready to be read. |
| long skip(long n)                       | It is used for skipping the characters.                      |
| void reset()                            | It repositions the [stream](https://www.javatpoint.com/java-8-stream) at a position the mark method was last called on this input stream. |
| void mark(int readAheadLimit)           | It is used for marking the present position in a stream.     |
| void close()                            | It closes the input stream and releases any of the system resources associated with the stream. |

eg：

```
import java.io.*;  
public class BufferedReaderExample {  
    public static void main(String args[])throws Exception{    
          FileReader fr=new FileReader("D:\\testout.txt"); 
          BufferedReader br=new BufferedReader(fr); 
          int i;    
          while((i=br.read())!=-1){  
          System.out.print((char)i);  
          }  
          br.close();    
          fr.close();    
    }    
}    
```

data in "testout.txt" file:   Welcome to java.

Output:  Welcome to java.

==通过 InputStreamReader 和 BufferedReader 从控制台读取数据==

```java
import java.io.*;  
public class BufferedReaderExample{    
public static void main(String args[])throws Exception{       InputStreamReader r=new InputStreamReader(System.in); 
    BufferedReader br=new BufferedReader(r);            
    System.out.println("Enter your name");    
    String name=br.readLine();    
    System.out.println("Welcome "+name);    
}    
}  
Output:
Enter your name
Nakul Jain
Welcome Nakul Jain
```

从控制台读取数据直到用户写入停止的另一个示例:读取和打印数据，直到用户停止打印。

```
import java.io.*;  
public class BufferedReaderExample{    
public static void main(String args[])throws Exception{
     InputStreamReader r=new InputStreamReader(System.in); 
     BufferedReader br=new BufferedReader(r);           
     String name="";    
     while(!name.equals("stop")){    
      System.out.println("Enter data: ");    
      name=br.readLine();    
      System.out.println("data is: "+name);    
     }              
    br.close();    
    r.close();    
  	}    
}  
```

Output:

```
Enter data: Nakul
data is: Nakul
Enter data: 12
data is: 12
Enter data: stop
data is: stop
```

for遍历hashmap

泛型

# List.of()与Arrays.asList()

hashMap 可以remove一个不存在的key吗，会不会报错