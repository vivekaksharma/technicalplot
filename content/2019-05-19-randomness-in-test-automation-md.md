---
title: Randomness in Test Automation
date: 2019-05-19T14:55:05.759Z
cover: /assets/randomness.jpg
slug: Automation
category: Automation
tags:
  - '#Automation #QE'
---
One of the major goals of Test Automation is to ensure no regressions. The automated tests are meant to run on regular basis (usually nightly builds) and detect if any code changes break existing features. This means that tests once automated execute a single path without deviation. The approach is successful and gives us an idea of the health of the builds.

What is Randomness?

Randomness is the ability to inject a random behaviour in one or more steps of an  automated test. This is useful when you wish to get coverage outside of the "straight path" automated tests and uncover different kinds of bugs.

**Pros:**

1. Randomness helps achieve test coverage across different paths. It can be helpful when your Test Matrix is huge and it is impractical to run the same test across variety of combinations

2. Helps exploratory test the software in an automated manner

3. Could be used for Chaos Monkey types of tests

4. Can help determine tests with dependencies (on results of previous tests) and fix them. This would in turn make the tests robust and independent

**Cons:**

1. Can lead to unpredictable test steps and hence making if difficult to generate a reproducible environment for a bug 

2. Can lead to additional debugging time

The cons can be overcome with a carefully chosen set of tests against which randomness can be applied. Secondly, if the test framework's logging capabilities are strong - it makes it easier to identify the exact test steps and reproduce the failure more predictably

**Techniques for Randomness**

1. Random function provided by the underlying programming languages. For example: Math.random() in Java, random module in python; Collections.shuffle() for Java collections

2. Add conditional statement in your test step based on criteria like if Date is even/odd or Day of the week is Mon/Wed/Fri

3. Utilize the underlying test framework randomization capabilities, such as TestNG's IMethodInterceptor interface to reorder the list of test methods or pytest-random-order plugin in pytest
