# Experiment 5a
## AIM: To write a JAVA program to implement Interface.
```java

// Sortable.java
public interface Sortable {
    void sort(int[] arr);
}

// BubbleSort.java
public class BubbleSort implements Sortable {

    public void sort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
}

// SelectionSort.java
public class SelectionSort implements Sortable {

    public void sort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int min = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[min]) {
                    min = j;
                }
            }
            int temp = arr[min];
            arr[min] = arr[i];
            arr[i] = temp;
        }
    }
}

// TestSort.java
import java.util.Scanner;

public class TestSort {

    static void printArray(int[] arr) {
        for (int x : arr) {
            System.out.print(x + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // -------- Bubble Sort Input --------
        System.out.print("Enter number of elements for Bubble Sort: ");
        int n1 = sc.nextInt();

        int[] arr1 = new int[n1];
        System.out.println("Enter elements:");
        for (int i = 0; i < n1; i++) {
            arr1[i] = sc.nextInt();
        }

        Sortable ref = new BubbleSort();
        ref.sort(arr1);
        System.out.println("Array sorted using Bubble Sort:");
        printArray(arr1);

        // -------- Selection Sort Input --------
        System.out.print("Enter number of elements for Selection Sort: ");
        int n2 = sc.nextInt();

        int[] arr2 = new int[n2];
        System.out.println("Enter elements:");
        for (int i = 0; i < n2; i++) {
            arr2[i] = sc.nextInt();
        }

        ref = new SelectionSort();
        ref.sort(arr2);
        System.out.println("Array sorted using Selection Sort:");
        printArray(arr2);

        sc.close();
    }
}


```
## output:
![the output is](5aoutput.png)

# Experiment 5b
## AIM: 
```java

// Vehicle.java
public class Vehicle {
    public void run() {
        System.out.println("Vehicle is running");
    }
}

// Car.java
public class Car extends Vehicle {

    @Override
    public void run() {
        System.out.println("Car is running on four wheels");
    }
}

// Bike.java
public class Bike extends Vehicle {

    @Override
    public void run() {
        System.out.println("Bike is running on two wheels");
    }
}

// TestVehicle.java
import java.util.Scanner;

public class TestVehicle {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Vehicle v;   // parent reference

        System.out.println("Choose vehicle type:");
        System.out.println("1. Car");
        System.out.println("2. Bike");

        int choice = sc.nextInt();

        if (choice == 1) {
            v = new Car();   // dynamic assignment
        } else if (choice == 2) {
            v = new Bike();  // dynamic assignment
        } else {
            v = new Vehicle(); // default
        }

        v.run();   // runtime polymorphism

        sc.close();
    }
}



```
## output:
![the output is](5boutput.png)

# experiment 5c
## AIM: 
```java

// ArrayOperation.java
import java.util.Scanner;

public class ArrayOperation {

    public void readAndAccessArray() {

        Scanner sc = new Scanner(System.in);

        // Dynamic array size
        System.out.print("Enter size of the array: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        // Read array elements dynamically
        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        // Ask for index
        System.out.print("Enter index to access: ");
        int index = sc.nextInt();

        // Exception handling
        try {
            System.out.println("Element at index " + index + " is: " + arr[index]);
        }
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Invalid index! Please enter index between 0 and " + (n - 1));
        }
    }
}


// TestException.java

public class TestException {
    public static void main(String[] args) {

        ArrayOperation obj = new ArrayOperation();
        obj.readAndAccessArray();

    }
}


```
## output:
![the output is](5coutput.png)

