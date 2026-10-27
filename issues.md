# Lab 5: Static Code Analysis — Issue Documentation

**File analyzed:** `ticket_booking_system.py`

**Tools used:** Pylint, Bandit, Flake8

Note: Line numbers below refer to the original version of the Python file before fixes.

| Issue | Type | Line(s) | Description | Fix Approach |
|---|---|---|---|---|
| Shell command execution | Security — High | 58 | `os.system()` executes a shell command and may introduce command-injection risk through a filename. | Removed the shell command and used `print()` to display the export message. |
| Weak MD5 hash | Security — High | 47 | MD5 is not appropriate for security-sensitive hashing. | Replaced MD5 with SHA-256. |
| Hard-coded box-office token | Security — High | 70, 79 | A credential was embedded in the source code and printed to the terminal. | Removed the hard-coded token and its print statement. |
| Use of `eval()` | Security — Medium | 42 | Evaluating a string as Python code can execute unintended expressions. | Replaced `eval()` with direct discount arithmetic and a validated discount rate. |
| Mutable default argument | Code quality / Bug | 15 | `order_history=[]` could share a list between function calls. | Changed the default to `None` and initialized a new list inside the function. |
| Bare exception | Error handling | 26 | A bare `except:` hides unexpected errors. | Removed broad exception handling and checked whether the seat exists. |
| Insecure PIN generation | Security — Low | 51 | `random.randint()` is not designed for security-sensitive values. | Used `secrets.randbelow()` to generate a four-digit PIN. |
| Unsafe file handling | Code quality | 55–56 | The file was opened without a context manager or explicit encoding. | Used `with open(..., encoding="utf-8")`. |
| Unused imports and variables | Code quality / Style | 6, 31, 41, 63 | Unused names make the code harder to maintain and trigger analysis warnings. | Removed unused imports and variables. |
| Incorrect `None` comparison | Style | 32 | Compared a value with `None` using `==`. | Used `is None` logic through a safe seat-availability check. |
| Naming and documentation issues | Style / Maintainability | 15 and function definitions | The function naming style was inconsistent and functions lacked docstrings. | Renamed `reserveSeat()` to `reserve_seat()` and added docstrings. |
| Missing final newline | Formatting | End of file | The file did not end with a newline. | Added the final newline and removed trailing whitespace. |

## Summary

The original Pylint score was 5.37/10. After correcting the code and formatting, the score reached 10.00/10. Bandit reported no issues in the final scan, and Flake8 produced no findings after the formatting fix.