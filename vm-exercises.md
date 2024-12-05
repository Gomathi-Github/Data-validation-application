# Virtual Machine (VM) Exercises

## :information_source: Read this before getting started
- The two exercises should not replicate the exact actions shown in your screencast. The goal of exercises is for learners to apply what was learned in the screencasts to new problems or situations. This is best pedagogical practice for retaining and building skills. For example, this can be done by using another dataset between screencasts and exercises or focusing on a different portion of the dataset.
- Power BI / Tableau specific: We can only run free versions of BI software in our virtual machine exercises. In the case of Power BI, make sure the exercises can run on [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) without any additional paid products. 
- Unsure what the scope of an exercise should be? Here's an [example](https://campus.datacamp.com/courses/introduction-to-power-bi/getting-started-with-power-bi?ex=14) from Introduction to Power BI. The first chapter of most DataCamp courses are free, so take a look at our [BI courses](https://learn.datacamp.com/courses?technologies=Tableau&technologies=Power%20BI) to get a feel for how we assess and guide learners.

## 1st VM Exercise

#### Dataset

- [ ] Add datasets used to the `datasets/` folder

#### Files

- [ ] **Initial**: Add file to the `exercises/`  folder with the name `ex-1-intial.twbx` or `ex-1-intial.pbix` or `ex-1-initial.yxmd`, depending if you are auditioning for a Tableau/Power BI/Alteryx course.
- [ ] **Solution**: Add file to the `exercises/`  folder with the name `ex-1-sol.twbx` or `ex-1-sol.pbix` or `ex-1-sol.yxmd`

#### Learning Objective

*Learners will be able to create static and dependent dropdown lists using named ranges in Excel, ensuring accurate hierarchical data selection, such as dynamically filtering subcategories based on a selected main category*

#### Context

*Creating static and dependent dropdown lists using named ranges is a critical skill for improving data entry accuracy and consistency in Excel. By implementing these dropdowns, users can limit input choices to predefined options, reducing errors and ensuring that data conforms to specific rules. Dependent dropdowns are especially useful in hierarchical data scenarios, such as selecting a department and dynamically filtering the corresponding roles, streamlining workflows and saving time. This approach is widely applicable in real-life situations like HR systems, inventory management, and financial reporting, where maintaining clean and reliable datasets is crucial*

#### Steps to be executed by the student (max 6)

*Steps needs to be followed.*

- Step 1: Load the Dataset
1.	Open the Excel file named HR_Validation_Exercises_Dataset.xlsx from the Datasets/Dropdowns folder.
2.	Examine the dataset:
o	The first row contains the main categories: HR, Finance, IT, Marketing, and Sales.
o	The rows under each column contain their respective roles.
- Step 2: Define Named Ranges
1.	Highlight the roles under HR (e.g., Recruiter, HR Manager, HR Coordinator, Trainer).
2.	Go to the Formulas tab → click Define Name.
3.	In the Name field, type HR (case-sensitive). Click OK.
4.	Repeat this process for the roles under Finance, IT, Marketing, and Sales:
Name the ranges Finance, IT, Marketing, and Sales, respectively.
- Step 3: Create a Static Dropdown for Departments
1.	Navigate to the DropdownLists worksheet.
2.	Select cell E2 (where the static dropdown for departments will be placed).
3.	Go to the Data tab → click Data Validation.
4.	In the Data Validation window:
o	Under Allow, choose List.
o	In the Source field, type:
HR, Finance, IT, Marketing, Sales
Click OK.
5.	Test the dropdown by selecting different options (e.g., HR, Finance).
- Step 4: Create a Dependent Dropdown for Roles
1.	Select cell F2 (where the dependent dropdown for roles will be placed).
2.	Go to the Data tab → click Data Validation.
3.	In the Data Validation window:
Under Allow, choose List.
In the Source field, type: =INDIRECT(E2) This formula dynamically links the dependent dropdown to the selection in cell E2.
Click OK.
- Step 5: Testing
Test the dropdown by selecting a department (e.g., HR) in E2 and verifying that the dependent dropdown shows the corresponding roles (e.g., Recruiter, HR Manager, HR Coordinator).

#### Exercise question:
*You have created static and dependent dropdown lists in Excel. Select the correct subcategory for the main category HR*
Accountant
HR Manager
Data Analyst
SEO Analyst
**Correct Answer**:
HR Manager
**Feedback**:
**Correct Answer**: "Well done! HR Manager is a valid subcategory under the HR department."
**Incorrect Answers**: "Not quite! Check the subcategories defined under the HR department in your dataset."

#### End goal:
*Learners will successfully implement static and dependent dropdown lists in Excel, allowing users to dynamically select subcategories (e.g., roles) based on the main category (e.g., departments). This ensures hierarchical data accuracy and eliminates invalid data entries, providing a streamlined and user-friendly data entry experience.*

## 2nd VM Exercise

#### Dataset

- [ ] Add datasets used to the `datasets/` folder

#### Files

- [ ] **Initial**: Add file to the `exercises/`  folder with the name `ex-2-intial.twbx` or `ex-1-initial.yxmd`, depending if you are auditioning for a Tableau/Power BI/Alteryx course.
- [ ] **Solution**: Add file to the `exercises/`  folder with the name `ex-2-sol.twbx` or `ex-2-sol.pbix` or `ex-1-sol.yxmd`

#### Learning Objective

*One measurable learning objective that this exercise assesses*

#### Context

*3 - 4 sentence description of why it’s important to learn how to do this task (linking back to the learning objective). Explain how this would be used in a real-life situation. Why is it useful, what problem does it solve?*

#### Steps to be executed by the student (max 6)

*Each bulleted instruction is a complete sentence that describes a specific task.*

- Step 1
- Step 2
- Step 3
- ...

#### Exercise question:
*This is a question presented to learners to check if the steps above were properly completed. It can be a multiple choice question or a question with a 1-3 word answer. It is often not possible to check if all the steps are completed, in this case; the priority is to check that the learner meets the learning objective.*

#### End goal:

*Add an image of the final visualization here.*

