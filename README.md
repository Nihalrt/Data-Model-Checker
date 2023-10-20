# DataGuard

## Description

The Data Model Checker for MySQL Databases is a versatile Python utility designed to rigorously evaluate the integrity and correctness of a MySQL database schema. It empowers database administrators and developers by verifying whether a given database aligns with the logical and relational schema designed for it. The tool encompasses a wide range of functionality, including the confirmation of superkeys, foreign keys, referential integrity, and functional dependencies.

## Table of Contents

- [Features](#features)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Code Overview](#code-overview)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Features

### Superkey Confirmation

**Function: `confirmSuperkey(attributes)`**

In relational database management, a superkey is a set of one or more attributes (columns) in a database table that can uniquely identify a tuple (row) in that table. This function checks if the provided attributes form a superkey for a table.

- **Parameters:**
  - `attributes`: An instance of the `Attributes` class containing the table name and a list of attributes to be checked for being a superkey.

- **Return Value:**
  - `True` if the provided attributes form a superkey.
  - `False` if they do not form a superkey.

### Foreign Key Confirmation

**Function: `confirmForeignKey(referencing_attributes, referenced_attributes)`**

A foreign key establishes a relationship between two tables in a database. This function verifies if a foreign key relationship between two tables is enforced correctly.

- **Parameters:**
  - `referencing_attributes`: An instance of the `Attributes` class representing the referencing table with its attributes.
  - `referenced_attributes`: An instance of the `Attributes` class representing the referenced table with its attributes.

- **Return Value:**
  - `True` if the foreign key relationship is enforced correctly.
  - `False` if it is not enforced correctly.

### Referential Integrity Confirmation

**Function: `confirmReferentialIntegrity(referencing_attributes, referenced_attributes, policy)`**

Referential integrity is crucial in maintaining relationships between tables. This function checks and enforces referential integrity constraints in a database schema.

- **Parameters:**
  - `referencing_attributes`: An instance of the `Attributes` class representing the referencing table with its attributes.
  - `referenced_attributes`: An instance of the `Attributes` class representing the referenced table with its attributes.
  - `policy`: An instance of the `RefIntegrityPolicy` class defining the operation and policy for handling violations.

- **Return Value:**
  - `True` if referential integrity constraints are maintained correctly.
  - `False` if they are not maintained or if an error occurs.

### Functional Dependency Confirmation

**Function: `confirmFunctionalDependency(referencing_attributes, referenced_attributes)`**

Functional dependencies are crucial in eliminating data redundancy and ensuring data integrity. This function checks for and enforces functional dependencies within a database schema.

- **Parameters:**
  - `referencing_attributes`: An instance of the `Attributes` class representing the referencing table with its attributes.
  - `referenced_attributes`: An instance of the `Attributes` class representing the referenced table with its attributes.

- **Return Value:**
  - `True` if functional dependencies are enforced correctly.
  - `False` if they are not enforced correctly or if an error occurs.

## Dependencies

To use the Data Model Checker, ensure you have the following dependencies installed:

- Python 3.x
- `mysql.connector` library (for MySQL database connectivity)

You can install the required dependencies using `pip`:

```bash
pip install mysql-connector-python
