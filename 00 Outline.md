
  
  
  

# Seducing Cypress
* TOC
* Introduction
	* About the Author &amp; Purpose of Book
	* Easy to learn but hard to master. Help people inch closer to mastery.
	* Docs are thorough, but are built for referencing – no handholding past the absolute basics. Easy to learn does not mean easy to master. Trying to help people inch themselves closer to mastery.
	* Target Audience
		* Who is this book for?
		* Help devs begin.
		* Help beginners to intermediate.
		* Help intermediates inch closer to expertise.
		* Refresher for experts.
		* Overview of Cypress for anyone who wants to learn more.
	* Pre-requisite Familiarities
		* Javascript
		* HTML // DOM (#ToDo)
		* JSON
		* jQuery
		* NodeJS
	* What you'll be able to do after reading this book.
		* Begin using Cypress (if you haven't already)
		* Make your tests more reliable.
		* Tackle tricky testing situations.
		* Ability to tackle novel situations.
	* What you'll need to begin practicing.
		* NodeJS
		* Google Chrome
		* Visual Studio Code
		* VLC Media Player
	* Testing in General
		* Types of testing intro info.
		* Benefits and drawbacks of each.
		* How does Cypress fit in to this paradigm.
		* Basic principles preview (how does it map).
# The Basics
* Installing, Setup, and Orientation
	* What you'll need
		* Compatible browser (chrome) 
		* NodeJS 
		* IDE, (visual studio)
			* Cypress Helper
			* Auto-complete
			* Docs in code. 
		* .mp4 video player (VLC)
	* Installation
		* git clone repo
		* `npm init`
		* `npm install cypress --save-dev` 
	* Command Line
		* `npx cypress run`
		* flags categorized
			* special attention to `--config`
	* Directory Tour
		* integrations - where your tests live.
		* support 
			* commands.js - custom commands.
			* index.js - run once before any and all tests. imports custome commands.
		* fixtures
			* data! 
			* stores common data used across any and all tests.
			* see docs for more info
	* Configuration
		* cypress.json
		* `"$schema":  "https://on.cypress.io/cypress.schema.json",`
		* baseUrl
		* all options categorized
			* special attention to folder redirection
	* Splitting dev and prod testing.
	* `Cypress.config` API and examples.
	* Summary and Cheat sheet
* Foundational Concepts
	* DOM and Javascript (always changing).
	* Promises and Async code.
	* Enque and the cy object.
	* Parent commands, child commands, and hybrids.
	* Retry ability simplified. timeout references.
* Writing Tests: Basics
	* Goal of this section.
	* Balancing Priorities
		* Automating user behavior. (User story)
		* Interacting versus consuming.
		* Automate your _own_ behavior. (Developer story)
		* Your organization's priorities.
	* Manipulating the browser
		* User story
		* Commands and explanations.
		* Cheat sheet
	* Identifying Elements.
		* User Story
		* Get
		* jQuery Selection API
			* Substring search
			* AND and OR logic.
			* Pseudo Selectors
		* Contains
		* Selection Helpers
		* Cheat Sheet
	* Interacting with Elements
		* User Story
		* Commonly used action commands.
		* Chaining action commands
		* Yeilding a subject
		* .then and .each
		* Cheat Sheet
	* Assertions
		* Developer Story
		* Should method
			* A get method will fail if any chained should methods fail in the test runner. `"not.exist"`
		* Commonly used chainers
		* Chainers
		* Implicit versus Explicit Assertions
		* Cheat Sheet
	* Application
		* Building App State & Assertions
			* Maybe before, during, interspersed or after.
		* Login Error Test
		* Login Success Test
	* Test Composition
		* Where does all that code go?
		* The it function.
		* The describe function
			* Context alias
			* Single describe
			* Multiple describes
			* Nested describes
			* Global (root-level) describe

		* Mocha hooks intro
			* Before
			* Before Each
			* After
			* afterEach

	* Running Tests: Basics
		* The Test Feedback loop
		* Overview of the Process
		* CLI Command
			* `npm cypress run` vs `npm cypress open`
		* Test Launcher Tour
		* Using .skip
		* Using .only
		* Remove .skip and .only before pushing or use https://github.com/bahmutov/stop-only
		* It functions should be standalone. (more in next section)
		* The Test Runner Tour: Basics
			* Command log
			* Run Time
			* Pass, Fail, Pending
			* Auto-scroll, stop, and re-run
	* Unit exercises
		* Repo instructions
			* git clone & npm install
			* place all exercises in same it block unless asked to created another one.
			* try yourself without reference.
			* Then reference book and docs.
			* Then check solutions below.
			* Hand holding until exercise #10.
		* Exercise Solutions and references
			* Exercise 1 - Run a test and visit repo
			* Exercise 2 - Set the baseUrl and $schema in cypress.json
			* Exercise 3 - Select a button, run an assert, and click it.
			* Exercise 4 - Only use the selector cy.get("button"). Ensure that there are three buttons on the page. Click these buttons in this order (first, last, middle).
			* Exercise 5 - Check three checkboxes and submit.
			* Exercise 6 - Check one of two radios and submit.
			* Exercise 7 - Select div, and check a checkbox in sibling div and submit.
			* Exercise 8 - Type a string into a text field and submit
			* Exercise 9 - Get the contents of a p tag and type it into the textbox.
			* Exercise 10 - Only use the following selector: get("[type=checkbox]"). 4x4 matrix of checkboxes. Only check checkboxes with label "Pick Me!" and click submit.
			* Exercise 11 - 4x4 matrix of checkboxes. Only check checkboxes with id attr of "a" OR "b"
			* Exercise 12 - 4x4 matrix of checkboxes. Only check checkboxes with id attr of "a" AND "b".
			* Exercise 13 - Create a second it block and ask it to log "second it block." Create a after hook and insert the following code (scroll down, click button)
 			* Exercise 14 - Add a before, beforeEach, and afterEach hook that clicks the buttons on toolbar below.
# Advanced
* Writing Tests: Advanced
	* The Test Runner Tour: Advanced
		* The Test Runner is a dev tool.
		* Re-run on save + .only or .skip
		* Decreases test feedback loop.
		* (and flag because it can get annoying).
		* Selector Playground
		* DOM Screenshots and the screenshot() command.
		* Command Log pinning & the console.
		* Useful in debugging.
		*  [https://github.com/bahmutov/cypress-skip-and-only-ui](https://github.com/bahmutov/cypress-skip-and-only-ui)

* Test Composition
	* it block
		* Pending it functions
		* Call back to standalone it.
			* Repeated code in subsequent it functions 
			* Remove problematic code?
			* Merge tests?
			* Use a before hook.
	* Building complex app state.
		* It alone inside a describe.
		* It with a before hook inside a describe.
		* It with two before hooks inside a describe.
		* It with three before hooks, one inside a nested describe.
		* It with four before hooks, one of them being a root level describe.
		* Cleaning app state
			* Excessive state cleaning runtime problem 
			* State cleaning via login and dangling state.
			* Cleaning global app state using before and support/index.js
			* Clean app state in before hook, THEN build new app state.
			* Failure in one test can affect subsequent tests. Tests that are further down on the list are more flaky. Sometimes clean app state *within* the it block prior to its execution.
* Identifying Elements
	* Focused element. (google.com example) (contrast with .focus())
	* Narrow search filter/not
	* Scoping within/root
	* Aliasing? Before each, cleared before hook.
	* Window/document/title
	* Cookies
		* Clear cookie behavior \*clears before every it
		* getCookie and getCookies
	* Intro to wrap
* Interacting with the Server
	* Request
	* Repetitive DOM manipulation
	* Testing the API.
	* Circumventing CSRF and forwarding redirects.

# MORE TO COME!
