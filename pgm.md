https://www.udemy.com/course/devops-with-docker-kubernetes-and-azure-devops/learn/lecture/18050129#overview

https://www.udemy.com/course/testing-spring-boot-application-with-junit-and-mockito/learn/lecture/47006601#overview

# 9. Setup
### pom.xml
```xml
  <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>
```
# 10. 1st Junit
### Class under Test - Calculator.java
```java
package net.javaguides;

public class Calculator {

    public int add(int a, int b){
        return a + b;
    }
}
```
### Positive Scenario
```java
package net.javaguides;

import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.*;

class CalculatorTest {

    @Test
    public void addTest(){

        Calculator calculator = new Calculator();
        int actualResult = calculator.add(10, 20);

        assertEquals(30,actualResult);
    }
}
```
# 11. Test annotation
### SUT
```java
package net.javaguides;

public class Factorial {

    public int factorial(int number){

        int factorial = 1;

        for(int i = 1; i <= number; i++){
            factorial = factorial * i;
        }

        return factorial;
    }
}
```
### Junit
```java
package net.javaguides.annotations;

import net.javaguides.Factorial;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.*;

 class FactorialTest {

    @Test
     void factorialTest(){

        Factorial fact = new Factorial();
        int actualResult = fact.factorial(5);

        assertEquals(120,actualResult);
    }
}
```
# 12.
### Student
```java
package net.javaguides;

public class Student {
    public int id;
    public String name;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```
