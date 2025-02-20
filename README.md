# 📖 Jupyter Notebook Repository  

This repository houses Jupyter notebooks for various courses. Each notebook references external datasets and Python scripts stored in a separate data repository. Follow the instructions below to correctly add and integrate your notebooks.  

---

## 🚀 How to Add a Notebook  

### 1️⃣ **Upload Your Data Files**  

Before adding your notebook, ensure that all required data files and scripts are uploaded to the **data repository**:  
📌 **Follow the instructions here:** [Data Repository README](https://github.com/cal-icor/textbook.data/blob/main/README.md)  

### 2️⃣ **Make a Pull Request in the Data Repository**  

- Submit a pull request in the **data repo**: [Data PRs](https://github.com/cal-icor/textbook.data/pulls)  
- **Link your data pull request in your notebook pull request** to provide visibility.  

### 3️⃣ **Update Your Notebook to Reference External Data Files**  

Modify your notebook so it properly accesses the uploaded data files via URLs instead of local paths.  

#### 📂 **For CSV, JSON, and Other Data Files**  

**Before:**  

```python
pd.read_csv("iris.csv")
```

**After:**  

```python
pd.read_csv("https://cal-icor.github.io/textbook.data/<YOUR_COURSE_NAME>/iris.csv")
```

#### 🐍 **For Local Python Scripts**  

If your notebook imports a local Python file, update it to load from the data repository.  

**Before:**  

```python
import data101grader  # Assuming data101grader.py exists locally
```

**After:**  

```python
import httpimport
with httpimport.remote_repo("https://cal-icor.github.io/textbook.data/<YOUR_COURSE_NAME>"):
    import data101grader
```

### 4️⃣ **Ensure Your Notebook Runs Without Errors**  

- Execute the entire notebook and confirm that all cells run successfully.  
- Fix any broken links, incorrect imports, or missing dependencies.  

### 5️⃣ **Update `requirements.txt`**  

If your notebook requires additional Python packages, **add them to** [`requirements.txt`](https://github.com/cal-icor/textbook.notebooks/blob/main/requirements.txt).  

### 6️⃣ **Update the Table of Contents (`_toc.yml`)**  

The `_toc.yml` file manages the structure of the notebook collection. Update it to include your new notebook.  

#### 📌 **If the Subject Already Exists**  

- Find the subject section in `_toc.yml`.  
- Add your notebook file name (`- file: <YOUR NOTEBOOK NAME>`) at the same indentation level.  

**Example: Adding a new ESPM notebook**  

```yaml
- caption: Environmental Science, Policy, and Management
  numbered: true
  chapters:
  - file: espm-regression
  - file: <your file name>  ###################
```

#### 📌 **If the Subject Does Not Exist**  

- Create a new **chapter** section at the end of `_toc.yml`.  
- Add a `file` entry for each notebook.  

**Example: Adding a new subject (e.g., Data Ethics)**  

```yaml
- caption: Data Ethics
  numbered: true
  chapters:
  - file: data-ethics-intro
  - file: fairness-in-ml
```

---

## 🤝 Contribution Guidelines  

Want to add a new notebook? Follow these steps:  

1. **Fork** this repository.  
2. **Clone** the forked repo to your local machine.  
3. **Create a new branch** named after your course (`git checkout -b <YOUR_COURSE_NAME>`).  
4. **Make your changes** (update your notebook, fix errors, update `_toc.yml`, etc.).  
5. **Commit & Push** your changes (`git push origin <YOUR_BRANCH_NAME>`).  
6. **Open a Pull Request** (PR) in this repository.  
7. **Link your data PR** from the [data repo](https://github.com/cal-icor/textbook.data/pulls).  
8. Wait for review and approval before merging. 🚀  

---

## 📝 Example Pull Request Format  

When submitting a PR, include the following details:  

### 📌 Summary  

- Added a new notebook: `<NOTEBOOK_NAME>.ipynb`  
- Updated `_toc.yml` to include the notebook  
- Updated `requirements.txt` to include new dependencies  
- Linked data PR: [Data PR #123](https://github.com/cal-icor/textbook.data/pull/123)  

### ✅ Checklist  

- [ ] My notebook runs without errors  
- [ ] All external file references use URLs  
- [ ] Updated `_toc.yml`  
- [ ] Updated `requirements.txt` (if necessary)  
- [ ] Linked the corresponding data PR  

---

## 🛠 Common Issues & Troubleshooting  

🔹 **Issue: Notebook fails to load data**  
✅ **Solution:** Ensure that the file URL is correct and formatted as:  

```python
pd.read_csv("https://cal-icor.github.io/textbook.data/<YOUR_COURSE_NAME>/your_file.csv")
```

🔹 **Issue: ImportError for a local Python file**  
✅ **Solution:** Use `httpimport` to import files from the data repo. Example: 

```python
import httpimport
with httpimport.remote_repo("https://cal-icor.github.io/textbook.data/<YOUR_COURSE_NAME>"):
    import my_script
```

🔹 **Issue: Missing Packages When Running the Notebook**  
✅ **Solution:** Add required packages to `requirements.txt` and ensure it's up to date.  

🔹 **Issue: Notebook Not Listed in Table of Contents (`_toc.yml`)**  
✅ **Solution:** Double-check `_toc.yml` and make sure your notebook is added correctly under the correct subject.  

---

## 📜 License  

This repository is licensed under the MIT License. See [LICENSE](LICENSE) for details.  

---

## 🎯 Final Checklist Before Submitting Your Pull Request  

✅ **Linked your data PR in your notebook PR**  
✅ **Updated all data references to use URLs**  
✅ **Ensured the notebook runs without errors**  
✅ **Updated `requirements.txt` if needed**  
✅ **Updated `_toc.yml` to include the new notebook(s)**  

---

## 🛠 Need Help?

If you encounter any issues, feel free to ask for help by opening an issue or reaching out to jonathanferrari AT berkeley.edu.


📌 **Reminder:** PRs that do not follow these guidelines may be rejected.  
