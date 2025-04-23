# Contents
- [Contents](#contents)
  - [topics](#topics)
  - [What is a Database?](#what-is-a-database)
    - [DBMS properties](#dbms-properties)
  - [Architecture of an RDBMS System](#architecture-of-an-rdbms-system)
  - [Types of Users](#types-of-users)

## topics
-  Introduction:
-  Database Management System (DBMS)
-  OS File System Storage Based Approach
-  DBMS Approach
-  Data Model
-  E/R (Entity/Relationship) Model
-  Representational Level Data Model
-  Data versus Schema or Meta-Data
-  Abstraction Levels in a DBMS: Three-Schema Architecture
-  Development Process of a Database System

## What is a Database?
```
Collection of related pieces of data Representing real-world 
```

Ex: University DB - reflects the state of affairs of the academics of uni

### DBMS properties

- Disk-resident databases
- Standard Queries
- Efficiently results
- Concurrent use 
- Guaranteed availability 

DB in **Disk** is **available** and can be **queried** + **efficiently** to **many users** 


## Architecture of an RDBMS System
- three level schema : View , Logical , Physical 
1. Start up
   1. Application pgm compilers
   2. Query Compiler and optimizer
   3. DDL Processor 
2. Middle : RDBMS Run Time Manager 
3. Later
   1. Buffer manager , Recovery M. , Transaction M. 
4. Disk storage : Meta/ schema , Data , Logs ****


## Types of Users
1. Naive user 
2. Application Programmer 
3. Sophisticated User 
4. DBA - Admin
