# Build a CRM with Claude

Claude connects to a NET Genium Online instance through its built-in MCP server and builds a CRM straight into it — the tables, the forms, the relations between them and the overviews — in one conversation. The result runs the moment it is written, and you keep developing it with the same agent.

Video and the full story: [Build a CRM with Claude on a real database](https://www.netgenium.com/en/products/ai/build-a-crm-with-claude?utm_source=github)

## The prompt to start with

```text
Build a CRM in my NET Genium instance. We track companies (name, city, country, industry, number of employees, customer since, notes), the contacts at each company (first name, last name, e-mail, phone, role) and a log of activities with a company and optionally a contact (type call / e-mail / meeting / demo, date, subject, description, done). Show the contacts and the activities on the company form. Propose the structure first, then write it.
```

## What the agent built in one conversation

- **A connected application, not three loose tables.** Companies, contacts and a log of activities, each with its own form and overview. On a contact, the company is a real foreign key chosen from a list, and the company form has tabs with its contacts and its activities.
- **Searching and filtering come with it.** The overviews can be searched and filtered without anyone setting them up.
- **A change to a running application.** Asked for annual revenue and a flag for key clients, the agent added both fields to the existing application and placed them on the form and in the overview.
- **Data written by the agent itself.** Eight companies, sixteen contacts and twenty-four activities from the last two months — after the agent first listed its plan and waited for confirmation.

Building the application took seventeen minutes, filling it with data six minutes.

## Try it

1. [Create an instance](https://www.netgenium.com/en/register.aspx?utm_source=github) — free with one user, no credit card.
2. In Claude, add a custom connector with the address `https://mcp.netgenium.online/api.aspx`, enter the name of your instance, sign in and allow reading and writing.
3. Paste the prompt above, review the proposal and let the agent write it.
4. Ask for new fields, overviews or sample data the same way — the agent changes the running application instead of starting over.
