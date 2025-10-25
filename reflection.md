1. Which issues were the easiest to fix, and which were the hardest? Why?
The easiest issues to fix were mostly formatting and style-related problems. Removing trailing whitespace, deleting unused imports, and breaking long lines were straightforward. Adjusting the function names from camelCase to snake_case was also simple since it did not affect the logic of the program.

The hardest issues were those that required structural or logical changes. Specifically, replacing the use of global variables, fixing the mutable default argument, and improving error handling required more thought. These changes involved refactoring how data was managed and ensuring the program still worked correctly after the modifications. Removing the use of eval() and introducing type validation were also more complex because they required changes to the control flow and additional checks to maintain the same functionality safely.

2. Did the static analysis tools report any false positives? If so, describe one example.
Most of the warnings from the static analysis tools were valid and helpful. However, there was one instance that could be considered a false positive. Pylint flagged the use of a general exception handler (except Exception as e:) as “catching too general exception.” While this is generally a good rule, in a small standalone script like this, catching all exceptions was initially intended to prevent the program from crashing unexpectedly. In this specific context, it was a safe and intentional use, so the warning was more of a stylistic suggestion rather than a real problem.

3. How would you integrate static analysis tools into your actual software development workflow?
Static analysis tools can be integrated both locally and in a continuous integration (CI) workflow. During development, tools like Pylint, Flake8, and Black can be run automatically each time code is saved or committed. This can be achieved using pre-commit hooks that check for linting and formatting issues before any code is pushed to a shared repository.

In a CI environment, the same tools can be added as part of the build pipeline. For example, a GitHub Actions or GitLab CI configuration could run linting commands on every pull request. If the linting score drops below a certain threshold or errors are found, the build can fail automatically. This ensures that coding standards are maintained consistently across the team and that issues are caught early in the development cycle.

4. What tangible improvements did you observe in the code quality, readability, or potential robustness after applying the fixes?
After applying the fixes, the overall code quality improved significantly. The code is now much easier to read due to consistent formatting, meaningful naming conventions, and clear documentation through docstrings. Replacing global variables with a class structure made the program more modular and easier to extend in the future.

The code also became more robust. File handling now uses context managers, which prevents resource leaks, and exception handling is more specific and controlled. Type checking ensures that invalid data does not break the program, and removing the eval() call eliminated a potential security vulnerability.

Overall, the program is now more maintainable, predictable, and aligned with Python best practices. These changes not only improved the static analysis scores but also made the code safer and more professional.
