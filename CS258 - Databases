# CS258 - Database systems

## Module Overview

- Part 1: Into to Databases and the Relational DB Model:
  - Background, Relational Model,
  - Database Constraints
- Part 2: DB Access and the SQL declarative language
  - SQL basics,
  - Advanced SQL,
  - SQL as a DDL (Database Definition Language) and DML (Database Manipulation Language)
- Part 3: Accessing a SQL DBS programmatically
  - Embedded SQL (C), and
  - JDBC (Java)
- Part 4: Logical DB Design
  - Data Modelling, ER and EER models
    - Mapping to the Relational Model
  - Normalisation
  - Relational Algebra and Calculus
- Part 5: Database Security





## Week 1  - Introduction to Database Systems

### Introduction to Database Systems

#### Key facts about data:

- Structured - tables with predefined columns
- Unstructured - web pages, text docs, images, videos
  - ​	Semi structured data - JSON or XML
- Traditionally, DBs managed structured (tabular data)
  - Nowadays “modern” DBs handle text, documents, graphs…
- DBs were designed for “structured” data
  - Un/semi-structured is textual data and is the subject of Information Retrieval (IR)
    - Nowadays, IR and DBs are coming closer
  - Also, many graphs DBSs have emerged to handle graph-type data (social networks, proteins, …)
- Data modelling “defines” the data space: 
  - If you give me a table, I will ask for rows and columns…,
  - If you give me a graph I will ask of nodes and edges and paths…,

#### Data Modelling

##### Need to understand:

- Which are the data items that I care about?
- What are the data items’ attributes (characteristics)?
- What are the relationships between data items?
- What are the attributes of such relationships?
- As mentioned, the data model employed in Relational DBs is table-centric.

How can a relationship be build between different linking bits of data?

#### Database Management Systems

- What are the principal functions of a DBS?
- In a nutshell, DB systems provide software too “manage” data
  - Model data
  - Access data: query + update
    - Analyse data: complex queries
  - Store data
  - Secure and ensure the integrity/consistence of data

What do they allow us to do?

- 1:
  - Ensure/maintain data consistency, integrity, and security in the dace of:
    - Attempts for unauthorized accesses and/or to corrupt data
    - Updates (a.k.a transactions) may violate “integrity constraints” on the data (e.g. bank account balances less than 0)
  - Failures (think of machine crashes due to sw bugs, power outages, disk crashes) and recovery from failures.
  - Concurrent transactions (think of multiple users or programs reading/writing the same data at the same time)…
- 2:
  - Optimize data accesses - that is, ensure tshort response times, proper utilization of resources, high throughput, etc.
    - Create and employ indexes - speed up finding where desired data items are
    - Find best way to execute a set of operators in a query
    - Find the best order for executing relational data operations:
      - Selection, progection, join
      - Order of joins in a multi-way

-------------------------

#### How to visualize DBSMs

- Can be seen as a box with a nice interface offering the previous functionality
- DBS interface is based on :
  - An easy way to understand the data space (model)
  - On a declarative programming language
- Once a query is received by the box, all previously mentioned functionality will be provided to us, transparently - the “box” worries about it ; NOT THE USER



**Architectural schematic of a database:**

![image-20210930170545157](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20210930170545157.png)

------------

## Week 1 Reading 

**A definition for a database** - a collection of related **data** - known facts that can be recorded and have implicit meaning

- This definition is typically too general



A database has the following implicit properties:

- A database represents some aspect of the real world, sometimes called the **miniworld** or the **universe of Discourse** changes to the minimiworld are reflected in the database
- A database is a logically coherent collection of data with some ingerent meaning. A random assortment of data cannot correctly be referred to as a database.
- A database is designed, build, and populated with data for a specific purpose. It has an intended group of users and some preconcieved applications in which the users are interested.

A database can be of any size and complexity.

### A Database Management System

A **database management system** is a computerized system that enables users to create and maintain a database. The DBMS is a general purpose software system, that facilitates the process of defining, constructing, manipluating and sharing databases among various users and applications.

#### Functions and definitions 

- **Defining** a DB entails specifying the data types, structures and constraints of the data to be stored in the database.
- On creation of the database, the above data is stored in the **metadata** of the database.
- **Constructing** the DB is the process of storing data on some medium that is controlled by the DBMS.
- **Manipulating** a database includes functions such as querying the database to retrieve specific data, updating the database to reflect changes, and generating reports from the data.
- **Sharing** a DB allows multiple users and programs access the database simultaneously.
- An **application program** accesses the database by sending queries or request for data to the DBMS
- A **query** typically causes some data to be retrieved
- A **transaction** may cause some data to be read and some data to be written.

#### Other functions

- Protecting the database and maintiaing it over time
- **Protection** can entail:
  - hardware or software malfunction
  - security protection against unauthorized  or malicious access



### The Database Approach

In a DB approach, a single repository maintains data that is defined once and then accessed by vaiour users repeatedly through queries, transactions and application programs.

The main characteristics of the DB approach are:

- Self-desciribing nature of the database system
- Insulation between programs and data, and data abstraction
- Support of multiple views of the data
- Sharing of data and multiuser transaction processing

#### Self describing nature of a DBS

The DBS contains not only itself, but also a complete definition or description of the database structure and contraints.

This definition is stored in the DBMS catalogue - metadata. 

- This is used by the DBMS software and users who need information about the DB structure

A DBMS is a very multi-purpose application, and must be able to work equally well with any number of DB applications - a university, a bank, or a company DB, so long as the DB definition is stored in the catalogue.

#### Insulating betwen Programs and Data and Data Abstraction

The structure of data files is stored in the DBMS catalogue seperately from the access programs:

- This is program data independence.













----------------

## Week 3 - Relational Data Base Model

### Informal Definitions

