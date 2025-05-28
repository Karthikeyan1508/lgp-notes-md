# Testing

Software testing is an organizational process within software development in which business-critical software is verified for correctness, quality, and performance. Software testing is used to ensure that expected business systems and product features behave correctly as expected.

## Types of Tests

### 1. Unit tests
Unit tests are very low level and close to the source of an application. They consist in testing individual methods and functions of the classes, components, or modules used by your software. Unit tests are generally quite cheap to automate and can run very quickly by a continuous integration server.

### 2. Integration tests
Integration tests verify that different modules or services used by your application work well together. For example, it can be testing the interaction with the database or making sure that microservices work together as expected. These types of tests are more expensive to run as they require multiple parts of the application to be up and running.

### 3. Functional tests
Functional tests focus on the business requirements of an application. They only verify the output of an action and do not check the intermediate states of the system when performing that action.

There is sometimes a confusion between integration tests and functional tests as they both require multiple components to interact with each other. The difference is that an integration test may simply verify that you can query the database while a functional test would expect to get a specific value from the database as defined by the product requirements.

### 4. End-to-end tests
End-to-end testing replicates a user behavior with the software in a complete application environment. It verifies that various user flows work as expected and can be as simple as loading a web page or logging in or much more complex scenarios verifying email notifications, online payments, etc...

End-to-end tests are very useful, but they're expensive to perform and can be hard to maintain when they're automated. It is recommended to have a few key end-to-end tests and rely more on lower level types of testing (unit and integration tests) to be able to quickly identify breaking changes.

### 5. Acceptance testing
Acceptance tests are formal tests that verify if a system satisfies business requirements. They require the entire application to be running while testing and focus on replicating user behaviors. But they can also go further and measure the performance of the system and reject changes if certain goals are not met.

### 6. Performance testing
Performance tests evaluate how a system performs under a particular workload. These tests help to measure the reliability, speed, scalability, and responsiveness of an application. For instance, a performance test can observe response times when executing a high number of requests, or determine how a system behaves with a significant amount of data. It can determine if an application meets performance requirements, locate bottlenecks, measure stability during peak traffic, and more. 

### 7. Smoke testing
Smoke tests are basic tests that check the basic functionality of an application. They are meant to be quick to execute, and their goal is to give you the assurance that the major features of your system are working as expected.

Smoke tests can be useful right after a new build is made to decide whether or not you can run more expensive tests, or right after a deployment to make sure that they application is running properly in the newly deployed environment.

---

# Test Driven Development (TDD)

Test-Driven Development (TDD) is a method in software development where the focus is on writing an Automation Tests before writing the actual code for any feature of an application or product. This approach uses short development cycles that repeat to verify the quality and correctness.

TDD simply means a method of coding in which you first write a test, and it fails, then write the code to pass the test of development, and clean up the code. This process is recycled for one new feature or change. In other methods in which you write either all the code or all the tests first, TDD will combine and write tests and code together into one.

## Process of Test Driven Development (TDD)
It is the process in which Test Cases are written before the code that validates those cases. It depends on the repetition of a concise development cycle. Test-driven Development is a technique in which automated Unit tests are used to drive the design and free decoupling of dependencies.

The process of Test-Driven Development (TDD) follows a repetitive cycle called Red-Green-Refactor.

