# Inheritance in Interface

An interface contains variable and methods like a class but the methods in a interface are abstract by default unlike a class. Multiple inheritance by interface occurs if a class implements multiple interfaces or also if an interface itself extend multiple interfaces.

Example:

--------


```Java
interface animalEat {
	void eat();
}

interface animalTravel {
	void travel();
}

class Animal implements animalEat, animalTravel {
	public void eat() {
		System.out.println("Animal is eating");
	}
	public void travel() {
		System.out.println("Animal is traveling");
	}
}

public class Demo {
	public static void main(String[] args) {
		Animal a = new Animal();
		a.eat();
		a.travel();
	}
}  
```

---