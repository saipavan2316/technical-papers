# Python pip Cheatsheet

## 1. What is pip?

`pip` is Python's package installer. It is used to install, update, and uninstall Python packages.

## 2. Check pip Version

```bash
pip --version
```

## 3. Install a Package

```bash
pip install requests
```

## 4. Install a Specific Version

```bash
pip install requests==2.31.0
```

## 5. Upgrade a Package

```bash
pip install --upgrade requests
```

## 6. Uninstall a Package

```bash
pip uninstall requests
```

## 7. List Installed Packages

```bash
pip list
```

## 8. Show Package Information

```bash
pip show requests
```

## 9. Save Installed Packages

```bash
pip freeze > requirements.txt
```

## 10. Install from Requirements File

```bash
pip install -r requirements.txt
```

## 11. Search for Package Information

```bash
pip index versions requests
```

## 12. Check Outdated Packages

```bash
pip list --outdated
```

## 13. Install Packages for a Specific Python

```bash
python3 -m pip install requests
```

## 14. Upgrade pip

```bash
python3 -m pip install --upgrade pip
```

## 15. Useful pip Commands

| Command | Purpose |
|---|---|
| `pip install package` | Install package |
| `pip uninstall package` | Remove package |
| `pip list` | List packages |
| `pip show package` | Package details |
| `pip freeze` | List exact versions |
| `pip check` | Check dependency conflicts |
| `pip --version` | Check pip version |

**Tip:** Activate your virtual environment before installing project dependencies.
