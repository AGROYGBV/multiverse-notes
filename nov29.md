> Written with [StackEdit](https://stackedit.io/).
> # Asynchronous JavaScript
**synchronous:** programming model means that operations can happen sequentially, or one at a time, otherwise the next operation is blocked until the previously called task is completed. JavaScript is a single-threaded, synchronous language. 

**asynchronous:** is a non-blocking model that means operations can happen independently from the main program flow.  JavaScript mimics async by using the event loop. 
example:

    function testFunc(){
	    console.log('A');
	    setTimeout(
		    function display(){
			    console.log('B')
			    },
			    0);
		 console.log('C');
    }
    
    testFunc();

**call stack:** dynamic data structure in runtime of JavaScript that organizes the execution of code. Organized by Last-In-Last-Out (LIFO). Operations are "pushed in" in order of call and "pop off" the stack when completed.

**stack trace:** when code errors, you often get a 'stack trace' as part of the error message. It shows the order of our function calls in the call stack. 

**stack overflow:** call stack runs out of space. ex. infinite loop

**error handling:** JavaScript provides mechanisms to program how to handle errors when they occur. 

 - The  `try`  statement lets you test a block of code for errors.
 - The  `catch`  statement lets you handle the error.
 - The  `throw`  statement lets you create custom errors.
 - The  `finally`  statement lets you execute code, after try and catch, regardless of the result.(https://www.w3schools.com/js/js_errors.asp)

example:

    function multiply (a, b) {										
    	throw new Error ("can't mulitply strings");
    	}
## Promises
The promise object represents the eventual completion (or failure) of an async operation and it's resulting value.

 - if success - resolve function (.then)
 - if unsuccessful - reject function (.catch)

**fetch web api:** a call to a fetch url will make a GET request to the given url. Network requests take a long time, so the fetch function returns a promise which represents a request. 
example:

    fetch('https://url.com/api')
    .then((res) => res.json())
    .then((data) => console.log(data)
    .catch((err) => console.error(err))
    
**async:** allows us to write promise based code as if it were synchronous. Operates asynchronously via the event loop. 

**await:** await function used to wait for the promise. Can only be used within the async block. Makes the code wait.

example:

    const  fetchPokemon  =  async () => {
	    try {
		    const  rest  =  await fetch(`https://pokeapi.co/api/v2/pokemon`);
		    const  data  =  await  rest.json();
		    return  data;
		    } 
		 catch (err) {
			 console.error(err);
			 }
	}
	
	fetchPokemon().then((data) => {
		console.log(data);
		})