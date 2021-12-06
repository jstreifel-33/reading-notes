# Random Module, Risk Analysis, and Test Coverage

## Random Module

[Source: pythonforbeginners - How to use the Random Module in Python](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

`random` is a module in the Python standard library with many useful functions:

* `randint(low, high)` - generated an integer between two given numbers
* `random()` - generates a random number between 0 and 1
* `choice(sequence)` - generates a random value from a provided sequence
* `shuffle(list)` - shuffles elements of a list in place
* `randrange(start, stop[, step])` - generates a randomly selected element from a range

## Risk Analysis

[Source: edureka.co - what is Risk Analysis in Software Testing and how to perform it?](https://www.edureka.co/blog/risk-analysis-in-software-testing/)

Risk can be defined as the probability of an unwanted incident.

Certain risks are unavoidable. The reading provides the following examples:

* Time allocated for testing
* A defect leakage due to the complexity or size of an application
* Urgency from clients to deliver a project
* Incomplete requirements

In the case that a risk in encountered, a risk assessment meeting should be held, and risk magnitude indicators should be assigned ot risks:

* **High risk** - non-tolerable. Company might face a loss
* **Medium risk** - tolerable but undesirable. Company may suffer financially but risk is limited.
* **Low risk** - tolerable. Little or no external exposure and no financial impact.

There are different types of risks to consider when identifying risks:

1. Business Risks - risk introduced by customer or company, not product.
2. Testing Risks - familiarity with testing tools, ability to use them effectively
3. Premature Release Risk - risk associated with releasing unsatisfactory or untested software.
4. Software Risks - risks associated with development process.

When assessing a risk, there are 3 perspectives to consider:

* Effect of the risk
* Cause
* Likelihood

## Test Coverage

[Source: martinfowler.com - Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)

Test coverage can be used to detect untested code in a codebase. Some workplaces may require minimum test coverage, but this can lead to tests being written that are not actually useful

when considering test coverage, weigh it against your acceptable risk and the complexity of creating a test for uncovered code.

On the flip side, there can be indicators of having too many tests. If small changes in the codebase lead to sweeping changes in tests, there is a good chance you have too many overlapping or duplicate tests.

Test Coverage is about finding a balance, and taking a measured approach to testing to ensure that enough code is tested that unforeseen risks won't cause catastrophic bugs.