- Informally, a relation is a table of values, having:
  - A set of rows. The data elements in each row represent certain facts that correspond to a real-world **entity** or **relationship**
    - An employee, a bank account, a student etc …
    - Formally, rows are called tuples
  - Each column 
    - Represents a characteristic/attribute of interest of that entity
    - Has a column header that gives an indication of the meaning of the data items in that column
    - Formally called attribute name
  - Key of relation:
    - Each row must be uniquely identifiable in the table
      - The key of the row does this
    - Sometimes row-ids or sequenctial numbers are assigned as keys to indentity the rows in a table
      - Called artificial key or surrogate kay

----------------------

### The Relational DB Model

- A prevalent data model and DBS type
- Based on tables (relations);
  - With known table names, and attribute (name, type) pairs.
- To formulate queries:
  - Specify the table name(s), and attribute names of interest
  - special constraints (predicates) that must be identified

-------------------------

### Formal Definitions 

- The **Schema** of a Relation:
  - Denoted by $R(A1, A2, …, An)$ 
  - $R$ is the name of the relation
  - The attributes of the relation are: $A1,A2, …,An$ 
- Example: CUSTOMER(Cust-Id, Cust-name)
  - CUSTOMER is the relation name
  - Defined over the two attributes
- Each attribute has a domain or a set of values
- A **tuple** (row) of a relation (table) is an (ordered) set if values, enclosed in angled brackets.
- Each value is derived from an appropriate domain
- A relation is an (unordered) set of tuples.
- A **domain** may have a specific format
- **Relation state** is the set of tuples currently in the relation.
- The relation state is a subset of the Cartesian product of the domains of its attributes
  - Each domain contains the set of all possible values the corresponding attribute can take.

-----------------------------------------

### Formal Notations

- Formally, 
  - Given $R(A1,A2,… ,An)$ 
- $R(A1,A2,… ,An)$  is the **schema** of the relation
- $R$ is the name of the relation
- $(A1,A2,…,An)$ are the attributes of the relation
- $r(R)$: a specific **state** [instance] or relation $R$ - an actual set of **tuples** [rows]
  - $r(R) = t_1,t_2,...,t_n$ where each $t_i$ is an $n$ tuple
  - $t_i = \langle v_1,v_2,...,v_n\rangle$ where each $v_i$ comes from $dom(An)$ 
  - $r(R) \sub dom(A1) \cross dom(A2) \cross ... \cross dom(An)$ 

Why use the mathematical model for the DB:

- Presents a human with an understandable format for our data
- With the goal to simplify how:
  - To interrogate it
  - Maintain it

-----------------------------

#### More on Schemas

- Database = collection of relations
- Relation schema = relation name and attribute list
  - Optionally: types are specified.
- Database schema = set of all relation schemas in the database.



#### More on the relational model 

- Order of 
  - Tuples in a relation is not important
  - Attributes in a tuple is not important - same order is assumes
- Collection of relation schemas
  - Relational database schema $\longleftarrow$ **intension** - model of your data, how you want it to be stored
- Corresponding relation instances/states
  - Relational database  $\longleftarrow$ **extension** - when that data has been inserted into the database
- NB:
  - intension vs. extension
  - schema vs. data
- Metadata of the DB: schema and other key table info

-------------------------------

- Why Relations?
  - Very simple
- Abstract model
  - Has been enriched with declarative languages, such as SQL, the most important in DBMS today, simplifying users’ interactions with data
  - If you just select a particular field, then will only return the individual instances.
- Set oriented
  - Sets of attributes in a tuple
  - Sets of tuples in a relation
- SQL is based on bags (multisets)
- NOTE Sets $\neq$ Bags

-----------------

### Relational Database Model Constraints

- on keys
- on entities (entity integrity)
- on references (referential integrity)
- Possible violations of contrains
- Functional Dependencies

-----------------

#### Relational DB Constraints

- Used to determine the permissible states of relation instances
- Three (explicit schema-based) constrains used in the R-DBMSs:
  - Key constrains
  - Entity contraints
  - Referential integrity constraints
- Domain constraints
  - Values in an attribute in a tuple must come from the domain of that attribute
    - values could also be NULL
    - NULL could be where we do not yet know 

---------------------

##### Key Constraints

- SuperKey of $R$ a subset of attributes $R, SK$ such that:
- In any valid state for $r(R)$:
  - For any two distinct tuples: $t_1,t_2 \in r(R)$ 
    - $t_1[SK] \neq t_2[SK]$ 
  - E.g.
    - $R$(Name, Country, PhoneNumber)
    - $SK = \{$County, PhoneNumber$\}$ 
- Candidate key of $R$: a minimal superkey
  - Any key $K$ is a “minimal” superkey if:
    - The removal of any attribute from $K$ results in a set of attributes that is no longer a superkey.
  - if a relation has several candidate keys, one is chosen arbitrarily.

---------------

##### Entity Integrity Constraints 

- Entity Integrity:
  - The primary key attributes ($PK$) cannot be NULL in any tuple of $r(R)$ 
    - This is because primary key values are used to indetiy the individual tuples
    - If PK has several attributes, null is not allowed as a value in any of these attributes
  - Any attribute or $R$ may not be allowed to be null
    - Specified when the table is created

-----------------------

##### Relational Integrity Constraints 

- A table Students lists data about students such as age, grades etc.
  - Students has an attribute **Student_Id**
  - This is the PK.
- Another table **Student-Courses** has an attribute **Student_ID**
  - Listing, for each module which students are taking it, at which term
- (Bad idea to put this into one table)



Splitting data across different tables allows for much ‘better’ queries with more depth, and prevents too much NULL data in feilds.



