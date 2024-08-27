Here's a day-wise training plan for Core Java development. This plan assumes a beginner to intermediate level of understanding and is structured over a two-week period. Each day will cover specific topics, with example code snippets to reinforce learning.

---

### **Week 1: Core Java Fundamentals**

#### **Day 1: Introduction to Java & Setting Up the Environment**
- **Topics:**
  - Introduction to Java and its ecosystem.
  - Installing JDK and setting up an IDE (Eclipse/IntelliJ IDEA).
  - Writing your first Java program.
- **Example Code:**
  ```java
  public class HelloWorld {
      public static void main(String[] args) {
          System.out.println("Hello, World!");
      }
  }
  ```

#### **Day 2: Basic Syntax & Variables**
- **Topics:**
  - Data types, variables, and constants.
  - Naming conventions.
  - Comments in Java.
- **Example Code:**
  ```java
  public class BasicSyntax {
      public static void main(String[] args) {
          int number = 10;
          String text = "Core Java";
          final double PI = 3.14159;

          System.out.println("Number: " + number);
          System.out.println("Text: " + text);
          System.out.println("PI: " + PI);
      }
  }
  ```

#### **Day 3: Operators & Expressions**
- **Topics:**
  - Arithmetic, relational, logical, and bitwise operators.
  - Expressions and operator precedence.
- **Example Code:**
  ```java
  public class Operators {
      public static void main(String[] args) {
          int a = 10, b = 20;
          int sum = a + b;
          boolean isGreater = a > b;

          System.out.println("Sum: " + sum);
          System.out.println("Is A greater than B? " + isGreater);
      }
  }
  ```

#### **Day 4: Control Statements**
- **Topics:**
  - If-else, switch-case.
  - Loops (for, while, do-while).
- **Example Code:**
  ```java
  public class ControlStatements {
      public static void main(String[] args) {
          int number = 5;

          if (number > 0) {
              System.out.println("Positive");
          } else {
              System.out.println("Negative");
          }

          switch (number) {
              case 1:
                  System.out.println("One");
                  break;
              case 5:
                  System.out.println("Five");
                  break;
              default:
                  System.out.println("Other");
          }

          for (int i = 1; i <= 5; i++) {
              System.out.println("Count: " + i);
          }
      }
  }
  ```

#### **Day 5: Arrays & Strings**
- **Topics:**
  - Introduction to arrays.
  - String handling (String class, methods).
- **Example Code:**
  ```java
  public class ArraysAndStrings {
      public static void main(String[] args) {
          int[] numbers = {1, 2, 3, 4, 5};
          String text = "Core Java";

          for (int number : numbers) {
              System.out.println("Number: " + number);
          }

          System.out.println("Length of text: " + text.length());
          System.out.println("Uppercase: " + text.toUpperCase());
      }
  }
  ```

#### **Day 6: Methods & Recursion**
- **Topics:**
  - Method definition, parameters, and return types.
  - Recursion.
- **Example Code:**
  ```java
  public class MethodsAndRecursion {
      public static void main(String[] args) {
          int result = factorial(5);
          System.out.println("Factorial of 5: " + result);
      }

      public static int factorial(int n) {
          if (n == 0) {
              return 1;
          } else {
              return n * factorial(n - 1);
          }
      }
  }
  ```

#### **Day 7: Object-Oriented Programming Basics**
- **Topics:**
  - Classes and objects.
  - Constructors.
  - Methods and encapsulation.
- **Example Code:**
  ```java
  class Car {
      private String model;
      private int year;

      // Constructor
      public Car(String model, int year) {
          this.model = model;
          this.year = year;
      }

      // Method
      public void displayInfo() {
          System.out.println("Model: " + model + ", Year: " + year);
      }
  }

  public class OOPBasics {
      public static void main(String[] args) {
          Car car = new Car("Toyota", 2022);
          car.displayInfo();
      }
  }
  ```

---

### **Week 2: Advanced Core Java**

