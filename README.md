Returning a Value from a Method
A method returns to the code that invoked it when it

completes all the statements in the method,
reaches a return statement, or
throws an exception (covered later),
whichever occurs first.

You declare a method's return type in its method declaration. Within the body of the method, you use the return statement to return the value.

Any method declared void doesn't return a value. It does not need to contain a return statement, but it may do so. In such a case, a return statement can be used to branch out of a control flow block and exit the method and is simply used like this:

return;
If you try to return a value from a method that is declared void, you will get a compiler error.

Any method that is not declared void must contain a return statement with a corresponding return value, like this:

return returnValue;
The data type of the return value must match the method's declared return type; you can't return an integer value from a method declared to return a boolean.

The getArea() method in the Rectangle Rectangle class that was discussed in the sections on objects returns an integer:

    // a method for computing the area of the rectangle
    public int getArea() {
        return width * height;
    }
This method returns the integer that the expression width*height evaluates to.

The getArea method returns a primitive type. A method can also return a reference type. For example, in a program to manipulate Bicycle objects, we might have a method like this:

public Bicycle seeWhosFastest(Bicycle myBike, Bicycle yourBike,
                              Environment env) {
    Bicycle fastest;
    // code to calculate which bike is 
    // faster, given each bike's gear 
    // and cadence and given the 
    // environment (terrain and wind)
    return fastest;
}
Returning a Class or Interface
If this section confuses you, skip it and return to it after you have finished the lesson on interfaces and inheritance.

When a method uses a class name as its return type, such as whosFastest does, the class of the type of the returned object must be either a subclass of, or the exact class of, the return type. Suppose that you have a class hierarchy in which ImaginaryNumber is a subclass of java.lang.Number, which is in turn a subclass of Object, as illustrated in the following figure.

The class hierarchy for ImaginaryNumber
The class hierarchy for ImaginaryNumber

Now suppose that you have a method declared to return a Number:

public Number returnANumber() {
    ...
}
The returnANumber method can return an ImaginaryNumber but not an Object. ImaginaryNumber is a Number because it's a subclass of Number. However, an Object is not necessarily a Number — it could be a String or another type.

You can override a method and define it to return a subclass of the original method, like this:

public ImaginaryNumber returnANumber() {
    ...
}
This technique, called covariant return type, means that the return type is allowed to vary in the same direction as the subclass.
