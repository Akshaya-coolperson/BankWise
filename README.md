## Features

BankWise is a console-based Java application. A single home menu launches
six modules, each building on a different part of the course.

### Module 1: Fundamentals
- Transaction receipt with withdrawal charge (0.5%) and account number validation
- Simple interest, fixed deposit (quarterly compounding) and loan EMI calculation
- Late fee calculation for overdue EMIs

### Module 2: ATM-style banking
- PIN login with 3 attempts, then the card is blocked
- Deposit and withdrawal with minimum balance, daily limit and max deposit rules
- Loan eligibility check, EMI due alerts and a daily summary

### Module 3: Methods, recursion and arrays
- Overloaded methods for deposits and interest
- Recursive compound interest and recurring deposit maturity
- 2-D array branch performance report, plus top 3 customers (bubble sort)

### Module 4: Object-oriented design and exceptions
- Account hierarchy: Savings, Current and Loan accounts (abstract class, interfaces, polymorphism)
- Customer registration, multiple accounts per customer, three branches
- Fund transfers with duplicate-reference blocking
- Loan approval, monthly interest crediting and account statements
- Five custom exceptions, including InsufficientBalance and LoanValidation

### Module 5: Strings, algorithms and file I/O
- Customer search by name/city and account search using binary search
- Sorting with Comparable and Comparator
- Statements built with StringBuilder and saved to files
- Deposits saved to data files, plus a monthly financial and audit report

### Module 6: Collections and streams
- Executive dashboard, top customers, loan portfolio and high-value transaction views
- Branch-wise and transaction-type reports using groupingBy
- Filtering and sorting with lambdas, plus HashMap-based account lookup
## How to run

**Requirements:** JDK 8 or later (the code uses lambdas and streams).

**Folder layout:**
BankWise/
├── bankwise_final/
│   └── BankWise.java
└── data/
    ├── customers.txt
    ├── accounts.txt
    └── transactions.txt

**Compile and run** (from the BankWise folder, the one that contains `data`):

    javac bankwise_final/BankWise.java
    java bankwise_final.BankWise

Run it from this folder, because Modules 5 and 6 look for `data/` relative to
where you start the program. The `statements/` and `reports/` folders are
created automatically when you generate a statement or report.

**Data file format** (first line of each file is a heading):
- customers.txt: id,name,phone,city
- accounts.txt: accountNumber,type,customerId,branchCode,balance,rate,years
- transactions.txt: accountNumber,type,amount,balanceAfter,date (yyyy-MM-dd)

## Known limitations

- Modules 1-3 use demo or hard-coded data (for example, Module 2's demo PIN and
  account holder, and Module 3's fixed customer arrays).
- Module 4 runs entirely in memory. Nothing it creates is saved, and it does not
  use the data files.
- Modules 5 and 6 work on the data files, not on accounts created in Module 4.
- Loan interest is fixed at 10% per year.
- Reloading a loan from accounts.txt treats the stored outstanding balance as the
  principal, so a loan that has been partly repaid shows a smaller principal
  and EMI after reload.
- In Module 4, if account opening fails (for example, the opening balance is too
  low), the customer stays registered with no account.
- Transaction IDs restart on every run.
- Console only, no GUI.