### StudentService
```java
package net.javaguides;

import java.util.ArrayList;
import java.util.List;

public class StudentService {

    private List<Student> students = new ArrayList<>();

    public List<Student> getStudents(){
        return this.students;
    }

    public void addStudent(Student student){
        students.add(student);
    }
}
```
### Testing
```java
package net.javaguides.assertions;

import net.javaguides.Student;
import net.javaguides.StudentService;
import org.junit.jupiter.api.Test;

import java.util.List;

import static org.junit.jupiter.api.Assertions.*;

class StudentServiceTest {

    @Test
    public void testGetStudents(){

        StudentService studentService = new StudentService();

        List<Student> listOfStudents = studentService.getStudents();

        boolean actualResult = listOfStudents.isEmpty();

        assertTrue(actualResult);
    }
}
```
### Negative Scenario
```java
package net.javaguides.assertions;

import net.javaguides.Student;
import net.javaguides.StudentService;
import org.junit.jupiter.api.Test;

import java.util.List;

import static org.junit.jupiter.api.Assertions.*;

class StudentServiceTest {

    @Test
    public void testGetStudents(){

        StudentService studentService = new StudentService();

        Student student = new Student(1,"Ramesh");

        List<Student> listOfStudents = studentService.getStudents();

        listOfStudents.add(student);

        boolean actualResult = listOfStudents.isEmpty();

        assertTrue(actualResult);
    }
}
```
### Overloaded Positive assertTrue(BooleanSuplier)
```java
package net.javaguides.assertions;

import net.javaguides.Student;
import net.javaguides.StudentService;
import org.junit.jupiter.api.Test;

import java.util.List;

import static org.junit.jupiter.api.Assertions.*;

class StudentServiceTest {

    @Test
    public void testGetStudents(){
        StudentService studentService = new StudentService();

        //If i don't add Student to list
//        Student student = new Student(1,"Ramesh");

        List<Student> listOfStudents = studentService.getStudents();

//        listOfStudents.add(student);

        boolean actualResult = listOfStudents.isEmpty();

        assertTrue(()->actualResult);
    }
}
```
### Overloaded Negative assertTrue(BooleanSuplier)
```java
package net.javaguides.assertions;

import net.javaguides.Student;
import net.javaguides.StudentService;
import org.junit.jupiter.api.Test;

import java.util.List;

import static org.junit.jupiter.api.Assertions.*;

class StudentServiceTest {

    @Test
    public void testGetStudents(){
        StudentService studentService = new StudentService();

        Student student = new Student(1,"Ramesh");

        List<Student> listOfStudents = studentService.getStudents();

        listOfStudents.add(student);

        boolean actualResult = listOfStudents.isEmpty();

        assertTrue(()->actualResult);
    }
}
```
### For rest overloaded method check out scrren shot
# 14.
###  StudentService
```java
package net.javaguides;

import java.util.ArrayList;
import java.util.List;

public class StudentService {

    private List<Student> students = new ArrayList<>();

    public List<Student> getStudents(){
        return this.students;
    }

    public void addStudent(Student student){
        students.add(student);
    }

    public Student getStudentById(int studentId){
      return  students.stream()
                .filter(student -> (student.getId() == studentId))
                .findFirst()
                .orElse(null);
    }
}
```
### For code check screeen shots.
# 15
- check screen shots.
# 16
- Check screen shots
# 17
- Check ss
# 18
### Student
```java
package net.javaguides;

public class Student {
    private int id;
    private String name;
    private String department;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    //Don't break existing code add another constructor
    public Student(int id,String name, String department) {
        this.id = id;
        this.name = name;
        this.department = department;
    }

    public int getId() {
        return id;
    }
    public void setId(int id) {
        this.id = id;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }

    public String getDepartment() {
        return department;
    }

    public void setDepartment(String department) {
        this.department = department;
    }
}
```
### StudentService.java
```java
package net.javaguides;

import java.util.ArrayList;
import java.util.List;

public class StudentService {

    private List<Student> students = new ArrayList<>();

    public List<Student> getStudents(){
        return this.students;
    }

    public void addStudent(Student student){
        students.add(student);
    }

    public Student getStudentById(int studentId){
      return  students.stream()
                .filter(student -> (student.getId() == studentId))
                .findFirst()
                .orElse(null);
    }

    //Create a method which return Arrays of Student name
    public String[] getStudentNameByDepartment(String department){
      return  students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getName)            //use map method to map only student name
                .toArray(String[]::new); //Convert stream into an array by using toArray() it will take type
    }

    public Integer[] getStudentIdByDepartement(String department){
        return students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getId) //use map method to map only ids
                .toArray(Integer[]::new); //Convert Stream into array by using toArray() it will take type
    }
}
```
### See screnshots
# 19. 
### StudentService
```java
package net.javaguides;

import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class StudentService {

    private List<Student> students = new ArrayList<>();

    public List<Student> getStudents(){
        return this.students;
    }

    public void addStudent(Student student){
        students.add(student);
    }

    public Student getStudentById(int studentId){
      return  students.stream()
                .filter(student -> (student.getId() == studentId))
                .findFirst()
                .orElse(null);
    }

    public String[] getStudentNameByDepartment(String department){
      return  students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getName)            //use map method to map only student name
                .toArray(String[]::new); //Convert stream into an array by using toArray() it will take type
    }

    public Integer[] getStudentIdByDepartement(String department){
        return students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getId) //use map method to map only ids
                .toArray(Integer[]::new); //Convert Stream into array by using toArray() it will take type
    }


    public List<String> getStudentNameListByDepartment(String department){
        return  students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getName)            //use map method to map only student name
                .collect(Collectors.toList()); //Convert stream into  list
    }

    public List<Integer> getStudentIdListByDepartement(String department){
        return students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getId) //use map method to map only ids
                .collect(Collectors.toList()); //Convert Stream into list via this
    }
}
```
### For remaining see screenshots
# 20.
### StudentNotFoundException
```java
package net.javaguides;

public class StudentNotFoundException extends RuntimeException{

    public StudentNotFoundException(String msg){
        super(msg);
    }
}
```
### StudentService
```java
package net.javaguides;

import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class StudentService {

    private List<Student> students = new ArrayList<>();

    public List<Student> getStudents(){
        return this.students;
    }

    public void addStudent(Student student){
        students.add(student);
    }

    public Student getStudentById(int studentId){
      return  students.stream()
                .filter(student -> (student.getId() == studentId))
                .findFirst()
                .orElse(null);
    }

    public String[] getStudentNameByDepartment(String department){
      return  students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getName)            //use map method to map only student name
                .toArray(String[]::new); //Convert stream into an array by using toArray() it will take type
    }

    public Integer[] getStudentIdByDepartement(String department){
        return students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getId) //use map method to map only ids
                .toArray(Integer[]::new); //Convert Stream into array by using toArray() it will take type
    }


    public List<String> getStudentNameListByDepartment(String department){
        return  students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getName)            //use map method to map only student name
                .collect(Collectors.toList()); //Convert stream into  list
    }

    public List<Integer> getStudentIdListByDepartement(String department){
        return students.stream()
                .filter(student -> student.getDepartment().equals(department))
                .map(Student::getId) //use map method to map only ids
                .collect(Collectors.toList()); //Convert Stream into list via this
    }

    //Create method which throw StudentNotFoundException
    public Student getStudentByName(String name){
        return students.stream()
                .filter(student -> student.getName().equals(name))
                .findFirst()
                .orElseThrow(()->new StudentNotFoundException("Student not found with name : "+name));
    }
}
```
# 21
- Check screenshots
# 22
### Calculator
```java
package net.javaguides;

public class Calculator {

    public int add(int a, int b){
        return a + b;
    }

    public int subtract(int a, int b){
        return  a - b;
    }

    public int multiply(int a, int b){
        return  a * b;
    }

    public int divide(int a, int b){
        if(b == 0){
            throw new ArithmeticException("Division by Zero");
        }
        return  a / b;
    }
}
```
### CalculatorTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.DisplayName;
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

