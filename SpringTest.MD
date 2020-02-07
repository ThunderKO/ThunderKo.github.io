# Testing Spring Framework

## Table of Contents
1. [Test Terminology](#test-terminology)
2. [Testing Goals](#testing-goals)
3. [Test Scope Dependencies](#test-scope-dependencies)

## Test Terminology

- **Code Under Test** - This is the code (or application) you are testing
- **Test Fixture (JUnit Doc)**
    - Fixed state of a set of objects used as a baseline for running test.
    - Purpose is to ensure there is well known and fixed environment
    - In which tests run and results are repeatable
    - Example: input data, mock objects, loading database with known data, etc
- **Unit Tests / Unit Testing** - Code written to test code under test
    - Designed to test specific sections of code
    - Percentage of lines of code tested is code coverage
        - Ideal coverage is in the 70-80% range
    - Should be ‘unity’ and execute very fast
    - Should have no external dependencies
        - *Example*: no database, no Spring context, etc
- **Integration Tests** - Designed to test behaviours between objects and parts of the overall system
    - Much larger scope
    - Can include the Spring Context, database, and message brokers
    - Will run much slower than unit tests
- **Functional Tests / End-to-End Testing** - Typically means you are testing the running application
    - Application is live, likely deployed in a known environment
    - Functional touch pointes are tested
        - *Example*: Using a web driver, calling web services, sending / receiving messages, etc

- **TDD** - Test Driven Development 
    - Write tests first, which will fail, then code to ‘fix’ test.
- **BDD** - Behaviour Driven Development 
    - Builds on TDD and specifies that test of any unit of software should be specified in terms of desired behaviour of the unit.
    - Often implemented with DSLs to create natural language tests
    - JBehave, Cucumber, Spock
    - *Example*: given, when, then

- **Mock** - A fake implementation of a class used for testing. Like a test double.
- **Spy** - A partial mock, allowing you to override select methods of a real class.

## Testing Goals

- Majority of your tests to be unit tests
- Use spring context makes your tests exponentially slower
- Test specific business logic in unit tests
- Test interactions in integration tests
- Pyramid:
    - Base: unit test
    - Middle: integration test
    - Top: function test
    
## Test Scope Dependencies

- Spring-boot-starter-test
    - JUnit - The de-facto standard for unit testing Java applications
    - Spring Test and Spring Boot - Utilies and integration test support for Spring Boot applications
    - AssertJ - A fluent assertion library
    - Hamcrest - A library for matcher objects
    - Mockito - A Java mocking framework
    - JSONassert - An assertion library for JSON
    - JSONPath - XPath for JSON

- JUnit 4
    - Originally written by Erich Gamma and Kent Beck (creator of extreme programming)
    - JUnit 5

| Annotation    | Description           |
| :------------ |:--------------|
| @Test | Identifies a method as a test method. |
| @Before | Executed before each test. It is used to prepare the test environment. (e.g., read input data, initialize the class). |
| @After | Executed after each test. It is used to cleanup the test environment. It can also save memory by cleaning up expensive memory structures. |
| @BeforeClass | Executed once, before the start of all tests. Methods marked with this annotation need to be defined as static to work with JUnit. |
| @AfterClass| Executed once, after all tests have been finished. Methods annotated with this annotation need to be defined as static to work with JUnit. |
| @Ignore | Marks that the test should be disabled. |
| @Test(expected = Exception.class) | Fails if the method does not throw the named exception. |
| @Test(timeout = 10) | Fails if the method takes longer than 100 millseconds. |
| @RunWith(SpringRunner.class) | Run test with Spring Context |
| @SpringBootTest | Search for Spring Boot Application for configuration |
| @TestConfiguration | Specify a Spring configuration for your test |
| @MockBean | Injects Mockito Mock |
| @SpyBean | Injects Mockito Spy |
| @JsonTest | Create a Jackson or Gson object mapper via Spring Boot |
| @WebMvcTest | Used to test web context without a full http server |
| @DataJpaTest | Used to test data layer with embedded database |
| @JdbcTest | Like @DataJpaTest, but does not configure entity manager |
| @DataMongoTest | Configures an embedded MongoDB for testing |
| @RestClientTest | Creates a mock server for testing rest clients |
| @AutoConfigureRestDocks | Allows you to use Spring Rest Docs in tests, creating API documentation |
| @BootstrapWith | Used to configure how the TestContext is bootstrapped |
| @ContextConfiguration | Used to direct Spring how to configure the context for the test |
| @ContextHierarchy | Allows you to create a context hierarchy with @ContextConfiguration |
| @ActiveProfiles | Set which Spring Profiles are active for the test |
| @TestPropertySource | Configure the property sources for the test |
| @DirtiesContext | Resets the Spring Context after the test (expensive to do) |
| @WebAppConfiguration | Indicates Spring should use a Web Application context |
| @TestExecutionListeners | Allows you to specify listeners for testing events |
| @Transactional | Run test in transaction, rollback when complete by default |
| @BeforeTransaction | Action to run before starting a transaction |
| @AfterTransaction | Action to run after a transaction |
| @Commit | Specifies the transaction should be committed after the test |
| @Rollback | Transaction should be rolled back after test. (Default action) |
| @Sql | Specify SQL sciprts to run before |
| @SqlConfig | Define meta data for SQL scripts |
| @SqlGroup | Group of @Sql annotations |
| @Repeat | Repeat test x number of times |
| @Timed | Similar to JUnit's timeout, but will wait for test to complete, unlike JUnit |
| @IfProfileValue | Indicates test is enabled for a specific testing environment |
| @ProfileValueSourceConfiguration | Specify a profile value source |

