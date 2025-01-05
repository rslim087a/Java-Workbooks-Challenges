# The World of Objects - Extra Practice

From the `Java Bootcamp Resources`, launch **`Part 1`**.

![1.png](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-03_22-45-35-fc3a726b8efda1383a99329b586504f7.png)

## **Task 1**

Create a new file named `Contact.java`. Inside the file, create the `Contact` class.


```java
public class Contact {

}
```

The Contact class will define the following fields:

```java
    private String name;
    private String phoneNumber;
    private String birthDate;
    private int age;
```

The Contact class serves as a blueprint for creating Contact objects.


## Task 2

Create a constructor that initializes the fields of a newly created object.


## Task 3

Create a constructor that initializes a new object using an existing object's fields.

## Task 4

Test your constructor by creating four instances (objects) of the Contact class.

```java
public static void main(String[] args) {
    Contact contact1 = new Contact("Alice", "123-456-7890", "1990-01-01", 33);
    Contact contact2 = new Contact("Bob", "234-567-8901", "1992-02-02", 31);
    Contact contact3 = new Contact("Charlie", "345-678-9012", "1994-03-03", 29);
    Contact contact4 = new Contact("David", "456-789-0123", "1996-04-04", 27);
}
```
## Task 5

Use breakpoints to visualize the initialization of each field as objects are created.

## Task 6

Test the copy constructor by creating two objects with fields copied from two existing objects.


```java
public static void main(String[] args) {
    // Assuming the Contact objects from Task 4 are available
    Contact copyContact1 = new Contact(contact1);
    Contact copyContact2 = new Contact(contact3);
}
```

## Task 7

Use breakpoints to inspect field initialization in the new objects created using the copy constructor.

----------

##### Your Path to Cloud-Native Engineering (After Learning Java)
###### 1. Develop Java Web Applications With Spring Boot → [Spring Boot Bootcamp](https://www.udemy.com/course/the-complete-spring-boot-development-bootcamp/?couponCode=SPRING_BOOTCAMP)
###### 2. Containerize and Deploy Web Applications with Docker → [Docker Bootcamp](https://www.udemy.com/course/docker-bootcamp-conquer-docker-with-real-world-projects/?couponCode=DOCKER_BOOTCAMP)
###### 3. Orchestrate Cloud Native Applications with Kubernetes → [Kubernetes Bootcamp](https://kubernetestraining.io/)