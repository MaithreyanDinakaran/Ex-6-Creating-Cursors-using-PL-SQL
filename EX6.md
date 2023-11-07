# Ex. No: 6 Creating Cursors using PL/SQL
## DATE:07/09/2023

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table:
```
CREATE TABLE employd (
  empid NUMBER,
  empname VARCHAR(10),
  dept VARCHAR(10),
  salary NUMBER
);
select * from employd;
INSERT INTO employd VALUES (1, 'Nagul', 'Sales', 100000);
INSERT INTO employd VALUES (2, 'Arvind', 'Marketing', 120000);
```
### PLSQL Cursor code
```
DECLARE
   CURSOR employd_cursor IS
   SELECT empid,empname,dept,salary
   FROM employd;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employd_cursor;

  LOOP
    FETCH employd_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employd_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employd_cursor;
END;
/
```
### Output:
![280724693-b91e3234-1784-45cf-8225-0a0b573295ca](https://github.com/MaithreyanDinakaran/Ex-6-Creating-Cursors-using-PL-SQL/assets/119104032/b530205a-f3fd-4417-928c-ffc2dc66ad65)

### Result:
The program has been implemented sucessfully.
