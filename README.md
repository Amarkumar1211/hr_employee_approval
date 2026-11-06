# HR Employee Approval Workflow for Odoo 17

[![Odoo Version](https://img.shields.io/badge/Odoo-17.0-purple.svg)](https://www.odoo.com/)
[![License: LGPL-3](https://img.shields.io/badge/License-LGPL--3-blue.svg)](https://www.gnu.org/licenses/lgpl-3.0)

A custom Odoo 17 module that introduces an approval lifecycle for employee creation in the Human Resources app.

---

## 📌 Features

- **Automatic Draft/Inactive Status**: When a new employee is created, they are automatically saved with `active = False` and status set to `Pending Approval`.
- **Manager Email Notification**: Automatically sends an email notification to the assigned manager (or HR Managers group as fallback) upon creation.
- **Approval & Rejection Workflow**:
  - **Approve**: HR Managers can approve pending employees directly from the employee form or tree view, activating the employee profile and notifying the creator/employee.
  - **Reject**: A rejection wizard prompts the HR Manager for a mandatory rejection reason, posts the reason to the employee chatter, and sends an email notification.
- **Dedicated Menu & List View**: Direct access to all pending approval requests under **Employees > Pending Approvals**.
- **Chatter Audit Trail**: All approval and rejection events are tracked in Odoo's chatter with timestamps and user identification.

---

## 📂 Module Structure

```
hr_employee_approval/
├── __init__.py
├── __manifest__.py
├── .gitignore
├── README.md
├── data/
│   └── email_template.xml
├── models/
│   ├── __init__.py
│   └── hr_employee.py
├── security/
│   └── ir.model.access.csv
└── views/
    └── hr_employee_views.xml
```

---

## ⚙️ Installation

1. Place the `hr_employee_approval` directory into your Odoo custom addons directory.
2. Restart your Odoo server instance.
3. Update the Apps list (Settings > Activate the Developer Mode > Apps > Update Apps List).
4. Search for `HR Employee Approval Workflow` in the Apps menu and click **Install**.

---

## 📋 Requirements & Dependencies

- Odoo 17.0 Community or Enterprise
- Depends on:
  - `hr`
  - `mail`

---

## 📄 License

This module is licensed under the [LGPL-3.0 License](https://www.gnu.org/licenses/lgpl-3.0).
