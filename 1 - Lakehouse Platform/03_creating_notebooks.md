## Notebooks

### Magic Commands
- **`%run`**: Executes another notebook, making its variables available in the current one.  
  **Example**: `%run ./notebook1`
- **`%fs`**: Lists all files and folders at the specified path.  
  **Example**: `%fs ls '/databricks-datasets'`

### Databricks Utilities (`dbutils`)
- **`dbutils`**: Provides an interface to interact with the filesystem.
  - **`dbutils.help()`**: Displays a list of available commands.
  - **`dbutils.fs`**: Manage files.  
    **Example**: `dbutils.fs.help()`
  - **List Files**:  
    ```python
    files = dbutils.fs.ls('/databricks-datasets')
    display(files)
    ```
- **Advantages**: `dbutils` can be integrated with Python code, offering more flexibility than magic commands.

---

## Exporting Notebooks
- **Single notebook**: Export as **IPython (.ipynb)**.
- **Multiple notebooks**: Export as a **DBC Archive** (a zip file containing directories and notebooks).

