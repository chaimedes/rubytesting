# Understanding Testing: An Overview
Note: This is being written as I learn. I have done my best to verify the information, but I make no guarantees; I'm still learning -- _Martin_

## Unit Testing
_To be used in parallel with development._

You've written code, just enough to get one component to work. Seal that component up tight (in most cases) before you move on (which makes unit testing ideal for bottom-up implementations, though there are alternatives). 

Every time a new function, model, etc, is complete, write unit tests for it. Ask what responses are expected from that unit, and what pathways should get there. 

The unit becomes a black box, through which you should be able to blindly and confidently send an input and receive the expected output. 

If it doesn't work, you crack open the black box and get back to work.
Perform this for each unit, ignoring (for now) the overall picture and how each unit will be integrated into the whole.

### Unit testing strategies:
- **Automate:** develop or use existing tools to write simple unit tests based on the function of your code
- **Isolate:** move individual units and their sole dependency structures to an external environment. This eliminates noise possibly incurred from other code, and simplifies the process of locating the sources of possible errors and issues with the unit.
- **Test in Tandem:** Write tests alongside the initial code, testing at a very minimal level, checking each function or bit of code, in simple ways that can be removed later, without requiring separate tests to be laboriously written later.
- **Mocking:** Once the system is complete, we'll have the advantage of each piece being robustly tested and can rely on the messages being sent between the part. We make that assumption here by using mock objects to mimic the inputs and outputs that a unit expects. If it responds as it ought to in the situations devised (assuming those situations represent the portending reality) then the unit is reliable.

## Integration Testing
_To test overall functionality and how the parts connect._

How do all the pieces work together? Does everything fit in neatly? Are the units passing messages back and forth in the way you'd expect? 

Wider-ranging logic is considered here, as units begin to operate more broadly as a complete function

Integration testing exposes any flaws in the flow of information, and how components connect through data interfaces.

There are many techniques for integration testing; picking the correct one is largely a question of context.

### Integration testing strategies:
- **Consistency:** Select, and stick with, a testing technique.
- **Plan:** Create pre-planned courses of testing (such as use cases). Ideally these should be considered from the start of the project and as the units were developed.
- **Identify Critical Paths:** Find all critical components, through which all data must flow, and test all connections to these components with extra rigor.
- **Mocking:** Establish mock data before beginning integration testing, to ensure a consistent and unified testing process and reduce the chances of catering the data to the tests.

## System Testing
_Development is complete, now we test before releasing._

It might seem likely that after unit testing and integration testing, there can't be much left to test. Unfortunately, it's all but impossible to catch all contingencies with lower-level testing. 

System testing is the first time testers have the opportunity to use the system as it is intended to be released, plying tests against real, complete systems rather than approximating the supposed inputs and outputs with mock data and the like.

Everything is coming together -- by now all our units are in place. Ideally, our timing is effective, and we know that all our units work correctly and we've caught most edge cases for them, and integration testing has shown we can rely on the logic of our system composition. 

Now we test the full system itself, running it through its paces as we expect it to be used in the real world. No holds are barred here - anything is fair game. System testing also puts the software through its paces in context of the larger solution of which it is part -- such as the logic for an automated vacuum when it is now housed within the vacuum itself and interacting with the hardware components and the user.

Specific strategies for system testing are difficult to describe broadly -- even more than in integration testing, system testing is context-dependent, driven by the use cases for the product and the expectations of the end users.
