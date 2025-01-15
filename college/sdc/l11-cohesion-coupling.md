### **Coupling**
**Coupling** measures the degree of dependence between different modules in a system. Lower coupling (loose coupling) is desirable because it results in more modular and maintainable systems.

#### **Levels/Types of Coupling**
1. **Content Coupling** (Worst):
   - One module directly accesses or modifies the content of another.
   - Example: Directly changing another module's variable or using `goto` statements.
   - **Issues**: Breaks encapsulation, unexpected results, and hard to maintain.
   - **Solution**: Use encapsulation; access other modules’ data via methods.

2. **Common Coupling**:
   - Modules share global data.
   - Example: Multiple components reading/writing from a global variable.
   - **Issues**: Error propagation, reduced readability, poor reuse.
   - **Solution**: Introduce a data manager that controls access to the global data.

3. **Control Coupling**:
   - One module controls the behavior of another by passing flags or control information.
   - Example: Passing a mode parameter to dictate functionality.
   - **Issues**: Hard to understand, maintain, and reuse.
   - **Solution**: Use polymorphism or break functionality into separate methods.

4. **Stamp Coupling**:
   - Modules share a composite data structure, but not all fields are used.
   - Example: Passing an entire object when only one attribute is needed.
   - **Issues**: Tight dependency on structure, reduced reusability.
   - **Solution**: Pass only the required fields as arguments.

5. **Data Coupling** (Best):
   - Modules communicate through simple data parameters.
   - Example: Passing primitive types or single attributes.
   - **Benefits**: Easy to test, maintain, and reuse.

---

### **Cohesion**
**Cohesion** measures how closely related and focused the responsibilities of a module are. High cohesion (tight cohesion) is desirable as it makes modules easier to understand and maintain.

#### **Levels/Types of Cohesion**
1. **Coincidental Cohesion** (Worst):
   - Elements have no meaningful relationship and are grouped arbitrarily.
   - Example: A class that handles file I/O and GUI interactions.
   - **Solution**: Separate unrelated parts into distinct modules.

2. **Logical Cohesion**:
   - Elements are grouped because they perform similar tasks, but not for the same function.
   - Example: A module with functions like `handleMouseInput`, `handleKeyboardInput`.
   - **Solution**: Break into more focused modules or use inheritance.

3. **Temporal Cohesion**:
   - Elements are grouped because they are executed at the same time.
   - Example: Initialization routines that do multiple unrelated tasks.
   - **Solution**: Distribute tasks to individual components or modules.

4. **Procedural Cohesion**:
   - Elements are grouped because they are executed sequentially.
   - Example: `readDataFromFile`, `processData`, `writeDataToFile`.
   - **Solution**: Abstract responsibilities into smaller, independent modules.

5. **Communicational Cohesion**:
   - Elements are grouped because they operate on the same data.
   - Example: A class that reads and updates the same data set.
   - **Solution**: Break into focused methods that share the data through parameters.

6. **Functional Cohesion** (Best):
   - Elements work together to perform a single well-defined task.
   - Example: A `Stack` class with methods like `push`, `pop`, and `peek`.
   - **Benefits**: High maintainability, reusability, and clarity.

---

### **Good Design Practices**
- **Loose Coupling and High Cohesion**:
   - Ensures modular, maintainable, and extendable code.
   - Example: Use interfaces and design patterns like Dependency Injection, Strategy, or Observer.

- **Avoid Anti-patterns**:
   - **God Class**: A class with too many unrelated responsibilities (low cohesion).
   - **Spaghetti Code**: Tightly coupled and tangled dependencies.

Would you like specific examples or help applying these principles in your own code?