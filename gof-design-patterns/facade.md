# Facade

### **Type of Pattern**

Structural

### **Problem at Hand**

* Complex systems with a large number of objects, settings, and interactions can be hard to understand and use for clients.
* Tight coupling between a system and its clients makes future modifications to the system difficult without also having to modify its clients.

### **Solution**

* The Facade pattern provides a unified, simplified interface to a set of interfaces in a subsystem, making the subsystem easier to use. It hides the complexities of the subsystem and provides a high-level interface that makes the subsystem more accessible and easier to use.

### **Example**

* A computer starting up involves complex processes like loading the CPU, memory management, and other system checks. A simple interface like pressing the power button (the facade) initiates these complex processes without the user needing to understand the details.**v**

```java
javaCopy code// Facade
public class ComputerFacade {
    private CPU cpu;
    private Memory memory;
    private HardDrive hardDrive;

    public ComputerFacade() {
        this.cpu = new CPU();
        this.memory = new Memory();
        this.hardDrive = new HardDrive();
    }

    public void startComputer() {
        cpu.freeze();
        memory.load(BOOT_ADDRESS, hardDrive.read(BOOT_SECTOR, SECTOR_SIZE));
        cpu.jump(BOOT_ADDRESS);
        cpu.execute();
    }
}

// Subsystem classes
class CPU {
    public void freeze() { /* ... */ }
    public void jump(long position) { /* ... */ }
    public void execute() { /* ... */ }
}

class Memory {
    public void load(long position, byte[] data) { /* ... */ }
}

class HardDrive {
    public byte[] read(long lba, int size) { /* ... */ return null; }
}

// Client code
public class Client {
    public static void main(String[] args) {
        ComputerFacade computer = new ComputerFacade();
        computer.startComputer();
    }
}
```

### **Components of the Design**:

* **Facade**: Provides a simple interface to a complex subsystem.
* **Subsystems**: The components being wrapped by the Facade. These can be complex systems themselves.

### **Subcategories/Types**

Not applicable to the Facade pattern as it is primarily a singular concept aimed at simplifying interaction with complex systems.

### **Drawbacks**

* A facade can become a god object coupled to all classes of an app.
* It might discourage developers from using the subsystem directly, even when they need the extra flexibility.
