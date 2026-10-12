# Task 7 — Phishing Simulation & Security Awareness

**Internee.pk Cybersecurity Internship**
**Prepared by:** Zunaira Shahzad
**University:** University of Education, Lahore

## Objective

Educate Internee.pk's team on identifying and avoiding phishing attacks by designing and running a controlled, simulated phishing campaign, analyzing user interactions, and producing a security awareness report.

## Scope

Since Internee.pk's real internal mailing list was not available, this simulation used my own email as the sole test "employee," standing in for staff. All mail was routed through **Mailtrap's Email Sandbox**, so nothing was ever delivered to a real inbox.

## Tools Used

- [GoPhish](https://getgophish.com/) — open-source phishing simulation framework
- [Mailtrap](https://mailtrap.io/) Email Sandbox — SMTP sending profile for safe testing

## Methodology

1. Configured a GoPhish sending profile against the Mailtrap sandbox SMTP server and verified it with a test email.
2. Built a phishing email template impersonating Internee.pk IT Support, using an urgency-based pretext (a 24-hour password verification deadline).
3. Built a custom landing page that captures submitted credentials, with a redirect to a legitimate page afterward.
4. Created a target group and launched the campaign.
5. Tracked the full funnel: email sent, opened, link clicked, and data submitted.

## Results

| Stage | Result |
|-------|--------|
| Email Sent | 1/1 |
| Email Opened | 1/1 |
| Clicked Link | 1/1 |
| Submitted Data | 1/1 |

The test recipient progressed through every stage of the attack chain — a 100% conversion rate — with under a minute between the email being sent and credentials being submitted.

## Key Takeaways

- **Urgency as a trigger:** the email's 24-hour deadline pressured faster action with less scrutiny.
- **Authority impersonation:** spoofing "IT Support" exploited trust in internal technical staff.
- **Speed of compromise:** real attacks can succeed faster than detection and response times.
- **No report submitted:** the simulated target did not flag the email, meaning in a real scenario, security teams would have no early warning.

Full details, methodology, and the results funnel are in [`report/Task7_Phishing_Simulation_Report.pdf`](./report/Task7_Phishing_Simulation_Report.pdf).

## Repository Structure

```
.
├── README.md
├── LICENSE
├── .gitignore
├── report/
│   └── Task7_Phishing_Simulation_Report.pdf   # Full report
├── templates/
│   ├── email_template.html                    # Phishing email used
│   └── landing_page.html                       # Fake login page used
├── data/
│   └── campaign_results.csv                    # GoPhish campaign export
└── screenshots/
    ├── gophish_dashboard.png
    ├── mailtrap_email.png
    └── campaign_results.png
```

## Disclaimer

All testing was performed against my own test email address in a fully sandboxed environment (GoPhish + Mailtrap). No real employees, systems, or inboxes were targeted or contacted. This repository is for educational purposes as part of an internship assignment.
