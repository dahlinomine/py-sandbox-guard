# PySandbox Guard

![security](https://img.shields.io/badge/security-blue?style=flat-square) ![sandbox](https://img.shields.io/badge/sandbox-blue?style=flat-square) ![python](https://img.shields.io/badge/python-blue?style=flat-square)

A lightweight Python execution sandbox using RestrictedPython for agent tool-use.

## Overview
PySandbox Guard provides a secure, isolated environment for executing untrusted Python code snippets, specifically designed for LLM agents and tool-use applications. By leveraging `RestrictedPython`, it prevents unauthorized access to the underlying operating system and sensitive built-in functions while maintaining the performance of native execution.

## Features
*   **Restricted Execution:** Blocks access to dangerous modules like `os`, `sys`, and `subprocess` by default.
*   **Safe Globals:** Provides a curated environment where only explicit, safe built-ins are accessible.
*   **Agent Optimized:** Lightweight enough to be used as a high-frequency tool in AI agent loops.
*   **Resource Control:** Facilitates clean separation between host logic and dynamic script execution.

## Installation
Ensure you have Python 3.8+ installed. Clone the repository and install the necessary dependencies:

```bash
git clone https://github.com/yourusername/py-sandbox-guard.git
cd py-sandbox-guard
pip install -r requirements.txt
```

## Usage
Run the main script to see the sandbox in action. You can define custom strings of Python code to be executed within the restricted environment.

```bash
python main.py
```

**Example:**
```python
from sandbox_guard import SecureSandbox

sandbox = SecureSandbox()
code = "result = 10 + 20"
output = sandbox.execute(code)

print(output['result']) # Output: 30
# Accessing __import__('os') would raise a SecurityError
```

## Contributing
Contributions are welcome! Please submit a Pull Request for any bug fixes or feature enhancements. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the [MIT License](LICENSE).