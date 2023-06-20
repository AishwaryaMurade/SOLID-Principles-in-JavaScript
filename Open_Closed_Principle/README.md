# Open/Closed Principle (OCP)

The Open/Closed Principle (OCP) states that software entities (classes, functions, etc.) should be open for extension but closed for modification. In other words, the behavior of a module should be easily extendable without modifying its existing code.

Here's a simple explanation of the Open/Closed Principle in JavaScript:

Imagine we have a Shape class with different subclasses like Circle, Square, and Triangle. Each shape has its own implementation of the calculateArea method.

```javascript
class Shape {
  calculateArea() {
    // Common logic for calculating area
  }
}

class Circle extends Shape {
  calculateArea() {
    // Calculate area of a circle
  }
}

class Square extends Shape {
  calculateArea() {
    // Calculate area of a square
  }
}

class Triangle extends Shape {
  calculateArea() {
    // Calculate area of a triangle
  }
}

```
Now, let's say we want to introduce a new shape, Rectangle. Instead of modifying the existing Shape class and its subclasses, we can adhere to the OCP by extending the functionality without changing the existing code.

```javascript
class Rectangle extends Shape {
  calculateArea() {
    // Calculate area of a rectangle
  }
}


```

By following the OCP, we extended the Shape class by adding a new shape without modifying its existing code. We kept the original behavior intact while allowing for new shapes to be added easily.

This principle promotes writing code that is easily extensible through inheritance, composition, or interfaces. By designing our code to be open for extension and closed for modification, we can introduce new features and behaviors without breaking existing code, making our codebase more maintainable and adaptable.