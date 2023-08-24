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
```
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
- A complete example of a Java source file:
	```java
	/*
	*	User class
	*	version 1.0.1
	*	Copywrite terms & conditions
	*/
	
	/**
	* This User class is used to demonstrate the overall schema of a user.
	* @version 1.0.1
	* @author Ashikul Islam Abir
	*/

	class User{
		private String username;
		private String teamName;
		User(String name, String teamName){
			this.username = name;
			this.teamName = teamName;
		}
		public void work(){
			System.out.println(username + " is working for "+teamName + "team.");
		}
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
	// Bad practice
	public void fun(args1, args2
 			, args3){		
		// Do something		
	}


 	// Good practice
	public void fun(args1, args2,
 			args3){		
		// Do something		
	}											
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
- **Single Statement**: Each line should have at most one statement.
	```java
	try{
		// Some logical functioanlities
	}
	catch(Exception e){
		System.out.println("Error occured !" + e);	exit(1);		// Bad practice
	}
	```
- **Compound statements**: Any number and any type of statements are put together inside of a curly braces to form a compound statements.
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
- **Return statements**: Different types of return statements can be:
	```java
	return;						// Returns nothing
	return mySongList.size();				// Returns the size of mySongList array. 
	return (colour="Red" ? "Yellow" : "Red");		// Returns the color based on condition 
	```
- **Conditional Statements**: Conditional statements includes: if, if-else, if-else if-else, switch
	```java
	// Only IF statement
	if(conndition){
		...
	}


	// IF-ELSE IF-ELSE statement
	if(condition1){
		...
	}else if(condition2){
		...
	}else{
		...
	}


	// IF-ELSE statement
	if(condition){
		...
	}else{
		...
	}


	// SWITCH statement
	switch (condition){ 
		case 1: statement1;  
		case 2: statement2;  
		case 3: statement3; 
		default: default_statement; 	// Every switch statement should have a default case.
		break; 
	}
	```
	> **NOTE:** if statement always uses curly braces {}.
	```java
	if(condition) 
		count+=1;					// Wrong 
	```
- **Loop statements**: We have *for*, *while*, *do-while* loops in Java.
	- **for**: The structure of *for* loop:
		```java
		for(initialization; condition; increment/decrement){	// Definition
			...
		}

		for(int i=0; i<5; i++){				// Example
			// statements
		}
		``` 
	- **while**: The *while* loop only works on the basis of a specific condition.
		```java
		while(condition){					// Definition
			...
		}

		int i=5;
		while(i>0){						// Example:
			// statements
			i-=1;
		}
		```
	- **do-while:** A *do-while* loop can be defined as:
		```java
		do{							// Definition
			// statements
		}while(condition);


		int i=5;
		do{							// Example
			// statements
			i-=1;
		}while(i>0)
		```
- **try-catch statements:** A try-catch statement has the following definition:
	```java
	try{
		// statements;
	}catch(ExceptionClass e){
		// statements
	}
	```

### Naming Conventions
- We should always follow the *camelCase* naming convention for any variable or class property.
- For naming any class or interface, we should always start with the capital letter of the word. If it requires to name a class/interface as a combined word of two or multiple words, then it is recommended to use the first character as capital for that joined class/interface name.
	```java
	class User{
		...
	}

	interface AuthenticationAndAuthorizationManager{
		...
	}
	```
	> **NOTE:** It is preferred to choose *noun* words for any classname.
- We should always choose such type of names that can be self-explanatory.
	```java
	int x;			// Doesn't make any sense for the purpose of using this varible.

	int age;		// It indicates the age of a person.
	```
- The method name should be *verbs*, which indicates the functional description.
	```java
	void startEngine();
	booelan authenticate(User user);
	``` 
- To define any *constant* variable, we should use the uppercase with words separated by underscores ("_") . 
	```java
	int MAX_SIZE = 10;
	String MONGO_URL = "https://mongo_connection_url";
	``` 
- Use the pronounceable words instead of using any type of random name.
	```java
	List<User> sdafekfd = new ArrayList <User> ();				// Bad practice

	List<User> users = new ArrayList <User> (); 				// Good practice.
	```
- To change or modify the name, we should always use searchable names rather than using single letter names for any variable or constants.
	```java
	if(totalUser>10){					`		// Bad practice	
		return "User limit exceeded !";
	}

	int MAX_USER_CAPACITY = 10;
	if(totalUser > MAX_USER_CAPACITY){					// Good practice
		return "User limit exceeded!";
	}
	```
### Convention for writing the functions
We have already discussed about the naming convention for writing a function/method in Java. Now let's discuss about some other practicing conventions related to these methods:
- A method should always be small and should not exceed more than 20 lines.
- Method should be responsible for doing only one task. 
- One Method can have multiple encapsulated methods.
	```java
	public double findTriangleArea(int height, int base){
		if(isValid(height) && isValid(base)){
			return .5 * height * base;
		}
		else return -1;
	}
	boolean isValid(int params){
		return ((params>=0) ? true : false); 
	}
	```
- Methods should have two or less than two arguments because "The fewer the better". 
- We can keep in mind that our method should be kept free from having *side effects*. Basically side effects may be responsible for changing the passed parameters, in case of passing by reference, or maybe changing a global variable.


### Some useful programming practices
- To initialize any class property, we should always declare them as **private** so that we can keep them protective and secure from outside of that class.
- If we have some **static** members in our class, we should invoke them directly by the classname without creating any object of that class.
	```java
	class NSL{
		private static companyName = "NSL";
	}
	class Main{
		public static void main(String args[]){
			System.out.println(NSL.companyName);
		}
	}
	```  
- *Variable Assignments:*
	-  We should avoid using several variable assignments in a single statement.
		```java
		int firstInitialPointerIndex = secondInitialPointerIndex = 0;
		```
	- Always avoid embedded assignments. We can break them into several single statement.
		```java
		Z = (X = a+b) + Y;				// bad practice


		X = a+b;
		Z = X + Y;					// Good practice 
		```
- In terms of multiple conditional checking statements, we should always use first parenthesis to separate each checking statemnt.
	```java
		if(a==b && b==c) { ... }			// Bad practice


		if((a==b) && (b==c)) { ... }			// Good practice
		```
- To keep our code more readable and understandable, we should use the proper intention that makes the code more structured & more organized.
	```java
		if(booleanCondition){ return true; }		// Avoid these type of format.
		else return false;


		return booleanCondition;			// Be Straight-forward.
		``` 
- If the method's outcome only depends on binary conditional checking, we can use ternary operator instead of *if-else* statements.
	```java
		if(age>=18) {
			return "has NID card."
		}else {
			return "No NID";
		}

		// More simple & Smart approach
		return (age>=18) ? "has NID card" : "No NID"
		``` 
- We should never leave our codes in comment section. Because if the variable/method name changes, it gets irrelevant & useless.
- We should avoid using the duplicate codes in multiple place. If it needs to change the same thing, then we have to change in those multiple duplicate sections. 