- A set of attributes $FK$ from relation $R1$ is a foriegn jey that references relation $R2$ if:
  - Attribute(s) in the $FK$ from $R1$ have the same domain as the attribute(s) in the primark key $PK$ of $R2$, and
  - A value of $FJ$ in a tuple $t_1$ of $R!$ mustt either:
    - Refer to a value of the $PK$ of some tuple $t_2$ in $R2$ 
    - Or be NULL

![image-20211005151305639](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211005151305639.png)

**Summary** 

Keys, Permissibility of NULL, Candidate Keys (called unique), Foreign Keys, Referential Integrity are expressed by the CREATE TABLE statement. 

- Other “sematic attribute integrity constraints” also exist.
  - For example bank balance > 0
- Constraints exist to define permissible values
  - This concerns DB updates
  - Tuple insertions/deletions
  - Attribute-value updates which may, by definition, cause constraint violations
- The DB ensures all contraints are respected at any point

-----------------------------------------------

##### Possible Violations For Each Operation

- Insert:
  - Domain
    - One of the attribute values for new tuple is not in the attribute domain
  - Key
    - The value of a key attribute in new tuple already exists
  - Referential Integrity
    - A foreign key value in new tuple references a primary key value that does not exist in referenced relation
  - Entity Integrity
    - If primary key value is null in new tuple

- Delete
  - May only violate referential integrity
  - If PK value of the tuple being deleted is referenced from other tuples in other relations
  - Some option must be specified during DB design for each foreign key constraint on how to handle such deletions leading to RI violations
- UPDATE
  - The domain and NOT NULL contraints may be violated on an attribute being modified
  - Updating PK 
  - Updating a FK
    - May violate RI
  - Updating an ordinary attribute may only violate domain contraints

#### Functional Dependencies

- Why do we need
  - A formal tool that allows derivation of “good” DB design
  - A good design depends on the dependecies between attributes chosen to be in the same relation.
- Assume 
  - $X,Y,Z$ represents sets of attributes
  - $A,B,C$ represents single attributes. $ABC$ denotes the set $\{ A, B, C\}$
- $X\Rightarrow Y$ is an assertion about a relation $R$ and two sets of attributes from $R$ 
  - Specifies a constraint on the possible tuples in $ r(R)$ 
- If $X \Rightarrow Y$ the values of the $Y$ component of a tuple depend on values of the $X$ components
  - The values of the $X$ component of a tuple uniquely (functionlally) determone those of the $Y$ component
- So, $X \Rightarrow Y$ specifies that whenever two tuples of $R$ agree on values of all the attributes of $X$, then they must also agree on values of attribute of $Y$ 
  - Formally: $t_1[X] = t_2[X] \Rightarrow t_1[y] = t_2[Y]$ 

----------------------

##### Keys and Functional Dependencies — TODO

- Claim: If $K$ is a superkey, then $K \Rightarrow A$, for any (subset of) attribute(s) $A \in R$ 
- Claim: If $X\Rightarrow R$  then $X$ is a superkey.



##### Who Determines Keys/FDs?

- We could assert a key $K$ 
  - Then onlys FDs asserted are that $K \Rightarrow A$ for every attribute $A$ 
  - No surprise: K is the only key for those FDs, according to the fomal defintition of key
- Or we could assert some FDs and deduce one or more keys by the formal definition.
- Rule of Thumb: Often, DFs either come from keyness or from physics.





## Week 2 Reading

### Chapter 2 - Database Systems Concepts and Architecture

**Data Abstraction** generally refers to the suppression of details of data organization and store, only highlighting the essential features for an improved understanding of data. One of the main features of the DB approach is to support data abstraction so that different users can perceive data at a preferred level of details.

**Data model** - a collection of concepts that can be used to describe the structure of a database - provides the necessary means to achieve this abstraction.

**Database Structre** - the data types, relationships, and contraints that apply to the data. Most data models also include a set of **basic operations** for specifying reteivals and updates on the DB.

In addition to this, it is becoming common to include concepts in the data model to specify the dynamic ascpect or behabiour of a DB application, allowing the DB designer to specify a set of valid user-defined operations that are allowed on the Db objects.

The basic operations such as INSERT, DELETE, UPDATE or RETRIEVE any kind of object are typically included in the basic data model operations.



#### Categories of Data Models

Data models range from the **high level** or **conceptual** models provide concecpts that are close to the way the user would typically perceive the dat, whereas **low level**  or **physica;** models typically describe the details of how data is stored on the computer storeage - mostly magnetic disls.

Between these two, are **representational** or **implementation** data models, which provide concepts more easily understood by end users, but not too far removed from the way data is organized in computer storage. Representational data models hide many details of data storage on disk, but can be implemented on a computer system directly.

**Conceptual** data models use concepts such as entities, attributes, and relationships. An **entity** represents real-world object or concept, such as en employee or a person which is described in the DB. An **attribute** represents some property of interest that further describes an entity. A relationship across two or more entities represents an association among the entities. E.g. an employee and a project to which they have been assigned.

**Representational or implementation** data models are those used most frequently in traditional DBMSs, including the relational data model, the network and hierarchical data models.

#### Schemas Instances and Database State

The description of a database is called the DB Schema, which is specified during design, and not expected to change often. This describes the structure of each record type, but not eh actual instances.

#### Three-Schema Architecture and Data Independence

1. The internal level has an internal schema, which describes the physical storage structure of the DB, it uses a physical data model and describes the complete details of data storage and access paths in the DB.
2. The conceptual level has a conceptual schema, describing the structure of the whole database for a community of users. This hides the details of storage, and concentrates on describing entities, data types, relationships, user operations and constraints. Typically, a representational data model is used to describe the conceptual schema when the DB is implemented.
3. The external view includes a number of external schemas or user view. Each external schema describes the part of the DB that a particular user group is interest in and hides the rest from that UG. A above, each schema is normally implemented using a representational data model based on an external schema.

