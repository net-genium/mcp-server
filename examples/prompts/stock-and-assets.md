# Stock and assets

## Description for the generator

Application name: **Stock and assets**

```text
We keep records of stock items and company assets. A stock item has a code, a name, a category, a unit of measure, a minimum stock level, the current quantity and a location in the warehouse. Stock movements are recorded as receipts and issues – each movement has a date, a type (receipt, issue), an item, a quantity, who made the movement and a note. An asset has an inventory number, a name, a category (computer, phone, furniture, vehicle, machine), the date of purchase, the purchase price, a responsible person, a location, a status (in use, under repair, disposed of) and a photo. For each asset we keep records of service and inspections with a date, a description and a price.
```

**What is created:** the forms Stock item, Stock movement and Asset together with category lists; service and inspections are nested tables in the asset form and their prices are summed, the current quantity of an item is calculated from the movements. The main forms and the category lists get view pages with lists and buttons for a new record.

## Prompts for the agent

- **Build:** “Create an application called Stock and assets: stock items (code, name, category, unit, minimum level, quantity, location), stock movements (date, receipt / issue, item, quantity, who, note) and assets (inventory number, name, category, purchase date, price, responsible person, location, status, photo) with nested service and inspection records.” — The agent creates the forms, the relations between them and the view pages.
- **Extend:** “Add a field Next inspection date to the asset form and a view page Inspections in the next 30 days that lists the assets with an inspection between today and 30 days ahead, sorted by date.” — The agent adds the field and creates a page with a date condition relative to today.
- **Daily work:** “List the assets Jane Smith is responsible for, with their purchase price and status, and calculate the total value of the assets in use.” — The agent reads the records from the instance and answers; nothing is changed.

Source: [Prompt gallery — Stock and assets](https://www.netgenium.com/en/products/ai/prompt-gallery?utm_source=github#stock-and-assets)
