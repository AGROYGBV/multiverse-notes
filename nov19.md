> Written with [StackEdit](https://stackedit.io/).
> # Object-Oriented Development

> ## Classes
 Classes are templates that define and build the shape of an object.  Coding one template follows DRY programming so that you're not coding the same properties over and over for different objects.

    class Example {
    			constructor(parameter) {
    				this.parameter = parameter,
    			};
    				method() {
    					console.log('This is a function and ${this.parameter} is a key 	
    					for a value of state.')	
    				};	
     };

> ## Objects

Objects inherits from a class, methods(behaviors), and properties (characteristics) and associates them with data to form key: value pairs. Key for name of the property and value for the object's data for that property. When you create a object, you're creating an instance of the class. 
 >"A property of an object can be explained as a variable that is attached to the object. Object properties are basically the same as ordinary JavaScript variables, except for the attachment to objects." - [Mozilla Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#objects_and_properties)
 >

To create an object from a constructed class, use the new keyword on the Class name and fill with parameter values.

    const example1 = new Example("value");

There are two ways to access the properties of objects - dot notation and bracket notation. Bracket notation is especially used if the property has a space, hyphen, or starts with a number. 

 **dot notation:**  `objectName.propertName` || `objectName.methodName(parameter)`
 **bracket notation:** `objectName['property-name'](parameter)`

> # Test-Driven Development
**Why we test before and during creating code?**
-   Ensures code is working
-   Ensure code continues to work after updates
-   Document what code actually does 
-   Adds precision/certainty to predicting outputs

In testing we use spies and stubs to see what happens with our code when we input "dummy" values. 
**spies:** Simply functions that record info about when/how they were called.
**stubs:** Spies that return a “canned” value.

We practiced TDD using **Jest** to test on our newly made, modular, classes and objects. "npm i jest" to install in directory of test files
Example formatting:

    `const  Airport  =  require("./airport")
    
    describe('testing x class', () => {
	    test('class has a property', () => {
		    const testClass = new Class('stub')
		    expect(testClass.property).toBe('stub')
	    });
	});

# To-Do
Create bear class with species objects (there are 8 species of bears) alongside jest tests.
    
