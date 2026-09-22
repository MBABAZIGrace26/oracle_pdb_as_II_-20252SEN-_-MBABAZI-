Oracle PDB Management — README
Overview

This task demonstrates basic Oracle Multitenant Database administration, including PDB creation, verification, opening, saving state, and deletion.

Oracle Environment
Oracle Database: 21.3.0.0.0 Enterprise Edition
CDB: ORCLCDB
OS: Windows 64-bit
Tools: SQL*Plus, Oracle Enterprise Manager Database Express
Tasks Completed
1. Create PDB

Created the required PDB:

CREATE PLUGGABLE DATABASE MB_PDB_20252SEN198
ADMIN USER MB
IDENTIFIED BY <password>
FILE_NAME_CONVERT = (...);

Result: PDB created successfully.
2. Verify PDB Status
SELECT name, open_mode FROM v$pdbs;

The PDB was initially MOUNTED.

3. Open and Save PDB State
ALTER PLUGGABLE DATABASE MB_PDB_20252SEN198 OPEN;

ALTER PLUGGABLE DATABASE MB_PDB_20252SEN198 SAVE STATE;

Result: PDB verified as READ WRITE.

4. Test PDB Deletion

Created a temporary PDB, opened it, verified its status, and removed it using:

DROP PLUGGABLE DATABASE MB_TO_DELETE_PDB_20252SEN198
INCLUDING DATAFILES;

Result: Temporary PDB and its datafiles were successfully removed.

Challenges & Solutions
PDB was initially MOUNTED: Opened it using ALTER PLUGGABLE DATABASE ... OPEN.
PDB state needed to persist: Used SAVE STATE.
Temporary PDB required complete removal: Used INCLUDING DATAFILES.
Verification: Used V$PDBS after operations to confirm the results.
Integrity Statement

I confirm that the commands and operations documented in this submission represent the work completed for this task.

Submission Details
Item	Details
Repository Link	[https://github.com/MBABAZIGrace26/oracle_pdb_as_II_-20252SEN-_-MBABAZI-/edit/main/README.md]
PDB Name Created	MB_PDB_20252SEN198
Issue Counter	No

Status: Completed successfully.

