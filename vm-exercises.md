# Virtual Machine (VM) Exercises

## :information_source: Read this before getting started
- The two exercises should not replicate the exact actions shown in your screencast. The goal of exercises is for learners to apply what was learned in the screencasts to new problems or situations. This is best pedagogical practice for retaining and building skills. For example, this can be done by using another dataset between screencasts and exercises or focusing on a different portion of the dataset.
- Power BI / Tableau specific: We can only run free versions of BI software in our virtual machine exercises. In the case of Power BI, make sure the exercises can run on [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) without any additional paid products. 
- Unsure what the scope of an exercise should be? Here's an [example](https://campus.datacamp.com/courses/introduction-to-power-bi/getting-started-with-power-bi?ex=14) from Introduction to Power BI. The first chapter of most DataCamp courses are free, so take a look at our [BI courses](https://learn.datacamp.com/courses?technologies=Tableau&technologies=Power%20BI) to get a feel for how we assess and guide learners.

## 1st VM Exercise

#### Dataset

- [x] Add datasets used to the `datasets/` folder

#### Files

- [x] **Initial**: Add file to the `exercises/`  folder with the name `ex-1-intial.twbx` or `ex-1-intial.pbix` or `ex-1-initial.yxmd`, depending if you are auditioning for a Tableau/Power BI/Alteryx course.
- [x] **Solution**: Add file to the `exercises/`  folder with the name `ex-1-sol.twbx` or `ex-1-sol.pbix` or `ex-1-sol.yxmd`

#### Learning Objective

*Learners will be able to create static and dependent dropdown lists using named ranges in Excel, ensuring accurate hierarchical data selection, such as dynamically filtering subcategories based on a selected main category.*

---

#### Context

*Creating static and dependent dropdown lists using named ranges is a critical skill for improving data entry accuracy and consistency in Excel. By implementing these dropdowns, users can limit input choices to predefined options, reducing errors and ensuring that data conforms to specific rules. Dependent dropdowns are especially useful in hierarchical data scenarios, such as selecting a department and dynamically filtering the corresponding roles, streamlining workflows and saving time. This approach is widely applicable in real-life situations like HR systems, inventory management, and financial reporting, where maintaining clean and reliable datasets is crucial.*

---

#### Steps to be Executed by the Student (Max 6)

*Steps need to be followed.*

- **Step 1: Load the Dataset**

  1. Open the Excel file named `HR_Validation_Exercises_Dataset.xlsx` from the `Datasets/Dropdowns` folder.
  2. Examine the dataset:
     - The first row contains the main categories: **HR**, **Finance**, **IT**, **Marketing**, and **Sales**.
     - The rows under each column contain their respective roles.

- **Step 2: Define Named Ranges**

  1. Highlight the roles under **HR** (e.g., `Recruiter`, `HR Manager`, `HR Coordinator`, `Trainer`).
  2. Go to the **Formulas** tab → click **Define Name**.
  3. In the **Name** field, type **HR** (case-sensitive). Click **OK**.
  4. Repeat this process for the roles under **Finance**, **IT**, **Marketing**, and **Sales**:
     - Name the ranges **Finance**, **IT**, **Marketing**, and **Sales**, respectively.

- **Step 3: Create a Static Dropdown for Departments**

  1. Navigate to the `DropdownLists` worksheet.
  2. Select cell A**2 (where the static dropdown for departments will be placed).**
  3. Go to the **Data** tab → click **Data Validation**.
  4. In the **Data Validation** window:
     - Under **Allow**, choose **List**.
     - In the **Source** field, type:
       ```
       HR, Finance, IT, Marketing, Sales
       ```
     - Click **OK**.
  5. Test the dropdown by selecting different options (e.g., **HR**, **Finance**).

- **Step 4: Create a Dependent Dropdown for Roles**

  1. Select cell B**2** (where the dependent dropdown for roles will be placed).
  2. Go to the **Data** tab → click **Data Validation**.
  3. In the **Data Validation** window:
     - Under **Allow**, choose **List**.
     - In the **Source** field, type:
       ```excel
       =INDIRECT(A2)
       ```
       This formula dynamically links the dependent dropdown to the selection in cell A**2**.
     - Click **OK**.