This idea helps the user visualise the schema levels in the DBS, despite this however most DBMSs do not separate these explicitly.

**Note** - all three levels of schemas are only descriptions of the data, not actual parts of the data itself.

#### Data Independence

The three schema architecture can be used to explain the concept of data independence.

1. Logical data independence is the capacity to change the conceptual schema without having to change external schemas or application programs
2. Physical data independence is the capacity to change the internal schema without having to change the conceptual schema

Wherever there is a multiple level DBMS its catalogue must be expanded to include information on how to map requests and data among the various levels.

----------

#### DBMS Languages

Where no strict separation of levels is maintained:

- DDL - data definition language is used by the DBA and the DB designers to define both schemas.
  - The DMBS will have a DDL compiler whose function it is to process the DDL statements in order to identify descriptions of the schema construct and to store the schema

Where a clear separation is maintained between the conceptual and internal levels, the DDL is used to specify the conceptual schema only:

- The SDL - storage definition language is used to specify the internal schema. The mapping between the two can be specified in either of the two languages
- Typically, now a days, there is no specific language that performs the role of SDL. The internal schema is specified by a combination of functions, parameters and specifications related to storage of files, permitting the DBA staff to control indexing choices and mapping of data to storage.

For a true three level architecture, we need a third language the:

- VDL - view definition language to specifiy user viewsa and the mappings to the schema
  - Typically, the DDL is used to define both conceptual and external schemas.
  - In relational databases, SQL is used in the role of VDL to define user applications views as results of predefine querues



Once this has been compiled, and the DB populated, the language used to manipulate the data is called the:

- DML - data manipulation language.



**NOTE** - currently, the previous types if languages are not considered distinct languages, rather an integrated language is used that includes the functionality of all of them combined. **Excluding** the storage definition, as it is used for defining physical storage structure to fine tune DB performance

Typically, DBMSs allow the user to either enter DML statements from a command line, a GUI, or embedded into a general-purpose programming language.

- A low level or procedural DML must be embedded in a gen-pop programming language.
  - This type of DML typically retrieved individual records or objects from the DB and processes each separately, therefore must use programming language construct, such as looping, to reteive and process each record. These are also often called **record at time** DMLs.
- High level DMLs such as SQL can specify and retrieve as many records in a single DML statement - called **set at a time** or **set oriented** DMLs. 
  - This generally specifies what data to retrieve rather than how - also called **declarative**.

#### The Database System Environment

##### DBMS Component Modules

- The image below shows a simplfied diagram of the DBMS components. This is divided into two parts:
  - The top half references the users of the database and the appropriate interfaces available to them.
  - The bottom half references the internal modules of the DBMS responsible for storeage of data and transactions.

- The database and the DBMS catalogue are usually stored on disk, access to the disk is controlled primarily by the OS, which schedules disk read/write. Many DBMSs have their own buffer management module to schedule dis read/write.
  - Management of buffer space has a considerable effect on performance.
  - Reducing tee number of disk read/write improves performance considerably.
- A higher level stored data manager module controls access to the DBMS information that is stored



**User Section**

- This interface shows the DBA staff, casual users, application programmers, and parametric users who do data entry by supplying parameters to pre-defined transactions.
- The DBA staff work on defining the database and tuning it by making changes ti uts definition using the DDL and other privileged commands.

![image-20211007121727745](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007121727745.png)

- Casual users and persons with occasional need for information from the DB interact using the interact query interact. These queries are validated for correctness etc by the query compiler that compiles the queries into an internal form. This query is then optimised - reordering of operations etc.
- Application programmers write programs in host languages such as Java or C, that are submitted to a precomplier. This extracts DML command from an application program written in the host programming language. These are send to the DML compiler for compilation into object code for DB access. The rest is sent to the host language compiler. The object codes for the DML commands and the rest of the program are linked. 
  - It is becoming common to use scripting language such as Python or #PHP to wrtie database programs

##### Database System Utilities

Most DBMSs have database utilities that help the DBA manage the DB system.

- **Loading** - a loading utility used to load existing files - text or sequential files into the DB.
  - Typically, the source format of the current  and the target database file structure are specified to the loading utility. This automatically reformats the data and stores it in the DB.
  - It has been very common to transfer data across databases, therefore some DBMSs come with conversion tools.
- **Backup** a backup utility created a copy of the entire database. Typically by dumping the entire DB onto tape or a mass storage medium. Incremental backups are also used to backup any changes made to the DB.
- **DB storage reorganisation** - This can be used to reorganise a set of DB files into different organizations and create new access paths to improve performance.
- **Performance Monitoring** - This monitors DB usage and provides statistics to the DBA. This uses the stats in making decisions such as whether to reorganise files or where to add or drop indexes to improve performance.

##### Tools, Application Environments and communications facilities.

- **Data dictionary/ repository system** - in addition to storing catalogue information about schemas …, the data dictionary stored information such as design decisions, usage standards, application program descriptions and user info.
  - This can be accessed directly by the user or the DBA when needed.
- **Application Development Environment** provide an environment for developing DB applications and inculde facilities that help in many aspects of  DB systems such as DB design, GUI development, query and updating, and AP development.
- **Communications software** - This allows users to remote access to the DB system site through computer terminal, workstations, or personal computers. These are connected to the DB site through various forms of data/network connection hardware.

##### Classification of Database Management Systems

- The main model is the relational data model, and the systems based of this are SQL systems.
- Occasionally some NOSQL systems
- Some object-relational DBSMs

This gives rise to the following classifications:

- Relational
- Object
- Object-Relational
- NOSQL
- Key-value
- Hierarchical
- Network

### Chapter 3  Data Modelling Using the Entity-Relationship Model

Conceptual modelling is a key phase in designing a DB application.

- DB application tends to refer to a particular database and the associated programs the implement the DB queires and updates

