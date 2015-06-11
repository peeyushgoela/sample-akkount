akkount
=======

This is a real-world application for managing personal finances. It can be practically useful if you live in a country where automatic services like mint.com don't work, and you don't mind entering all your money transactions manually.

This is also a good example of some non-trivial extensions of a CUBA application, such as customization of a visual component with client-side JavaScript code, and creating an additional lightweight web UI for mobile devices.

Based on CUBA Platform 5.5.0

Features
--------

In short the application solves two problems:
 1. It shows the current balance by all accounts: cash, credit cards, deposits, debts, etc.
 2. It can generate a report by expense and income categories that shows where the money came from and what they were spent on in some period of time.

Some details:
* There are _accounts_ that represent different kinds of money.
* There are _operations_: income to account, expense from account and transfer between accounts.
* A _category_ can be set for expense or income operations.
* The current balance is constantly displayed and is recalculated after each operation.
* Categories report shows the summary by two arbitrary periods of time to allow quick visual comparison. Any category can be excluded from the report. You can "drill down" into any row to see operations that comprise the row.
* The system consists of three web applications deployed onto one Tomcat instance:
   1. Middleware
   2. Full-functional CUBA UI
   3. Responsive UI built on Backbone.js + Bootstrap to simplify entering operations on mobile devices. 

Usage
-----

Open the project in Studio and execute **Run > Create database**, then **Run > Start application server**. Login to the application on `http://localhost:8080/app` with `admin` user name and `admin` password. You can generate test data in **Administration > JMX Console > app-core.akkount -> app-core.akkount:type=SampleDataGenerator** bean. Enter the number of days (e.g. 100) back from the current date, for which to create sample transactions, into the **generateSampleData()** method parameter and click **Invoke**. After the method execution is finished, logout and login again. You will see the balance for sample accounts in the left panel.
