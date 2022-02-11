# Pewlett-Hackard-Analysis
## Overview of the analysis
* The purpose of this analysis was to determine the number of retiring employees per title, and identify employees who are eligible to participate in a mentorship program through tools such as pgAdmin and SQL.
* The client tasked us with "future-proofing the company by determining how many people will be retiring and, of those employees, who is eligible for a retirement package."
## Results: 
* Task: **Determine The Number of Retiring Employees by Title**
    *   The largest groups about to retire are employees with the title "Senior Engineer" and "Senior Staff".
    *   **These "Senior" title holders make up 70% of the retirees.**
    *   Total number of retirees: 72, 458 personnel.

![goals](count_titles.png)

* Task: **Determine The Employees Eligible for the Mentorship Program**
    *   There are only 1549 employees that are eligible for the mentorship program
    *   The titles with the largest availablity for the mentorship program are "Engineers" and "Senior Staff".
        *   **These titles make up a total of 57% of the eligibility for the program.**

![goals](count_mentorship.png)

## Summary: 
* As the "silver tsunami" begins to roll through, we will need to prepare to fill 72, 458 positions.
   * A **company wide restructuring** opportunity should be considered to consolidate positions to minimize the overall cost of hiring. 
* There are currently 33, 118 positions being held by employees that will not retire in the new future and only 1549 retirees that are eligible for the mentorship program.
    * Clearly, there will not be enough mentors to go around. There is a need of training and development for current employees.
        * Proposal:
          * **Mentor group trainings,** each mentor will be assigned an average of 23 current employees to educate and pass on their knowledge to.
          * **External recruitment and training** will be required specifically for **Senior Engineers**, this department has the most amount of retirees coupled with the least amount of eligible mentors.

```
-- querie to select current employees
SELECT ri.emp_no,
	ri.first_name,
	ri.last_name,
	de.to_date
INTO current_emp
FROM retirement_info as ri
LEFT JOIN dept_emp as de
ON ri.emp_no = de.emp_no
WHERE de.to_date = ('9999-01-01');
```
