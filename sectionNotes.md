# * ***Section-1: Introduction***
![alt text](image-5.png)![alt text](image-7.png)![alt text](image-8.png)![alt text](image-9.png)![alt text](image-10.png)
![alt text](image-11.png)![alt text](image-12.png)![alt text](image-13.png)![alt text](image-14.png)
# * ***Section-2 Unit Testing with Junit***
https://github.com/RameshMF/mastering-junit-framework
## 7. Introduction to Junit
![alt text](image-6.png)![alt text](image.png)![alt text](image-1.png)![alt text](image-2.png)
## 8. Junit Basics Terminology
![alt text](image-3.png)![alt text](image-4.png)
## 9. Setup
![alt text](image-15.png)![alt text](image-16.png)![alt text](image-17.png)
- Within a test package we write all the JUnit test cases.
### Adding Junit Maven dependencies
![alt text](image-18.png)![alt text](image-19.png)
## 10. Writing your 1st Junit test
![alt text](image-20.png)![alt text](image-21.png)
### Need to create test class. IntelliJ shortCut
![alt text](image-22.png)![alt text](image-23.png)![alt text](image-24.png)![alt text](image-25.png)
### Write Test method
![alt text](image-26.png)![alt text](image-27.png)
### Run the test
![alt text](image-28.png)
### Negative scenario
![alt text](image-29.png)
## 11. Junit @Test Annotation
![alt text](image-30.png)
### Eg- Another SUT
![alt text](image-31.png)
### Create test class
![alt text](image-32.png)![alt text](image-33.png)![alt text](image-34.png)
### Run this
![alt text](image-35.png)
### Negative Scenario
![alt text](image-36.png)
### Find factorial of 1,2
![alt text](image-37.png)![alt text](image-38.png)
### About Test method
![alt text](image-39.png)![alt text](image-40.png)![alt text](image-41.png)![alt text](image-42.png)
### About Test class
![alt text](image-43.png)![alt text](image-44.png)![alt text](image-45.png)
## Quiz
![alt text](image-46.png)![alt text](image-47.png)![alt text](image-48.png)![alt text](image-49.png)![alt text](image-50.png)![alt text](image-51.png)![alt text](image-52.png)
# * ***Section-3 Assertions***
## 12. assertTrue Method
![alt text](image-53.png)
### Go to Api Doc 
![alt text](image-54.png)![alt text](image-55.png)![alt text](image-56.png)
### Coding
![alt text](image-57.png)![alt text](image-58.png)![alt text](image-59.png)![alt text](image-60.png)![alt text](image-61.png)
### Adding 1 student in the list - Negative Scenario
![alt text](image-62.png)![alt text](image-63.png)
### Overloaded method assertTrue(BooleanSuplieer booleanSuplier)
![alt text](image-64.png)
- So Boolean supplier is a functional interface.
- And we have to provide the lambda implementation for the Boolean supplier interface.
- here we are using Boolean supplier because the Boolean supplier logic will be evaluated lazily.
- It means the assert true method will execute this logic only if it is required.
- So this basically supports Java eight features like lambda expression functional interfaces and all those stuff.
- So in order to support, you know, lambda expressions and functional interfaces this method was introduced.
#### Positive Scenario
![alt text](image-67.png)![alt text](image-68.png)
#### Negative Scenario
![alt text](image-65.png)![alt text](image-66.png)
### Overloaded method assertTrue(boolean cond,String message)
![alt text](image-70.png)
#### Positive Senario
![alt text](image-71.png)![alt text](image-72.png)
-  if I run the test case.
- This test case will get passed
    - and you can see the custom error message haven't printed in a console because the test has passed.
- If the test failed,
    - then JUnit will, you know, display the report with this custom failure message.