#### Using High-Level Conceptual Data Models for Database Design

The image below shows a diagram of the rough process for designing a DB application.

![image-20211007161535607](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007161535607.png)

**Entity Relationship (ER) Diagrams**

- Entity relationship diagrams give a graphical representation of the relationships between different entities and their attributes.

**Entities and Attributes**

The basic concept that ER model represents is an **entity** - something that is a thing or an object in the real world with an independent existence. Either physical or conceptual.

Each entity has **attributes** - the particula properties that describe it (A person may have an attribute AGE)

 **Composite verus Simple (Atomic) Attributes**

- Composite attributes can be divided into sub-parts, which represent more basic attributes with independent meaning.
  - An Address for example may have multiple components:
    - Street name
    - Post code
    - House Number
- Simple attributes are those that are not divisible any more
- The composition of composite and atomic attributes can leave you with a hierarchy

![image-20211007162951121](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007162951121.png)

**Single-Valued versus Multivalued Attributes**

Most attributes have a single value for each entity: these are called single valued entities (a person has one age). Some attributes have multiple values: the colour of a car which has been painted red and blue has two values.

**Stored versus Derived Attributes**

In some cases, two (or more) attribute values are related, for example the age and birth date of a person are related. They are both derivable from each other.

- Say we store the Birth_Date of a person, the Age of that person is called a **derived attribute**, and is **derivable form** the birth date, which is called the **stored attribute**.
- Some attribute values can be derived from related entities. - The number of students on a course at university can be derived from the number of entries of students.

#### Entity Types, Entity Sets, Keys, and Value Sets

##### **Entity Types and Entity Sets** 

A database typically contrains groups of entities that are similar - a company may want to store similar information on each of the employess - they share the same attributes but with different values. An **entity type** defines a collection (or set) of entities that have the same attributes. 

- The collection of all entities of a particular type in the database at any point is called an **entity set** or collection, this is usually referred to using the same name as the entity type, despite being two different concepts. 
- An entity type is represented in ER diagrams as a rectangular box enclosing the type name. Attribute names are enclosed in ovals and attached to the entity with straight lines.
  - Composite attributes are attached to their components by straight lines
  - Multivalued attributes are depicted by double ovals.
- An entity type descibes the **schema** or **insertion** for a set of entities that share the same structure

##### **Key attributes of an Entity Type**

An important constraint on the entities of an entity type is the key or **uniqueness constraint** on attributes. An entity type usually has one or more attributers whose values are distinct for each entity in the set. This is called a:

- Key Attribute, and its values can be used to identity each entity uniqeuly. For example a company name could be a key as no company can have the same name as another.
- Sometimes multiple values may make up a key, meaning the combination of each attribute must form a unique key: an address. Lots of houses can share a house number or street, but none can have the same combination of both.
- If this is the case, the proper practice is to define a composite attribute and designate it as a kay attribute of the entity type.
  - In an ER diagram, they key attribute has its name underlined in the oval.
  - Defining something as a key, means that it must be unique for every entry in the set, at any point in time - not just a particular set.
  - Some entities may have multiple keys.

--------------------------------

##### **Value Sets (Domains) of Attributes**

(Covered in notes above in detail - see RDBM section)

------------------

#### Relationship Types, Relationship Sets, Roles, and Structural Constraints

##### **Relationship Types, Sets, and Instances**

A **relationship type** $R$ among $n$ entity types $E_1,…,E_n$ defines a set of associations or a **relationship set** among entities from these entity types. A relationship type and its corresponding set are typically referred to with the same name $R$.

- Mathematically, the set $R$ is the set of **relationship instances** $r_i$ where each $r_i$ associates $n$ individual entities: $(e_1,e_2,…,e_n)$, and each of these entities $e_j$ in $r_i$ is the remember of the entity set $E_j : 1 \leq j \leq n$,
- Therefore, a relationship set is a mathematical relation on $E_1,E_2,…,E_n$, or can be defined as a subset of the cartesian product of the entity sets. 
- Each of the entity types is said to participate in the relationship type $R$, and each of the individual entities is said to participate in the relationship instance $r_i = (e_1,e_2,…,e_n)$  

From the textbook “Informally, each relationship instance $r_i$ in $R$ is an association of entities, where the association includes exactly one entity from each participating entity type. Each such relationship instance $r_i$ represents the fact that the entities participating in $r_i$ are related in some way in the corresponding miniworld situation.”

View the example below:

![image-20211007171337953](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007171337953.png)

- In ER diagrams, relationship types are displayed as diamond box shapres, which are connected by straigt lines to the rectangular boxes representing the entity types. The relationship name is showed in a diamond shaped box.

-------------------------

##### Relationship Degree, Role Names, and Recursive Relationships

The degree of a relationship type is the number of participating eneity types.

- A degree of two is called binary, and of three is called ternary. An example of a ternary is shown below:

![image-20211007171726391](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007171726391.png)

- Relationships can be of any degree, but tend to be binary.

-----------

##### **Relationships as attributes**

Sometimes it is useful to think of a binary relationship as an attribute. 

As Stated by text book: - come back to this to explain better

Consider the WORKS_FOR relationship type in Figure 3.9. One can think of an attribute called Department of the EMPLOYEE entity type, where the value of Department for each EMPLOYEE entity is (a reference to) the DEPARTMENT entity for which that employee works. Hence, the value set for this Department attribute is the set of all DEPARTMENT entities, which is the DEPARTMENT entity set. This is what we did in Figure 3.8 when we specified the initial design of the entity type EMPLOYEE for the COMPANY database. However, when we think of a binary relationship as an attribute, we always have two options or two points of view. In this example, the alternative point of view is to think of a multivalued attribute Employees of the entity type DEPARTMENT whose value for each DEPARTMENT entity is the set of EMPLOYEE entities who work for that department. The value set of this Employees attribute is the power set of the EMPLOYEE entity set. Either of these two attributes—Department of EMPLOYEE or Employees of DEPARTMENT—can represent the WORKS_FOR relationship type. If both are represented, they are constrained to be inverses of each other.

