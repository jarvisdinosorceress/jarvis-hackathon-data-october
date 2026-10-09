# Jarvis Talent Incubation Hackathon 
## Overview
You will be tasked with designing and building a simplified bank transaction processing system in a group of 3-4. The purpose of this challenge is to demonstrate your attitude and aptitude for the sort of work you’ll be training towards as a software developer at a major Canadian institution. Throughout today’s activities, the judges will be evaluating your ability to:
-	Analyze and understand technical requirements
-	Solve technical problems and/or demonstrate programming capability
-	Work with and data and understand its business significance
-	Collaborate with teammates
-	Communicate technical ideas and decisions
However, there is no expectation that you have any experience with banking, financial services, or any specific computing system or programming language. You may use whatever technology or technologies you see fit, though you should be able to justify your choices at all stages of the exercise.
The challenge will be broken up into several phases:


## Phase One: Individual Analysis and Proposal
Working individually, each participant will produce a document to demonstrate your understanding of the problem statement and its scope, and to propose a realistic design for a solution. The document may take any form you see fit, but your proposal should include information like what technologies you would use, what design patterns or structures your proposed structures your project might include, how inputs, outputs, and data are handled, what assumptions you’re making, etc.
You can use this rough framework to get you started:
-	Briefly describe what problem is being solved, key business rules, and expected results.
-	Provide a data model with how you would represent accounts, transactions, and processes or processing results. Diagrams, pseudocode, class diagrams, JSON samples, or written descriptions are all acceptable.
-	Account for which data structures you would use, where, and why (maps, sets, lists, etc.)
-	Walk through the process of how transactions should be processed from beginning to end.
-	Identify any potential risks and edge cases you would need to account for.
-	Document any assumptions you are making and any questions or clarifications you would seek out before moving forward.

Remember: you are not expected to produce any working code at this stage. This is a design proposal only.
Since the actual hackathon will have you working as a team, your eventual product may not match your proposal. That’s fine – ideally your team’s eventual product will combine DNA from all its component members’ proposals, and undoubtedly you will make design changes throughout the day. Programming is an iterative process.
Since the purpose is to gauge your personal understanding, we ask that you avoid using AI for this portion of the exercise.


## Phase Two: Develop Your Solution
### Business Scenario
The Canadian Bank of Jarvis (CBOJ) received transaction files throughout the day from merchants, ATMs, online banking systems, and partnered financial institutions. 
The bank requires a transaction processing engine that can:
-	Validate transactions
-	Apply business rules
-	Update account balances
-	Identify transactions requiring manual review
-	Produce operational reports
You and your team are tasked with building a Minimum Viable Product of this system.
Sample input data for this system will be provided in the form of two CSVs:
accountData.csv 
transactionData.csv 

The actual data sets will include a mix of valid and invalid transactions.

### Business Rules
Transactions are invalid if:
-	The account does not exist or is not active.
-	The transaction amount is <= 0
-	A transaction with the same transaction ID has already been processed.
-	Processing a transaction would result in a negative balance.
Transactions must be reviewed if:
-	The amount exceeds a reasonable threshold.
-	The account exceeds its daily transaction limit.
-	An unreasonable number of transactions occur within a short timeframe.
Valid transactions should still be processed even if they require review.

### Outputs
Your solution must produce transaction results for each transaction: each transaction should be ‘approved’ or ‘rejected’. If a transaction is rejected, a reason is required.
Example: 
TX001 APPROVED
TX002 REJECTED - INVALID ACCOUNT

When transactions are processed, a processing summary should be produced:
Example:
Transactions Processed: 250
Approved: 220
Rejected: 30
Flagged For Review: 12

Your solution should also produce a summary report for flagged transactions.

### Assumptions
As in many real-world projects, not every possible scenario has been specified in advance. If you encounter ambiguity:
-	Make a reasonable assumption
-	Document your assumption
-	Be prepared to explain your reasoning
You may ask clarifying questions during the challenge.

### Technical Requirements
You may use any programming language or languages, framework, or development tools. Your solution does not have a mandated ‘shape’. It can be a command-line application, batch-processing application, web application, desktop application, etc.


## Phase Three: Presentation
Each team will deliver a presentation and demonstration at the end of the day. Each team’s presentation should be 10 minutes long, followed by approximately 5 minutes of Q&A. Please practice your presentation in advance to ensure it does not run overtime.
Every team member must participate in the presentation.

### Suggested Topics
•	Understanding of the problem
•	Solution design
•	Key technical decisions
•	Challenges encountered
•	Future improvement

### Success Criteria
A successful team does not necessarily build the most features.
Strong candidates typically:
•	Ask thoughtful questions
•	Make reasonable assumptions
•	Use appropriate data structures
•	Communicate clearly
•	Collaborate effectively
•	Deliver a working solution that satisfies the core requirements
Focus on building a solid MVP, supporting your teammates, and clearly explaining your decisions. Good luck!
