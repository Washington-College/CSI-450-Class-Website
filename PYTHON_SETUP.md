# Python Package Installation Fix

## The Problem

When you run code in a Quarto document (`.qmd` file), you might see:
```
ModuleNotFoundError: No module named 'pandas'
```

This happens because Quarto's Python engine may use a different Python environment than your terminal.

## The Solution

Run this command in the terminal to install packages for the correct Python:

```bash
python3 -m pip install -r requirements.txt
```

Or install specific packages:

```bash
python3 -m pip install pandas matplotlib numpy seaborn
```

## Why This Works

- `python3 -m pip` ensures packages are installed for the same Python that Quarto uses
- Regular `pip install` might install to a different Python environment

## For New Codespaces

The `.devcontainer/devcontainer.json` has been updated to automatically run:
```
python3 -m pip install -r requirements.txt
```

This means students creating new Codespaces won't have this issue.

## Quick Test

After installation, verify it works:

```bash
python3 -c "import pandas; print('Success!')"
```

Then try rendering your Quarto document again.
