# Java 中的 minuo 年表范围()方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo 年表-范围-java 中的方法-带示例/](https://www.geeksforgeeks.org/minguochronology-range-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的 **range()** 方法用于从 chrono 类型的指定字段中获取的范围。

**语法:**

```
public ValueRange range(ChronoField field)
```

**参数:**该方法以**型计时场**的场为参数。

**返回值:**该方法从指定的类型为 chrono 的字段中返回的范围。

以下是说明**范围()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// range() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in LocalDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(ChronoField.ERA);

            // display the result
            System.out.println(
                "Equivalent Range : "
                + range);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Equivalent Range : 0 - 1

```

**例 2:**

```
// Java program to demonstrate
// range() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in LocalDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(ChronoField.YEAR);

            // display the result
            System.out.println(
                "Equivalent Range : "
                + range);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Equivalent Range : -1000001910 - 999998088

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguoserterog . html # range-Java . time . temporal . chronofield-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#range-java.time.temporal.ChronoField-)