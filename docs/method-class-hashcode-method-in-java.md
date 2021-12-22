# Java 中的方法类| hashCode()方法

> 原文:[https://www . geesforgeks . org/method-class-hashcode-method-in-Java/](https://www.geeksforgeeks.org/method-class-hashcode-method-in-java/)

方法返回方法类对象的哈希代码。返回的 hashcode 是通过对方法的声明类名和方法名的 hashcode 进行异或运算来计算的。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用这个唯一的代码搜索一个对象。

**语法:**

```
public int hashCode()
```

**返回:**返回一个**整数**值，该值代表该方法的哈希值。

**示例:**

```
Method: public void getvalue(){}
HashCode: 1553975225
*Explanation*: Hashcode is a unique code generated by the JVM at time of creation of the object
of Method getValue.when we going to apply hashCode function on method object of 
getValue it will return 1553975225 as hashCode.

Method:public void paint(){}
HashCode: 1643975341

```

下面的程序举例说明了 method 类的 hashcode()方法:
**程序 1:** 获取通过调用 class 对象的 getDeclaredMethod()创建的特定方法对象的 hash 代码。

```
/*
* Program Demonstrate hashcode() method of Method Class.
*/
import java.lang.reflect.Method;

public class GFG {

    // create a Method name getSampleMethod
    public void getSampleMethod() {}

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for class name GFG
            Class c = GFG.class;

            // get Method object of method name getSampleMethod
            Method method = c.getDeclaredMethod("getSampleMethod", null);

            // get hashcode of method object using hashCode() method
            int hashCode = method.hashCode();

            // Print hashCode with method name
            System.out.println("hashCode of method " + method.getName()
                               + " is " + hashCode);
        }
        catch (Exception e) {
            // print if any exception occures
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
hashCode of method getSampleMethod is 1553813225

```

**程序 2:**

在本程序中，通过调用类对象的 getmethods()方法获取类对象的 Method 对象列表后，对列表中的每个方法对象调用 Method 对象的 hashCode()方法。最后，hashcode 和方法名一起被打印出来。

```
/*
* Program Demonstrate hashcode() method of Method Class.
*/
import java.lang.reflect.Method;

public class GFG {

    // create a Method name getSampleMethod
    public void getSampleMethod() {}

    // create a Method name setSampleMethod
    public String setSampleMethod()
    {

        String str = "hello India";
        return str;
    }

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for class name GFG
            Class c = GFG.class;

            // get list of Method objects
            // of class object of gfg class
            Method[] methods = c.getMethods();

            // loop through methods list
            // and get hashcode of every method
            // and print those hashcode along with Method Name
            for (Method m : methods) {

                // get hashcode of current method of loop
                int hashCode = m.hashCode();

                // Print hashCode along with method name
                System.out.println("hashCode of method "
                                   + m.getName()
                                   + " is " + hashCode);
            }
        }
        catch (Exception e) {
            // print Exception if any Exception occurs.
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
hashCode of method main is 3282673
hashCode of method getSampleMethod is 1553813225
hashCode of method setSampleMethod is -1830532123
hashCode of method wait is 1063184614
hashCode of method wait is 1063184614
hashCode of method wait is 1063184614
hashCode of method equals is -1918826964
hashCode of method toString is -1451283457
hashCode of method hashCode is 933549448
hashCode of method getClass is 1261057617
hashCode of method notify is -43061542
hashCode of method notifyAll is 1312178187

```

**解释:**这个程序的输出还显示了除了类对象中定义的方法之外的方法对象的结果，比如 wait、equals、toString、hashCode、getClass、notifyAll，它们都是从 java.lang 包的超类 object 中通过类 Object 继承的。

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#hashCode--)