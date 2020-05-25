https://www.journaldev.com/7153/core-java-tutorial    

## win10 installation   
Go to System Properties (Right Click on My Computer and select Properties) > Advanced > Environment Variables.    

In the popup window, System variables section, click on New button and add a variable with the following details:   

Name: JAVA_HOME   

Value: C:\Program Files\Java\jdk1.6.0_25    

After this, you need to edit the Path variable already present there. Just select the Path variable and click on Edit button. 
In the popup window value section, go to the end and add the following ;C:\Program Files\Java\jdk1.6.0_25\bin 
(The colon is used as a delimiter, so don’t miss that!)   

## check version    
```
java -version
```

## compile and run    
```

$javac JavaHelloWorldProgram.java

$java JavaHelloWorldProgram
Hello World

```
If you are using Java 11 or higher, then you can simply execute java JavaHelloWorldProgram.
java and it will compile and execute the program for you. No need to explicitly compile and then run the java program.    

## Java Super Constructor   
```

package com.journaldev.constructor;

public class Student extends Person {

	private String name;

	public Student() {
		System.out.println("Student Created");
	}

	public Student(int i, String n) {
		super(i); // super class constructor called
		this.name = n;
		System.out.println("Student Created with name = " + n);
	}

}

```

Note that super constructor call should be the first statement in the child class constructor. 
Also when instantiating child class constructor, java first initializes the super class and then child class. 
So if the super class constructor is not explicitly called then default or no-args constructor is called by java runtime.   

## Java Copy Constructor    
```

package com.journaldev.constructor;

import java.util.ArrayList;
import java.util.List;

public class Fruits {

	private List<String> fruitsList;

	public List<String> getFruitsList() {
		return fruitsList;
	}

	public void setFruitsList(List<String> fruitsList) {
		this.fruitsList = fruitsList;
	}

	public Fruits(List<String> fl) {
		this.fruitsList = fl;
	}
	
	public Fruits(Fruits fr) {
		List<String> fl = new ArrayList<>();
		for (String f : fr.getFruitsList()) {
			fl.add(f);
		}
		this.fruitsList = fl;
	}
}

```

## Access Modifiers   

Java Access Modifiers with Class Member   
We can have all the four access modifiers for class member variables and methods. 
However, member access modifier rules get applied after the class level access rules.     
```
public - anywhere
private - only inside the same class
protected - only to the classes in the same package and to the subclasses. 
default - in the same package only
```

## Java static block		
Java static block is the group of statements that gets executed when the class is loaded into memory 
by Java ClassLoader.		

Static block is used to initialize the static variables of the class. 
Mostly it’s used to create static resources when the class is loaded.		

## Java Static Class		
We can use static keyword with nested classes. static keyword can’t be used with top-level classes.		

A static nested class is same as any other top-level class and is nested for only packaging convenience.	

## OOPS Concepts		
```
Abstraction - Abstraction is the concept of hiding the internal details and describing things in simple terms. 
For example, a method that adds two integers. 

Encapsulation - Access modifier

Polymorphism:
compile time - method overloading
runtime - method overriding

Inheritance - Inheritance is the mechanism of code reuse. The object that is getting inherited is called the superclass 
and the object that inherits the superclass is called a subclass.

Composition - When the contained object in “HAS-A” relationship can’t exist on its own, 
then it’s a case of composition. 


```

## static nested class		
```
OuterClass.StaticNestedClass nestedObject =
     new OuterClass.StaticNestedClass();
```

## java inner class	
```

OuterClass outerObject = new OuterClass();
OuterClass.InnerClass innerObject = outerObject.new InnerClass();

```

## Java Primitive Data Types	
<table class="tg"><tbody><tr><th class="tg-two">Type</th><th class="tg-two">Size</th><th class="tg-two">Range</th><th class="tg-two">Default Value</th><th class="tg-two">Examples</th></tr><tr><td class="tg-one">boolean</td><td class="tg-one">1 bit</td><td class="tg-one">NA</td><td class="tg-one">false</td><td class="tg-one">boolean bool = true;</td></tr><tr><td class="tg-two">char</td><td class="tg-two">16 bits</td><td class="tg-two">Unicode Characters</td><td class="tg-two">‘\u0000’ or 0, which<br>is nothing but a <br>white space</td><td class="tg-two">char c = ‘A’;<br>char c = ‘\u0041’;<br>char c = 65;<br>char c = ‘\t’;</td></tr><tr><td class="tg-one">byte</td><td class="tg-one">8 bits</td><td class="tg-one">[-128,127] or<br>[-2^7 to 2^7-1]</td><td class="tg-one">0</td><td class="tg-one">byte b = 10;<br>byte b = 0b010;</td></tr><tr><td class="tg-two">short</td><td class="tg-two">16 bits</td><td class="tg-two">[-32768,32767]</td><td class="tg-two">0</td><td class="tg-two">short s = 32;<br>short s = ‘A’;</td></tr><tr><td class="tg-one">int</td><td class="tg-one">32 bits</td><td class="tg-one">[-2147483648,2147483647]</td><td class="tg-one">0</td><td class="tg-one">int i = 10;<br>int i = ‘A’;</td></tr><tr><td class="tg-two">long</td><td class="tg-two">64 bits</td><td class="tg-two">[-2^63,2^63-1]</td><td class="tg-two">0</td><td class="tg-two">long l = 3200L;<br>long l = 3200;</td></tr><tr><td class="tg-one">float</td><td class="tg-one">32 bits</td><td class="tg-one">[-3.4E38, 3.4E38]</td><td class="tg-one">0.0f</td><td class="tg-one">float f = (float) 12.34;<br>float f = 12.34f;</td></tr><tr><td class="tg-two">double</td><td class="tg-two">64 bits</td><td class="tg-two">[-1.7E308, 1.7E308]</td><td class="tg-two">0.0</td><td class="tg-two">double d = 12.34;</td></tr></tbody></table>

