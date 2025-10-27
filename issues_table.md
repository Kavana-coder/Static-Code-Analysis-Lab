# 🧩 Inventory System – Issues and Fix Summary

## 🔍 Overview
Static analysis and security scans were performed on the file `inventory_system.py` using:
- **pylint**
- **flake8**
- **bandit**

The following tables summarize all issues before and after fixes, including severity, type, and resolution status.

---

## 🧠 Issues Before Fixes

| **Category** | **Tool** | **Issue Code / Type** | **Description** | **Severity** | **Location** | **Status** |
|---------------|----------|------------------------|------------------|---------------|---------------|-------------|
| Documentation | pylint | C0114 | Missing module docstring | Low | L1 | Fixed |
| Documentation | pylint | C0116 | Missing function/method docstring | Low | Multiple | Fixed |
| Naming | pylint | C0103 | Function names not in `snake_case` (`addItem`, etc.) | Medium | Multiple | Fixed |
| Default Argument | pylint | W0102 | Dangerous default `[]` as argument | Medium | L9 | Fixed |
| String Formatting | pylint | C0209 | Used `%` instead of f-string | Low | L13 | Fixed |
| Exception Handling | pylint | W0702 | Bare `except:` used | High | L21 | Fixed |
| File Encoding | pylint | W1514 | `open()` used without encoding | Medium | L30, L37 | Fixed |
| Global Variable | pylint | W0603 | `global` statement used | Medium | L31 | ⚠️ Justified |
| File Handling | pylint | R1732 | Missing `with` for resource handling | Medium | L30, L37 | Fixed |
| Unused Import | flake8 | F401 | `logging` imported but unused | Low | L2 | Fixed |
| Bare Except | flake8 | E722 | Bare `except` usage | High | L21 | Fixed |
| Silent Exception | bandit | B110 | Try–Except–Pass block detected | High | L21 | Fixed |
| Insecure Function | bandit | B307 | `eval()` used (security risk) | High | L67 | Fixed |

---

## ✅ Issues After Fixes

| **Category** | **Tool** | **Issue Code / Type** | **Resolution Implemented** | **Status** |
|---------------|----------|------------------------|-----------------------------|-------------|
| Documentation | pylint | C0114, C0116 | Added descriptive docstrings for module and all functions | ✅ Fixed |
| Naming | pylint | C0103 | Renamed functions to `snake_case` (PEP8 compliant) | ✅ Fixed |
| Dangerous Default Value | pylint | W0102 | Changed `logs=[]` → `logs=None` and handled internally | ✅ Fixed |
| String Formatting | pylint | C0209 | Updated to f-string syntax | ✅ Fixed |
| Exception Handling | pylint / flake8 | W0702 / E722 | Used specific `except KeyError:` | ✅ Fixed |
| Encoding | pylint | W1514 | Added `encoding="utf-8"` for file operations | ✅ Fixed |
| Global Variable | pylint | W0603 | Retained for compatibility; documented rationale | ⚠️ Accepted |
| File Handling | pylint | R1732 | Used `with open(...) as f:` for safe resource handling | ✅ Fixed |
| Insecure Function | bandit | B307 | Removed `eval()` and replaced with safe print/logging | ✅ Fixed |
| Silent Exception | bandit | B110 | Replaced with meaningful exception handling | ✅ Fixed |
| Unused Import | flake8 | F401 | Removed unused imports | ✅ Fixed |

---

## 🧮 Summary Metrics

| **Tool** | **Before Fix** | **After Fix** |
|-----------|----------------|---------------|
| pylint | 4.80 / 10 | 9.81 / 10 |
| flake8 | 2 Issues | 0 Issues |
| bandit | 2 Issues (1 Medium, 1 Low) | 0 Issues |

---

## 🧱 Remaining Justified Warnings

| **Warning Code** | **Description** | **Justification** |
|-------------------|------------------|--------------------|
| W0603 | Use of `global` variable | `stock_data` is intentionally shared across functions to maintain inventory state; documented for clarity. |

---

## 📊 Outcome
All functional, stylistic, and security issues were successfully resolved. The code now conforms to:
- **PEP8 Naming and Style Guidelines**
- **Safe Exception and File Handling Practices**
- **No remaining Bandit or Flake8 violations**

Final Score: **Pylint 9.81/10**, **0 Bandit issues**, **0 Flake8 issues** 🎯
