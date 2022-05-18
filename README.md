# Testing Quick notes 📙

> _All code is guilty until proven innocent._

#

### Kinds of Tests

- Unit Tests
- Integration Tests
- E2E Tests

## Unit Tests

#

Unit-testing is the testing of a unit of code (e.g. a single function) without the need for the infrastructure that that unit of code relies on. i.e. test it in isolation.

If, for example, the function that you're testing connects to a database and does an update, in a unit test you might not want to do that update.

A unit test is a test written by the programmer to verify that a relatively small piece of code is doing what it is intended to do. They are narrow in scope, they should be easy to write and execute, and their effectiveness depends on what the programmer considers to be useful. The tests are intended for the use of the programmer, they are not directly useful to anybody else, though, if they do their job, testers and users downstream should benefit from seeing fewer bugs.

_Unit tests should only depend on the tested implementation unit; they should not depend on external components such as databases, network services, web browser interaction. When such external elements are required, unit tests use mock objects._

## Integration Tests

#

An integration test is done to demonstrate that different pieces of the system work together. Integration tests can cover whole applications, and they require much more effort to put together. They usually require resources like database instances and hardware to be allocated for them. The integration tests do a more convincing job of demonstrating the system works (especially to non-programmers) than a set of unit tests can, at least to the extent the integration test environment resembles production.

An integration test is done when the tested object or module is working like it should be, with other bits of code.

### Analogy

> _During the process of manufacturing a ballpoint pen, the cap, the body, the tail and clip, the ink cartridge and the ballpoint are produced separately and unit tested separately. When two or more units are ready, they are assembled and Integration Testing is performed. For example, whether the cap fits into the body or not._

_It's not about what they are, it's about what they do._

### Difference

The key difference, to me, is that integration tests reveal if a feature is working or is broken, since they stress the code in a scenario close to reality. They invoke one or more software methods or features and test if they act as expected.

On the opposite, a Unit test testing a single method relies on the (often wrong) assumption that the rest of the software is correctly working, because it explicitly mocks every dependency.

Hence, when a unit test for a method implementing some feature is green, it does not mean the feature is working

## End to End Testing

#

End-to-end testing is a methodology used to test whether the flow of an application is performing as designed from start to finish. The purpose of carrying out end-to-end tests is to identify system dependencies and to ensure that the right information is passed between various system components and systems.

End-to-end testing involves ensuring that the integrated components of an application function as expected. The entire application is tested in a real-world scenario such as communicating with the database, network, hardware and other applications.

For example, a simplified end-to-end testing of an email application might involve:

- Logging in to the application
- Accessing the inbox
- Opening and closing the mailbox
- Composing, forwarding or replying to email
- Checking the sent items
- Logging out of the application

Another Example:

Start of by being the user and use the application from the web UI. Then verify that all the actions that have been triggered by the webUI has been performed correctly. For example if you create an order from the gui, verify that the order has been created all the way down to the the database or at the third party integration