- **Step 5: Testing**

  1. Test the dropdown by selecting a department (e.g., **HR**) in A**2** and verifying that the dependent dropdown shows the corresponding roles (e.g., `Recruiter`, `HR Manager`, `HR Coordinator`).

---

#### Exercise Question

*You have created static and dependent dropdown lists in Excel. Select the correct subcategory for the main category ************HR************.*

1. Accountant
2. HR Manager
3. Data Analyst
4. SEO Analyst

**Correct Answer**:

- HR Manager

**Feedback**:

- **Correct Answer**: "Well done! HR Manager is a valid subcategory under the HR department."
- **Incorrect Answers**: "Not quite! Check the subcategories defined under the HR department in your dataset."

---

#### End Goal

*Learners will successfully implement static and dependent dropdown lists in Excel, allowing users to dynamically select subcategories (e.g., roles) based on the main category (e.g., departments). This ensures hierarchical data accuracy and eliminates invalid data entries, providing a streamlined and user-friendly data entry experience.*


## 2nd VM Exercise

#### Dataset

- [x] Add datasets used to the `datasets/` folder

#### Files

- [x] **Initial**: Add file to the `exercises/`  folder with the name `ex-2-intial.twbx` or `ex-1-initial.yxmd`, depending if you are auditioning for a Tableau/Power BI/Alteryx course.
- [x] **Solution**: Add file to the `exercises/`  folder with the name `ex-2-sol.twbx` or `ex-2-sol.pbix` or `ex-1-sol.yxmd`

#### **Learning Objective**

*Learners will be able to apply conditional formatting in Excel to visually highlight invalid entries, ensuring that dependent dropdown selections match predefined criteria, and errors are easily identifiable for correction.*

---

### **Context**

*Highlighting invalid data with conditional formatting builds upon static and dependent dropdown lists to further improve data quality. By visually flagging mismatched or missing entries, users can easily detect and correct errors in hierarchical datasets. This technique is particularly useful in systems like HR data entry, inventory categorization, and financial reporting, where ensuring data consistency is essential.*

---

#### **Step 1: Apply Conditional Formatting to Highlight Mismatched Roles**

1. Select the dependent dropdown range (e.g., B**2**\*\*:B100\*\*).
2. Go to **Home** → click **Conditional Formatting** → select **New Rule**.
3. Choose **Use a formula to determine which cells to format**.
4. Enter the formula:
   ```excel
   =ISERROR(MATCH(B2, INDIRECT(A2), 0))
   ```
   - **Explanation**:
     - `B2`: Refers to the cell in the **Role** column.
     - `A2`: Refers to the corresponding cell in the **Department** column.
     - `INDIRECT(A2)`: Dynamically references the named range for the selected department.
     - `MATCH(B2, INDIRECT(A2), 0)`: Checks if the value in `B2` exists in the named range linked to `A2`.
     - `ISERROR`: Highlights cells where the value in `B2` is invalid.
5. Set the formatting style (e.g., red fill) to indicate invalid entries.
6. Click **OK**.

---

#### **Step 2: Testing the Conditional Formatting**

1. Enter a valid role for a department (e.g., "HR Manager" under "HR"). Ensure no formatting is applied.
2. Enter an invalid role for a department (e.g., "Software Engineer" under "Finance"). Ensure the cell is highlighted in red.
3. Leave any cell in the **Department** or **Role** columns blank. Ensure the cell is highlighted in yellow.

---

### **Exercise Question**

#### **Question:**

Using the dropdowns and Conditional Formatting you just implemented:

- Select the department as **Marketing**.
- In the dependent dropdown, select a role.

Which role is **NOT** valid under Marketing?

1. Marketing Specialist
2. SEO Analyst
3. HR Manager
4. Content Writer

**Answer:** HR Manager

**Feedback:**

- **Correct Answer:** "Well done! HR Manager is part of HR, not Marketing."
- **Incorrect Answers:** "Not quite! Review the roles defined under Marketing in your dataset."

---

### **End Goal**

*Learners will successfully implement conditional formatting in Excel to visually identify invalid or missing entries, ensuring data accuracy and improving the overall quality of hierarchical datasets.*


