# Interface Segregation Principle (ISP)

The Interface Segregation Principle (ISP) states that clients should not be forced to depend on interfaces they do not use. In simpler terms, it promotes designing interfaces that are specific to the needs of clients and avoids imposing unnecessary dependencies.

Let's explain the ISP with a simple example in JavaScript:

Imagine we have an interface called Printer that provides printing functionality:

```javascript
class Printer {
  print() {
    // Common print functionality
  }

  fax() {
    // Fax functionality
  }

  scan() {
    // Scan functionality
  }
}

```

Now, let's say we have two classes, OfficePrinter and HomePrinter, implementing the Printer interface:

```javascript
class OfficePrinter implements Printer {
  print() {
    // Office-specific print implementation
  }

  fax() {
    // Office-specific fax implementation
  }

  scan() {
    // Office-specific scan implementation
  }
}

class HomePrinter implements Printer {
  print() {
    // Home-specific print implementation
  }

  fax() {
    throw new Error("Fax not supported in home printers.");
  }

  scan() {
    // Home-specific scan implementation
  }
}

```
In this example, both OfficePrinter and HomePrinter implement the complete Printer interface. However, the HomePrinter class doesn't support fax functionality.

To adhere to the Interface Segregation Principle, we can split the Printer interface into smaller, more specific interfaces:

```javascript

interface Printer {
  print();
}

interface FaxMachine {
  fax();
}

interface Scanner {
  scan();
}


```

Now, our classes can implement only the interfaces they actually need:

```javascript

class OfficePrinter implements Printer, FaxMachine, Scanner {
  print() {
    // Office-specific print implementation
  }

  fax() {
    // Office-specific fax implementation
  }

  scan() {
    // Office-specific scan implementation
  }
}

class HomePrinter implements Printer, Scanner {
  print() {
    // Home-specific print implementation
  }

  scan() {
    // Home-specific scan implementation
  }
}


```

By segregating the interfaces, we ensure that clients, such as HomePrinter, are not forced to depend on unnecessary functionality like faxing. This improves code modularity, avoids bloated interfaces, and allows clients to depend only on the specific functionality they require.

The ISP helps create interfaces that are tailored to the needs of clients, leading to cleaner code, improved maintainability, and easier code reuse.