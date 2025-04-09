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

# Relationships statements for each entity

# Logical model

# Physical model

# Arguing for normalisation