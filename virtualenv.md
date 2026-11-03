# Python Virtual Environment Cheatsheet

## 1. What is a Virtual Environment?

A virtual environment is an isolated Python environment for a project.

It allows different projects to use different package versions without affecting each other.

## 2. Create a Virtual Environment

```bash
python3 -m venv venv
```

Here, `venv` is the environment folder name.

## 3. Activate Virtual Environment

Linux / macOS:

```bash
source venv/bin/activate
```

Windows CMD:

```cmd
venv\Scripts\activate
```

Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

## 4. Check Active Python

```bash
which python
```

Check Python version:

```bash
python --version
```

## 5. Install Packages

```bash
pip install requests
```

## 6. List Installed Packages

```bash
pip list
```

## 7. Deactivate Environment

```bash
deactivate
```

## 8. Delete Virtual Environment

Linux / macOS:

```bash
rm -rf venv
```

Windows CMD:

```cmd
rmdir /s /q venv
```

## 9. Create Requirements File

```bash
pip freeze > requirements.txt
```

## 10. Install Packages from Requirements

```bash
pip install -r requirements.txt
```

## 11. Best Practices

- Create a separate virtual environment for each project.
- Do not push the `venv` folder to Git.
- Add `venv/` to `.gitignore`.
- Keep dependencies in `requirements.txt`.

Example `.gitignore`:

```gitignore
venv/
__pycache__/
*.pyc
```
