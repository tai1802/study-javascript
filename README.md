# Regular function - Arrow function difference.
  ## - This value
    This value inside a regular function is dynamic and depends on the invocation.But this inside 
    the arrow function is bound lexically and equals to this of the outer function.
  ## - Constructors
    The regular function can easily construct objects.
    Arrow function cannot be used as a constructor.If you try to invoke an arrow function prefixed 
    with new keyword, JavaScrip throws an error.
  ## - Arguments object
    Arguments object inside the regular functions contains the list of arguments. The arrow function, on the
    opposite, doesn't define arguments (but you can easily access the arrow function arguments using a rest 
    parameter ...args).
  ## - Implicit return
    If the arrow function has one expression, then the expression is returned implicitly, even without using 
    the return keyword.
  ## - Methods
    When you need to provide a method as a callback, regular functions need to bind this value and arrow functions
    don't need to bind

# Example of the difference normal function - arrow function
  ## - Contructor with normal funtion and arrow function 
  ### + Regular functions
  ```js 
  function myProfile(name) {
    this.name = name
  }
  const profile = new myProfile('Test Name');
  ```
  ### + Regular functions
  ```js 
  function myProfile = (name) => {
    this.name = name
  }
  const profile = new myProfile('Test Name');
  // show error myProfile is not a constructor
  ```
  ## - Context of this 
  ```js 
  const person = {
    name: "A",
    getProfile: function () {
      console.log(this);
    },
    getProfileArrowFunction: () => {
      console.log(this)
    }
  }
  person.getProfile() // the context of this is the person object
  person.getProfileArrowFunction() // the context of this is the window object
  ```
# The differences between call, apply, and bind
  ## + call
    binds the this value, invokes the function, and allows you to pass a list of arguments.
  ## + apply
    binds the this value, invokes the function, and allows you to pass arguments as an array.
  ## + bind
    binds the this value, returns a new function, and allows you to pass in a list of arguments.
# When use bind, apply, call
  ## + bind
    Bind is used to specify the this parameter for a function
  
  ```html
    <button id="button">Click Button</button>
  ```
  ```js
    const person = {
      firstName: 'firstName',
      lastName: 'lastName',
      showName: function() {
        console.log(this.firstName + ' ' + this.lastName);
      }
    };

    // context this is button
    document.getElementById('button').addEventListener('click', person.showName);
    // result => undefined undefined

    // context this is person
    document.getElementById('button').addEventListener('click', person.showName.bind(person));
    // result => firstName lastName
  ```
  ## + call and apply
    Call and Apply is used to specify the this parameter for a function and pass the parameter.
  ``` html
    <button id="button1">Click Button 1</button>
    <button id="button2">Click Button 2</button>
  ```
  ```js
    const person = {
      showName: function (firstName, lastName) {
        console.log(firstName + ' ' + lastName);
      }
    };

  // call
  document.getElementById('button1').addEventListener('click', function () {
    person.showName.call(person, 'A', 'B')
  });

  // apply
  document.getElementById('button2').addEventListener('click', function () {
    person.showName.apply(person, ['A', 'B'])
  });
  ```
