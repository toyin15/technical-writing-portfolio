# Data Migration Guide: Legacy CRM to New Cloud Platform

**Author:** Toyin Oteri  
**Created On:** April 17, 2025  
**Purpose:** To ensure a smooth, secure, and accurate data migration process from the legacy CRM system to the new cloud-based CRM platform.  

---

## Table of Contents
1. Overview
2. Migration Prerequisites
3. Data Mapping Plan
4. Step-by-Step Migration Process
5. Testing & Validation Procedures
6. Post-Migration Tasks
7. Troubleshooting
8. FAQs
9. Contact & Support

---

## 1. Overview

This guide outlines the end-to-end process of migrating customer and business data from the legacy CRM system (OnPremCRM 7.2) to the new cloud-based CRM (Cloud360). It is intended for system admins, project managers, and data analysts involved in the migration.

---

## 2. Migration Prerequisites

Before beginning the migration:

- ✅ Stakeholders have signed off on the final data mapping plan.
- ✅ Backup of the legacy CRM database has been created.
- ✅ All third-party integrations have been disabled.
- ✅ Migration sandbox environment is tested and functional.
- ✅ User accounts and permissions are pre-provisioned on Cloud360.

---

## 3. Data Mapping Plan

| Legacy Field (OnPremCRM) | Target Field (Cloud360) | Transformation Rule |
|--------------------------|--------------------------|---------------------|
| `cust_name`              | `full_name`              | Combine first + last |
| `email_addr`             | `email`                  | Validate format      |
| `cust_phone`             | `phone_number`           | Standardize format   |
| `created_dt`             | `signup_date`            | Convert to UTC       |
| `account_mgr_id`         | `owner_id`               | Map via lookup table |

Ensure field types, formats, and validations match prior to migration.

---

## 4. Step-by-Step Migration Process

1. **Extract:**  
   Use the `onprem_extract.py` script to export customer records into CSV format.

2. **Transform:**  
   Clean and normalize the data using the `data_cleaner.ipynb` notebook.

3. **Load:**  
   Import the cleaned data into Cloud360 via the API bulk loader.

4. **Verify:**  
   Compare record counts, run field-level checks, and validate key relationships.

5. **Backup:**  
   Archive all source files and logs in `/archives/YYYY-MM-DD/`.

---

## 5. Testing & Validation Procedures

- Validate 100% of required fields are migrated.
- Perform sample audits on 10% of migrated records.
- Run functional tests on dependent workflows and integrations.
- Confirm no data loss or formatting errors in final tables.

---

## 6. Post-Migration Tasks

- Reactivate third-party integrations (e.g. Zapier, Mailchimp).
- Notify users that Cloud360 is now the system of record.
- Schedule live training sessions for end users.
- Monitor support channels for user-reported bugs/issues.

---

## 7. Troubleshooting

| Issue | Common Cause | Suggested Fix |
|-------|--------------|---------------|
| Missing records | Failed transform | Re-run transform script |
| Field mismatch | Mapping error | Check mapping table |
| Permission error | Role not provisioned | Contact IT admin |

---

## 8. FAQs

**Q: Can we migrate only active customers?**  
Yes. Modify the extraction query to include a status filter (`status = 'active'`).

**Q: What if duplicate emails are detected?**  
The transform script flags these for review in the `duplicates.csv` file.

**Q: Who do I contact for access errors?**  
Reach out to `it-support@company.com`.

---

## 9. Contact & Support

If you encounter issues or need help with the migration, contact:

📧 Email: it-support@company.com  
📞 Phone: +1 (800) 555-0199  
🧠 Documentation Portal: [docs.company.com/migration](http://docs.company.com/migration)

---

> This document will be reviewed quarterly to reflect updates to the migration process and tools.
