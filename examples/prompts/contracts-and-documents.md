# Contracts and documents

## Description for the generator

Application name: **Contracts and documents**

```text
We keep track of contracts with partners and the related documents. A contract has a number, a name, a contracting party, a type (purchase, service, lease, framework, NDA, employment), the date of signature, valid from, valid to, a notice period in months, a value, a currency, a responsible person, a status (in preparation, for signature, valid, terminated, ended) and the signed contract as an attachment. A contract has amendments – each amendment has a number, the date of signature, a description of the change and an attachment. We also store related documents on the contract with a name, a type (quotation, purchase order, report, invoice, correspondence), a date and a file.
```

**What is created:** the forms Contracting party and Contract; amendments and documents are nested tables in the contract form, type, currency and status are select controls, the signed contract and the document files are attachments. The contracting parties and the contracts get view pages with lists and buttons for a new record.

## Prompts for the agent

- **Build:** “Create an application called Contracts and documents: a contract (number, name, contracting party, type, date of signature, valid from / to, notice period in months, value, currency, responsible person, status in preparation / for signature / valid / terminated / ended, attachment) with nested amendments (number, date, description of the change, attachment) and documents (name, type, date, file). Add overviews of valid contracts and of contracts by contracting party.” — The agent proposes the structure and writes it into the instance once approved.
- **Extend:** “Add a view page Contracts expiring within 90 days — valid contracts whose validity ends between today and 90 days ahead, sorted by the end of validity, with a sum of their value.” — The agent creates a page with conditions on the status and the date range and with a totals row.
- **Daily work:** “Which contracts end by the end of the year, what is their value and who is responsible for them? Give the number of amendments for each.” — The agent reads the contracts and amendments from the instance and answers; nothing is changed.

Source: [Prompt gallery — Contracts and documents](https://www.netgenium.com/en/products/ai/prompt-gallery?utm_source=github#contracts-and-documents)
