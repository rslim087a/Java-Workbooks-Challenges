# **Cheat Sheet**

This cheat sheet contains the most important takeaways that lead up to section nine.

## **Definitions**
---------------

-   **Class**: blueprint from which you can create objects.

-   **Object**: an object is a *thing* that you can see or describe.

-   **Field**: class variable that describes an object.

-   **Action**: method (function) that represents what the object can do.

-   **Constructor**: runs when you create a `new` object.

    -   Purpose: update every field of the newly created object.

-   **`this`**: refers to the current object that's calling the constructor or method.

    -   Purpose: useful when fields and parameters have conflicting names.

-   **Copy Constructor**: runs when you create an object.

    -   Purpose: copy every value from a `source` object into a `new` object.

-   **Getter**: method (function) that returns a copy of a `private` field's value.

-   **Setter**: method (function) that updates the value of a `private` field.

-   **`toString`**: method that returns a `String` representation of every field in an object.

    -   Purpose: When you print an object, Java internally calls the `toString` method.

## `public` **vs.** `private`
----------------------------------

-   `public`: provides public access to a field or method from anywhere.

    -   Constructors and methods tend to be `public`.

-   `private`: prevents direct access of a field or method outside of its class.

    -   To protect the state of an object, fields tend to be `private`.

## **The Big Three**
-----------------

If a `class` has fields, you need to add:

1.  **Constructor** -- to update the fields of a `new` object.

2.  **Getters** -- to get the value of a `private` field.

3.  **Setters** -- to set the value of a `private` field.

## **Debugging**

![Screen Shot 2021-06-19 at 2.53.23 PM.png](https://firebasestorage.googleapis.com/v0/b/learnthepart-75aed.appspot.com/o/images%2Fba457400-93c8-4508-b14c-7b92f4a54a46?alt=media&token=bbdd983c-2102-47c9-aa73-d8d9dddcae72)


1. **Continue**: continues to the next breakpoint. 
2. **Step over**: steps over a line (see Debugging Exercise 3).
3. **Step into**: steps into a function/cons. 
4. **Step out**: steps out of a function/cons.
5. **Restart**: restarts the runtime.
6. **Stop**: stops the runtime

## **Exceptions**
-----

**Checked**:
- Compile-time.
-  Outside the application's control.
- Java forces you to `try-catch` the potential failure. 

**Unchecked**:
-  Runtime.
-  Results from badly written code.
- Do not catch unchecked exceptions. Instead, fix your code.

**Throwing Exceptions**:
- Forces the caller to improve their code.
- Throw an `IllegalArgumentException` if the caller passes illegal values into a method/constructor.
- Throw an `IllegalStateException` if the caller invokes a method at a bad time (object not in a valid state).


## **Mutable / Immutable Objects**
-----------------
- **Mutable class**: class with accessible mutators (setters).
- **Immutable class**: class without accessible mutators (setters).
 
![Screen Shot 2021-06-18 at 11.42.14 PM.png](https://firebasestorage.googleapis.com/v0/b/learnthepart-75aed.appspot.com/o/images%2F1dbdd592-1aed-475f-b555-5d578e9a248d?alt=media&token=f3ca2d55-952a-4d6c-aa5a-2173420ecab2)

**Example 1:**
> An array is a **mutable** object.

Every array is a **mutable** object of a `type[]` class.

![image.png](https://firebasestorage.googleapis.com/v0/b/learnthepart-75aed.appspot.com/o/images%2Fa06a2100-6241-4610-b719-d96d67443367?alt=media&token=61e8b0ad-b4a3-4ef5-80dc-ad01109af0a1)

It follows that arrays are vulnerable to the reference trap.

**Example 2:**

> `String` is an **immutable** class. 

It follows that objects of the `String` class are immune to the reference trap.


**Reference Trap**
-------------------

> The state of a variable should not change because you updated another.

![Screen Shot 2021-06-18 at 11.54.20 PM.png](https://firebasestorage.googleapis.com/v0/b/learnthepart-75aed.appspot.com/o/images%2Fc4f86f12-85ae-4bfe-bbdd-2a24479f64bb?alt=media&token=355d8102-f495-43e9-8dcc-93a42a347f3e)

Falling into a reference trap can:

1.  lead to unpredictable behavior.

2.  lead to variables changing when you don't expect them to.

3.  leave you wondering: *why is my code doing this?*


## Wrapper class
----
**Wrapper**: Immutable class that wraps around a primitive. 

![Screen Shot 2021-06-19 at 12.05.42 AM.png](https://firebasestorage.googleapis.com/v0/b/learnthepart-75aed.appspot.com/o/images%2F242fff1b-8bf3-4ce8-9e02-5f21af4ab7cb?alt=media&token=34b48784-0ccb-41c4-a757-1fb14f28adef)

`String` is not a wrapper class. But, it is immutable.

**Rule:**  
- Use primitive when possible (faster and less memory). 
- Use wrapper only when you need to (inside `ArrayList`...).

## **`Array` vs. `ArrayList` vs. `HashMap`**
-----
- `Array`
 
  - fixed.
  - stores primitives and objects.
  - `type[] values = new type[]`
- `ArrayList`
  - resizable.
  - stores objects.
  - `ArrayList<object> values = new ArrayList<object>();`
- `HashMap`
  - resizable.
  - stores key-value pairs.
  - `HashMap<Object, Object> pairs = new HashMap<Object, Object>()`

**Rule:** use arrays when size is fixed (less overhead). Use `ArrayList` when size can vary. Use `HashMap` when there is parity between data.

## Test-Driven Development.

1. Identify meaningful test cases.
2. Write a unit test for each test case.
     - Write code to make the test fail.
     - Write code to make the test pass.
     - Refactor if necessary.

`@Test` annotates a unit test. `@Before` annotates a method that runs before each test.

## Stream Pipeline

Instead of loops, you should pass elements into a pipeline:

```java
collection.stream()
	.intermediateOperation(lambda expression)
        .intermediateOperation(lambda expression)
	.intermediateOperation(lambda expression)
	.intermediateOperation(lambda expression)
        .terminalOperation(lambda expression)
```
**Intermediate operation**: processes the sequence of elements and continues the pipeline.  
**Terminal operation**: ends the pipeline and may return a final value.  
**Lambda expression syntax:**

```
((parameter) -> {
  code goes here
})
```
## `equals()` method
 
    public boolean equals(Object obj) {
    
        return false if parameter is null.
        
        return false if parameter isn't instance of class.

        typecast the object.
        
        compare fields from both objects and return the result.
    }

## `hashCode()` method
When you add an `equals()` method, you must **always** add a `hashCode()` method.

    public int hashCode() {
         return Objects.hash(fields go here);    
    }



## Naming Conventions
- class: `CamelCase`
- variable: `lowerCamelCase`
- method: `lowerCamelCase`
- constant: `UPPER_SNAKE_CASE`

## `static` and `final`
- `static`: variable or method belongs to the class.
- `final`: cannot be updated.

--------
##### Your Path to Cloud-Native Engineering (After Learning Java)
###### 1. Create Enterprise Java Apps With Spring Boot → [Spring Boot Bootcamp](https://www.udemy.com/course/the-complete-spring-boot-development-bootcamp/?couponCode=SPRING_BOOTCAMP)
###### 2. Ship Code Like A Tech Giant With Docker → [Docker Bootcamp](https://www.udemy.com/course/docker-bootcamp-conquer-docker-with-real-world-projects/?couponCode=DOCKER_BOOTCAMP)
###### 3. Build Production-Grade Cloud Systems → [Kubernetes Bootcamp](https://kubernetestraining.io/)