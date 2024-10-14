
import java.util.Scanner;

// Person class (Base Class)
class Person {
    String name;
    int age;

    // Constructor to initialize name and age
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method to display person information
    void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}

// Student class (Subclass of Person)
class Student extends Person {
    String studentID;
    String course;
    int units;
    final int feePerUnit = 1000;

    // Constructor to initialize student details
    Student(String name, int age, String studentID, String course, int units) {
        super(name, age); // Call the Person class constructor
        this.studentID = studentID;
        this.course = course;
        this.units = units;
    }

    // Method to calculate total fees
    double calculateFees() {
        return units * feePerUnit;
    }

    // Override displayInfo method for Student
    @Override
    void displayInfo() {
        super.displayInfo(); // Call the Person class displayInfo method
        System.out.println("Student ID: " + studentID);
        System.out.println("Course: " + course);
        System.out.println("Units: " + units);
        System.out.println("Total Fees: " + calculateFees());
    }
}

// Instructor class (Subclass of Person)
class Instructor extends Person {
    String employeeID;
    String department;
    double salary;

    // Constructor to initialize instructor details
    Instructor(String name, int age, String employeeID, String department, double salary) {
        super(name, age); // Call the Person class constructor
        this.employeeID = employeeID;
        this.department = department;
        this.salary = salary;
    }

    // Override displayInfo method for Instructor
    @Override
    void displayInfo() {
        super.displayInfo(); // Call the Person class displayInfo method
        System.out.println("Employee ID: " + employeeID);
        System.out.println("Department: " + department);
        System.out.println("Salary: " + salary);
    }
}

// Test program
public class EnrolmentSystem {

    // Method to print details of a Person object (demonstrates polymorphism)
    static void printDetails(Person p) {
        p.displayInfo(); // Calls the appropriate displayInfo method based on the type of object
    }

    public static void main(String[] args) {
        // Creating two Student objects
        Student student1 = new Student("Mirasol Briones", 20, "S001", "Computer Engineering", 18);
        Student student2 = new Student("Mira Briones", 22, "S002", "Computer Engineering", 18);

        // Creating two Instructor objects
        Instructor instructor1 = new Instructor("Prof. Tanya Carmela Jovillano", 23, "I001", "Computer Engineering", 80000);
        Instructor instructor2 = new Instructor("Prof. Sarrahlyn Catimbang", 35, "I002", "Mechanical Engineering", 95000);

        // Using the printDetails method to print information for each person
        System.out.println("Details of Student 1:");
        printDetails(student1);

        System.out.println("\nDetails of Student 2:");
        printDetails(student2);

        System.out.println("\nDetails of Instructor 1:");
        printDetails(instructor1);

        System.out.println("\nDetails of Instructor 2:");
        printDetails(instructor2);
    }
