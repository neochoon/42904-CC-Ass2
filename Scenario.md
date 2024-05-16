## Scenario: Contract and Document Management Workflow

### Objective:
To create a party, link it with a contract, attach a document to the contract, and validate the workflow including validation rules, task creation, and email notifications.

---

### Steps:

#### 1. Create a Party

**Entity:** Party

**Details:**
- **Party ID**: P0010 (AUTO)
- **Party Name**: XYZ Corporation
- **Party Type**: Partner
- **Address**: 123 Business Street, Business City, BC 12345
- **Status**: Active

**Action:**
1. Navigate to the "Party" object in Salesforce.
2. Create a new record with the above details.

---

#### 2. Create a Contract and Validate

**Entity:** MContract

**Details:**
- **Contract ID**: C0010 (AUTO)
- **Contract Name**: Service Agreement with XYZ Corp
- **Start Date**: 2024-06-01
- **End Date**: 2025-05-31
- **Contract Status**: Draft
- **Contract Value**: $100,000
- **Related Party**: XYZ Corporation (Party ID: P001)

**Validation Rules:**
1. Ensure the `Start Date` is not in the past.
2. Ensure the `End Date` is after the `Start Date`.
3. Ensure the `Contract Value` is a positive number.

**Action:**
1. Navigate to the "MContract" object.
2. Create a new contract with the above details.
3. Ensure validation rules are checked and passed.

---

#### 3. Attach a Document to the Contract

**Entity:** Document

**Details:**
- **Document ID**: D001
- **Document Name**: XYZ Service Agreement
- **Document Type**: PDF
- **Upload Date**: 2024-05-16
- **Related Contract**: Service Agreement with XYZ Corp (Contract ID: C0010)
- **Document File**: [Attach the actual PDF file]

**Action:**
1. Navigate to the "Document" object.
2. Create a new document and link it to the contract (Contract ID: C0010).

---

#### 4. Update Contract Status to "Under Review" and Verify Task Creation

**Entity:** MContract

**Details:**
- **Contract ID**: C0010
- **Contract Status**: Under Review

**Action:**
1. Navigate to the "MContract" object.
2. Update the status of the contract to "Under Review".
3. Verify that a task is automatically created and assigned to the Legal Assistant role.

---

#### 5. Update Contract Status to "Approved" and Verify Email Notification

**Entity:** MContract

**Details:**
- **Contract ID**: C0010
- **Contract Status**: Approved

**Action:**
1. Navigate to the "MContract" object.
2. Update the status of the contract to "Approved".
3. Verify that an email notification is automatically sent to the relevant stakeholders.

---

### Summary:

In this scenario, we created a party and linked it to a contract. We ensured the contract passed the validation rules and attached a document to the contract. Upon changing the contract status to "Under Review", we verified that a task was created. Finally, by changing the contract status to "Approved", we confirmed that an email notification was sent.

This scenario helps ensure that the contract management workflow is functioning correctly, including validation rules, task creation, and email notifications.
