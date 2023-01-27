## Regular function - Arrow function difference.
  ### - This value
    This value inside a regular function is dynamic and depends on the invocation.But this inside 
    the arrow function is bound lexically and equals to this of the outer function.
  ### - Constructors
    The regular function can easily construct objects.
    Arrow function cannot be used as a constructor.If you try to invoke an arrow function prefixed 
    with new keyword, JavaScrip throws an error.
  ### - Arguments object
    Arguments object inside the regular functions contains the list of arguments. The arrow function, on the
    opposite, doesn't define arguments (but you can easily access the arrow function arguments using a rest 
    parameter ...args).
  ### - Implicit return
    If the arrow function has one expression, then the expression is returned implicitly, even without using the 
    return keyword.
  ### - Methods
    When you need to provide a method as a callback, regular functions need to bind this value and arrow functions 
    don't need to bind

## Example of the difference normal function - arrow function
  ### - Contructor with normal funtion and arrow function 
  #### + Regular functions
  ```js 
  function myProfile(name) {
    this.name = name
  }
  const profile = new myProfile('Test Name');
  ```
  #### + Regular functions
  ```js 
  function myProfile = (name) => {
    this.name = name
  }
  const profile = new myProfile('Test Name');
  // show error myProfile is not a constructor
  ```
