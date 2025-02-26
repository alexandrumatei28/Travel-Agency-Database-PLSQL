# Tourism Agency Database

## Overview
This project is a comprehensive database system designed for a tourism agency, implemented using Oracle SQL. It manages clients, employees, vacation packages, reservations, accommodations, transportation, and related entities, utilizing sequences, tables, triggers, procedures, functions, and packages to ensure robust data handling and business logic enforcement.

## Features
- **Database Structure**:
  - **Sequences**: 10 custom sequences (e.g., `SEQ_CLIENT`, `SEQ_REZERVARE`) for auto-incrementing primary keys across entities.
  - **Tables**: 10 interconnected tables (`CLIENT`, `ANGAJAT`, `SALARIU`, `REZERVARE`, `PACHET_VACANTA`, `SEDIU`, `ADRESA`, `DEPARTAMENT`, `CAZARE`, `TRANSPORT`) with foreign key relationships to maintain data integrity.
- **Data Population**: Sample data inserted for all tables, covering clients, employees, vacation packages, reservations, and more, with realistic values (e.g., destinations like New York, Paris).
- **Stored Procedures**:
  - `afisare_informatii_rezervare`: Displays reservation details using nested tables, index-by tables, and varrays.
  - `detalii_rezervari`: Lists reservations within a date range using classic and parameterized cursors.
  - `detalii_pachet_vacanta_angajati`: Shows vacation package details and associated employees with reservation counts.
- **Function**:
  - `detalii_pachet_vacanta`: Returns formatted vacation package details with custom exceptions (`NO_ID_FOUND`, `TOO_FEW_STARS`).
- **Triggers**:
  - `trg_prevent_delete_new_york`: Prevents deletion of vacation packages with "New York" as the destination.
  - `trg_update_pret_sejur`: Automatically adjusts the price of a vacation package based on duration changes.
  - `trg_prevent_drop_rezervari`: Blocks dropping the `REZERVARE` table at the schema level.
- **Package**: 
  - `PACHET_TURISM`: Encapsulates four key subprograms (`afisare_informatii_rezervare`, `detalii_rezervari`, `detalii_pachet_vacanta`, `detalii_pachet_vacanta_angajati`) for modular functionality.

## Technologies Used
- **Oracle SQL**: Core language for defining database schema, sequences, tables, and constraints.
- **PL/SQL**: Used for procedural logic in triggers, procedures, functions, and packages, including advanced features like cursors, collections (nested tables, varrays, index-by tables), and exception handling.

## How to Run
1. Clone the repository: `git clone [repository-url]`.
2. Open the SQL script in an Oracle SQL environment (e.g., SQL Developer, SQL*Plus).
3. Ensure `DBMS_OUTPUT` is enabled to view procedure/function outputs (`SET SERVEROUTPUT ON`).
4. Execute the script in sequence:
   - Run "Cerinta 4" to create sequences and tables.
   - Run "Cerinta 5" to insert sample data.
   - Run "Cerinta 6-12" to create procedures, functions, and triggers.
   - Run "Cerinta 13" to create and compile the package.
5. Test individual components (e.g., execute `afisare_informatii_rezervare(3)` or `detalii_pachet_vacanta(1)`).

## Purpose
This project was developed as part of a database management course to demonstrate proficiency in Oracle SQL and PL/SQL. It showcases the ability to design a relational database, implement complex business rules, and handle data efficiently using advanced SQL features.

## Notes
- The project assumes an Oracle database environment is available.
- Sample data and procedures are designed for demonstration; real-world usage would require additional validation and error handling.
- Some triggers (e.g., `trg_prevent_delete_new_york`) enforce specific business rules that may need adjustment based on requirements.