## Java Ternary Operator	
```
result = testStatement ? value1 : value2;
```

## interface	
```
By default any attribute of interface is public, static and final.

By default interface methods are implicitly abstract and public.

public interface Shape extends Cloneable{}.

implements keyword is used by classes to implement an interface.

java class can implements multiple interfaces, it’s better to use interfaces 
as super class in most of the cases.

java8:


```

Are static methods inherited in Java?	
https://stackoverflow.com/questions/10291949/are-static-methods-inherited-in-java	

## Java String substring	
1. substring(int beginIndex): This method returns a new string that is a substring of this string. The substring begins with the character at the specified index and extends to the end of this string.	
2. substring(int beginIndex, int endIndex): The substring begins at the specified beginIndex and extends to the character at index endIndex – 1. Thus the length of the substring is (endIndex – beginIndex).		

## String to char Java	
1. char[] toCharArray(): This method converts string to character array. The char array size is same as the length of the string.	
2. char charAt(int index): This method returns character at specific index of string. This method throws StringIndexOutOfBoundsException if the index argument value is negative or greater than the length of the string.	

## Java ArrayList of Array	
```

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class JavaArrayListOfStringArray {

	public static void main(String[] args) {
		// List of String arrays
		List<String[]> list = new ArrayList<String[]>();
		
		String[] arr1 = { "a", "b", "c" };
		String[] arr2 = { "1", "2", "3", "4" };
		list.add(arr1);
		list.add(arr2);
		// printing list of String arrays in the ArrayList
		for (String[] strArr : list) {
			System.out.println(Arrays.toString(strArr));
		}
	}

}

```

## Array of ArrayList in Java
```
ArrayList<Integer>[] al = new ArrayList[n];
ArrayList<Individual>[] group = (ArrayList<Individual>[])new ArrayList[4];
```

## How java varargs work?	
```

//method with variable arguments
public static int sum(int i, int...js ){
    int sum = i;
    for(int x : js){
        sum+=x;
    }
    return sum;
}

//method with same implementation as sum with array as argument
public static int sumArray(int i, int[] js ){
    int sum = i;
    for(int x : js){
        sum+=x;
    }
    return sum;
}

```

## ArrayList to Array in Java	
strArr = strList.toArray(new String[0]);	

## Java Array to List	
1. Arrays.asList(T… a): This is the simplest way to convert Array to ArrayList in java but this method returns the underlying representation of the array in the form of ArrayList. The returned ArrayList is fixed-sized and any attempt to modify that will result in UnsupportedOperationException at runtime. Also, any change in the array will change the elements in ArrayList also.	
2. Collections.addAll(ArrayList<T> strList, T[] strArr): This is the best way to convert array to ArrayList because the array data is copied to the list and both are independent object. Once the array is copied, you can modify both the objects independently. Collections is a very useful class in Java Collections Framework that provides a lot of utility methods.	

## Java List sort	
Collections.sort(ints);		

## Comparable		
```

class Person implements Comparable<Person> {
    int id;
    String name;

    public Person(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public int compareTo(Person p) {
        return this.name.compareTo(p.name);
    }

    @Override
    public String toString() {
        return this.name;
    }
}

```

## Comparator		
```

package com.journaldev.sort;

import java.util.Comparator;

public class EmployeeComparatorByIdAndName implements Comparator<Employee> {

    @Override
    public int compare(Employee o1, Employee o2) {
        int flag = o1.getId() - o2.getId();
        if(flag==0) flag = o1.getName().compareTo(o2.getName());
        return flag;
    }

}

```

## Java TreeMap Example		
```

package com.journaldev.java;

import java.util.Comparator;
import java.util.Map;
import java.util.TreeMap;

public class JavaTreeMapExample {

	public static void main(String[] args) {
		
		Map<Integer,String> map = new TreeMap<>();
		
		map.put(10, "10");
		map.put(1, "1");
		map.put(5, "5");
		
		System.out.println(map);
		
		map = new TreeMap<>(new Comparator<Integer>() {

			@Override
			public int compare(Integer x, Integer y) {
				return (x > y) ? -1 : ((x == y) ? 0 : 1);
			}
			
		});
		map.put(10, "10");
		map.put(1, "1");
		map.put(5, "5");
		System.out.println(map);

	}

}

```


