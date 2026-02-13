# Experiment 6a
## AIM: To write a JAVA program that describes exception handling mechanism.
```java
// ArrayInput.java
import java.util.Scanner;

public class ArrayInput {

    public int[] readArray() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the size of the array: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        return arr;
    }
}

// ArrayAccess.java
import java.util.Scanner;

public class ArrayAccess {

    public void accessElement(int[] arr) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the index to access: ");
        int index = sc.nextInt();

        try {
            System.out.println("Element at index " + index + " is: " + arr[index]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println(
                "Invalid index! Please enter an index between 0 and " + (arr.length - 1)
            );
        }
    }
}

// ExceptionHandlingDemo.java

public class ExceptionHandlingDemo {

    public static void main(String[] args) {

        ArrayInput input = new ArrayInput();
        int[] array = input.readArray();

        ArrayAccess access = new ArrayAccess();
        access.accessElement(array);
    }
}



```
## output:
![the output is](6aoutput.png)

# Experiment 6b
## AIM: To write a JAVA program Illustrating Multiple catch clauses.
```java

// ArithmeticOperation.java
import java.util.Scanner;

public class ArithmeticOperation {

    public int divide() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int a = sc.nextInt();

        System.out.print("Enter second number: ");
        int b = sc.nextInt();

        int result = a / b;   // May throw ArithmeticException
        System.out.println("Division Result = " + result);

        return result;
    }
}

// ArrayOperation.java

import java.util.Scanner;

public class ArrayOperation {

    public void accessArray() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter size of array: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        System.out.println("Enter " + n + " array elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        System.out.print("Enter index to access array element: ");
        int index = sc.nextInt();

        System.out.println("Element at index " + index + " = " + arr[index]);
    }
}

// MultipleCatchDemo.java
import java.util.InputMismatchException;

public class MultipleCatchDemo {

    public static void main(String[] args) {

        try {
            ArithmeticOperation ao = new ArithmeticOperation();
            ao.divide();

            ArrayOperation ar = new ArrayOperation();
            ar.accessArray();
        }

        catch (ArithmeticException e) {
            System.out.println("Error: Division by zero is not allowed.");
        }

        catch (InputMismatchException e) {
            System.out.println("Error: Please enter numeric values only.");
        }

        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Error: Invalid array index.");
        }

        catch (Exception e) {
            System.out.println("Some other error occurred.");
        }

        System.out.println("Program continues...");
    }
}


```
## output:
![the output is](6boutput.png)

# experiment 6c
## AIM: To write a JAVA program for creation of Java Built-in Exceptions
```java

// DivisionOperation.java

import java.util.Scanner;

public class DivisionOperation {

    public void divideNumber() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter an integer to divide 100: ");
        int n = sc.nextInt();

        int result = 100 / n;   // May cause ArithmeticException
        System.out.println("Result = " + result);
    }
}

// ArrayExceptionDemo.java

public class ArrayExceptionDemo {

    public void accessArray() {
        int[] arr = {10, 20, 30};

        // Intentionally accessing invalid index
        System.out.println("Accessing element: " + arr[5]);
    }
}

// NumberFormatDemo.java
import java.util.Scanner;

public class NumberFormatDemo {

    public void convertStringToInt() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number as text: ");
        String s = sc.next();

        int num = Integer.parseInt(s);  // May cause NumberFormatException
        System.out.println("Converted number = " + num);
    }
}

// BuiltInExceptionDemo.java
public class BuiltInExceptionDemo {

    public static void main(String[] args) {

        try {
            DivisionOperation d = new DivisionOperation();
            d.divideNumber();

            ArrayExceptionDemo a = new ArrayExceptionDemo();
            a.accessArray();

            NumberFormatDemo n = new NumberFormatDemo();
            n.convertStringToInt();
        }

        catch (ArithmeticException e) {
            System.out.println("ArithmeticException: division by zero.");
        }

        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBoundsException: invalid index.");
        }

        catch (NumberFormatException e) {
            System.out.println("NumberFormatException: invalid numeric format.");
        }

        catch (Exception e) {
            System.out.println("Some other exception occurred.");
        }

        System.out.println("Program continues...");
    }
}


```
## output:
![the output is](6coutput.png)


