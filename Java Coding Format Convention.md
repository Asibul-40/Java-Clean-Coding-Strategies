# Java Clean-Coding Convention

As a developer, we need to code regularly to develop any types solutions. But there are some conventions, or we can say some sort of strategies to code, which makes other readers to read our codes comfortably and precisely. Practicing clean coding is about to recognize yourself to others as a real-life human beings rather than just a computer. 
Here I will share my knowledge about such type of practicing **Java** coding conventions.

## Structure of a Java file
- Any java file should be saved with **.java** extension, and for any class file **.class** extension is used.
```java
// Class File
Example.class

// Java File
Example.java
````
- A Java file should not have more than 2000 lines of code in total.
- Java Source file conventions:
	- Begins with comments (includes: Classname, application version info, copywrite terms & conditions).
	- All import statements about package & classes.
	```java
	// importing "ArrayList" class under "java.util" package
	import java.util.ArrayList;
	```
	- Class and Interface declarations:
	```java
	class className{ 
		// body
	}
	interface interfaceName{
		// body
	}
	```

## Convention of writing the code

By following some well defined convention, we can increase the readability of our code quite easily. 
### Indentation
- Four spaces should be considered as a unit of indentation.
- Each line should not exceed more than 80 characters.
- To break the lines:
	- Break after a comma
	```java
	// Bad practice										// Good practice
	public void fun(args1, args2						public void fun(args1, args2,
					, args3){											args3){
		// Do something											// Do something
	}													}
	```
	- Break before an operator
	```java
	// Bad Practice
	int sum = number1 + (number2 -
		 number3) * number4


	// Good practice
	int sum = number1 + (number2 - number3)
					* number4;
	```

### Comments
Comments are simply used to provide some additional information of the code. When writing some comments for any specific portion of code, we need to keep in mind one thing: We should write our code in such a way that it is easier to understand and self-descriptive rather than writing a bunch of line of description about the code in comment.
Usually in Java, comments can be two types: *Implementation comments* and *Documentation comments*. Hence Implementation comments can be of four types: *block*, *single-line*, *trailing*, *end-of-line*. 
- **Implementation Comments:**	These type of comments are used to explain the implementation details of some particular portion of code.
```java
/*
* This is a Block comment format.
*/


// This is a single line comment format.


/*  This one is trailing comment format  */


private String commentType="End-of-line";	// This type of comment exists at the end of a line.
``` 
	
- **Documentary Comments:**	These type of comments are used for providing the description of Java classes, interfaces, constructors, methods and fields.
```java
/**
This Mobile class describes that it has some properties (brandName & androidVersion) 
& behavior(capturing an image). And these description are provided inside of a 
Documentary comment section.
*/
class Mobile{
	private String brandName;
	private int androidVersion;
	public void captureImage(){
		// Implementation of this action.
	}
}
```

### Property declarations
- Each line should have only one property declaration per line.
	```java
	// Bad practice
	int age, salary;


	// Good practice
	int age;
	int salary;
	```
- In terms of using local variables, we should *declare* and *initialize* the variable only at the beginning of its use.
	```java
	public void check(){
		if(condition){
			int count;
			// Do something using this local count variable
		}
	}
	```
- For declaring a class and interface:
	```java
	class Java{
		int integerVariable;
		String stringVariable;
		boolean booleanVarible;
		
		public void Inheritance(){
			// Implementation
		}
		
		public void Encapsulation(){
			// Implementation
		}

		// Other actions
	}
	```
### Statements
- *Single Statement*: Each line should have at most one statement.
	```java
	try{
		// Some logical functioanlities
	}
	catch(Exception e){
		System.out.println("Error occured !" + e);	exit(1);		// Bad practice
	}
	```
- *Compound statements*: Any number and any type of statements are put together inside of a curly braces to form a compound statements.
	```java
	for(int i=0; i<totalSize; i++){
		// Inside every statement inside this loop forms a compound statement
		int count = 5; 
		if(count == i){			
			break;
		}else{
			count-=1;
		}
	}
	```
- *Return statements*: Different types of return statements can be:
	```java
	return;											// Returns nothing
	return mySongList.size();						// Returns the size of mySongList array. 
	return (colour="Red" ? "Yellow" : "Red");		// Returns the color based on condition 
	```
- *Conditional Statements*: Conditional statements includes: if, if-else, if-else if-else, switch
	```java
	// Only IF statement
	if(conndition){
		...
	}


	// IF-ELSE IF-ELSE
	if(condition1){
		...
	}else if(condition2){
		...
	}else{
		...
	}


	// IF-ELSE
	if(condition){
		...
	}else{
		...
	}
	```
	> **NOTE:** if statement always uses curly braces {}.
	```java
	if(condition) 
		count+=1;			// Wrong 
	```
- *Loop statements*: We have *for*, *while*, *do-while*, 