#### Negative Scenario
![alt text](image-73.png)![alt text](image-74.png)
### Overloaded method assertTrue(BooleanSuplier sup, String message)
![alt text](image-75.png)
- Well notice here the first parameter is the Boolean supplier functional interface.
- So this boolean supplier implementation will be evaluated lazily.
- It means this logic will be executed only when the assertion is executed.
- So this logic won't be executed initially when the assertion is executed at that time, this you know,
Boolean supplier implementation logic will be evaluated.
#### Positive Senario
![alt text](image-76.png)![alt text](image-77.png)
-  if the boolean supplier implementation returns value true, 
    - then this assertion passes and then JUnit test case will be passed.
- If the boolean supplier you know returns the value false,     
    - then assertion false.
### Negative Scenario
![alt text](image-78.png)![alt text](image-79.png)
### Overload method assertTrue(boolean con, Supplier<
String> message)
![alt text](image-80.png)
- So supplier is a functional interface.
- And we have to provide the lambda expression implementation to the supplier functional interface.
#### Positive Scenario
![alt text](image-81.png)![alt text](image-82.png)
#### Negative Scenario
![alt text](image-83.png)![alt text](image-84.png)
### Overloaded method assertTrue(BooleanSuplier sup, Suplier<String> msg)
![alt text](image-85.png)
#### Positive Scenario
![alt text](image-86.png)![alt text](image-87.png)
#### Negative Scenario
![alt text](image-88.png)![alt text](image-89.png)
# 13. assertFalse method
![alt text](image-90.png)
- assert false method is a static method in a assertions class.
-  assert false method verifies that the supplied condition or a given condition should be false.
    - If the supplied condition is false, then the test case will pass.
    - If the supplied condition is true, then the test case will fail.
### assertFalse(boolean cond)
![alt text](image-91.png)
#### Negative Scenario
![alt text](image-92.png)![alt text](image-93.png)
#### Positive
![alt text](image-94.png)![alt text](image-95.png)
### assertFalse(boolean con,String message)
![alt text](image-96.png)
#### +ve 
![alt text](image-97.png)![alt text](image-98.png)
#### -ve
![alt text](image-99.png)![alt text](image-100.png)![alt text](image-101.png)
### assertFalse(BooleanSupplier cond)
![alt text](image-102.png)
- here this boolean supplier condition will be evaluated lazily.
- It means this condition will be executed only when the assertion is executed.
#### -ive
![alt text](image-103.png)![alt text](image-104.png)
#### +ive
![alt text](image-105.png)![alt text](image-106.png)
### assertFalse(BooleanSuplier con,String message)
![alt text](image-107.png)
#### +ive 
![alt text](image-108.png)![alt text](image-109.png)
#### -ive
![alt text](image-110.png)![alt text](image-111.png)
### assertFalse(boolean cond, Supplier<String> msg)
![alt text](image-112.png)
#### -ive
![alt text](image-113.png)![alt text](image-114.png)
#### +ve
![alt text](image-115.png)![alt text](image-116.png)
### assertFalse(BooleanSupplier con,Supplier<String> msg)
![alt text](image-117.png)
#### +ve
![alt text](image-118.png)![alt text](image-119.png)
#### -ve
![alt text](image-120.png)![alt text](image-121.png)
- So this supplier functional interface logic will be evaluated lazily.
- It means this supplier functional interface implementation logic will be executed 
    - only when the test case will fail.
