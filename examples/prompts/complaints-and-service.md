# Complaints and service

## Description for the generator

Application name: **Complaints and service**

```text
We receive complaints and service requests from customers. A complaint has a number, a customer, the date received, the product complained about, its serial number, a description of the fault, photos of the fault and a status: received, in progress, waiting for a part, resolved, rejected. Each complaint is handled by one technician, and we record how it was resolved (repair, replacement, refund, rejected) and the date of resolution. The technician records service interventions on the complaint – each intervention has a date, a description of the work done, the parts used, the number of hours and a price. On the complaint we want to see the total hours and the total price of the interventions.
```

**What is created:** the form Complaint with the nested table Service intervention; the hours and prices of the interventions are summed on the complaint automatically, the technician is chosen from the users of the instance and the customer from an existing customer list, if the instance has one (otherwise the AI creates a Customer form as well). The complaints get a view page with a list and a button for a new complaint.

## Prompts for the agent

- **Build:** “Build an application called Complaints and service: a complaint (number, customer, date received, product, serial number, fault description, photos, status received / in progress / waiting for a part / resolved / rejected, technician, resolution, date of resolution) with nested service interventions (date, work done, parts, hours, price) and the sum of hours and price.” — The agent proposes the structure including the nested form and writes it once approved.
- **Extend:** “Add a view page Open complaints by technician — a statistics table with the number of unresolved complaints and the total hours for each technician — and a page Complaints waiting for a part sorted by the date received.” — The agent creates two view pages: one with an aggregate query grouped by technician, the other with a condition on the status.
- **Daily work:** “Which complaints have been in progress for more than 14 days and who is handling them? For the ones waiting for a part, list the fault description.” — The agent reads the complaints and interventions from the instance and answers; nothing is changed.

Source: [Prompt gallery — Complaints and service](https://www.netgenium.com/en/products/ai/prompt-gallery?utm_source=github#complaints-and-service)
