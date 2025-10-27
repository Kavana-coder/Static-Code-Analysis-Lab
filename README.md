# Static-Code-Analysis-Lab


## Overview
A simple inventory management system built in Python that maintains stock data, allows item addition/removal, and generates reports.  

This project demonstrates **static code analysis**, **linting**, and **security testing** using:
- pylint
- flake8
- bandit

## Fixed Issues Summary
- Removed insecure `eval()` call
- Added docstrings and followed PEP8 naming
- Used `with` statement for safe file I/O
- Replaced bare `except` with specific exceptions

## Linting & Security Results
| Tool | Before Fix | After Fix |
|------|-------------|-----------|
| Pylint | 4.80/10 | 9.81/10 |
| Flake8 | 2 Issues | 0 Issues |
| Bandit | 2 Issues | 0 Issues |

## How to Run
```bash
python fixes/inventory_system_fixed.py