- Otherwise this logic will not be executed.
# 14. assertNull method
![alt text](image-122.png)![alt text](image-123.png)
- This supplier functional interface implementation will be evaluated lazily.
- It means if the test case fails, then only this supplier, you know functional interface implementation will be executed and this message will be shown in the Result.
### Coding
![alt text](image-124.png)
- Add this method in code.
### assertNull(object actual)
#### -ve
![alt text](image-125.png)![alt text](image-126.png)
#### +ve 
![alt text](image-127.png)![alt text](image-128.png)
### assertNull(Object actual,String msg)
#### +ve
![alt text](image-129.png)![alt text](image-130.png)
#### -ve
![alt text](image-131.png)![alt text](image-132.png)
### assertNull(Object actual,Supplier<String> msg)
#### -ve
![alt text](image-133.png)![alt text](image-134.png)
#### +ve
![alt text](image-135.png)![alt text](image-136.png)
# 15. assertNotNull method
![alt text](image-137.png)![alt text](image-138.png)
### assertNotNull(Object actual)
#### -ve
![alt text](image-139.png)![alt text](image-140.png)
#### +ve
![alt text](image-141.png)![alt text](image-142.png)
### assertNotNull(Object actual,String msg)
#### +ve
![alt text](image-143.png)![alt text](image-144.png)
#### -ve
![alt text](image-146.png)![alt text](image-145.png)
### assertNotNull(Object actual,Supplier<String>msg)
#### -ve
![alt text](image-147.png)![alt text](image-148.png)
#### +ve
![alt text](image-149.png)![alt text](image-150.png)
# 16. assertEqual method
![alt text](image-151.png)![alt text](image-152.png)![alt text](image-153.png)![alt text](image-154.png)
- lot of overloaded assertEquals method in documentation
- we look imp one
### assertEquals(int expected, int actual)
- So we are going to check the student id 
#### +ve
![alt text](image-155.png)![alt text](image-156.png)
#### -ve
![alt text](image-157.png)![alt text](image-158.png)
### assertEquals(String expected,Stirng actual)
#### +ve
![alt text](image-159.png)
#### -ve
![alt text](image-160.png)
### assertEquals(Object expected,Object actual)
#### +ve
![alt text](image-161.png)
#### -ve
![alt text](image-162.png)
### assertEqual(int ex,int act,String msg)
![alt text](image-163.png)![alt text](image-164.png)
### assertEqual(String ex, String ac, Supplier<String> msg)
![alt text](image-165.png)![alt text](image-166.png)
# 17. assertNotEqual method
![alt text](image-167.png)
- There are lot of overloaded assertNotEquals() static method in apidoc
### assertNotEquals(int expected,int actual)
![alt text](image-168.png)![alt text](image-169.png)
### assertNotEquals(String expected,String actual)
![alt text](image-170.png)![alt text](image-171.png)
### assertNotEquals(int expected,int actual, String msg)
![alt text](image-172.png)![alt text](image-173.png)
### assertNotEquals(String expected,String actual, Supplier<String> msg)
![alt text](image-174.png)![alt text](image-175.png)
### assertNotEquals(Object expected,Object actual)
![alt text](image-176.png)![alt text](image-177.png)![alt text](image-178.png)
# 18. assertArrayEquals method
![alt text](image-179.png)
- Lot of overloaded assertEquals method are there in document api.
### Coding
![alt text](image-180.png)![alt text](image-181.png)
### assertArrayEquals(String[] ex,String[] actual)
![alt text](image-182.png)
### assertArrayEquals(String[] ex,String[] actual,String msg)
![alt text](image-183.png)![alt text](image-184.png)
### assertArrayEquals(String[] ex,String[] actual,Supplier<String> msg)
![alt text](image-185.png)![alt text](image-186.png)
- So this supplier interface implementation will be evaluated legally.
- It means whenever this test case will fail, then only this logic will be executed.
### assertArrayEquals(Integer[] ex,Integer[] actual)
![alt text](image-187.png)![alt text](image-188.png)
### assertArrayEquals(Integer[] ex,Integer[] actual,String msg)
![alt text](image-189.png)
### assertArrayEquals(Integer[] ex,Integer[] actual,Supplier<String> msg)
![alt text](image-190.png)
# 19. asseertIterableEquals method
- Well, in a collection framework we have a list, set, Queue interfaces.
- And these interfaces extends the iterable interfaces.
- And in order to verify that two lists are, you know, deeply equal, then we can go ahead and use this assertIterableEquals method.

![alt text](image-193.png)![alt text](image-194.png)
- Since list interface extends iterable interface.
- So here we have expected list and actual list.
    - The elements in both the list should be equal.
    - The order of elements should match in both the list.
    - The number of elements should match in both the list.
