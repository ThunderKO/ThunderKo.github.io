# JUnit 5

## Table of Contents
1. [Introduction](#introduction)
2. [Why JUnit5](#why-junit5)
3. [JUnit Vintage](#junit-vintage)
4. [Key Differences from JUnit4](#key-differences-from-junit4)
5. [New Annotations](#new-annotations)

## Introduction

- Started as a project called JUnit Lambda
    - Crowdfunding campaign in 2015 raised €54,000
    - Corporate Sponsors include Pivotal and American Express
- First GA Release September 10th, 2017

## Why JUnit5

- JUnit 4 Originally Released in February 2006
    - Java 6 Released in December 2006
- ~12 Minor Releases since 2006
- Significant changes to Java Language
- Still the de facto standard for Java unit testing

- JUnit 5 leverages new features of Java 8
    - Lambda Expressions
    - Streams
    - Java 8 or Higher is required
- Designed for better integration and extensibility

## JUnit Vintage

- Optional JUnit 5 Library
- Provides a test runner for JUnit 3 and 4 tests using JUnit 5
    - Allows easy migration to JUnit 5

## Key Differences from JUnit4

| JUnit 4 | JUnit 5 |
| :-----------: |:--------------|
| @Test(expected = Foo.class) | Assertions.assertThrows(Foo.class... |
| @Test(timeout = 1) | Assertions.assertTimeout(Duration... |
| @RunWith(SpringJUnit4ClassRunner.class) | @ExtendWith(SpringExtension.class) |

## New Annotations

| JUnit 4 | JUnit 5 |
| :-----------: |:--------------|
| @Before | @BeforeEach |
| @After | @AfterEach |
| @BeforeClass | @BeforeAll |
| @AfterClass | @AfterAll |
| @Ignored | @Disabled |
| @Category | @Tag |
