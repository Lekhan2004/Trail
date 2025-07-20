Product Development: STAR Framework
SITUATION
When I joined JPMorgan for my internship, the internal banking team was facing inefficiencies and compliance risks in handling cheque duplication checks. The existing process for determining which cheques should undergo duplication checks was largely manual, inconsistent, and lacked a flexible rule management system. There was a clear need for a secure, scalable, and user-friendly tool to empower internal users to create and manage rules that automate and standardize this process.

TASK
My primary responsibility was to design and develop an internal web application called "Rules Studio"—a centralized interface that would allow authorized users to:

Create, edit, and simulate rules for cheque duplication checks,

Define both "Inclusion" and "Exclusion" rules with various condition fields,

Manage role-based access and approval workflows,

Ensure a secure, seamless user experience across the application.

ACTION
To accomplish this, I:

Gathered requirements by collaborating closely with stakeholders (Kushal, Roshan, Jhansi), understanding real pain points and user flows.

Designed the architecture using React (with Vite) for the frontend, and Node.js with SQLite3 for the backend.

Developed the front-end with custom UI components (like resizable tables, tooltips, toast notifications, and accordions), focusing on accessibility and usability.

Implemented robust authentication and authorization using JWT tokens, and wrote custom middleware to ensure secure role-based access throughout the UI and API.

Engineered a flexible rule engine where users could dynamically create rules with different conditions based on rule type (as shown in UI screenshots), and built the simulation/approval workflow.

Addressed technical challenges: Migrated the backend database from H2 to SQLite3 for Node.js compatibility; resolved Redux state and UI bugs using systematic testing and feature branches.

Ensured code quality with proper version control and modular backend structure.

RESULT
Delivered a fully functional Rules Studio application that:

Automated the cheque duplication check process through a robust, user-driven rule engine.

Enabled secure, role-based access and approval workflows for both users and approvers.

Significantly improved operational efficiency and consistency for internal users.

Reduced manual errors and compliance risks associated with cheque processing.

Showcased advanced technical solutions (custom UI, secure backend, scalable architecture) and strong problem-solving during development.

The solution was well-received by stakeholders and set a new standard for how internal tools could streamline compliance operations at JPMorgan.

(Optional Closing)
This project not only honed my technical and collaborative skills but also taught me how to drive impactful change in a complex, real-world financial environment.
