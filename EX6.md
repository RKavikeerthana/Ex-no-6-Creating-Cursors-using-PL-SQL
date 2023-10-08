# Ex. No: 6 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
```
NAME: R.Kavi Keerthana
Reg.no: 212222100022
```
```
create table employee1(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
insert into employee1 values(1,'sudhiksha','HR',50000);
insert into employee1 values(2,'mithra','IT',65000);
insert into employee1 values(3,'kavi','MD',55000);
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
```
### Output:
![image](https://github.com/RKavikeerthana/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120431120/7680a299-8782-48e7-a280-ead54db74285)

### Result:
The Program has been implemented successfully.
