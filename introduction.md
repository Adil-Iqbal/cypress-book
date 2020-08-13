# 1 Introduction
This book is about Cypress, a modern, all-in-one, end-to-end testing framework. It was written because Cypress was made to be easy to learn, but not as easy to master. The Cypress Getting Started guide is great for beginners, though it will not hold your hand past the basics. I've written this book to help the uninitiated use Cypress, and help those who are already using Cypress, inch closer to mastery.

## 1.1 About the Author
My name is Adil Iqbal.  I began my programming career at a start-up called GeoNotebook. Prior to my arrival, the dev-team had dabbled with testing. As we built out the app, a day came when all of our existing tests were out-dated and began to break. I was assigned to revamp our entire testing setup. Not only did I update the testing setup and fix the old tests, I began to write new tests as well and established myself as the go-to testing guru at my company.

I also learned that *tests are best written by the developer who built the feature being tested.* I presented Cypress to my team members, taught them the ropes, and made myself available as they began to write tests themselves. Then I thought, *why limit my newfound expertise to just the developers at my company?*

## 1.2 Target Audience
This book is designed with three categories of readers in mind: 

1. The Non-User who would like to get started.
2. The New User who has begun, but would like to get better.
3. The Advanced User who would like a refresher.

There are built-in features to address the concerns of users who are at one of these levels. We'll also discuss some pre-requisite knowledge and *suggested* software needed follow along with this book. Most importantly though, I want to touch on exactly what this book will get you.

### 1.2.1 The Non-User
This book will present information in a digestible way that will set you up to *improve quickly*. The unit called **The Basics** assumes no prior knowledge of testing. Once you've finished reading the first unit, you'll be directed to a github repository that will test out your knowledge by creating tests for a mock web app. You'll want to have a good handle on the basics before moving on to the next unit.

That said, Cypress does *a lot* to make new users feel comfortable using their tool. The Getting Started section on their website is a great place to start. When Cypress is initially installed, they include example test files that you can play around with to get a good feel of how Cypress operates. They've published a ton of example code if you need help beyond what's provided out of the box. The documentation is also stellar and designed for easy referencing.


 - ***Cypress Getting Started:*** [https://docs.cypress.io/guides/getting-started/installing-cypress.html#System-requirements](https://docs.cypress.io/guides/getting-started/installing-cypress.html#System-requirements)
 - ***Cypress Examples:*** [https://docs.cypress.io/examples/examples/recipes.htm](https://docs.cypress.io/examples/examples/recipes.htm) 

 
### 1.2.2 The Average User
When you feel ready to continue your journey, the next unit lies waiting. It's called **Advanced**, and there you'll start building the skills necessary to test enterprise applications. The **Advanced** unit is building on the knowledge you acquired in **The Basics** unit.  That's why its recommended that even those who have prior experience with Cypress take the time to read through **The Basics**. Once you've finished reading the **Advanced** unit, you'll be directed to another github repository, where you'll be asked to apply what you've learned. *Be warned: This time, there will be no hand-holding.*

* ***jQuery Selection API:*** [https://api.jquery.com/category/selectors/](https://api.jquery.com/category/selectors/)

### 1.2.3 The Advanced User
 Each chapter in this book ends with a Chapter Summary and each unit ends with a Cheat Sheet that lists the commands for at-a-glance referencing. If you've used this book to learn Cypress the first time around, you'll notice that the chapters are numbered and most topics have been indexed.


### 1.2.4 Pre-requisite Familiarities
No matter where you are in terms of your experience with Cypress, there are some things you need to be familiar with *before* you can start working with Cypress. Notice, I did not use the word "expert" or "master," I used the word "familiar." You just need to be able to work with these pre-requisites. That said, the more you know about the following technologies, the more you'll be able to do with Cypress:

 1. **Javascript** - Cypress is a Javascript library. In fact, you may hear me say this statement a few times during the book: "Cypress is *just* Javascript." The more adept you are at working with Javascript, the better off you will be when its time to develop tests. We'll review the most important Javascript concepts briefly - but it's your responsibility to have this skill on board as you read through this book.
 
 2. **jQuery** - Cypress uses jQuery under the hood. Many of the methods that Cypress implements are closely mirroring some of the features you will find in jQuery. The more familiar you are with jQuery, and in particular its Selection API, the better off you will be when developing tests. We will briefly some jQuery, but its your responsibity to have this skill on board as you read through this book.
 
 3. **JSON** - Cypress uses a JSON in many places (one of which is their configuration file). It becomes especially important when we start talking about fixtures.
 4. **NodeJS** - Cypress is a node module, so any experience you have with node will be of benefit.
 
 ### 1.2.5 Value Proposition
 
 It's important to note what this book is offering you. By the time you finish reading this book (and hopefully the exercises that it recommends) you should be able to do the following:

1. After reading **The Basics** unit, you should be able to:
	* Install, configure, and run Cypress in your NodeJS project.
	* Begin writing tests by selecting elements on the page and interacting with them.
	* Run all or *some* of your tests.
	* Do the recommended exercises and understand them.
	* Open and review someone elses test code and not get too flustered by what you see.
	* Begin writing your own tests with some confidence.

2. After reading **The Advanced** unit, you should be able to:
	* Use the Test Runner to help you develope tests.
	* Build complex app state across multiple tests and reset app state prior to every test run.
	* Write conditional tests.
	* Use scoping and aliasing when selecting elements.
	* Be able to work with cookies.
	* Drag and drop, upload file, and select an option from a dropdown menu.
	* Interact with the server without using the user interface.
	* Write custom commands.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg5OTg3NjcwMl19
-->