# Java Design Conventions

## General

### Tabs

Use real tabs that equal 4 spaces

### Conventions

Use typically trailing braces everywhere (if, else, functions, class definitions, etc)

	if( condition ) {
		//something
	}

The else statement starts on the same line as the closing brace and includes the next opening brace

	if( condition ) {
		//something
	} else {
		//something else
	}

Pad parenthesized expressions and assignment operators ("=" sign) with spaces

	if( condition ) {
		//something
	}
	
	x = ( Math.cos( this.theta * 2.0f ) );
	
Refer to any internal methods of fields of a class with `this`

	this.pos = this.calculatePosition();

Explicitly use floating point values unless there is a need to double precision, and format values with a trailing zero, if needed

	float f = 1.0f;
	float f2 = 90.5f;
	float f3 = 0.0f;
	
Variable/field names are camel case

	public float thisIsAField;

Constant (final) fields are uppercase with underscores

	public final int THIS_FIELD_IS_CONSTANT = 1;

## Functions

### Naming conventions

Function names should be in camel case

	public void ThisIsAFunction();
	
Function names should try to be named with the convention: verbContextNoun(), such as

	public int getEventValue();
	public Vector3f calculateUnitVector();
	public void startStateMainMenu();

Attempt to use public getters and setters rather than publicly exposing a field

	private int value;
	public int getValue() {
		return this.value;
	}
	public void setValue( int value ) {
		this.value = value;
	}

## Classes

### Naming conventions

Class names should be in capital case

	public class ThisIsAClass {
	}

Class names should begin with the name of the highest level class's name in the class hierarchy

	public abstract Entity {}
	public abstract EntityMovable extends Entity {}
	public class EntityPlayer extends EntityMovable {}
	public class EntityEnemy extends EntityMovable {}

Interfaces should be named using adjectives ending in "-able"

	public interface Comparable {}
	public interface Movable {}

### Design

Whenever possible, factor out common code between multiple classes into a common abstract class, named after the function of the common code.

## Comments

The header of a function (when documenting) will be to the JavaDoc spec ([Here is a good reference](http://students.cs.byu.edu/~cs240ta/fall2012/tutorials/javadoctutorial.html))

Inline comments shall not be able to be derived from function/variable names and the operations on them.

Code should be rewritten in such a way to minimize the need for inline comments.
