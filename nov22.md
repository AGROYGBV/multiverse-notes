> Written with [StackEdit](https://stackedit.io/).

# Static Functions & Class Inheritance

## Static Functions

Static functions are called on the class itself instead of the instance of a class (object). Static functions cannot access data from objects. They are used for helper and utility functions. 
**utility function:** (Don't feel I fully understand the definition and haven't found one I like online. ToDo - ask Michael for clarification.)

    class ClassWithStaticMethod {
      static staticProperty = 'someValue';
      static staticMethod() {
        return 'static method has been called.';
      }
      static {  
        console.log("Class static initialization block called");
      }
    }
>"Note that for static methods, the **_this_** keyword references the class. You can call a static method from another static method within the same class with **_this_**." - [eechen, Static Methods in ES6, Medium](https://medium.com/@yyang0903/static-objects-static-methods-in-es6-1c026dbb8bb1)

## Class Inheritance 
Inheritance is when a class shares properties and methods of another class. The child class inherits from the parent class.

Parent Class: (key word - class, constructor)

    class  Pets {
    constructor(name, color, species) {
		this.name  =  name;
		this.color  =  color;
		this.species  =  species;
		};
	};
	
	module.exports = Pets;
	
Child class: (key words - extends, super, class, constructor)

    const  Pets  =  require("./pets");
    
    class Dog extends Pets {
	    constructor(name, color, breed) {
		    super(name, color, 'dog');
		    this.breed = breed;
		    };
	};	     

## Testing Inheritance with Jest 
test to see if new pet is an instance of dog class inherited from pet class:

    test('is an instance of a Dog', () => { 
	    const pet1 = new Dog('Spot', 'white, brown spots', 'terrier')
	    expect(spot instanceof Dog).toBeTruthy() 
    });