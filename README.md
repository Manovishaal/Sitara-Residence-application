Community Management Platform
Overview
A robust, scalable web application designed to streamline residential society operations. It provides a secure, decoupled portal for administrators to manage billing, and for residents to track their financial dues and community updates in real time.
Core Features
Secure Authentication: Fully integrated login flow ensuring all users are cryptographically verified before accessing the dashboard.

Dynamic Billing System: Admins can issue global, society-wide payment requests (e.g., Annual Maintenance) or upload a CSV to instantly dispatch customized monthly utility bills (Water, Genset) to individual flats.

Approval Workflow: Residents submit payment references that enter a Pending state. The Admin hub allows the Treasurer to reconcile these with actual bank statements before locking the status to Verified.

Automated Timeline Management: A community noticeboard powered by a backend Edge Function and a pg_cron schedule that automatically purges expired social posts every night at midnight without manual intervention.
Security Architecture
Row Level Security (RLS): The PostgreSQL database is locked down at the kernel level. Custom RLS policies dynamically cross-reference the user's secure authentication token with their assigned FlatNo.

Strict Data Isolation: Residents can only query and view their own financial history. The database mathematically rejects unauthorized client-side API requests, making it impossible to view cross-tenant data.

Protected Tables: By shifting security rules away from the front-end HTML/JS and directly into the database bouncer, the architecture completely neutralizes the risk of malicious client-side scripts altering or deleting financial records.
the page is under development. will be full functional with Gate entry protocols introduced for a safer enviroment for the residents.
