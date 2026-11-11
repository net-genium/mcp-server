# Orders and enquiries

## Description for the generator

Application name: **Orders and enquiries**

```text
We keep track of enquiries from customers and of the orders that come out of them. An enquiry has a customer, a contact person, the date received, a description of the request, an estimated price and a status: new, in negotiation, won, lost. Each enquiry is handled by one salesperson from our team. A won enquiry becomes an order with a number, a name, a delivery date, a responsible person and a status: entered, in progress, completed, invoiced. An order consists of items – each item has a name, a quantity, a unit, a unit price and a total price. On the order we want to see the sum of all item prices. We also keep notes from meetings and attachments on the order, for example the quotation as a PDF.
```

**What is created:** the forms Customer, Contact person, Enquiry, Order, Note and Attachment; the order items are a nested table right in the order form and their prices are summed automatically, the salesperson and the responsible person are chosen from the users of the instance. Each form gets a view page with a list of records and a button for a new record.

## Prompts for the agent

- **Build:** “Build an application called Orders and enquiries in my instance: we track enquiries from customers (customer, contact, date received, description, estimated price, status new / in negotiation / won / lost, salesperson) and the orders that come out of them (number, name, delivery date, responsible person, status entered / in progress / completed / invoiced). An order has nested items with a name, quantity, unit and price, and a sum of the item prices. Propose the structure first, then write it.” — The agent reads the model of the instance, proposes the forms and their controls and, once approved, creates them through the MCP server together with the view pages.
- **Extend:** “Add the fields Handed over to customer (a date) and Complaint (a checkbox) to the Order form. Show both in the order overview and add a view page Overdue orders that lists unfinished orders whose delivery date is in the past.” — The agent adds both fields to the existing form, puts them among the columns of the overview and creates a new view page with query conditions.
- **Daily work:** “How many enquiries have we received this year, how many of them did we win, and what is the total value of the orders in progress? List the five orders with the nearest delivery date as well.” — The agent reads the records straight from the database of the instance and answers from them; nothing is changed.

Source: [Prompt gallery — Orders and enquiries](https://www.netgenium.com/en/products/ai/prompt-gallery?utm_source=github#orders-and-enquiries)
