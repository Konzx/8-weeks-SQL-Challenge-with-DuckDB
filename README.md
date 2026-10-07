# SQL challenge workspace

Open `8 weeks SQL challenge` as the VS Code workspace folder. All case folders
share the `.venv` in this root; do not create a virtual environment inside each
 folder.

In each notebook, choose **Select Kernel > Python Environments** and select
the root `.venv\Scripts\python.exe`. VS Code uses each notebook's folder as its
working directory, so each case can keep its own `setup.sql` beside its notebook.

To install the shared dependencies, run this from the project root in PowerShell:

```powershell
& .\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

If rebuilding the environment on another machine:

```powershell
py -m venv .venv
& .\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

The Danny's Dinner notebook uses an in-memory DuckDB database per notebook
session. Run its setup cell after starting a kernel. Rerunning setup resets the
sample data without a database file lock. The saved `diner.duckdb` is left intact;
this notebook no longer opens it.
