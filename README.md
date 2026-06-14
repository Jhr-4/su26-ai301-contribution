# Contribution 1: [Add compatibility test for `$stdDevSamp`](https://github.com/documentdb/functional-tests/issues/197)

* **Contribution Number:** 1 
* **Student:** Jay Rana  
* **Issue:** [Add compatibility test for `$stdDevSamp`](https://github.com/documentdb/functional-tests/issues/197)
* **Status:** Phase II

---

## Why I Chose This Issue

I chose this issue because it seems like I'm contributing meaningfully to a project by adding more extensive tests, while also learning things myself. While I have experience with basic unit testing in Python, this issue gives me the opportunity to further learn and improve on it as this is an actual database engine.

This also will be my first issue/contribution, thus I will be learning how to read/follow documentation and effectively contribute to a large project.

---

## Understanding the Issue

### Problem Description

There is no bug or error. The main problem/issue is that currently the expression $stdDevSamp only has a smoke test, it doesn't have actual test cases that test the operator and it's edge cases. 


### Expected Behavior

There should be test cases that test for functonality. For us that means there should be test cases that pass with MongoDB as the DB engine. 

### Current Behavior

Currently only the smoke tests run. No other test cases are present to test functonlaity and edge cases of the operator.

### Affected Components

The only affected component/files are in `documentdb_tests/compatibility/tests/core/operator/expressions/accumulator/stdDevSamp/` in which we will create files for the test cases.

---

## Reproduction Process

### Environment Setup

When setting up the main issue I faced was that my WSL was brining up errors after updating Docker after a really long time of it just being idle. However, the fix was really simple and everything worked smoothly after restarting WSL. After this I just had to follow the documentation for installing MongoDB on Docker and installing the the dev-requirements. 

**Working Branch:** https://github.com/Jhr-4/functional-tests/tree/feature/stddevsamp-second-pass

### Steps to Reproduce

1. Run MongoDB in the background on Docker using: `docker run -d -p 27017:27017 --name mongo-test mongo:latest`
2. Run the test cases using: `pytest --connection-string mongodb://localhost:27017 --engine-name mongodb ./documentdb_tests/compatibility/tests/core/operator/expressions/accumulator/stdDevSamp/ -v`
3. There's only one test case that runs which is the smoke test which doesn't do the actual functionality and edge case testing.

### Reproduction Evidence

- **Commit showing reproduction:** https://github.com/Jhr-4/functional-tests/commit/1f76b70f2a15143c18e57e9d0b5de3894f83c2b1
- **Screenshots/logs:** ![Screenshot showing tests.](./image.png)
- **My findings:** Basically currently there are no functional tests, only some tests.

---

## Solution Approach

### Analysis

There is not error or bug. The issue is that there are no test cases for stdDevPop currently that test for edge cases of the operator that may throw an error. 

### Proposed Solution

Will create a new file for test cases that test the expression throughly.  

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** $stdDevSamp needs test cases that check for edge cases.

**Match:** Currently there are many other issues too regaring tests for oppoarators. However, it seems like none of the testing of the other opporators has been done yet. I will mostly be following the example for testing for $divide that was provided in the documentation.

**Plan:** 
1. Create a new file for test cases.
2. Add tests for regular usability, all data types including ones that should be errors or valid, datatype mismatches, test for null returns, check for double/Decimal128. Esecnially I will follow the documentation and the testing guidlines/checklist layed out at: https://github.com/documentdb/functional-tests/blob/main/docs/testing/TEST_COVERAGE.md.
3. Check for sucess and passing of test cases with MongoDB, submit a pull request, itterate if something is missing, etc.

**Implement:** 

**Review:** I will follow the checklist provided here in the [main repo]( https://github.com/documentdb/functional-tests/blob/main/docs/testing/TEST_COVERAGE.md). I will ensure all points are hit and self review.

**Evaluate:** Ensure all my tests pass. Make sure all the points in the contibution doc are followed. There is no other way to evaluate really besides creating the PR and getting feedback from the repo maintainers.

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
