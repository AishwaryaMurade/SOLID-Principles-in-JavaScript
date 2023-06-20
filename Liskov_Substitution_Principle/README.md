# Liskov Substitution Principle (LSP)

Let's explain the Liskov Substitution Principle (LSP) in a simple way with an example.

Imagine we have a Bird class that has a fly method:

```javascript
class Bird {
  fly() {
    console.log("Flying...");
  }
}


```
Now, we create two subclasses: Eagle and Penguin, which inherit from the Bird class:

```javascript
class Eagle extends Bird {
  fly() {
    console.log("Soaring high in the sky...");
  }
}

class Penguin extends Bird {
  fly() {
    throw new Error("I cannot fly!");
  }
}


```

According to the Liskov Substitution Principle, instances of subclasses should be able to replace instances of the superclass without causing issues. In this example, both Eagle and Penguin are subclasses of Bird, but they have different capabilities when it comes to flying.

We can see that the Eagle class overrides the fly method to specify how eagles fly, while the Penguin class overrides it to indicate that penguins cannot fly.

If we have a function that expects a Bird object, we should be able to pass an instance of Eagle or Penguin without any problems:

```javascript
function flyBird(bird) {
  bird.fly();
}

const eagle = new Eagle();
flyBird(eagle); // Output: "Soaring high in the sky..."

const penguin = new Penguin();
flyBird(penguin); // Throws an error: "I cannot fly!"

```

The Liskov Substitution Principle ensures that we can use instances of subclasses interchangeably with instances of the superclass, without unexpected behavior. In this case, the code that expects a Bird can handle both an Eagle and a Penguin, even though they have different flying capabilities.