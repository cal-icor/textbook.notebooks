### 📌 Pull Request Checklist  

#### 1️⃣ **Data Repository Submission**  
- [ ] I have uploaded all necessary data files and scripts to the **data repository**: [Data Repository](https://github.com/cal-icor/textbook.data)  
- [ ] I have created a **pull request** in the data repository and linked it below:  
  - **Data PR:** [textbook.data PR](https://github.com/cal-icor/textbook.data/blob/main/.github/pull_request_template.md)

#### 2️⃣ **Notebook Updates**  
- [ ] My notebook **references data files via URLs** instead of local file paths  
  - Example:  
    ```python
    pd.read_csv("https://cal-icor.github.io/textbook.data/<YOUR_INTITUTION_NAME>/<YOUR_COURSE_NAME>/your_file.csv")
    ```
- [ ] If my notebook imports a local Python script, I have used `httpimport`  
  - Example:  
    ```python
    import httpimport
    with httpimport.remote_repo("https://cal-icor.github.io/textbook.data/<YOUR_INTITUTION_NAME>/<YOUR_COURSE_NAME>"):
        import my_script
    ```

#### 3️⃣ **Execution & Validation**  
- [ ] I have run the notebook **from start to finish** and confirmed that it executes **without errors**  
- [ ] All outputs are correct and expected  

#### 4️⃣ **Repository Updates**  
- [ ] I have updated [`requirements.txt`](https://github.com/cal-icor/textbook.notebooks/blob/main/requirements.txt) with any additional packages needed for my notebook  
- [ ] I have updated the **Table of Contents** in [`_toc.yml`](https://github.com/cal-icor/textbook.notebooks/blob/main/_toc.yml)  

  **If my subject already exists:**  
  - I added my notebook to the appropriate section  
  - Example:
    ```yaml
    - caption: Environmental Science, Policy, and Management
      numbered: true
      chapters:
      - file: espm-regression
      - file: <your file name>  ###################
    ```

  **If my subject is new:**  
  - I created a new chapter at the end of `_toc.yml`  
  - Example:
    ```yaml
    - caption: <YOUR SUBJECT>
      numbered: true
      chapters:
      - file: <NOTEBOOK 1 NAME>
      - file: <NOTEBOOK 2 NAME>
    ```

#### 5️⃣ **Final Review**  
- [ ] I have **reviewed my changes** to ensure all files are correct and formatted properly  
- [ ] I have **linked my data PR** in this submission  
- [ ] I acknowledge that PRs that do not follow these guidelines **may be rejected**  

---

### 🔗 **Pull Request Summary**  
- **Notebook Name:** `<NOTEBOOK_NAME>.ipynb`  
- **Linked Data PR:** [Insert link here]  
- **New Dependencies (if any):** `<List any added packages>`  
- **TOC Updated:** `Yes / No`  

---

## 🚀 Need Help?  
If you encounter any issues, check the [Troubleshooting Guide](https://github.com/cal-icor/textbook.notebooks/blob/main/README.md#-common-issues--troubleshooting) or ask for assistance.  
