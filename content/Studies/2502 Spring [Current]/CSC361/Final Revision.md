---
publish: true
created: 2026-05-27T17:18:06.173+03:00
modified: 2026-05-27T18:06:04.693+03:00
---

# Definitions:

## Entities:

**Strong Entity:** Exists independantly
_Example: Student entity and Book entity, each with its own attributes, and they're not dependant on each other_
**Weak Entity:** the opposite; is dependant on another entity, usually a strong one.
_Example:_ A chapter has no meaning without being part of a book

## Attributes:

Properties or the characterstics of entities

### Simple Attribute:

Cannot be subdivided
_Ex: First Name_

### Composite Attribute:

An attribute that can be divided into smaller **Simple Attributes**
_Ex: Full Name -> First Name & Last Name_

### Derived Attribute:

An attribute that can be figured out using other attributes
_Ex: Age can be derived from Birthdate_

### Multivalued Attribute:

_Ex: Someone with multiple email addresses would have his Email Address attribute as a Multivalued Attribute_

### Key Attributes:

#### Primary Key (PK):

A unique identifier for each record within a table

- Must ensure no duplication
- Every table should have one
- Is denoted by a constraint in the db design

#### Foreign Key (FK):

An attribute in one table that refers to the **PK** of another table

- Establishes relationships between tables (referential integrity)
- Ensures the correspondence of every **FK** value to an existing **PK** value in the referenced table

#### The Overall Significance of Key Attributes:

- Ensures accuracy and consistency of data through duplication prevention
- Retrieves data quickly with the use of indices

## Relationships:

_Ex: Between "Book" and "Student" entities in a library db, there would be a "Borrows" relationship._

### Types of Relationships:

#### Unary Relationship:

Between two instances of a single entity type
_Ex: "Manages" relatipnship between "Employee" if an employee manages the others_

#### Binary Relationship:

A relationship between instances of two entity types
_Ex: "Book" and "Author": "Writes"_

#### Ternary Relationship:

A relationship involving instances of three entity types.
\*Ex:)

# Diagram Types:

## ERD:

### Visual Example:

![[Studies/2502 Spring [Current]/CSC361/Media/Screenshot 2026-05-27 at 5.23.56 PM.png]]

# Practical Applications:

- Two tables with an N:M relationship: **Junction Table** that holds both of the **PK** values of the two tables as **FK's**
- Multivalued Attribute: Dedicated **Table**
- 1:N relationship: The **FK** is stored at the "Many" table side
