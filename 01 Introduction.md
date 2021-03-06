# 1 Introduction
This book is about working with Cypress: a modern, all-in-one, end-to-end testing framework. It was written because Cypress was made to be easy to learn, but not as easy to master. The Cypress Getting Started guide is great for beginners, though it will not hold your hand past the basics. I've written this book to help the uninitiated use Cypress, and help those who are already using Cypress, inch closer to mastery.

## 1.1 About the Author
My name is Adil Iqbal.  I began my programming career at a start-up called GeoNotebook. Prior to my arrival, the dev-team had dabbled with testing. As we built out the app, a day came when all of our existing tests were out-dated and began to break. I was assigned to revamp our entire testing setup. Not only did I update the testing setup and fix the old tests, I began to write new tests as well. Over time, I established myself as the go-to testing guru at my company.

I also learned that *tests are best written by the developer who built the feature being tested.* I presented Cypress to my team members, taught them the ropes, and made myself available as they began to write their own tests. Then I thought, *why limit my newfound expertise to just the developers at my company?*

## 1.2 Target Audience
This book is designed with three categories of readers in mind: 

1. The New User who would like to get started.
2. The Professional who uses Cypress, but would like to get better.
3. The Veteran who would like a refresher.

There are built-in features to address the concerns of users who are at one of these levels. We'll also discuss some pre-requisite knowledge and *suggested* software needed follow along with this book. Most importantly though, I want to touch on exactly what this book will get you.

### 1.2.1 The New User
This book will present information in a digestible way that will set you up to *improve quickly*. The first unit is called **The Basics** and it assumes no prior knowledge of testing. Through-out the **The Basics** unit, you'll be directed to a github repository that will test out your knowledge by creating tests for a dynamic web app. You'll want to have a good handle on the basics before moving on to the next unit.

