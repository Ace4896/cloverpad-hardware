# Jupyter Notebooks

This folder contains any Jupyter Notebooks I used while figuring out the calculations needed for this project.

- [magnet-distance](./magnet-distance.ipynb): Determining magnet distance from the magnetic flux value.

## Usage

You can preview these notebooks with GitHub's online viewer, but if you want to view/edit them locally, some setup is needed:

- Install Python 3.12 or higher
- [Create a virtual environment and activate it](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment):

```bash
python -m venv .venv

# Bash
source .venv/bin/activate

# PowerShell
.\.venv\bin\Activate.ps1
```

- Install requirements with `pip`:

```bash
pip install -r requirements.txt
```

- Start up Jupyter:

```bash
jupyter notebook
```