-------------

##### **Role Names and Recursive Relationships**

Each entity that participates in a relationship type plays a particular role in the relationship. The **role name** signifies the role that a participating entity from the entity type plays in each relationship instance.

- Taking the example for a WORKS_FOR relationship:
  - An EMPLOYEE plays the role of employee or worker
  - DEPARTMENT plays the role of department or employer.

- Role names are not technically necessary in relationship types where all the participating entity types are distinct, since each entity type name can be used as the role name.
- In some cases, the same entity type participates more than once in a relationship type in different roles
  - Here it becomes essential for distinguishing the meaning of the role that each entity plays
- This is called **recursive relationships** or **self referencing relationships**

Take the example below:

- The SUPERVISION relationship can have multiple connections for each employee.
- The lines labelled 1 represent the supervisor role, and 2 represent the supervisee role. 

![image-20211007190357504](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007190357504.png)

----------------

##### Constraints on Binary Relationship Types

Relationship types have constraints that limit the certain possible combinations of entities that may participate in the relationship set.

----------------

##### **Cardinality Ratios for Binary Relationships**

The cardinality ration specifies the maximum number of relationship instances that an entity can participate in. The possible values for these rations are:

- $1:1$ 
- $1:N$ 
- $N:1$ 
- $M:N$ 

--------------

##### **Participation Constraints and Existence Dependencies**

The participation constraint specifies whether the existence of an entity depends on its being relation to another entity via the relationship type.

- This specifies the minimum number of relationship instances that each entity can participate in   (**minimum cardinality constraint**). There are two types of participation constraints:
  - Total: Take the example of a company policy that every employee must work in a department is **total participation**. In other words, this is called an **existence dependency**
  - Partial: Take the example where not every employee is expected to run a department, this is **partial participation**. 

- In ER diagrams, total participation is displayed as a double line, and partial participation is displayed as a single line

--------------

##### **Attributes of Relationship Types**

- Relationships can have attributes similar to those of entity types.
- To record the number of hours per week that an employee works on a project, an attribute HOURS can be added to a the WORKS_ON relationship

---------------

#### Weak Entity Types

Entities without key attributes are called **weak entity types** - all previous so far, are called **strong entity types**. Entities belonging to a weak entity type are identified by being related to specific entities from another type combined with one of their attribute values.

The other entity is called the **identifying/owner entity type**, and call the relationship between them the **identifying relationship**.

A weak entity always has a total participation constraint with respect to its identifying relationship, as it cannot be identified without its owner.

Take the example of CHILDREN related to EMPLOYEE, used to keep track of each employee with a 1:N relationship. The children of different employees may be called the same thing, and have the same DOB, but they are still distinct. In this case what separates the children is the EMPLOYEE which relates to that child.

This means that each weak entity type typically has a partial key, which can identify different weak entities related to the same owner entity.

----------------

#### ER Diagrams, Naming Conventions, Design Issues

#####  Design Choices for ER Conceptual Design

![image-20211007193856263](C:\Users\leonc\AppData\Roaming\Typora\typora-user-images\image-20211007193856263.png)

------------------

### Chapter 5

- Come back to this, mainly slightly more in depth than what was on slides.



## Week3 - Declarative Languages

### DB system Philosophy

- SQL  is a Higher level language
  - Declarative
  - What to do rather than how
    - How to do is typically  used in procedural languages
    - Declarative languages avoid a lot of the complexity involved for data-manipulation which is present in languages like Java
    - Even during data definition, we simply state the constraints and the DB behind the scenes ensures the consistency

- The Philosophy is:
  - Tell a DBS what is wanted
    - The DBS will find an “optimal” solution to execute the query
    - Referred to as query optimisation
- SQL is both:
  - DDL - Data definition Language: schemas, relations constrains
  - DML - Data manipulation language: updates, queries

### Terminology vs the relational model

| Relational | SQL    |
| ---------- | ------ |
| Relation   | Table  |
| Tuple      | Row    |
| Attribute  | Column |

Definitions created via the CREATE command.

#### SQL standards

- Evlolving over time
- Later standards have core specifications and extensions
  - Extensions are typicallh for emerging applications - data mining for example
- SQL-2006 added XML and 2008 added O-O features
- SQL-3 is the current standard which started with SQL-1999
- SQL must operate with the provided DBMS

### SQL as a DDL

#### Databases, Schemas and Catalogue

Each DB contains one or more schemas

- Each schema contains one or more tables

The CREATE SCHEMA statement: CREATE SCHEMA company AUTHORIZATION ‘leon’;

- Creates a schema company owned by leon
- The schema company can create one or more tables

Catalogue

- Name collection of schemas in an SQL environment

#### Create Table Command

- This specifies new relations they provide:
  - Name of the table
  - The attributes, along with their types and names
  - Any constrains
- All tables belong in a schema
- Base tables (relations)
  - Relation and its tuples are created and stored as a file by the DBMS
- Virtual relations (views)
  - Created through the CREATE VIEW command - doesn’t necessarily correspond to any physical file.

##### Syntax

- SQL Create table:

  ```sql
  CREATE TABLE <tableName> (...);
  ```

  - tableName is subsituted with the name of the table/relation variable
  - (…) is the list of attributes and constraints

- Attribute/Constraint List Format

  ```sql
  (<Att1Name><Att1DataType><AttConstraints>,<Att2Name><Att2DataType><AttConstraints>)
  ```

##### Attribute Data Types

