# Java 中的抽象顺序列表移除所有()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-remove all-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-removeall-method-in-java-with-example/)

**Java . util . abstractsequentialist**类的 **removeAll()** 方法用于从该列表中移除指定集合中包含的所有元素。

**语法:**

```
public boolean removeAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该列表中移除的元素的参数。

**返回值:**如果该列表因调用而改变，则该方法返回**真**。

**异常:**如果此列表包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则此方法抛出**空指针异常**。

以下是说明 *removeAll()* 方法的示例。

**例 1:**

```
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist1 = new LinkedList<Integer>();

            // Populating arrlist1
            arrlist1.add(1);
            arrlist1.add(2);
            arrlist1.add(3);
            arrlist1.add(4);
            arrlist1.add(5);

            // print arrlist1
            System.out.println("AbstractSequentialList before "
                               + "removeAll() operation : "
                               + arrlist1);

            // Creating another object 
// of  AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist2 = new LinkedList<Integer>();
            arrlist2.add(1);
            arrlist2.add(2);
            arrlist2.add(3);

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrlist2);

            // Removing elements from arrlist
            // specified in arrlist2
            // using removeAll() method
            arrlist1.removeAll(arrlist2);

            // print arrlist1
            System.out.println("AbstractSequentialList after "
                               + "removeAll() operation : "
                               + arrlist1);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
AbstractSequentialList before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : [1, 2, 3]
AbstractSequentialList after removeAll() operation : [4, 5]

```

**示例 2:** 适用于*空指针异常*

```
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist1 = new LinkedList<Integer>();

            // Populating arrlist1
            arrlist1.add(1);
            arrlist1.add(2);
            arrlist1.add(3);
            arrlist1.add(4);
            arrlist1.add(5);

            // print arrlist1
            System.out.println("AbstractSequentialList before "
                               + "removeAll() operation : "
                               + arrlist1);

            // Creating another object of  AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist2 = null;

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrlist2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from arrlist
            // specified in arrlist2
            // using removeAll() method
            arrlist1.removeAll(arrlist2);

            // print arrlist1
            System.out.println("AbstractSequentialList after "
                               + "removeAll() operation : "
                               + arrlist1);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
AbstractSequentialList before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : null

Trying to pass null as a specified element

java.lang.NullPointerException

```