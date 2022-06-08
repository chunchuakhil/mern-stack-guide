# this keyword inside functions.

## functions
- this keyword inside a function will point object, who is calling that function.
- this keyword inside function will not point to object, where it is defined.
- if you write functions inside object, their is no use, because this keyword inside that function is determined
at run time.
- that is why we need to bind methods to object, so that it will not loose its context,
even if we use use them outside of object.
- after binding this inside function will point to the object, where it is defined/written.
- => after binding, if you call that function out side its scope, it will still point to the binded object.

# arrow functions
- arrow functions dont have this keyword.
- if you still write this keyword inside arrow function will point to object where it is defined/written.
- arrow funcions are automatically binds to its object, where their defined/written.
no need explict binding.
- =>if you call that arrow function out side its scope, it will still point to the object where it is defined/written.