@DisplayName("Calculation Operation Test")
public class CalculatorTest {

    @DisplayName("Test subtract of 2 number \uD83D\uDE00")
    @Test
    void testsubtract(){
        Calculator calculator = new Calculator();
        int subtraction = calculator.subtract(3, 2);

        assertEquals(1,subtraction);
    }

    @DisplayName("Test Addition of Two Numbers ")
    @Test
    void testAdd(){
        Calculator calculator = new Calculator();//Create Calculator instance
        int addition = calculator.add(2, 3);//Calling method

       assertEquals(5,addition);
    }
}
```
# 23.
### Calculator
```java
package net.javaguides;

public class Calculator {

    public int add(int a, int b){
        return a + b;
    }

    public int subtract(int a, int b){
        return  a - b;
    }

    public int multiply(int a, int b){
        return  a * b;
    }

    public int divide(int a, int b){
        if(b == 0){
            throw new ArithmeticException("Division by Zero");
        }
        return  a / b;
    }
}
```
### DisabledCalculatorTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.Disabled;
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class DisableCalculatorTest {

    @Disabled("Disable until bug #40 is fixed")
    @Test
    void testAdd(){
        Calculator calculator = new Calculator();
        int addition = calculator.add(2, 3);
        assertEquals(5,addition);
    }

    @Disabled("Isko bhi disabled")
    @Test
    void testsubtract(){
        Calculator calculator = new Calculator();
        int subtraction = calculator.subtract(3, 2);
        assertEquals(1,subtraction);
    }
    @Test
    void testmultiply(){
        Calculator calculator = new Calculator();
        int multipication = calculator.multiply(3, 2);
        assertEquals(6,multipication);
    }
    @Test
    void testdivide(){
        Calculator calculator = new Calculator();
        int division = calculator.divide(4, 2);
        assertEquals(2,division);
    }
}
```
# 24. Theory
# 25.
### Calculator
```java
package net.javaguides;

public class Calculator {

    public int add(int a, int b){
        return a + b;
    }

    public int subtract(int a, int b){
        return  a - b;
    }

    public int multiply(int a, int b){
        return  a * b;
    }

    public int divide(int a, int b){
        if(b == 0){
            throw new ArithmeticException("Division by Zero");
        }
        return  a / b;
    }
}
```
### BeforeEachDemoTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class BeforeEachDemoTest {
    private Calculator calculator;//Declare instace
    @BeforeEach
    void setup(){    //use void as return type
         calculator = new Calculator(); //Create instance
        System.out.println("setup() method is called");
    }
    @Test
    void testAdd(){
        int addition = calculator.add(2, 3);
        assertEquals(5,addition);
        System.out.println("addTest() method is calling");
    }
    @Test
    void testsubtract(){
        int subtraction = calculator.subtract(3, 2);
        assertEquals(1,subtraction);
        System.out.println("subtractTest() method is calling");
    }
    @Test
    void testmultiply(){
        int multipication = calculator.multiply(3, 2);
        assertEquals(6,multipication);
        System.out.println("multiplyTest() method is calling");
    }
    @Test
    void testdivide(){
        int division = calculator.divide(4, 2);
        assertEquals(2,division);
        System.out.println("divideTest() method is calling");
    }
}
```
# 26.
### Calculator same pgm
### AfterEachDemoTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.AfterEach;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class AfterEachDemoTest {
    private Calculator calculator;

    @BeforeEach
    void setup(){
         calculator = new Calculator();
        System.out.println("setup() method is calling");
    }

    @AfterEach
    void tearDown(){
        //Here we don't have a file to close; we have object
        calculator = null; //assign null to it.
        System.out.println("tearDown() method is calling");
    }

    @Test
    void testAdd(){
        int addition = calculator.add(2, 3);
        assertEquals(5,addition);
        System.out.println("addTest() method is calling");
    }
    @Test
    void testsubtract(){
        int subtraction = calculator.subtract(3, 2);
        assertEquals(1,subtraction);
        System.out.println("subtractTest() method is calling");
    }
    @Test
    void testmultiply(){
        int multipication = calculator.multiply(3, 2);
        assertEquals(6,multipication);
        System.out.println("multiplyTest() method is calling");
    }
    @Test
    void testdivide(){
        int division = calculator.divide(4, 2);
        assertEquals(2,division);
        System.out.println("divideTest() method is calling");
    }
}
```
# 27.
### Calculator class same
### BeforeAllDemoTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class BeforeAllDemoTest {
    private static Calculator calculator;//Declare instace

    @BeforeAll
    static  void setupBeforeClass(){
        calculator = new Calculator();
        System.out.println("setupBeforeClass method is calling");
    }
    @Test
    void testAdd(){
        int addition = calculator.add(2, 3);
        assertEquals(5,addition);
        System.out.println("addTest() method is calling");
    }
    @Test
    void testsubtract(){
        int subtraction = calculator.subtract(3, 2);
        assertEquals(1,subtraction);
        System.out.println("subtractTest() method is calling");
    }
    @Test
    void testmultiply(){
        int multipication = calculator.multiply(3, 2);
        assertEquals(6,multipication);
        System.out.println("multiplyTest() method is calling");
    }
    @Test
    void testdivide(){
        int division = calculator.divide(4, 2);
        assertEquals(2,division);
        System.out.println("divideTest() method is calling");
    }
}
```
# 28.
### Calculator same
### AfterAllDemoTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.AfterAll;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class AfterAllDemoTest {
    private static Calculator calculator;//Declare instace

    @BeforeAll
    static  void setupBeforeClass(){
        calculator = new Calculator();
        System.out.println("setupBeforeClass method is calling");
    }

    @AfterAll
    static void tearDownAfterClass(){
        calculator = null;
        System.out.println("tearDownAfterClass method is calling");
    }
    @Test
    void testAdd(){
        int addition = calculator.add(2, 3);
        assertEquals(5,addition);
        System.out.println("addTest() method is calling");
    }
    @Test
    void testsubtract(){
        int subtraction = calculator.subtract(3, 2);
        assertEquals(1,subtraction);
        System.out.println("subtractTest() method is calling");
    }
    @Test
    void testmultiply(){
        int multipication = calculator.multiply(3, 2);
        assertEquals(6,multipication);
        System.out.println("multiplyTest() method is calling");
    }
    @Test
    void testdivide(){
        int division = calculator.divide(4, 2);
        assertEquals(2,division);
        System.out.println("divideTest() method is calling");
    }
}
```
# 29.
### Calculator same code
### RepeatedTestDemoTesgt
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.*;

