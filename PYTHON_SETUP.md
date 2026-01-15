# Python Package Installation Fix

## The Problem

When you run code in a Quarto document (`.qmd` file), you might see:
```
ModuleNotFoundError: No module named 'pandas'
```

This happens because Quarto's Python engine needs packages installed in the user's Python environment.

## The Solution

**Best Method (Works in Codespaces):**

```bash
python3 -m pip install --user pandas matplotlib numpy seaborn plotly scikit-learn
```

Or install from requirements.txt:

```bash
python3 -m pip install --user -r requirements.txt
```

**The `--user` flag is important** - it installs packages in your user directory where Quarto can find them.

## After Installation

1. Stop any running preview (press Ctrl+C in the terminal)
2. Run `quarto preview` again
3. Your Python code should now work!

## For New Codespaces

The `.devcontainer/devcontainer.json` automatically runs the installation command when the Codespace is created, so this should just work for new users.

## Quick Test

After installation, verify packages are available:

```bash
python3 -c "import pandas, matplotlib; print('✓ Packages installed successfully!')"
```