- Then only the assert iterable equals method will pass, and eventually the test will pass.
### Coding
![alt text](image-195.png)
### assertIterableEquals(Iterable exp,Iterable actual)
![alt text](image-196.png)
- It means both the Iterables are deeply equal 
### assertIterableEquals(Iterable exp,Iterable actual,String msg)
![alt text](image-197.png)
### assertIterableEquals(Iterable exp,Iterable actual,Supplier<String> msg)
![alt text](image-198.png)
- Notice here this supplier functional interface implementation logic is evaluated lazily.
- It means whenever the test case will fail, then only this logic will execute and the message will be displayed in the report.
- If the test case passes, then this logic won't execute.
### differnt datatype
![alt text](image-200.png)![alt text](image-201.png)![alt text](image-202.png)![alt text](image-203.png)
# * ***Section-4: Exception***
# 20. assertThrow Method
![alt text](image-205.png)![alt text](image-206.png)
- For example, let us say we have StudentNotFoundException that extends RuntimeException, 
- and here the RuntimeException is a superclass of StudentNotFoundException
- So instead of specifying the you know StudentNotFoundException One exception to this asserThrow method.
- We can also specify the superclass that is a RuntimeException
- So in this case also the assertion will pass.
### About methods
- The first overloaded assert throws method expect two parameters.
    - First one is expected type, 
    - second one is executable, 
    - expected type is the exception 
    - and executable is the functional interface.

![alt text](image-207.png)
- For example, if I go inside this executable interface, you can see it is a functional interface and
- we have to provide the lambda expression to implement this functional interface.
- And within this executable implementation we specify the code that throws the expected type.
### Coding
![alt text](image-208.png)![alt text](image-209.png)
- Next, let us go ahead and let us create a in a JUnit test case that will test this method.
- And this method basically throws this StudentNotFoundException.
- And we will use assertThrows method to check whether this method, you know throws this correct StudentNotFoundException or not.
### assertThrows(Class expected,Executable excutable)
![alt text](image-210.png)
- if I run the test case, you can see test failed because the StudentNotFoundException is not thrown by this method.
- Because this student Ramesh is already exist in the student list.

