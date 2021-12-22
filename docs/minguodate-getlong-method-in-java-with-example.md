# Java 中的 MinguoDate getLong()方法，示例

> 原文:[https://www . geesforgeks . org/minuodate-getlong-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-getlong-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的 **getLong()** 方法用于以长格式检索传递的时态字段。

**语法:**

```
public long getLong(TemporalField field)

```

**参数**:该方法以任意类型的时态字段为参数。

**返回值**:该方法以长格式返回传递的时态字段。

以下是举例说明 **getLong()** 方法:

T4】例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getLong() method

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

            // getting temporal field in long format
            // by using getLong() method
            long tempo
                = hidate.getLong(
                    ChronoField.EPOCH_DAY);

            // display the result
            System.out.println(
                "specified temporal field"
                + "in long format: "
                + tempo);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**Output:**

```
specified temporal fieldin long format: 18376

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getLong() method

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

            // getting temporal field in long format
            // by using getLong() method
            long tempo
                = hidate.getLong(
                    ChronoField.DAY_OF_WEEK);

            // display the result
            System.out.println(
                "specified temporal field"
                + "in long format: "
                + tempo);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**Output:**

```
specified temporal fieldin long format: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # getLong-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#getLong-java.time.temporal.TemporalField-)