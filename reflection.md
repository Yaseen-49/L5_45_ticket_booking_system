# Lab 5: Static Code Analysis — Reflection

## 1. What is static code analysis, and why is it useful?

Static code analysis examines source code without executing it to identify potential bugs, security vulnerabilities, and coding-style violations. It is useful because it helps detect problems early, improves readability, and makes software easier to maintain.

## 2. What issues did you identify and fix?

I identified multiple issues, including unsafe use of `eval()`, MD5 hashing, insecure PIN generation, shell command execution, a mutable default argument, broad exception handling, unused imports, and formatting violations. I corrected these issues by using safer Python features, improving exception handling, validating discount values, and following Python naming and formatting conventions.

## 3. What are the differences between Pylint, Bandit, and Flake8?

Pylint examines overall code quality, naming conventions, missing documentation, and potential programming mistakes. Bandit focuses on common security vulnerabilities and unsafe coding patterns. Flake8 identifies style and formatting problems, including unused imports, whitespace violations, and missing final newlines. Using all three gives a more complete assessment than relying on a single tool.

## 4. What did you learn from this lab, and what are the limitations of static analysis?

I learned that code can run successfully and still contain security and maintainability problems. Static analysis helped me identify and correct those problems systematically. My Pylint score improved from 5.37/10 to 10.00/10, Bandit reported no remaining issues, and Flake8 passed without findings. However, static analysis cannot guarantee that a program is completely correct or secure. Runtime testing, functional tests, and code review are still important.