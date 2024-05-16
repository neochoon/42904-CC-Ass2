# 42904-CC-Ass2
Cloud Computing and Software as a Service Assignment (42904) Assignment 2 - Application Development using Force.com PaaS (35%)

## Members

* Choonsik Cho 24585388
* Lin Chen 24905111
* Zixuan Wang 24866523

## Assessment Item 1: Software Application Development using Force.com platform


### (i) Data Objects (Minimum three objects showing look up (association) and master- detail relationships)

```
    +----------------+           +----------------+           +-----------------+
    |     Party      |           |    MContract   |           |    Document     |
    +----------------+           +----------------+           +-----------------+
    | Party ID       | 1       n | Contract ID    | 1       n | Document ID     |
    | Party Name     |-----------| Contract Name  |-----------| Document Name   |
    | Party Type     |           | Start Date     |           | Document Type   |
    | Contact Info   |           | End Date       |           | Upload Date     |
    | Address        |           | Contract Status|           | Related Contract|
    | Registration # |           | Contract Value |           | Document File   |
    | Status         |           | Related Party  |           +-----------------+
    +----------------+           +----------------+
```

### (ii) Data Validation Rules (Minimum three successfully implemented data validation rules)

```
    Object: MContract
    Validate Contract Date Range
    Purpose: Ensure that the start date of a contract is before its end date to prevent data entry errors.

    Object: MContract
    Active Parties in Contracts
    Purpose: Ensure that a contract can only be associated with active parties.

    Object: Document
    Approved or Rejected Contract can not have document.
    Purpose: Ensure that certain types of contract can not have document anymore.
```

### (iii) Object-level security and Tab-Level security (Implement minimum one implemented object-level security and one tab-level security settings using Custom Profiles)
```
    Document Legal Assistant Profile
        Contracts Tab - hidden
        Document Object - Read, Update Only

    Contract Operations Profile
        Every Objects and Tabs
```

### (iv) Organisation-wide default (Minimum one successfully implemented organisation- wide default access)
```
    Machinemind
        CEO
            Contract Manager    - Choonsik Cho
                Legal Assistant - Lin Chen

    MContract   Controlled by Parent
    Party       private
    Document    Public Read/Write
```
<img src="Role%20Hierarchy.jpg" alt="Role Hierarchy" width="500"/>


### (v) Email Notification (Minimum two successful implementations of email notification automation process using workflow mechanisms)
```
Contract Approval Notifier
```
<img src="Contract%20Approval%20Notifier.jpg" alt="Contract Approval Notifier" width="1024"/>

### (vi) Task creation and assignment (Minimum one successful implementation of task creation and automation process using workflow mechanisms)
```
Contract Task Under Review
```
<img src="My%20Task.jpg" alt="My Task" width="1024"/>


### (vii) Time-based workflow (Minimum one successful implementation of time-based workflow)
```
Start Date Integrity Guard
```
<img src="Start%20Date%20Integrity%20Guard.jpg" alt="Start Date Integrity Guard" width="1024"/>
