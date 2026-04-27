# SQL Basics - Complete Beginner Guide 🎓

## What is SQL?
SQL = **Structured Query Language**
- Used to talk to databases
- Ask for data, add data, update data, delete data
- Think of it like asking questions to a library database

---

## 1️⃣ THE MOST BASIC COMMAND: SELECT

### What does SELECT do?
Shows you data from a table (like opening a spreadsheet)

```sql
SELECT * FROM students;
```

**Breaking it down:**
- `SELECT *` = "Show me EVERYTHING"
- `FROM students` = "from the students table"
- `;` = "End of command" (like a period in a sentence)

### Example Database: Students Table
| student_id | name      | age | marks |
|------------|-----------|-----|-------|
| 1          | Abhishek  | 22  | 85    |
| 2          | Priya     | 21  | 90    |
| 3          | Rahul     | 23  | 78    |

---

## 2️⃣ SELECT SPECIFIC COLUMNS (Not everything)

```sql
SELECT name, marks FROM students;
```

**Result:**
| name      | marks |
|-----------|-------|
| Abhishek  | 85    |
| Priya     | 90    |
| Rahul     | 78    |

---

## 3️⃣ WHERE - Filter your data

Show only students with marks > 80:

```sql
SELECT name, marks FROM students WHERE marks > 80;
```

**Result:**
| name      | marks |
|-----------|-------|
| Abhishek  | 85    |
| Priya     | 90    |

### Common Filters:
```sql
WHERE marks > 80          -- greater than
WHERE marks < 80          -- less than
WHERE marks = 85          -- equal to
WHERE marks >= 80         -- greater than or equal
WHERE marks <= 80         -- less than or equal
WHERE marks != 85         -- not equal to
WHERE name = 'Abhishek'   -- text (use quotes!)
```

---

## 4️⃣ AND, OR - Multiple conditions

```sql
SELECT name FROM students WHERE marks > 80 AND age > 21;
```
(Show students with marks > 80 AND age > 21)

```sql
SELECT name FROM students WHERE marks > 80 OR age > 22;
```
(Show students with marks > 80 OR age > 22)

---

## 5️⃣ ORDER BY - Sort your results

```sql
SELECT name, marks FROM students ORDER BY marks DESC;
```

**Result:** (sorted from highest marks to lowest)
| name      | marks |
|-----------|-------|
| Priya     | 90    |
| Abhishek  | 85    |
| Rahul     | 78    |

```sql
ORDER BY marks ASC;       -- Ascending (lowest to highest)
ORDER BY marks DESC;      -- Descending (highest to lowest)
```

---

## 6️⃣ LIMIT - Show only first few rows

```sql
SELECT name, marks FROM students LIMIT 2;
```

**Result:** (only first 2 rows)
| name      | marks |
|-----------|-------|
| Abhishek  | 85    |
| Priya     | 90    |

---

## 7️⃣ COUNT - How many?

```sql
SELECT COUNT(*) FROM students;
```

**Result:** `3` (there are 3 students)

```sql
SELECT COUNT(*) FROM students WHERE marks > 80;
```

**Result:** `2` (2 students have marks > 80)

---

## 8️⃣ SUM, AVG, MAX, MIN - Math operations

```sql
SELECT SUM(marks) FROM students;          -- Total: 253
SELECT AVG(marks) FROM students;          -- Average: 84.33
SELECT MAX(marks) FROM students;          -- Highest: 90
SELECT MIN(marks) FROM students;          -- Lowest: 78
```

---

## 9️⃣ GROUP BY - Organize by category

Table: Exams
| exam_id | subject | marks | student_id |
|---------|---------|-------|------------|
| 1       | Math    | 85    | 1          |
| 2       | English | 88    | 1          |
| 3       | Math    | 90    | 2          |
| 4       | English | 92    | 2          |

```sql
SELECT subject, AVG(marks) FROM exams GROUP BY subject;
```

**Result:**
| subject | AVG(marks) |
|---------|-----------|
| Math    | 87.5      |
| English | 90        |

---

## 🔟 JOIN - Combine two tables

Teachers Table:
| teacher_id | name      | subject |
|------------|-----------|---------|
| 1          | Mr. Singh | Math    |
| 2          | Ms. Patel | English |

Exams Table:
| exam_id | teacher_id | marks |
|---------|------------|-------|
| 1       | 1          | 85    |
| 2       | 2          | 88    |

```sql
SELECT exams.marks, teachers.name 
FROM exams 
JOIN teachers ON exams.teacher_id = teachers.teacher_id;
```

**Result:**
| marks | name      |
|-------|-----------|
| 85    | Mr. Singh |
| 88    | Ms. Patel |

---

## 📝 QUICK CHEAT SHEET

```sql
SELECT column1, column2 FROM table_name;
SELECT * FROM table_name WHERE condition;
SELECT * FROM table_name ORDER BY column DESC;
SELECT COUNT(*) FROM table_name;
SELECT AVG(column) FROM table_name;
SELECT * FROM table_name LIMIT 10;
SELECT column, COUNT(*) FROM table_name GROUP BY column;
SELECT * FROM table1 JOIN table2 ON table1.id = table2.id;
```

---

## ✅ Practice Exercises

Try writing queries for:
1. Show all students names
2. Show students with age > 21
3. Show top 5 highest marks
4. Count how many students have marks > 80
5. Show average marks for each subject

---

**Ready to practice? Move to the next file!** 👉