That said, Cypress does *a lot* to make new users feel comfortable using their tool. The Getting Started section on their website is a great place to start. When Cypress is initially installed, they include example test files that you can play around with to get a good feel of how Cypress operates. They've published a ton of example code if you need help beyond what's provided out of the box. The documentation is also stellar and designed for easy referencing.


 - ***Cypress Getting Started:*** [https://docs.cypress.io/guides/getting-started/installing-cypress.html#System-requirements](https://docs.cypress.io/guides/getting-started/installing-cypress.html#System-requirements)
 - ***Cypress Examples:*** [https://docs.cypress.io/examples/examples/recipes.htm](https://docs.cypress.io/examples/examples/recipes.htm) 

 
### 1.2.2 The Professional
When you feel ready to continue your journey, the next unit lies waiting. It's called **Advanced**, and there you'll start building the skills necessary to test enterprise applications. The **Advanced** unit is building on the knowledge you acquired in **The Basics** unit.  That's why we recommend that even those who have prior experience with Cypress take the time to read through **The Basics**. Once you've finished reading the **Advanced** unit, you'll be directed to another github repository, where you'll be asked to apply what you've learned. *Be warned: This time, there will be no hand-holding.*

### 1.2.3 The Veteran
 Each chapter in this book ends with a Chapter Summary and each unit ends with a Cheat Sheet that lists the commands for at-a-glance referencing. If you've used this book to learn Cypress the first time around, you'll notice that the chapters are numbered and most topics have been indexed.


### 1.2.4 Pre-requisite Familiarities
No matter where you are in terms of your experience with Cypress, there are some things you need to be familiar with *before* you can start working with Cypress. You're not expected to be a grandmaster at any of these skills. That said, the more you know about the following technologies, the more you'll be able to do with Cypress:

 - **HTML and the DOM** - Cypress was built to test web apps. Which means, if you plan on using Cypress, you'll be interacting with the DOM in some way. We'll briefly touch on this topic later in the book.

 - **Javascript** - Cypress is a Javascript library. In fact, you may hear me say this statement a few times during the book: "Cypress is *just* Javascript." The more adept you are at working with Javascript, the better off you will be when its time to develop tests. We'll review the most important Javascript concepts briefly - but it's your responsibility to have this skill on board as you read through this book.
 
 - **jQuery** - Cypress uses jQuery under the hood. Many of the methods that Cypress implements are closely mirroring some of its features. The more familiar you are with jQuery, and in particular its Selection API, the better off you will be when developing tests. We will briefly review *some* jQuery, but its your responsibity to have this skill on board as you read through this book.
 
 - **JSON** - Cypress uses a JSON in many places (one of which is their configuration file). It becomes especially important when we start talking about fixtures.
 
 - **NodeJS** - Cypress is a node module, so any experience you have with node will be of benefit.
 
 ### 1.2.5 Value Proposition
 By the time you've finished reading this book, you will be able to do the following:
 
 - **Begin using Cypress *routinely*.** Most people think testing is a cumbersome affair. Cypress simplifies the setup so much, that testing your apps can become routine. This book goes through the Installation and Setup process in detail. It'll shows you exactly how fast and flexible it can be.

 - **Make your tests more reliable and less likely to break.** A test that works most of the time *but not always* is referred to as a "flaky tests." This book will train you to write testing code that will work 100% of the time. It will also help you develop the intuition to spot potential flakiness before it ever becomes an issue.
 - **Gain the knowledge necessary to tackle tricky testing situations.** If you're working on an especially innovative app, chances are that you're going to run into a testing situation that has never existed before. Though we can't predict your exact test case -- we can help show you how to write custom Cypress commands. We can also show you how to use the existing commands together in interesting ways.  We can expose you to dynamic testing and how that works within the Cypress testing paradigm. All of these things *and more* will be covered in this book. 
 
 ## 1.3 Testing in General
Brief history, features, etc.
### Types of Tests
There are many categories of tests that I won't list, but suffice it to say, they tend to fall into three broad categories:
 - **Unit Tests** - Small units of code are tested in isolation to see if they work.

 - **Integration Tests** - *Many* small units are tested as a group to see how well they interact.

 - **End-to-End** - Also known as "E2E tests," these are fully "zoomed out" tests that includes all systems and sub-systems as they exist to the end user.

By the descriptions above, you should see that these three categories exist on a spectrum with Unit tests on one end and E2E tests on the other. Let's talk about the benefits and draw backs of Unit Tests vs. E2E tests. (We can infer that Integration tests will have a blend of the benefits and drawbacks of Unit and E2E tests.)

### Benefits and Drawbacks
As we compare E2E and Unit Tests, I want you to keep in mind the worst case senario for a hypothetical tech company: They have an extremely large code base that is expanding by the minute, they have a limited budget, a limited number of developers, and the industry they're in is fairly saturated. How would these benefits and drawbacks affect that company?

**Testing Runtime** 
Unit tests are extremely fast and can provide feedback to developers in *near* realtime. By contrast, E2E tests are slower because they have a lot more moving parts. 

**Code Coverage per Keystroke**
E2E tests have by far the best code coverage per keystroke, since they are testing all systems and sub-systems together. By contrast, unit tests can only cover the unit they are actually testing.

**Localizing Cause of Test Failure**
Unit tests will get you to localize the cause of failure much more precisely than an E2E test. Since, with E2E tests, all systems and sub-systems are in play. 

**Prioritizing Bugs**
E2E Tests are far better at triage then unit tests. Because you can see how each individual bug affects the end user. In that sense, you can distribute resources much more effectively.

**Overall Cost to the Tech Company**
 Unit tests represent a large upfront cost since it would take developers a lot of keystrokes to get the unit tests up and running, but the operational cost of unit tests (that is, the time spent waiting for test results and bug fixing) would be much lower. By contrast, writing E2E tests, the up front cost is much lower, and operational cost would to be higher.  However, our hypothetical tech company doesn't live in a vacuum. E2E tests are quicker to get up and running, and that means they have a reduced time-to-market for any given feature they are developing, which, in turn, reduces opportunity cost.


### Why Cypress?
### Principles of Testing
