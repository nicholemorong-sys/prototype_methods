# ISKOLAR MARSU

Responsive, multi-page scholarship application and monitoring prototype for Marinduque State University. Built with semantic HTML, CSS, and vanilla JavaScript; no framework or package installation is required.

## Run locally

Serve this folder with a local web server and open `index.html`. For example:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000`. A local or hosted web server is recommended for document uploads and browser storage.

The official MarSU seal is bundled at `assets/marsu_logo.png`; a MarSU-colored monogram appears if the image is unavailable.

## Account access

- Choose Student or Staff / Admin from the landing page to open the corresponding sign-in page.
- Both roles enter an institutional or personal email address and a password. For this demonstration, any syntactically valid email and non-empty password will proceed; credentials are not verified or stored.
- Student and Staff / Admin sessions remain separate and open their matching dashboards. No account registration is provided.
- This navigation-only sign-in is not authentication. Production deployments require institution-managed identity verification and server-side role authorization.

## Pages

- `index.html` — Role portal chooser.
- `login.html` — Student email and password sign-in.
- `staff-login.html` — Dedicated Staff / Admin sign-in.
- `student-access.html` — Student sign-in information; it does not create accounts.
- `student-dashboard.html` — Student applications, scholarship summaries, and announcements.
- `admin-dashboard.html` — Staff overview, application review queue, and CSV export.
- `scholarships.html` — Searchable scholarship catalog; staff can add and edit programs.
- `application.html` — Scholarship requirements, application details, and document uploads.
- `profile.html` — Student profile and optional photo management.
- `tracking.html` — Student-only application status timeline and decision notes.
- `announcements.html` — Student announcement board; staff can publish and remove notices.
- `payouts.html` — Payout schedule list; staff can publish, edit, or remove entries.

Shared behavior is in `app.js`; visual styles and responsive rules are in `styles.css`.

## Features

- Separate email/password sign-in pages and dashboards for Students and Staff / Admin; demo credentials are not verified.
- There is no account registration form or account provisioning requirement for demonstration sign-in.
- Student and staff dashboards, student profiles, scholarship search and filters, requirements, applications, and document uploads.
- Student-visible status tracking; only staff-facing review controls can update application decisions.
- Staff can open each submitted application, review applicant details and uploaded requirements, then save an Approved, Rejected, or Pending decision. Students see final decision notices on their dashboard, notification panel, and status-tracking page.
- Staff review includes documents, applicant verification, application CSV export, scholarship programs, announcements, and payout schedules.
- Notification panel, responsive navigation, accessible status feedback, and input/file validation.

The initial scholarships, announcements, and payout dates are sample content. Confirm eligibility, deadlines, award amounts, and release dates with MarSU and each provider before relying on them.

## Accessibility and responsive design

- Semantic landmarks, headings, lists, forms, labels, and data tables.
- Skip link, visible keyboard focus, native controls, and keyboard-operable actions.
- Accessible names and state attributes for menus, notification panel, review dialog, status updates, and file selection.
- Text alternatives for the university seal and profile image; decorative icons are hidden from assistive technology.
- Desktop uses a persistent side navigation and multi-column layouts; tablet and mobile reduce columns and stack content.
- Mobile navigation collapses into an accessible menu. Tables scroll horizontally on narrow screens.
- Reduced-motion preferences are respected.

## Testing procedures

1. Start the local server. Confirm the role chooser opens separate Student and Staff / Admin sign-in pages.
2. Sign in as Student using any valid email format and non-empty password; confirm the Student Dashboard opens without account registration or credential verification.
3. Sign out, use any valid email and non-empty password on the Staff / Admin page, and confirm the Admin Dashboard opens.
4. Confirm Students cannot access the Admin Dashboard and do not see approval or rejection controls.
5. Submit or seed a pending application, open it from the Staff / Admin review queue, approve or reject it, and confirm the student sees the decision on the dashboard, notification panel, and tracking page.
6. Test scholarship browsing, search/filters, profile editing, document uploads, application tracking, announcements, and payout schedules as a Student.
7. As Staff / Admin, review an application, update its status, manage scholarship programs, publish announcements and payout schedules, and export applicant records.
8. Test keyboard navigation and visible focus, then check layouts at approximately 375 px, 768 px, and 1280 px widths.

## Prototype security boundary

This is a browser-only demonstration, not a production scholarship service. Sign-in accepts any valid email format and non-empty password and performs no credential or account verification. Role checks control navigation in the prototype only and can be bypassed; applications, profiles, decisions, and schedules are stored in browser local storage, and uploaded files are stored in IndexedDB. Production use requires verified institutional authentication, server-enforced role permissions, protected document storage, validation, audit logging, and approved privacy/security practices. Do not enter real student data or passwords in this prototype.