#### **Day 8: Inheritance & Polymorphism**
- **Topics:**
  - Inheritance.
  - Method overriding.
  - Polymorphism.
- **Example Code:**
  ```java
  class Animal {
      public void sound() {
          System.out.println("Animal makes a sound");
      }
  }

  class Dog extends Animal {
      @Override
      public void sound() {
          System.out.println("Dog barks");
      }
  }

  public class InheritanceAndPolymorphism {
      public static void main(String[] args) {
          Animal myDog = new Dog();
          myDog.sound(); // Polymorphism
      }
  }
  ```

#### **Day 9: Abstraction & Interfaces**
- **Topics:**
  - Abstract classes and methods.
  - Interfaces.
- **Example Code:**
  ```java
  interface Animal {
      void sound();
  }

  class Dog implements Animal {
      @Override
      public void sound() {
          System.out.println("Dog barks");
      }
  }

  public class AbstractionAndInterfaces {
      public static void main(String[] args) {
          Animal myDog = new Dog();
          myDog.sound();
      }
  }
  ```

#### **Day 10: Exception Handling**
- **Topics:**
  - Try-catch blocks.
  - Throwing exceptions.
  - Custom exceptions.
- **Example Code:**
  ```java
  public class ExceptionHandling {
      public static void main(String[] args) {
          try {
              int result = divide(10, 0);
              System.out.println("Result: " + result);
          } catch (ArithmeticException e) {
              System.out.println("Error: " + e.getMessage());
          }
      }

      public static int divide(int a, int b) {
          return a / b;
      }
  }
  ```

#### **Day 11: Collections Framework**
- **Topics:**
  - List, Set, and Map interfaces.
  - ArrayList, HashSet, HashMap implementations.
- **Example Code:**
  ```java
  import java.util.ArrayList;
  import java.util.HashSet;
  import java.util.HashMap;

  public class CollectionsFramework {
      public static void main(String[] args) {
          // List Example
          ArrayList<String> list = new ArrayList<>();
          list.add("Java");
          list.add("Python");
          System.out.println("List: " + list);

          // Set Example
          HashSet<String> set = new HashSet<>();
          set.add("Java");
          set.add("Java"); // Duplicate won't be added
          System.out.println("Set: " + set);

          // Map Example
          HashMap<String, Integer> map = new HashMap<>();
          map.put("Java", 1);
          map.put("Python", 2);
          System.out.println("Map: " + map);
      }
  }
  ```

#### **Day 12: File Handling**
- **Topics:**
  - Reading and writing files.
  - File handling using `FileReader` and `FileWriter`.
- **Example Code:**
  ```java
  import java.io.FileWriter;
  import java.io.FileReader;
  import java.io.IOException;

  public class FileHandling {
      public static void main(String[] args) {
          try {
              // Writing to a file
              FileWriter writer = new FileWriter("example.txt");
              writer.write("Hello, File Handling!");
              writer.close();

              // Reading from a file
              FileReader reader = new FileReader("example.txt");
              int character;
              while ((character = reader.read()) != -1) {
                  System.out.print((char) character);
              }
              reader.close();
          } catch (IOException e) {
              System.out.println("Error: " + e.getMessage());
          }
      }
  }
  ```

#### **Day 13: Multithreading**
- **Topics:**
  - Creating threads.
  - Synchronization.
  - Thread lifecycle.
- **Example Code:**
  ```java
  class MyThread extends Thread {
      public void run() {
          for (int i = 1; i <= 5; i++) {
              System.out.println(i + " " + Thread.currentThread().getName());
              try {
                  Thread.sleep(500);
              } catch (InterruptedException e) {
                  e.printStackTrace();
              }
          }
      }
  }

  public class Multithreading {
      public static void main(String[] args) {
          MyThread thread1 = new MyThread();
          MyThread thread2 = new MyThread();

          thread1.start();
          thread2.start();
      }
  }
  ```

#### **Day 14: Final Project**
- **Topics:**
  - Build a small console-based project that integrates the concepts learned throughout the course.

