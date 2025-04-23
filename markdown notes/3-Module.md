# Contents
- [Contents](#contents)
  - [Relation Instance](#relation-instance)
    - [Keys for a relation](#keys-for-a-relation)
  - [Intergrity Contraints](#intergrity-contraints)
  - [Relational Algebra](#relational-algebra)
    - [Derived Operators](#derived-operators)
  - [Queries](#queries)
  - [E/R Diagrams to Relational Schema](#er-diagrams-to-relational-schema)
- [Module 3.1](#module-31)
  - [predicates](#predicates)
  - [Assignments](#assignments)
  
## Relation Instance
- No duplicate tuples ( or rows ) in a relation instance <br>
  (in SQL, duplicate rows would be allowed in tables)

### Keys for a relation 
- intrinsic property - can be only determined from attributes' meaning 
- Relation Can have more than one key
- primary - indexing , super , candidate

## Intergrity Contraints
- Domain 
- Key
  -  Forign Keys : It is possible for a foreign key in a relation to refer to the primary key of the relation itself
- Referential Integrity Constraints ( RIC )
  - RIC ensures that references to tuples in r2 are for currently existing tuples.
  - No dangling references
- if R1 Intersection R2 is Null -> there's no overlap in Attribute names

## Relational Algebra
- SQL queries are internally translated into RA expression
- Select : Select operation is commutative
- Size of project expression result : 
  > projection in relational algebra removes duplicate rows, the number of tuples in the result depends <br> on which attributes you project
- Set Operators : must have union compatibility
  > Resulting table has same attribute names (schema ) as the first relation r1

### Derived Operators 
- Theta Join: All pairs of tuples (t1 from r1 and t2 from r2) such that the combined <br> tuple satisfies the condition θ
- Division is basically all the values r1 that are associated with all the values in <br> r2 individually (look at the last eg)
  - Find those students who have enrolled for all courses offered <br> in the dept of Computer Science
- Intersection – union and difference
- Join – cross product followed by selection
- Division – project, cross product and differenc

## Queries
- Retrieve the list : Select OP
- Obtain the X and Y of all Z Relation_Name : Proj + Sel OP
- Obtain the X of students who never obtained an ‘E’ grade : Diff needed , Sel OP itself can't do it
- Obtain the rollNo of male students who have obtained at least one S grade : <br> Intersection between selections 

## E/R Diagrams to Relational Schema


---
# Module 3.1
## predicates

- t ->  tuple variable
- r -> relation 
- ( cwa ) closer world assumption is that  r(t) will true if t is in r 
- ( TRC ) Tuple relational calculus Basic Form - 
    > {s.rollNo,s.name| student(s)^ s.sex=‘F’^ s.deptNo=2}
  - s is Tuple Variable , Student is "r" meaning Relation
- Free Variable - s - Means the variables on the left which will actually get displayed   
- Bounded variables are on the right of the "|" bar
- RA and EQUI
  - RA: 
  > π_name (σ_deptId = 5 (STUDENT ⨝ STUDENT.deptNo = DEPARTMENT.deptId))
  - Equi TRC
  > { s.name |
    student(s) ∧
    (∃ d)(department(d) ∧ d.deptId = s.deptNo ∧ d.deptId = 5)
  }
- For All is usually used with implies (->) and negation  
- Unsafe Queries : when we are trying to refer to values outside of relation


<!-- 
what if following table r:
A  C B D
a1 c1 b1 d1
a2 c1 b2 d1
a1 c2 b1 d2
a1 c3 b1 d3
a2 c3 b2 d3

was divided by 
A B
a1 b1
a2 b2 

Ans : Chalega , kyoki internally projection aur difference use hota hai 
-->

## Assignments

9. Courses in which a proper subset of female students have enrolled.
10. A join operation is equivalent to performing a cross product of its operands followed by a select operation using the join condition. <br>
The operators constitute a complete set of relational algebra operators. <br>
The difference relational algebra operator requires its operands to be union-compatible.