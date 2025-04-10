## Building a database for YrkesCo

This document describes the process of designing a database model for YrkesCo. It includes multiple data models along with detailed explanations.

## Table of contents
- [Business requirements](#business-requirements)
- [Conceptual model](#conceptual-model)
- [Relationships statements for each entity](#relationships-statements-for-each-entity)
- [Logical model](#logical-model)
- [Physical model](#physical-model)
- [Arguing for normalisation](#arguing-for-normalisation)

# Business requirements

- Students: First name, last name, personal identification number, and email.

- Trainers: Can be consultants.

- Permanent trainers: They plan to hire full-time trainers (BONUS).

- Education managers: Their personal details.

- Education managers: Responsible for 3 classes.

- Courses: Name, course code, number of credits, and a short description.

- Programs: Consist of multiple courses.

- Program approval: A program is approved in three rounds, meaning there are three classes.

- Standalone courses: Also available (BONUS).

- Consultants: Their company details, including organization number, F-tax status, address, and hourly rate.

- Facilities: YrkesCo has two locations, one in Gothenburg and one in Stockholm. In the future, they may expand to more cities (BONUS).

# Conceptual model

<img src = "./yh_labb_assets/conceptual_diagram.png" width=500>

# Relationships statements for each entity

- A `student` is enrolled in one `class`
- A `student` has exactly one associated `studentInformation` containing sensitive personal data
- A `class` has many `students`
- A `class` belongs to one `program`
- A `class` is managed by one `educational leader`
- A `class` is connected to `multiple` courses through `ClassCourse`
- An `educational leader` can be `responsible` for up to `three classes`
- A `program `includes multiple `classes`
- A `program` can have several `courses`
- A `course` can be part of multiple programs.
- A `course` can be given in `multiple classes` via `ClassCourse`
- A `course` can be taught by multiple educators through EducationalCourse.
- A `ProgramCourse`connects programs to their respective `courses`
- `ClassCourse` links classes to the `courses` they take.
- Each `ClassCourse` is taught by one `educator`
- A `campus` can host multiple `classes`
- An `educator` can teach many courses through `EducationalCourse`
- An `educator`can be assigned to `multiple ClassCourses`
- An `educator` can be a `consultant`
- `EducationalCourse` connects `educators` to the `courses` they are qualified to teach.
- A `consultant` can also be an `educator`
- A `consultant company` can employ multiple `consultants`

# Logical model

<img src = "./yh_labb_assets/logical_diagram.png" width=500>

# Physical model

<img src = "./yh_labb_assets/physical_diagram.png" width=500>

# Arguing for normalisation

The model satisfies `First Normal Form (1NF)` as all attributes are indivisible and contain only a single value. Primary keys are used to uniquely identify each row. Furthermore, the model avoids redundancy by using relationships instead of duplicating data—many-to-many relationships are handled using bridge tables.

It also fulfills `Second Normal Form (2NF)` by eliminating partial dependencies. Data has been separated into dedicated tables to ensure that all attributes depend solely on their own primary keys. In the bridge tables, all non-key attributes are fully dependent on the entire composite key.

Finally, the model meets the requirements of `Third Normal Form (3NF)` by avoiding transitive dependencies, "non-primary attributes depend on the key, the whole key, and nothing but the key."