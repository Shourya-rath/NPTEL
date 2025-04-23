# Contents
- [Contents](#contents)
- [Topics in this Module](#topics-in-this-module)
- [SQL](#sql)
- [DDL](#ddl)
  - [Specifying Integrity Constraints in SQL](#specifying-integrity-constraints-in-sql)
  - [RIC Violation](#ric-violation)
  - [Modifying a Defined Schema](#modifying-a-defined-schema)
- [Data Manipulation in SQL](#data-manipulation-in-sql)
  - [Select :](#select-)
  - [Union, Intersection and Difference Operations](#union-intersection-and-difference-operations)
- [Aggregation Functions](#aggregation-functions)
- [Join](#join)
- [Views](#views)
- [Inserting - Deleting - Updating](#inserting---deleting---updating)
- [Miscellaneous keywords](#miscellaneous-keywords)


# Topics in this Module
- The SQL Standard
- History of SQL
- Components of SQL Standard
- Data Definition in SQL
- Domain Types in SQL-92 
- Specifying Integrity Constraints in SQL
- Specifying Referential Integrity Constraints  
- Specifying What to Do if RIC Violation Occurs
  - Table Definition Example
- Modifying a Defined Schema
- Data Manipulation in SQL
- Meaning of the Basic Query Block
- SQL Query Result
  - Example Relational Scheme with RIC
  - Example Queries Involving a Single Table
  - Examples Involving Two or More Relations 
- Nested Queries or Subqueries
  - Nested Query Example
- Set Comparison Operators
- Semantics of Set Comparison Operators
- Correlated and Uncorrelated Nested Queries
- Example of a Correlated Subquery
- The EXISTS Operator
- The NOT EXISTS Operator
- Example Involving Universal Quantifier
  - Same query expressed in TRC
  - An Example Involving the Universal Quantifier
  - Missing where Clause
- Union, Intersection and Difference Operations
  - Example using UNION , Intersecion 
  - Example using EXCEPT
- Aggregation of Data
- Aggregate functions
  - Examples involving aggregate functions 
- Date Aggregation and Grouping
  - Examples involving grouping
  - Having clause
  - Where clause versus Having clause
- String Operators in SQL
- Using the ‘LIKE’ operator
- Join Operation
- Explicit Specification of Joining in ‘From’ Clause
- Natural join
- Views ( or Virtual Tables)
  - Creating Views
  - Queries on Views
  - Operations on Views
  - Restrictions on Updating Views
  - Allowed Updates on Views
- Inserting data into a table
- Deleting rows from a table
- A Remark on Deletion
- Updating tuples in a relation
- Miscellaneous features in SQL Database System Architectures
- Application Development Process: 2-tier Systems
- Impedance Mismatch
- Embedded SQL Approach
- Declaring Variables
- Handling Error Conditions
- Database Connections in Embedded SQL Approach
- Embedded SQL Statements – An example
- Query result handling and Cursors
- Embedded SQL - Cursors Declaring a cursor on a query
- Dynamic SQConnecting to Database from HL – Other Approaches
- A comparison of the Approaches

# SQL
- Every relational database management system (RDBMS) is required to support / implement the SQL standard.
- Components :
  -  DDL
  -  DML
  -  Embedded - Dynamic SQL
  -  Transaction Control
  -  Authorisation 

# DDL
-  Numeric Datatypes 
   -  Int , SmallInt 
   -  Float , Real , Double 
   -  Decimal , Numeric (formatted numbers)
-  Character : Char and Var Char 
-  Bit string : 
   -  Bit(n) : fixed length
   -  Bit Varying(n) 
-  Date data type ( yyyy-mm-dd )
-  Time data type ( HH-MM-SS ) and Others

## Specifying Integrity Constraints in SQL
- primary and unique key
- Foreign key - referential integrity


## RIC Violation 
- On Update : Set Null , Cascade , Set Default
- On Delete : Set Null , Cascade , Set Default

## Modifying a Defined Schema
- use of Alter with Add and DROP
- We use RESTRICT and CASCADE with DROP

# Data Manipulation in SQL
## Select :
- seletc (attributes) - from (table) - where (condition)
  - Subquery : IN / NOT IN - can be used with Tuple values
  - Comparison : ANY / ALL  - used with single values
  - Any : at least one matches
- Can have duplicate Rows (unlike Relation) - "DISTINCT" removes them 
- Isn't same as the sigma select in R.A.
- In case of selecting from multiple tables , <br>
the dot operator is used eg : s.name, f.name 
- Correlated : If the inner nested query is using some outer attribute (especially of different table) - Correlated

- NOT In / IN should not be used in case of NULL values
- Exists and Not Exists are better alternatives to IN / NOT IN


|Predicate Type |Expressed in SQL using  | Easy?|
|--|--|--|  
|Existential (∃) |	EXISTS |✅ Yes |
|Universal (∀)| Rewrite using NOT EXISTS |⚠️ Needs transformation |

- For all TO Not Exists
  - For all :
  > ∀ c (if c is taught by Ramanujam → student s is enrolled in c)
  - Not Exists :
  > ¬ ∃ c (c is taught by Ramanujam AND student s is NOT enrolled in c)

## Union, Intersection and Difference Operations
- For diff - EXCEPT word used
- Results of these operations -> sets meaning no duplicates 
- Operands need to be union compatible and also have same
attribute names in the same orde 


# Aggregation Functions
- 5 functions : AVG, SUM, COUNT, MAX, MIN
- use distinct to remove duplicates 
- Group BY :
  > All columns in SELECT must be: <br>
    Either in the GROUP BY, OR <br>
    Inside an aggregate function.
  - Eg :
  > SELECT city, name, MAX(marks)  -- ❌ name not grouped or aggregated
  <br>FROM gateMarks
  <br>GROUP BY city;
- Where clause : Performed before any grouping of rows is done
- Having clause: Always performed after grouping
  - Tests can only involve grouping attributes and aggregate
functions 

# Join 
- Types: inner (-> default) , full , left , right Joins
- Natural : FROM ( r1 NATURAL \<join type> r2 [USING \<attr. list>] )
- Join doesn't support **Spirit of Declarative Style** of Queries <br> though it makes queries easier to understand

# Views
- can be materialised    
- CREATE VIEW v AS <query expr>
- Quering : allowed ,
- Casese where Updates Not Allowed :
  1. Views Involving Joins
  2. Views with GROUP BY or Aggregates
  3. Views Without a Primary Key from the Base Table
- Updates to views are allowed only if
  1. defined on single base table
  2. not defined using ‘group by’ clause and aggregate functions
  3. view includes Primary Key of base table
  <!-- It also doesn’t use DISTINCT, UNION, subqueries, or joins -->

# Inserting - Deleting - Updating
- Use of INSERT INTO and Values (not needed in "2." case)
  1. Insert Full Tuples Manually
  2. Insert Data from Another Table (or Query Result)
  3. Insert Partial Tuples (Sub-Tuple Insert)

- Delete: DELETE FROM table_name WHERE condition;
  - This deletes entire rows (tuples) — you can’t delete just some columns of a row.
  - One Relation at a time 
  - Where condition is evaluated first for all the tuples and then deletion takes place

- Update can "set" multiple Columns and also use expressions 

# Miscellaneous keywords
- order by
- is null
- between - and 
- distinct
- (*) -> select all 
