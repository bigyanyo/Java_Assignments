# Default Method in Interface

Default methods are implictly public like regular interface (There's no need to specify the public modifier). Unlike regular interface methods, they are declared with the default keyword at the beginning of the method signature and they provide an implementation.

Example:

```Java
public interface testInterface
{
	//regular interface methods
	default void defaultMethod()
	{
		//default method implementation
	}
}
```

Default interface methods is an efficient way to deal with issue like a program having multiple inplementation of interface where all the implementation is forced to implement otherwise break down occurs. They allows us to add new methods to an interface that are automatically available in the implementations. Thus, there is no need to modify the implementing classes. In this way, backward compatibility is neatly preserved without having to refurnish the implementers.

Code:

---


```Java
interface MyInterface{  
    
    default void newMethod(){  
        System.out.println("Newly added default method");  
    }  
   
	void existingMethod(String str);  
}  
public class Example implements MyInterface{ 
	// implementing abstract method
    public void existingMethod(String str){           
        System.out.println("String is: "+str);  
    }  
    public static void main(String[] args) {  
    	Example obj = new Example();
    	
    	//calling the default method of interface
        obj.newMethod();     
        //calling the abstract method of interface
        obj.existingMethod("Java is easy to learn"); 
  
    }  
```

---