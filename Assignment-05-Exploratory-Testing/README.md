# Assignment 5 – Exploratory Testing

This session explored product sorting, sort behavior after returning from a product detail page, and order PDF generation in SauceDemo.

## Test session

- **Date** — 16 November 2026
- **Browser** — Microsoft Edge 157.0.4341.60 (Official build) (64-bit)

## Product sorting

I checked the order of every product on the **Products** page for each sort option.

| Sort option | Observed result |
|---|---|
| Price (low to high) | All products were sorted by price in ascending order. |
| Price (high to low) | All products were sorted by price in descending order. |
| Name (A to Z) | All products were sorted by name from A to Z. |
| Name (Z to A) | All products were sorted by name from Z to A. |

## Returning from a product detail page

For each return method, I selected **Price (low to high)** on **Products**, opened a product detail page, and returned to the product list.

| Return method | Sort option displayed after return | Observed product order |
|---|---|---|
| **Back to products** | Name (A to Z) | Matched the displayed sort option. |
| Browser **Back** button | Name (A to Z) | Matched the displayed sort option. |

**Open requirement question** — Should the product list retain the selected sort option when the user returns from a product detail page?

## Order PDF

On **Checkout: Complete!**, I clicked **Generating PDF order**. The application generated an order PDF that I could open. It contained the order date, contact details, items, item total, tax, and total.

The check covered field presence only.
