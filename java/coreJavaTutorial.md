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


