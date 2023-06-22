# Files Structure & Principles

In a typical application architecture following the Domain-Driven Design (DDD) principles, the Entity, Repository, and Service components play distinct roles in managing data and business logic.

## 1. Entity:

> 💡 The entity in Java is basically the Table (we create SQL table by doing this)

An entity represents a domain object or a concept within the application's domain. It encapsulates both data and behavior related to that concept. For example, in a student management system, the "Student" entity might have attributes like name, age, and grade. Entities are typically annotated with JPA annotations (`@Entity`, `@Table`, etc.) to map them to the underlying database tables.

```java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;
    private int age;
    private String grade;

    // Constructors, getters, setters, and other methods omitted for brevity
}

```

## 2. Repository:

> 💡 Respository are responsible for and have has direct access to the Student TABLE in the database with custom methods like (save, delete, update)

A repository acts as an abstraction layer between the application's business logic and the underlying data storage mechanism (e.g., database). It provides methods for performing CRUD (Create, Read, Update, Delete) operations on entities. The repository is responsible for data access and persistence. It abstracts away the specific details of the database and provides a clean interface for working with entities.

The repository typically implements an interface provided by a framework like Spring Data JPA (e.g., `CrudRepository`, `JpaRepository`). These interfaces already define common methods for CRUD operations, eliminating the need to write boilerplate code for data access.

```java
public interface StudentRepository extends CrudRepository<Student, Long> {
    // Custom query methods can be defined here if needed
    // save, delete, update are already here as it extends from CRUD repository
}

```

## 3. Service:

> 💡 Performs validation and checks and other important stuff before it passes it off to the repostory to save the information to the database

A service represents the business logic and acts as an orchestrator for operations that involve multiple entities or more complex logic. Services encapsulate domain-specific rules, validations, and complex operations that go beyond basic CRUD operations. They provide a higher-level abstraction over repositories.

Services interact with repositories to perform data operations and enforce business rules. They coordinate the interaction between multiple entities, perform validations, and apply any necessary transformations or calculations before persisting data. Services can also include additional methods for performing specific business operations.

```java
@Service
public class StudentService {
    private final StudentRepository studentRepository;

    public StudentService(StudentRepository studentRepository) {
        this.studentRepository = studentRepository;
    }

    public Student saveStudent(Student student) {
        // Additional business logic, validations, and transformations can be performed here
        return studentRepository.save(student);
    }

    public void deleteStudent(Long studentId) {
        // Additional business logic can be implemented here
        studentRepository.deleteById(studentId);
    }

    public Student findStudentById(Long studentId) {
        // Additional business logic can be implemented here
        return studentRepository.findById(studentId).orElse(null);
    }

    // Other methods for performing business operations related to students
}

```

## The relationship between entities, repositories, and services:

- Entities define the structure and behavior of domain objects.
- Repositories provide the interfaces and implementation for data access and persistence. They handle the mapping between entities and the underlying data storage.
- Services use repositories to perform data operations and incorporate business logic. They provide higher-level operations and coordinate multiple entities.

In summary, entities represent domain concepts, repositories handle data access and persistence, and services encapsulate business logic and orchestrate operations involving entities. The entities and repositories focus on data management, while services handle the domain-specific operations and business rules.