| ANSI Data Type                        | Desc.                                           | PostgreSQL                | SQLITE3 |
| ------------------------------------- | ----------------------------------------------- | ------------------------- | ------- |
| CHARACAT(n)                           | Character string on n chars, fixed length       | CHAR(n)                   | TEXT    |
| CHARACTER VARYING(n)                  | Character String up to n chars, variable length | VARCHAR(n), TEXT          | TEXT    |
| NUMERIC(p,s)                          | Number with selectable precision                | NUMERIC(p,s) DECIMAL(p,s) | NUMERIC |
| INTEGER, INT, SMALLINT                | Integers with 4 or 2 bytes respectively         | INT, INT4, INT2           | INTEGER |
| FLOAT(b), DOUBLE PRECISION(c) REAL(d) | Floating point numbers                          | FLOAT4, FLOAT8            | REAL    |

- ANSI datatypes are standard
- A DBMS may have its own datatypes
- Many DBMS recognise ANSI and convert to their own

```sql
CREATE TABLE students (
	studentID INTEGER PRIMARY KEY,
	studentName CHAR VARYING(30),
    courseID INTEGER FOREIGN KEY
);
```

- This created this table schema and recorded it and the constraints in the catalog

##### Specifying Constraints with SQL

- Seen that SQL supports 3 contraint types

  - Key constraint: A PK value is unique
  - Entity integrity Constraint: a primary key value cannot be null
  - Referential Integrity contraints: a “foreign key” must have a value that is already present as a primary key or it may be null

###### Attribute constraints.

- Additional restrictions on attribute domains can be specified.

  - Null not permitted
  - Default value

  ```sql
  AccountBalance REAL NOT NULL DEFAULT 0.0;
  ```

  - Check Clauses

  ```sql
  Age INT NOT NULL CHECK (Age > 0 AND Age < 125)
  ```

###### Key Constraints:

- PRIMARY KEY clause

  - Specifies one or more attributes that make up the primary key of a relation

  ```sql
  Dnumber INT PRIMARY KEY;
  ```

- UNIQUE clause

  - Specifies alternate keys - candidate keys in the relational model

  ```sql
  Dname VARCHAR(15) UNIQUE; 
  ```

###### Referential Integrity Constraints

- FOREIGN KEY clause induces contraints which must be checked and handled during updates
  - Default operation: reject updates on violation
  - Attach referential triggered action clause
    - SET NULL
    - CASCADE
    - SET DEFAULT
- Attach action to be taken upon violation can be made to vary based on updates
  - ON DELETE or ON UPDATE

###### Referential Integrity Triggered Actions

- ```sql
  CONSTRAINT SuperSSN-SSN
  FOREIGN KEY (Super_ssn) REFERENCES EMPLOYEE(SSN)
  ON DELETE SET NULL ON UPDATE CASCADE
  ```

- If a supervisors tuple is deleted from EMPLOYEE,

  - The tuples referencing (through the Foreign key Super_ssn) the deleted tuple will have its Super_ssn value set to NULL

- If a supervisors tuple’s SSN value in EMPLOYEE is updated:

  - The new SSN value will be cascaded to the value of Super_ssn of all tuples referencing the updated EMPLOYEE tuple

###### Constraint Primary Key Syntax:

Primary KEY

```sql
<attName><attType> NOT NULL PRIMARY KEY,
<attName><attType> NOT NULL, ..., PRIMARY KEY(<attName>),
```

This identifies the \<attNAme\>   attribute as primary key - also means it is unique

The syntax is the same for UNIQUE

###### Constraint Foreign Key Syntax

```sql
FOREIGN KEY(<attName1>) REFERENCES <tableName>(<attName2>),
```

Sets \<attName1\> to act as a foreign key that refers to attribute \<attName2\> in tableName.

**Note** \<attName1\> can be both a primary key and a foreign key.

Example: 

```sql
FOREIGN KEY(students.courseID) REFERENCES courses(courseID)
```

**Note** The foreign key does not have to reference an attribute of the same name - the integrity check only cares about comparing values

- Imposes a fixed order to operations:
  - Must add a course with ID=3 before adding a student with a reference to 3. 

###### Attribute Constraint Syntax:

Domain restrictive constraints:

```sql
<attName><attType> CHECK(<boolean expr.>),
<attName><attType>,..., CHECK(<boolean expr.>),			
```

- CHECK applies restrictions on the accepted values, they do not only need to match the domain constraints, but must also evaluate the boolean expression to true.
- CHECK can be added at the end of CREATE TABLE - regardless, it will be run whenever a tuple is inserted or updated

Example

```sql
StudentID INT PRIMARY KEY
CHECK (StudentID > 0 AND StudentID <5000)
```

Constraint Naming:

- Naming constraints allows for easier references, especially if a constraint is more complex.

```sql
CONSTRAINT <constraintName> <constraint>
StudentID INT CONSTRAINT nonzero CHECK(StudentID > 0)
CourseID INT DEFAULT 1,
```

###### Constraints - Syntax for Referential Integrity Triggered Actions

```sql
FOREIGN KEY(students.courseID) REFERENCES courses(courseID) ON UPDATE CASCADE
FOREIGN KEY(students.courseID) REFERENCES courses(courseID) ON DELETE SET NULL
FOREIGN KEY(students.courseID) REFERENCES courses(courseID) ON DELETE SET DEFAULT
```

Provide actions based on triggerss:

#### DROP TABLE

```sql
DROP Table <tableName>;
```

- Deletes the table - the entire relation, including the schema and the data.

#### DROP SCHEMA 

```sql
DROP Schema <schemaName>;
```

- Deletes the schema and all its objects - all the tables contained in it.



### SQL as a Data Manipulation Language

#### Basic Retrieval Queries - Results and Semantics

- The relational model is set-theory based:
  - Relations in RM are defined to be a set of tuples:
  - $\{a,b,c,…\}$ 
