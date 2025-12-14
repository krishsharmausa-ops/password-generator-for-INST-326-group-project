# password-generator-for-INST-326-group-project
Group 11 INST 326 Final Project- Password Generation Manager

A local password generation manager  and strength checker implemented in Python.   We decided to develop this program because we wanted to test ourselves on how well we could have made use of databases and the secrets function in Python.

Features: generate passwords, check strength, store entries in SQLite, view/import/export via Pandas, and unit tests with `pytest`.


Project files
- `PasswordDictionary.py`  
 A dictionary file for "PasswordGenerator.py", provides the letters and special characters for password generation. Character sets used by the generator (letters, digits, punctuation).

- `PasswordGenerator.py`  
  The file which generates passwords when prompted in the main file. "PasswordDictionary.py" is required for it to function. 

- `PasswordManager.py`  
The file which manages password entries using SQLite for storage. Uses Pandas for viewing, importing, and exporting password data.  Database-backed manager. Uses SQLite to persist entries and Pandas for viewing, importing, and exporting.

- `PasswordStrengthChecker.py`  
The file which checks your password and determines its strength when entered into the storage database. Password strength classification and rules used to accept/reject passwords.

- `main.py`  
The program uses all three classes together to generate, store, manage, strength check, and export data. Requires each of the previous python files to function. Simple CLI that uses the classes above to generate, store, manage, and export passwords.

- `TestPasswordGenerator.py`, `TestPasswordStrengthChecker.py`  
  `pytest` unit tests for generator and strength checker.

Note: Verify that filenames match imports. `PasswordManager.py` imports `PasswordStrengthChecker`; if your repository contains a misspelled file like `PasswordStrenghChecker.py`, rename it to `PasswordStrengthChecker.py`.

Requirements
- Python 3.13 (as provided) — the code uses standard library modules plus:
  - `pandas`
  - `pytest` (for running tests)
- Standard libraries used: `sqlite3`, `random`, `datetime`

HOW 2 RUN:
Install each of the given files, make sure they are all in the same folder. You can run the program with either VS code or straight in your terminal. Python 3.13 is required.
Simply type any number provided and the chosen choice will run. 
Open the project in your editor (VS Code, Visual Studio) and run `main.py`. The program will prompt you for any additional input required.
CLI usage
When started, the program presents a numeric menu. Available options:
1) Add password — prompts for site, username, password (password strength enforced)  
2) Generate password — choose length 15–32, prints a generated password  
3) View all passwords — lists stored entries  
4) Search by site — case-insensitive site lookup  
5) Update password by ID — enforces strength on new password  
6) Delete password by ID  
7) Export to CSV — `pandas.DataFrame.to_csv` (no index column)  
8) Import from CSV — CSV must include `site`, `username`, `password` columns; weak passwords are skipped and counted  
0) Exit
