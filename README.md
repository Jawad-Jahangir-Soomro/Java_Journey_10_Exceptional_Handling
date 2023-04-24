# Java Journey, 10: Exception Handling.

This repository covers the topic of exception handling in Java. Exceptions are a way to handle runtime errors in a program, and they can occur due to a variety of reasons, such as invalid input, network errors, or hardware failure. In this repository, you will learn how to handle exceptions using try-catch blocks, throw statements, and exception subclasses. Proper exception handling can improve the reliability and robustness of your programs.

## Learn about exceptions and errors in Java.

In Java, an exception is a problem that occurs during the execution of a program that disrupts its normal flow. This could be due to various reasons such as invalid input, lack of resources, etc. When an exception occurs, an object of the corresponding exception class is thrown.

Errors, on the other hand, are caused due to issues outside of the program's control, such as hardware failure, lack of memory, etc.

It is important to handle these exceptions and errors in Java to prevent program crashes and ensure graceful error handling. Exception handling in Java involves identifying and handling exceptions through try-catch blocks, finally block, and throwing exceptions using the throw keyword. Understanding exception hierarchy and creating custom exceptions is also an important part of exception handling in Java.

## Study the difference between exceptions and errors.

In Java, both exceptions and errors are used to represent exceptional conditions that occur during the execution of a program. However, there are some differences between the two.

Exceptions are used to indicate that a problem occurred during the execution of a method. They are typically recoverable and can be handled by the program. For example, if a program tries to open a file that doesn't exist, an exception will be thrown, and the program can handle the exception by displaying an error message to the user.

Errors, on the other hand, indicate serious problems that are usually not recoverable by the program. They are typically caused by problems with the environment in which the program is running, such as running out of memory or a hardware failure. Examples of errors include StackOverflowError, OutOfMemoryError, and VirtualMachineError.

In general, it's recommended to handle exceptions in the program, while errors should be left for the JVM to handle.

## Get an understanding of the different types of exceptions (checked and unchecked).

In Java, exceptions are used to handle runtime errors and unexpected situations that may occur during the execution of a program. Java has two types of exceptions: checked and unchecked.

Checked exceptions are checked at compile-time and must be handled explicitly using try-catch blocks or declared in the method signature with the throws keyword. Examples of checked exceptions are IOException, ClassNotFoundException, and SQLException.

Unchecked exceptions, also known as runtime exceptions, occur during the execution of the program and are not checked at compile-time. They do not need to be explicitly handled, but it is good practice to do so. Examples of unchecked exceptions are NullPointerException, ArrayIndexOutOfBoundsException, and IllegalArgumentException.

By understanding the difference between checked and unchecked exceptions, developers can write more robust and reliable code that handles errors effectively.

## Study the use of keywords for exception handling in Java.

In Java, exception handling is done using the try-catch-finally blocks. The try block contains the code that is being monitored for exceptions, while the catch block is used to handle the exceptions. The finally block is used to execute the code that is always to be executed, whether an exception occurs or not.

Java provides several keywords for exception handling, including:

1- try: This block is used to enclose the code that may generate an exception.

2- catch: This block is used to catch the exception and handle it accordingly.

3- finally: This block is used to execute the code that is always to be executed, regardless of whether an exception occurs or not.

4- throw: This keyword is used to explicitly throw an exception from a method.

5- throws: This keyword is used in a method signature to declare the types of exceptions that may be thrown by the method.

For example:

```bash
public void divide(int a, int b) throws ArithmeticException {
   try {
      int result = a/b;
      System.out.println("Result: " + result);
   } catch (ArithmeticException e) {
      System.out.println("Cannot divide by zero");
   } finally {
      System.out.println("Execution completed");
   }
}
```

In the above example, the divide() method takes two integers as input and tries to divide them. If the second integer is zero, an ArithmeticException is thrown, which is caught in the catch block and an appropriate message is displayed. The finally block is used to print a message indicating the completion of the execution, regardless of whether an exception occurs or not.

## Learn about the syntax and methods for handling exceptions.

Exception handling is a mechanism used in Java to handle errors and exceptional conditions that can occur during the program's execution. It helps to prevent the program from crashing and provides a way to gracefully handle errors.

Java provides a syntax for handling exceptions using the try-catch block. The try block contains the code that can generate an exception, and the catch block handles the exception. If an exception occurs in the try block, the execution is transferred to the catch block, which handles the exception.

Here's an example:

```bash
try {
    int num1 = 10;
    int num2 = 0;
    int result = num1 / num2;
}
catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero.");
}
```

In this example, we are trying to divide the variable num1 by num2, which is zero. This will result in an ArithmeticException, which is caught in the catch block. The catch block then prints a message saying that we cannot divide by zero.

Java provides several methods for handling exceptions. The getMessage() method returns the error message associated with the exception. The printStackTrace() method prints the stack trace of the exception. The toString() method returns a string representation of the exception.

Here's an example of using these methods:

```bash
try {
    // code that can generate an exception
}
catch (Exception e) {
    System.out.println(e.getMessage()); // prints the error message
    e.printStackTrace(); // prints the stack trace
    System.out.println(e.toString()); // prints a string representation of the exception
}
```

In this example, we are catching any exception that occurs in the try block. We are then using the getMessage(), printStackTrace(), and toString() methods to handle the exception.

In addition to the try-catch block, Java also provides the finally block, which is used to execute code regardless of whether an exception occurs or not. The code in the finally block is executed after the try-catch block, even if an exception is thrown.

Here's an example:

```bash
try {
    // code that can generate an exception
}
catch (Exception e) {
    // handle the exception
}
finally {
    // code to be executed regardless of whether an exception occurs or not
}
```
In this example, the code in the finally block will always be executed, regardless of whether an exception occurs in the try block or not. This is useful for releasing resources, closing files, or cleaning up any state that needs to be cleaned up regardless of whether an exception occurs or not.

## Get an overview of common exceptions

In Java, an exception is an object that represents an unusual situation or error that occurs during the execution of a program. Some common exceptions that can occur in Java include:

1- NullPointerException: This exception is thrown when a program tries to access an object or variable that is null.
Example:

```bash
String str = null;
if(str.equals("hello")) {
    // will throw NullPointerException
}
```

2- ArrayIndexOutOfBoundsException: This exception is thrown when a program tries to access an array element outside of the valid range.
Example:

```bash
int[] arr = new int[5];
arr[10] = 3;  // will throw ArrayIndexOutOfBoundsException
```

3- ArithmeticException: This exception is thrown when an arithmetic operation cannot be completed due to an error, such as division by zero.
Example:

```bash
int a = 5, b = 0;
int c = a / b;  // will throw ArithmeticException
```

4- FileNotFoundException: This exception is thrown when a file cannot be found or opened.
Example:

```bash
try {
    File file = new File("myfile.txt");
    Scanner scanner = new Scanner(file);
} catch (FileNotFoundException e) {
    System.out.println("File not found!");
}
```

5- ClassCastException: This exception is thrown when a program tries to cast an object to a class that it is not compatible with.
Example:

```bash
Object obj = "hello";
Integer num = (Integer) obj;  // will throw ClassCastException
```


Exception Handling is a crucial aspect of Java programming that ensures programs can handle and recover from errors and unexpected events. By using the keywords and syntax provided in Java, programmers can effectively handle exceptions and prevent their programs from crashing. It is important to understand the different types of exceptions, their causes, and how to handle them properly. With this knowledge, developers can write more robust and reliable software that can gracefully handle unexpected situations.