import static org.junit.jupiter.api.Assertions.*;

public class RepeatedTestDemoTesgt {
    @BeforeEach
    void setup(){
        System.out.println("Setup method is calling..");
    }
    @AfterEach
    void tearDown(){
        System.out.println("tearDown method is calling..");
    }

    @BeforeAll
    static void setupBeforeClass(){
        System.out.println("setupBeforeClass method is calling..");
    }

    @AfterAll
    static void tearDownAfterClass(){
        System.out.println("tearDownAfterClass method is calling..");
    }

    @RepeatedTest(value = 5, name = RepeatedTest.LONG_DISPLAY_NAME)
    @DisplayName("Test Addition Repeatedly")
    public void addTest(){
        Calculator calculator = new Calculator();
        assertEquals(5,calculator.add(2,3));
        System.out.println("addTest() method is calling");
    }
}
```
# 30.
### Calculator same
### NestedCalculatorTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Nested;
import org.junit.jupiter.api.Test;

import static  org.junit.jupiter.api.Assertions.*;

public class NestedCalculatorTest {
    private Calculator calculator;
    @BeforeEach
    void setup(){
        calculator = new Calculator();
    }
    @Nested
    class AdditionTests{
        @Test
         public void testAddPositiveNumber(){ //create test method which are related to this Nested class
            assertEquals(7,calculator.add(3,4));
        }
        @Test
        public void testAddPositiveAndNegativeNumber(){
            assertEquals(1,calculator.add(4,-3));
        }
        @Test
        public void testNegativeNumber(){
            assertEquals(-7,calculator.add(-4,-3));
        }
    }
    @Nested
    class SubtractionTEsts{
        @Test
        public void testSubtractPositiveNumber(){
            assertEquals(1,calculator.subtract(4,3));
        }
        @Test
        public void testSubtractLargerFromSmaller(){
            assertEquals(-4,calculator.subtract(3,7));
        }

        @Nested
        class EdgeCases{
            @Test
            public void testSubtractZero(){
                assertEquals(2,calculator.subtract(2,0));
            }
            @Test
            public void testSubtractSelf(){
                assertEquals(0,calculator.subtract(2,2));
            }
        }
    }
}
```
# 31
### Calculator same story
### OrderCalculatorTest
```java
package net.javaguides.annotations;

import net.javaguides.Calculator;
import org.junit.jupiter.api.MethodOrderer;
import org.junit.jupiter.api.Order;
import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.TestMethodOrder;

import static org.junit.jupiter.api.Assertions.*;

@TestMethodOrder(MethodOrderer.OrderAnnotation.class) //passing Ordering Strategy
public class OrderCalculatorTest {

    @Order(1) //1st this will execute
    @Test
    void testAdd(){
        Calculator calculator = new Calculator();
        assertEquals(5,calculator.add(2,3));
    }

    @Order(3)
    @Test
    void testSubtract(){
        Calculator calculator = new Calculator();
        assertEquals(1,calculator.subtract(3,2));
    }

    @Order(2)
    @Test
    void testMultiply(){
        Calculator calculator = new Calculator();
        assertEquals(6,calculator.multiply(2,3));
    }

    @Order(4)
    @Test
    void testDivide(){
        Calculator calculator = new Calculator();
        assertEquals(2,calculator.divide(4,2));
    }
}
```
# 32.
### pom.xml
```java
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>net.javaguides</groupId>
    <artifactId>junit-tutorial</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>21</maven.compiler.source>
        <maven.compiler.target>21</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>
        <!-- https://mvnrepository.com/artifact/org.junit.platform/junit-platform-suite-engine -->
        <dependency>
            <groupId>org.junit.platform</groupId>
            <artifactId>junit-platform-suite-engine</artifactId>
            <version>1.11.0</version>
            <scope>test</scope>
        </dependency>

        <!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-engine -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```
