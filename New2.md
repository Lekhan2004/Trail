3. Product Development Deep Dive — "Rules Studio"
3.1 Product Overview
"Rules Studio" is an internal interface designed for bank users to decide whether a particular cheque should undergo duplication checks.

The product features a dashboard where internal users can create, manage, and simulate rules that govern the cheque validation process.

The rules act as filters; if a cheque matches certain conditions, it is flagged for duplication check, ensuring compliance and reducing fraud risk.

3.2 Rule Types & Workflow
There are two main types of rules:

Inclusion Rules (with 4 conditions)

Exclusion Rules (with up to 12 conditions)

Example of rule conditions (as seen in the screenshots):

Inclusion: Account Length, Account Number, Amount, Routing Number

Exclusion: Account Number, Amount, Routing Number, Aux Ons, Application Field, Source, Product Code, Process Control, Channel, Gender, Origin Routing Number, and Optional fields

Users can:

Add, Edit, and Simulate rules

Submit rules for approval

Approvers can promote or reject a rule

3.3 Technical Architecture
Frontend:

Built using React with Vite for fast performance and a modern developer experience

Developed custom components from scratch:

Accordions

Tooltips

Toast notifications

Sheet sidebar

Resizable tables

Role-based Authorization:

Users have access based on their role (Creator, Approver, Admin, etc.)

Token-based authentication in the UI for secure actions

Backend:

Node.js environment

JWT Token Generation for authentication

Custom Middleware for authorization to protect endpoints and enforce user permissions

Database:

SQLite3 chosen for seamless Node.js integration (Initial plan was H2, but lack of drivers in Node.js prompted the switch)

3.4 Rule Creation Example (from UI screenshots)
When creating a rule, users select the rule type (Inclusion/Exclusion)

Fill in relevant conditions (like Account Number, Amount, etc.)

Submit the rule, which then moves through the approval process

Visual elements (from screenshots):

Dynamic fields based on rule type

Dropdowns for requestor, channels, etc.

Description and name fields with character limits for clarity

3.5 Product Flow Summary
User logs in (Authenticated by JWT token)

Creates a rule via dashboard UI

Rule goes for approval (Role-based access determines available actions)

Approved rules become active for cheque processing

System automatically checks cheques against rules and flags for duplication check when a match occurs

Users can simulate rules to test their effectiveness before going live

3.6 Key Technical Challenges & Solutions
Role-based Access: Building secure, scalable role-based UI and backend logic

State Management: Handling dynamic rule forms with Redux; resolving Immer state update bugs

Custom Components: Building advanced UI elements (ResizableTable, Tooltips, Toasts) from scratch without libraries

Database Choice: Migrated from H2 to SQLite3 for better Node.js compatibility

Bug Handling: Used feature branches to isolate, test, and resolve UI/logic bugs efficiently

3.7 What Sets Rules Studio Apart?
Highly configurable and user-driven rule engine for cheque validation

Secure and scalable, with robust authentication and authorization

Clean, modern UI with advanced components, offering great user experience

Flexibility for users to simulate rule changes before deploying to production

3.8 Demo & Q/A
Ready to walk through the interface:

Show rule creation for both Inclusion and Exclusion types

Simulate rules, highlight role-based features

Demo approval workflow

Invite questions on:

Technical implementation

Security choices (JWT, role-based middleware)

Custom UI component design

Database decision and migration
