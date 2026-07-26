Bank Database Application

Overview

The Bank Database Application is a Java console program that allows users to create and manage bank accounts using a local SQLite database. The application demonstrates object-oriented programming concepts such as abstraction, inheritance, polymorphism, interfaces, composition, and database connectivity.

Users can add new bank accounts, view all accounts, deposit money into an account, withdraw money from an account, and delete an account.

All account data is stored in an SQLite database file named MikaylaDickerson.db.

Author

Mikayla Dickerson

Date: May 3, 2026

Features

The application allows users to create checking or savings accounts, store the account owner's name, balance, and account type, view all existing accounts, update balances with deposits and withdrawals, and delete accounts by ID.

It uses SQLite for persistent data storage and automatically creates the Accounts table if it does not already exist.

The project demonstrates abstraction using the abstract Account class, inheritance with CheckingAccount and SavingsAccount, polymorphism through overridden methods and interface references, interfaces with BankOperations, composition with the Bank class containing a collection of accounts, and encapsulation using private fields and public getters.

Project Structure

4.2/
App.java
Account.java
CheckingAccount.java
SavingsAccount.java
Bank.java
BankOperations.java
BankDB.java
MikaylaDickerson.db
lib/
sqlite-jdbc-3.53.0.0.jar
App.class
Bank.class
CheckingAccount.class
SavingsAccount.class

Class Descriptions

App.java is the main program entry point. It displays the menu and handles user interaction.

Account.java is the abstract base class for all account types. It contains the fields owner and balance. Its methods include deposit(), withdraw(), displayAccountInfo(), and the abstract method monthlyUpdate().

CheckingAccount.java extends Account and applies a monthly service fee of $10.

SavingsAccount.java extends Account and adds $25 in monthly interest.

BankOperations.java is an interface that defines the methods deposit(double amount) and withdraw(double amount).

Bank.java demonstrates composition by maintaining an ArrayList<Account>.

BankDB.java handles all SQLite database operations. Its methods include createTable(), addAccount(), getAllAccounts(), updateBalance(), and deleteAccount().

Database Schema

The Accounts table contains the following columns:

id - INTEGER - Primary key with auto-increment

owner - TEXT - Account owner's name

balance - REAL - Current account balance

type - TEXT - Checking or Savings

Requirements

The project requires Java JDK 17 or later, the SQLite JDBC Driver (sqlite-jdbc-3.53.0.0.jar), and Visual Studio Code or another Java IDE.

How to Compile

Windows Command Prompt or PowerShell:

javac -cp ".;lib/sqlite-jdbc-3.53.0.0.jar" *.java

macOS/Linux:

javac -cp ".:lib/sqlite-jdbc-3.53.0.0.jar" *.java

How to Run

Windows:

java -cp ".;lib/sqlite-jdbc-3.53.0.0.jar" App

macOS/Linux:

java -cp ".:lib/sqlite-jdbc-3.53.0.0.jar" App

Sample Program Output

Week 4 Project - Bank Database Application

Mikayla Dickerson

This program stores bank accounts using SQLite.

You can create, view, update, and delete accounts.

--- MENU ---

Add Account
View Accounts
Deposit
Withdraw
Delete Account
Exit

Example Usage

To add an account, select option 1, enter the owner's name, enter the starting balance, and enter the account type as either Checking or Savings.

To deposit funds, select option 3, enter the account ID, and enter the deposit amount.

To withdraw funds, select option 4, enter the account ID, and enter the withdrawal amount.

To delete an account, select option 5 and enter the account ID.

Learning Objectives

This project demonstrates Java class design, abstract classes and interfaces, inheritance and method overriding, database programming with JDBC, CRUD operations, and user input handling with Scanner.

Known Limitations

Withdrawals made directly through the database do not validate available funds. Input validation is minimal. Monthly update methods are not currently called by the menu. Database resources are not explicitly closed.

Possible Enhancements

Future improvements include adding input validation for invalid menu entries, preventing overdrafts in the database layer, adding account search by owner name, adding transfers between accounts, closing database connections safely, and implementing monthly updates through a menu option.

License

This project was created for educational purposes as part of a Java programming course.

Contact

Mikayla Dickerson

For questions about this project, contact the author through your course platform or GitHub repository.