![alt text](image-211.png)
### What happen if i pass different type of exception. Instead of StudentNotFound i pass NullPointer
![alt text](image-212.png
### assertThrows(Class expected,Executable excutable,String msg)
![alt text](image-213.png)![alt text](image-214.png)
### assertThrows(Class expected,Executable excutable,Supplier<String> msg)
![alt text](image-215.png)![alt text](image-216.png)
- And this supplier functional interface implementation logic will be evaluated lazily.
- It means whenever the test case fails, then only this logic will be, you know, executed and this message will be displayed in the result.
### Exception hierarchy
- Well, if you go to the StudentNotFoundException, it extends the RuntimeException.
- If we pass RuntimeException instead fo StudentNotFound one it still works great

![alt text](image-217.png)![alt text](image-218.png)
# 21. assertThrowsExactly method
- The difference between assertThrows and assertThrowsExactly method is that 
- in case of assertThrows method, we can specify the inheritance hierarchy like.
    - We can specify the superclass or subclass of a expected type in a assertThrows method.
- But in case of assertThrowsExactly method, we have to specify the exact specific type of the exception.
    - Then only the test case will pass.
    - If we specify the superclass or subclass of actual type of exception, then this you know, assert will fail and eventually the test case will fail.
    - It does not support the inheritance hierarchy.

![alt text](image-221.png)![alt text](image-222.png)
### assertThrowsExactly(Class expectedType, Executable exe)
![alt text](image-223.png)
- The Student Umesh is not present in the list so exactly the StudentNotFoundException is thrown by this method.

![alt text](image-224.png)
- This method throw StudentNotFound exception when some student is not found
### What happen if we thrown RuntimeExecption instead of StudentNotFound
![alt text](image-225.png)
### assertThrowsExactly(Class expectedType, Executable exe, String msg)
![alt text](image-226.png)![alt text](image-227.png)
### Instead i pass NullPointer then
![alt text](image-229.png)
### assertThrowsExactly(Class expectedType, Executable exe, Supplier<String> msg)
![alt text](image-228.png)
### This method return the exception type also
![alt text](image-230.png)
# * ***Section-5: Display Test Names and Disable Tests***
# 22. Display Test Names - @DisplayNames
![alt text](image-232.png)
- The @DisplayName annotation is used to define a custom name for a test method or a test class.
- While displaying meaningful test names can make test results more readable and understandable,
    - especially when running a large suite of test cases.
### Coding
![alt text](image-233.png)![alt text](image-234.png)
- The test class name and test method name are printed in result.

![alt text](image-235.png)![alt text](image-236.png)
### Passing special character and emojis
![alt text](image-237.png)
### emoji
![alt text](image-238.png)![alt text](image-239.png)![alt text](image-240.png)
- serach smily face and copy
# 23. @Disable Disable Test
![alt text](image-241.png)![alt text](image-242.png)
### Known issues.
- If a test is falling due to a known bug or issue that you are working on, you might disable the test until the issue is resolved.
### Incomplete features.
- If a test is for a feature that is not yet fully implemented, you might disable the test until the feature is complete.
### Refactoring.
- When the refactoring code, you might temporarily disable tests that are affected by the changes until the refactoring is complete.
### External dependencies.
- If a test relies on external service or a resource that is currently unavailable, you might disable the test until the dependency is back online.
### Coding
![alt text](image-243.png)![alt text](image-244.png)
### Some more coding
![alt text](image-245.png)![alt text](image-246.png)
### Disable add test method
![alt text](image-247.png)
### We can also optionally pass String to this annotation
![alt text](image-248.png)
### U can disabled multiple test method
![alt text](image-249.png)
# * ***Section-6: Lifecycle Annotation***
# 24. LifeCycle annoatations
![alt text](image-251.png)![alt text](image-252.png)![alt text](image-253.png)![alt text](image-254.png)![alt text](image-255.png)
- JUnit provides a special annotations that help control how our test cases runs.
- Well, these annotations help us set up things before a test case starts and clean up after a test case
finishes.
## Eg
### ***@BeforeEach***
- if you are testing a calculator you might want to reset the calculator to zero before each test.
### ***@AfterEach***
- If you opened a file during the test, you would close it here to make sure everything is tidy and ready
for the next test.
###  ***@BeforeAll***
- connecting to the database.
- So connecting to the database is kind of an expensive task.
    - So you only want to do it once.
### ***@AfterAll***
- So this is where you put all the cleanup tasks that should only happen once, like closing the database
connection or writing a final log entry.
# 25. @BeforeEach Annotation
![alt text](image-256.png)
- This annotation is pretty useful for setting up the test environment, such as initializing, initializing
the objects, and setting initial conditions well.
- Instead of writing the same a repeated code in each and every test method, 
    - we can create a method,
    - and we can keep the common code in that method, 
    - and we can annotate that method with @BeforeEach
annotation.
### Coding
![alt text](image-257.png)![alt text](image-258.png)
####  observation
- Here we are creating instance of Calculator class in every test case.
#### some more
![alt text](image-259.png)![alt text](image-260.png)
### via @BeforeEach annotation
![alt text](image-261.png)![alt text](image-262.png)
### verifying it is working before each test method
![alt text](image-263.png)![alt text](image-264.png)
# 26. @AfterEach Annotation
![alt text](image-267.png)
### Coding
![alt text](image-268.png)![alt text](image-269.png)![alt text](image-270.png)
# 27. @BeforeAll Annotation
![alt text](image-271.png)
- Whenever you annotate a method with @BeforeAll annotation, you must make that method as a static
    - so that it can share the resources among all the test methods,
    -  and also it should call before creating the object.
### Coding
![alt text](image-272.png)![alt text](image-273.png)
# 28. AfterAll Annotations
![alt text](image-275.png)
- Why method must be static
    - as we are going to clean up the shared resources.
    - So, make sure that you make you know method as a static.
### Coding
![alt text](image-276.png)![alt text](image-277.png)![alt text](image-278.png)
### execute single test method
![alt text](image-279.png)
# *** ***Section-7*** Nested Test and Repeated Test
# 29. RepeatedTest






















