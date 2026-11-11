# Leave and expense approvals

## Description for the generator

Application name: **Leave and expense approvals**

```text
Employees submit leave requests and expense claims, and their manager approves them. A leave request has an applicant, a date from, a date to, a number of days, a type (holiday, sick day, unpaid leave, home office), a reason and a status: submitted, approved, rejected. An expense claim has an applicant, a date, an amount, a currency, a category (travel, accommodation, meals, equipment purchase, other), a description, the scanned receipt as an attachment and the same statuses. For both kinds of request we record who approved or rejected it and when, and the approver's note.
```

**What is created:** the forms Leave request and Expense claim — the applicant and the approver are chosen from the users of the instance, type, currency and category are drop-down lists, the status is a radio button and the receipt an attachment. Each form gets a view page with a list of requests and a button for a new request.

## Prompts for the agent

- **Build:** “Create an application for leave and expense approvals: a leave request (applicant, from, to, number of days, type holiday / sick day / unpaid leave / home office, reason, status submitted / approved / rejected, who decided and when, note) and an expense claim (applicant, date, amount, currency, category, description, receipt as an attachment, the same statuses). Add a view page Pending requests where the approver sees the submitted requests of both kinds.” — The agent creates both forms and three view pages; it proposes the status and category as select controls with the values from the prompt.
- **Extend:** “Add Approve and Reject buttons to both forms. They should set the status, fill in the signed-in user and today's date in the decision fields and save the record. Show the buttons only on a submitted request.” — The agent adds the buttons with scripts that set the values and save the record, and a form JavaScript that hides the buttons on a request that has been decided.
- **Daily work:** “List all submitted leave requests and expense claims and, for each, give the applicant, the dates or the amount and how long it has been waiting for a decision.” — The agent reads the requests from the instance and composes the answer; nothing is changed.

Source: [Prompt gallery — Leave and expense approvals](https://www.netgenium.com/en/products/ai/prompt-gallery?utm_source=github#leave-and-expense-approvals)
