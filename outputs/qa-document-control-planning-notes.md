# Bakery QA Document Control - Planning Notes

## Confirmed Requirements

- Two interfaces:
  - QA Admin: create folders, upload documents, publish new versions, archive or delete older versions, add review reminders.
  - Regular User: view, download, and print only the current published document.
- Documents are mostly PDFs, including SOPs, forms, checklists, and training records.
- Current versions must be viewable inside the website, not only listed as filenames.
- Previous versions should be archived. Archived versions can appear as filenames for QA audit purposes.
- QA can create folders freely for departments such as Sanitation, Maintenance, Production, Packaging, and Training.
- Full document viewing can use a modal or overlay.
- Authentication options to consider: email/password, Google sign-in, or existing Active Directory / Microsoft Entra ID.
- Include print support and a dark mode button.

## Recommended First Build Scope

1. Admin dashboard with folder navigation, document table, status filters, and PDF preview.
2. Upload document flow with title, folder, document type, owner, effective date, version number, and review date.
3. Publish new version flow that automatically archives the previous version.
4. Reminder setup for review due dates and notification recipients.
5. Regular user portal showing only current published PDFs with view, download, and print actions.
6. Role-based permissions so regular users cannot edit, upload, archive, delete, or see archived document contents.

## Suggested Data Model

| Entity | Purpose | Example Fields |
| --- | --- | --- |
| User | Authentication and authorization | name, email, role, department |
| Folder | QA-created document grouping | name, parent folder, created by |
| Document | Stable document record | title, type, folder, current version, status |
| Version | Uploaded file revision | version number, file URL, change notes, published date, archived flag |
| Reminder | Review scheduling | due date, frequency, recipients, status |
| Audit Event | Compliance traceability | actor, action, timestamp, document, version |

## Authentication Recommendation

For the prototype, email/password is fastest. For production, Active Directory / Microsoft Entra ID is likely best if employees already use company accounts. Google sign-in is a good option only if the company uses Google Workspace.

## Open Questions For Next Planning Pass

1. Should regular users see all published folders, or only folders matching their department?
2. Should users be allowed to download PDFs, or only view and print them?
3. Do archived versions need legal/audit retention rules, such as "cannot permanently delete after publish"?
4. Should review reminders send email notifications, in-app alerts, or both?
5. Do uploaded Word or Excel files need to be converted to PDF before publishing?
