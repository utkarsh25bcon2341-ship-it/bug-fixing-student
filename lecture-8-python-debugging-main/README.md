# Lecture 8: Fixing a Buggy Python Script

## Project Overview

This project demonstrates testing and debugging a Python script using
`unittest` and the **RED → FIX → GREEN** cycle.

The project contains:

-   `student_utils.py` --- utility functions for calculating an average,
    checking whether a mark is passing, and assigning a grade.
-   `test_student_utils.py` --- unit tests that check the expected
    behaviour of those functions.

## Bugs Investigated

The assignment identifies three bugs:

1.  **Average calculation:** The function divides by `len(marks) - 1`
    instead of the number of marks. This can produce an incorrect
    average (for example, `135.0` instead of `90.0` for `[80, 90, 100]`)
    and can fail for a single mark.
2.  **Passing-mark boundary:** A mark of exactly `40` should pass, so
    the comparison must include the boundary.
3.  **Grade ordering:** The `Distinction` condition must be checked
    before broader grade conditions; otherwise, a score such as `95` can
    be classified as `First`.

## How to Run the Tests

Run the test file from the directory containing both Python files:

``` bash
python test_student_utils.py
```

## RED → FIX → GREEN Workflow

-   **RED:** Run the tests against the original buggy implementation and
    record the failures.
-   **FIX:** Correct the implementation in `student_utils.py`. Keep the
    expected results in the tests unchanged.
-   **GREEN:** Run the same test suite again and confirm that all **9
    tests pass**.

A successful run should end with output similar to:

``` text
Ran 9 tests in ...
OK
```

## Submission Checklist

-   [ ] `student_utils.py` with the corrected implementation
-   [ ] `test_student_utils.py` containing the 9 tests
-   [ ] Evidence of the RED test run
-   [ ] Evidence of the GREEN test run showing all 9 tests pass
-   [ ] `bug_notes.md` documenting each bug, evidence, cause, and fix
-   [ ] This `README.md`
-   [ ] GitHub commits showing the failing stage and the later fix as
    separate commits

## Note

This README follows the Lecture 8 assignment instructions. Update the
file list or details if your repository uses different filenames.
