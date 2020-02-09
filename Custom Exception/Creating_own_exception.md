# How to create your own Exception?

At first, lets learn about *Exception* in Java. The Exception Handling in Java is one of the powerful mechanism to handle the runtime errors such as **ClassNotFoundException**, **IOException**, **SQLException**, **RemoteException**, etc. so that normal flow of the application can be maintained.

Now, lets talk about custom Exception. JDK's exceptions are not enough in real world. So you will call JDK’s exceptions **built-in exceptions** and call our own exceptions **custom exceptions**. When you couldn’t find any relevant exceptions in the JDK, it’s time to create new ones of your own.

Custom exceptions are very much useful when we need to handle specific exceptions related to the business logic. When used properly, they can serve as a useful tool for better exception handling and logging.

---

Lets write our own Exception by following the below steps in Java.

+ Create a new class whose name should end with *Exception* like *ClassNameException*.
+ Make the class extends one of the exceptions. Generally, a custom exception class always extends directly from the *Exception* class.
+ Create a constructor with a String parameter which is the detail message of the exception. In this constructor, simply call the super constructor and pass the message.

```Java
public class StudentNotFoundException extends Exception {
 
    public StudentNotFoundException(String message) {
        super(message);
    }
}
```