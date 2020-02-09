# Annonymous Array

An array is a data structure/container/objectthat stores a fixed-size sequential collection of elements of the same type. The size/length of the array is determined at the time of creation. The position of the elements in the array is called as index or subscript. The first element of the array is stored at the index 0 and, the second element is at the index 1 and so on. Each element in an array is accessed using an expression which contains the name of the array followed by the index of the required element in square brackets.

An array to be recognised as Anonymous Array in Java should have the following features: 

+ The array should have no name.
+ The array is created using the **new** keyword and pair of curly braces.
+ The array is created and initialized at the same time.
+ The array can be passed as an argument to a method.
+ The array can be of any dimension.


---

Example:

```Java
public class Anonymous_array_and_methods {
	
	public static int getSum(int[] Arr){
		int sum=0;
		for(int i=0 ; i<Arr.length ; ++i){
			sum = sum + Arr[i];
		}
		return sum;
	}

	public static void main(String[] args){
		System.out.println("Array sum = " + total);
	}
}
```

---