### ClassATest
```java
package net.javaguides.suite;

import org.junit.jupiter.api.Test;

public class ClassATest {

    @Test
    void testClassA(){
        System.out.println("Within ClassATest.testClassA method");
    }
}
```
### ClassBTest
```java
package net.javaguides.suite;

import org.junit.jupiter.api.Test;

public class ClassBTest {

    @Test
    void testClassB(){

        System.out.println("Within ClassBTest.testClassB method");
    }
}
```
### ClassCTest
```java
package net.javaguides.suite;

import org.junit.jupiter.api.Test;

public class ClassCTest {

    @Test
    void testClassC(){

        System.out.println("Within ClassCTest.testClassC method");
    }
}
```
### TestSuite
```java
package net.javaguides.suite;

import org.junit.platform.suite.api.SelectClasses;
import org.junit.platform.suite.api.SelectPackages;
import org.junit.platform.suite.api.Suite;

@Suite
@SelectPackages({"net.javaguides.annotations","net.javaguides.suite"})
public class TestSuite {

}
```
# 33. Theory
# 34.
### pom.xml
```java
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>net.javaguides</groupId>
    <artifactId>junit-tutorial</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>21</maven.compiler.source>
        <maven.compiler.target>21</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>
        <!-- https://mvnrepository.com/artifact/org.junit.platform/junit-platform-suite-engine -->
        <dependency>
            <groupId>org.junit.platform</groupId>
            <artifactId>junit-platform-suite-engine</artifactId>
            <version>1.11.0</version>
            <scope>test</scope>
        </dependency>

        <!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-engine -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>

        <!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-params -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-params</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```
### MathUtils
```java
package net.javaguides;

public class MathUtils {

    //Create a method will check number is even or not
    public boolean isEven(int number){
        return number%2 == 0;
    }
}
```
### ValueSourceDemoTest
```java
package net.javaguides.parameterized;

import net.javaguides.MathUtils;
import org.junit.jupiter.api.Test;
import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.ValueSource;

import static org.junit.jupiter.api.Assertions.*;

public class ValueSourceDemoTest {

    @ParameterizedTest
    @ValueSource(ints = {2,3,6,8,10})
    void testIsEven(int number){
        MathUtils mathUtils = new MathUtils();
        assertTrue(mathUtils.isEven(number));
    }

    @ParameterizedTest
    @ValueSource(strings = {"Hello","Junit","Parameterized","Test"})
    void valueSouceTest(String parameter){
        //Check this parameter is not null
        assertNotNull(parameter);
    }
}
```

