# Nested Interface

Anything that possess the repetation of same thing is entitled as nested. So, we can define nested interface as an interface that is declared within another interface or class. They are also known as *inner interface*.

The nested interfaces are used to group related interfaces so that they can be easy to maintain. The nested interface must be referred by the outer interface or class. It can't be accessed directly.

Rules:
+ Nested interface must be *public* if it is declared inside the interface but it can have any access modifier if declared within the class.
+ Nested interfaces are static by default.

---

###Example 1: Nested interface declared inside another interface

```Java
interface MyInterfaceA{  
    void display();  
    interface MyInterfaceB{  
        void myMethod();  
    }  
}  
      
class NestedInterfaceDemo1 
    implements MyInterfaceA.MyInterfaceB{  
     public void myMethod(){
         System.out.println("Nested interface method");
     }  
      
     public static void main(String args[]){  
         MyInterfaceA.MyInterfaceB obj=
                 new NestedInterfaceDemo1(); 
      obj.myMethod();  
     }  
}
```

---

Example 2: Nested interface declared inside a class

```Java
class MyClass{  
    interface MyInterfaceB{  
        void myMethod();  
    }
}  
    
class NestedInterfaceDemo2 implements MyClass.MyInterfaceB{  
     public void myMethod(){
         System.out.println("Nested interface method");
     }  
    
     public static void main(String args[]){  
        MyClass.MyInterfaceB obj=
               new NestedInterfaceDemo2();  
        obj.myMethod();  
     }  
}
```

---