- Unlike the RM, SQL DBs allow tables to contain duplicates of tuples
  - $\Rightarrow$ Multi-set semantics or bag semantics:
  - $\{a,b,b,a,c,…\}$ 
- Why allow duplicates
  - SQL query results are also tables
  - It is expensive to delete duplicates:
    - requires a sorting operation - expensive.
- Duplicates may be desirable
  - Different ‘entities’ have the same value - name, address, or the same car
  - For aggregates (AVG,SUM,COUNT)
- There must still be a way to identify each tuple in a table.
  - A tuple-id (auto inc.) may be used as a key to ensure uniqueness 

##### SELECT clause

```sql
SELECT <attribute1,attributei> FROM <table list> WHERE <condition>
```

- Defines a list of attributes
- Defined a list of the relation names/tables needed to process the query
- Defines a boolean expression
  - Only return tuples who satisfy the boolean condition.

```sql
SELECT DISTINCT studentName FROM students;
```

- This removes any duplicates from the output

##### WHERE:

- The where clause can have multiple expressions, with AND, OR, NOT combinations.

General view:

```sql
WHERE val1 BETWEEN 0 AND 1;
WHERE boolExpr1 AND boolExpr2 OR boolExpr1 AND NOT boolExpr3;
```



##### Asterisk in Select:

```sql
SELECT * FROM students:
```

##### Naming Qualification:

```sql
SELECT students.studentID FROM students:
```

- references the studentID  column from the students Table
- Useful if tables in your table list have a shared attribute name between them

##### Naming Qualification and Aliasing

```sql
SELECT S.studentID  FROM students S;
```

- The students table has been aliased to the name S
  - The name S is now used for any qualification - even in a WHERE  clause

##### Compute Result for a Single Relation Query

- Start with the relation in the FROM clause
- Apply the row selection indicated by the WHERE clause
- Apply the column projection indicated by the SELECT clause

Operational semantics

- Imagine a tuple variable ranging over all tuples $t_v$ ranging over all tuples in the relation mentioned in FROM 
  - For each tuple:
    - Check if it satisfies the predicates/expressions in the WHERE clause
    - IF so, computer the attributes or expressions of the SELECT clause using the components of the tuple
    - Move to the next
- A SQL query only produces a tuple in the answer if its truth value for the WHERE clause evaluates to TRUE

##### Select Semantics of Single Relation Queries

Comparing a Java method with the same variables:

```sql
SELECT dateOfBirth, houseNumber, street
FROM Employee
WHERE city = 'Warwick';
```

```java
public void employeeDetails(){
    System.out.println("dateOfBirth" + " " + "houseNumber" + " " + "street");
    for(int e = 0; e < nEmployees; e ++) 
        if (city == "Warwick") System.out.println("dateOfBirth" + " " + "houseNumber" + " " + "street");
}
```

- Both are iterating through the set of tuples
  - For each one, the boolean expression is evaluated
  - If TRUE, output the values specified in SELECT clause

##### Wildcards for Attributes, Ordering  Result Tuples

```sql
Select *
FROM Teas
WHERE manf='Tetley'
ORDER BY name;
```

By default, done alphabetically or in growing size, however this can be defined.

##### Renaming Columns

- To change the attribute name on a query:

  As \<newName\> renames the attribute - this can be useful where two columns have the same name in different tables that are being queried

##### Expression as Values in Columns

- Any expressions which make sense can appear as an element of a SELECT clause

```sql
SELECT productName, price*147 AS priceInYen 
FROM Sells;		
```

- a constant can also be added here - where it makes sense - a particular string would work in a `VARCHAR` field, but not in an `INT` field

##### Strings in Where Clauses

- Can also have conditions for strings, in which a string is compared with a pattern to see if it matches
- General form:
  - `<StringAttr> LIKE <pattern>` 
  - `<StringAttr> NOT LIKE <pattern>` 
- A pattern is a quotes string with special chars:
  - % = “any string” of 0 or more chars
  - _ = “any characters” - exactly one char

#### NULL values

- Tuples in SQL can have NULL values as a special value for one or more attributes
- Needs care - They are not real values
- Each individual NULL is considered from every other NULL values
- Very iseful:
  - Unknown value
  - Unavailable value
  - Inapplicable

##### Comparing NULL’s to Values

The WHERE clause in SQL provides logical Boolean expressions in order to identify the tuples desired by the query.

- a SQL query only proeduces a tuple in the answer if its true value for the WHERE-clause evaluates to true

  ```sql
  SELECT name WHERE surname ='chipchase';
  ```

- To account for NULLs, the logic of conditions in SQL is not just TRUE,FALSE, but includes a third state - UNKNOWN

- When any values is compared with NULL, the true value is UNKNOWN

##### Truth tables for 3 Valued Logic

##### AND

| TRUE   | FALSE | UNKNOWN | AND     |
| ------ | ----- | ------- | ------- |
| TRUE   | FALSE | UNKNOWN | TRUE    |
| FALSE  | FALSE | UNKNOWN | FALSE   |
| UNKOWN | FALSE | UNKNOWN | UNKNOWN |

##### OR

| TRUE | FALSE   | UNKNOWN | OR      |
| ---- | ------- | ------- | ------- |
| TRUE | TRUE    | TRUE    | TRUE    |
| TRUE | FALSE   | UNKNOWN | UNKNOWN |
| TRUE | UNKNOWN | UNKNOWN | UNKNOWN |

##### NOT

| NOT     |         |
| ------- | ------- |
| TRUE    | FALSE   |
| FALSE   | TRUE    |
| UNKNOWN | UNKNOWN |

##### How to Use NULL in Predicates

- Never use “A = NULL” will never return true
- USE `<Attr> IS NOT NULL` or the `IS NULL` operator.