![image](https://github.com/user-attachments/assets/764c980e-37c5-4c15-a0bc-c4a4f4a5e80d)

Run all the test cases and make sure that the new test case fails.

- Red - Create a test case and make it fail, Run the test cases
- Green - Make the test case pass by any means.
- Refactor - Change the code to remove duplicate/redundancy and Refactor code - This is done to remove duplication of code.

Once you completed through the Red-Green-Refactor cycle, you continue repeating the process for the next piece of functionality or unit of code. Every time you write a new test, your code gets better and more reliable, making the overall software stronger.

## Approaches of Test Driven Development (TDD)

There are two main approaches to TDD: Inside Out and Outside In.

### 1. Inside Out:
In Test-Driven Development (TDD), you begin by testing the smallest units of code, such as individual functions or methods. Inside Out approach is also known as the Detroit School of TDD or Classicist.

- Focuses on testing the smallest units first and building up from there.
- The architecture of the software emerges naturally as tests are written.
- Design and architecture are refined during the refactor stage, which can sometimes lead to significant changes.
- Easier to learn for beginners.
- Minimizes the use of mocks.
- Helps prevent over-engineering.

### 2. Outside In:
Outside In approach known as the London School of TDD or Mockist. It will focuses on testing user behavior and interactions.

- Testing starts at the outermost level, such as the user interface, and works inward to the details.
- Relies heavily on mocks and stubs to simulate external dependencies.
- Harder to learn but ensures the code meets overall business needs.
- Design is considered during the red stage, aligning tests with business requirements from the start.

## Test-driven work in Test Driven Development (TDD)
TDD, or Test-Driven Development, is not just for software only. It is also used to create product and service teams as test-driven work. To make testing successful, it needs to be created at both small and big levels in test-driven development.

This means testing every part of the work, like methods in a class, input data values, log messages, and error codes. Other side of software, teams use Quality Control (QC) will check before starting work. These will be checks to help plan and check the outcomes of the tests. They follow a similar process to TDD, with some small changes which are as follows:

1. "Add a check" instead of "Add a test"
2. "Run all checks" instead of "Run all tests"
3. "Do the work" instead of "Write some code"
4. "Run all checks" instead of "Run tests"
5. "Clean up the work" instead of "Refactor code"
6. Repeat these steps

## Advantages of Test Driven Development (TDD)
- Unit test provides constant feedback about the functions.
- Quality of design increases which further helps in proper maintenance.
- Test driven development act as a safety net against the bugs.
- TDD ensures that your application actually meets requirements defined for it.
- TDD have very short development lifecycle.

## Disadvantages of Test Driven Development (TDD)
- Increased Code Volume: Using TDD means writing extra code for tests cases , which can make the overall codebase larger and more Unstructured.
- False Security from Tests: Passing tests will make the developers think the code is safer only for assuming purpose.
- Maintenance Overheads: Keeping a lot of tests up-to-date can be difficult to maintain the information and its also time-consuming process.
- Time-Consuming Test Processes: Writing and maintaining the tests can take a long time.
- Testing Environment Set-Up: TDD needs to be a proper testing environment in which it will make effort to set up and maintain the codes and data.

---

# Debugging

In the context of software engineering, debugging is the process of fixing a bug in the software. When there's a problem with software, programmers analyze the code to figure out why things aren't working correctly. They use different debugging tools to carefully go through the code, step by step, find the issue, and make the necessary corrections.

## Process of Debugging
Debugging is a crucial skill in programming. Here’s a simple, step-by-step explanation to help you understand and execute the debugging process effectively:

### Step 1: Reproduce the Bug
- To start, you need to recreate the conditions that caused the bug. This means making the error happen again so you can see it firsthand.
- Seeing the bug in action helps you understand the problem better and gather important details for fixing it.

### Step 2: Locate the Bug
- Next, find where the bug is in your code. This involves looking closely at your code and checking any error messages or logs.
- Developers often use debugging tools to help with this step.

### Step 3: Identify the Root Cause
- Now, figure out why the bug happened. Examine the logic and flow of your code and see how different parts interact under the conditions that caused the bug.
- This helps you understand what went wrong.

### Step 4: Fix the Bug
- Once you know the cause, fix the code. This involves making changes and then testing the program to ensure the bug is gone.
- Sometimes, you might need to try several times, as initial fixes might not work or could create new issues.
- Using a version control system helps track changes and undo any that don't solve the problem.

### Step 5: Test the Fix
After fixing the bug, run tests to ensure everything works correctly. These tests include:

- Unit Tests: Check the specific part of the code that was changed.
- Integration Tests: Verify the entire module where the bug was found.
- System Tests: Test the whole system to ensure overall functionality.
- Regression Tests: Make sure the fix didn’t cause any new problems elsewhere in the application.

### Step 6: Document the Process
- Finally, record what you did. Write down what caused the bug, how you fixed it, and any other important details.
- This documentation is helpful if similar issues occur in the future.

## Debugging Tools

Debugging tools vary in their functionalities, but they generally provide command-line interfaces to help developers identify and resolve issues. Many also offer remote debugging features and tutorials, making them accessible to beginners. Here are some of the most commonly used debugging tools:

### 1. Integrated Development Environments (IDEs)
IDEs like Visual Studio, Eclipse, and PyCharm offer features for software development, including built-in debugging tools. These tools allow developers to:

- Execute code line-by-line (step debugging)
- Stop program execution at specific points (breakpoints)
- Examine the state of variables and memory
- IDEs support many programming languages and scripting languages, often through open-source plugins.

2. Standalone Debuggers
Standalone debuggers like GDB (GNU Debugger) provide advanced debugging features:
- Conditional breakpoints and watchpoints
- Reverse debugging (running a program backwards)
- These tools are powerful but have a steeper learning curve compared to IDE debuggers.

3. Logging Utilities
Logging utilities log a program’s state at various points in the code, which can then be analyzed to find problems. Logging is particularly useful for debugging issues that only occur in production environments.

4. Static Code Analyzers
Static code analysis tools examine code without executing it to find potential errors and deviations from coding standards. They focus on the semantics of the source code, helping developers catch common mistakes and maintain consistent coding styles.

5. Dynamic Analysis Tools
Dynamic analysis tools monitor software as it runs to detect issues like resource leaks or concurrency problems. These tools help catch bugs that static analysis might miss, such as memory leaks or buffer overflows.

6. Performance Profilers
Performance profilers help developers identify performance bottlenecks in their code. They measure:
- CPU usage
- Memory usage
- I/O operations

---
