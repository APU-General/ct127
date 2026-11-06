# CT127 Programming for Data Analysis: Lab Environment

This repository is a ready-made Python environment for the CT127 demos and labs. It runs in **GitHub Codespaces**, a VS Code editor in your web browser, so you do not need to install Python or any packages on your own computer. Everyone gets the same setup, so code that works for your lecturer works for you.

## What is in the environment

- Python 3.12
- Jupyter notebook support, with the kernel **Python (CT127)** already set up
- These packages: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`, `scikit-learn`, `openpyxl`, `requests`, `ipykernel`

## Get your own copy

1. Sign in to GitHub.
2. Select **Use this template**, then **Create a new repository**.
3. Name it (for example `ct127-labs`), choose **Private**, and select **Create repository**.

Your work is saved in your own repository, so it is still there next time.

## Open it in a Codespace

1. In your new repository, select **Code**, then **Codespaces**, then **Create codespace on main**.
2. Wait for the setup to finish. The first start takes a few minutes. Later starts are much faster. Do not open a notebook until the editor has fully loaded, or the kernel may not be ready yet.
3. When the editor opens, this page is shown first. You are ready to work.

When you finish, close the browser tab. The Codespace stops after a period of inactivity. You can also stop it from the Codespaces page on GitHub (github.com/codespaces). You have a monthly free allowance of Codespaces time, so stop it when you are not using it.

## Your Codespace expires after 30 days

**GitHub deletes a Codespace that has not been opened for 30 days.** When that happens, everything inside it is lost:

- notebooks and files you did not push to GitHub
- the data files you uploaded from Moodle
- any extra packages you installed

Your repository on GitHub is not deleted. So:

- **Push your work to GitHub regularly** (see "Save your work to GitHub" below). Anything you have pushed is safe.
- If your Codespace is deleted, create a new one from the same repository. It starts from scratch with a fresh environment and your pushed files. **Download the data from Moodle and upload it again.** Extra packages need `uv add` again, unless you pushed your changes, in which case they come back automatically.

## Add the lab data

Data files are **not** stored in this repository. Download them from Moodle for each lab, then upload them to the `data` folder in your Codespace.

1. Download the lab's data files from Moodle to your computer. Unzip them first if they come as a `.zip`.
2. In the Codespace, open the **Explorer** panel on the left (the top icon, or **Ctrl+Shift+E**).
3. Upload the files in one of these ways:
   - **Drag and drop:** drag the files from your computer's folder and drop them onto the `data` folder in the Explorer.
   - **Upload menu:** right-click the `data` folder, select **Upload...**, choose your files, and select **Open**.
4. Check that the files appear inside the `data` folder in the Explorer.

Tips:

- Upload to `data`, not to the main folder. If you drop a file in the wrong place, drag it into `data`.
- Files keep the name they had on Moodle. Use that exact name in your code, including capital letters.
- You can upload several files at once. To upload a whole folder, drag the folder in.
- Files in `data` are never committed to Git, so you can safely leave them there.

## Work on a notebook

1. Create a notebook: select **File**, **New File**, then **Jupyter Notebook**. You can also open a notebook your lecturer gave you. Save it with **Ctrl+S** (**Cmd+S** on a Mac).
2. If you are asked to choose a kernel, select **Python (CT127)**. You can also select **Python Environments**, then `.venv`.
3. Run a cell with **Shift+Enter**.

To read a data file from a notebook in the main folder, use a path that starts with `data/`:

```python
import pandas as pd

df = pd.read_csv("data/your_file.csv")
```

If your notebook is in a subfolder, use `../data/your_file.csv` instead.

## Install an extra package

If a lab needs a package that is not in the list above, open a terminal (**Terminal**, then **New Terminal**) and run:

```bash
uv add package-name
```

For example, `uv add plotly`. Then restart your notebook's kernel with **Restart** in the notebook toolbar.

Do not use `pip install` in this environment. Use `uv add`, which keeps the package list and your environment in step.

## Save your work to GitHub

Your notebooks are saved in the Codespace, but save them to GitHub too. Do this at the end of every session:

1. Open **Source Control** in the left bar (the branch icon).
2. Type a short message, such as `Lab 2 done`.
3. Select **Commit**, then **Sync Changes**.

## If something goes wrong

- **The notebook says "Select Kernel":** choose **Python (CT127)** as described above.
- **A package is missing:** run `uv add package-name` in the terminal.
- **The Codespace is broken or was deleted:** your pushed files are safe in your repository. Delete the Codespace on github.com/codespaces and create a new one. You will need to upload the Moodle data again.
- **A data file is not found:** check that the file is in the `data` folder and that the name in your code matches exactly, including capital letters.

If you are still stuck, ask your lecturer.
