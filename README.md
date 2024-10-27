## Needs clarification:
- What is  `Point of Sale` in `Sales channel`
- Is billing region same as shipping region? What is difference?
- Difference between Order ID and Sale ID and Order?

## Consider delete cols:
- Billing country
- Billing city
- POS location? (what is it?)

## Needs to clean:
### Object Types
**1. Product type**
- Clean `sale` | `Sale` type to ['Athletics' '2 Piece Set' 'dresses' 'Accessories' 'Earrings' 'blazers' 'Apparel & Accessories' 'Pants' 'Shirts & Tops' 'Jumpsuit' 'Dress' 'Dresses' 'Bracelet' 'Coats & Jackets' 'Jumpsuits & Rompers' 'Shorts' 'Skirt Suits' 'Gift Card' 'Shirt']
- Can the product types be sorted further? Ex: `Jumpsuits & Rompers` with `Jumpsuit`

**2. Product vendor**
- Does the shop want to see anything related to this?

**3. Product, Variant, Variant SKU**
- ***Product***: Sort to colors => might have column about colors
- ***Variant***: Sort to sizes only
- ***Variant SKU***: Do we need this?

**4. Transaction**
- Handle the unknowns
- Should we convert `gift_card` into `product` since they are money tho? If not, is there more info on this `gift_card`?

**5. Sale type, Sales channel**
- Handle `return` in `Sale type`. Might extract return transactions into a separate dataset.
    + Check if each `return` has corresponding `order` within the dataset. If yes, remove its `return`, else N/A.

### Numeric Types
**1. Order ID, Sale ID, Date, Order**
- Figure out this first:

      `Count of unique identifiers for Order ID: 207
       Count of unique identifiers for Sale ID: 172
       Count of unique identifiers for Order: 230`

**2. Returns**
- Check if `Sale type` == `return` results in `Returns` != 0

## Recommended analysis
**Returns analysis:**

    + Overall return rate
    + Which product has most returns?
    + Returns by Season/Month
    + Time Between Purchase and Retur
    + Revenue Loss Due to Returns (Profitability Impact)
    + Return Rate by Sales Channel
    + Return Patterns by Size and Fit
    + Returns by Region
  
**Normal transactions analysis:**

***1. Sales Performance Analysis***

- Gross Sales vs. Net Sales: Compare gross sales (before discounts and returns) with net sales to understand how much of the revenue is lost due to returns and discounts.
- Sales by Product Type: Analyze which product types (e.g., jeans, dresses) perform the best in terms of sales volume and revenue.
- Sales by Product Variant: Examine the performance of specific variants (e.g., color, size) to identify which combinations drive the most revenue.
- Top-Selling Products: Identify the products generating the most revenue and their variants. Use this information to guide inventory or marketing strategies.

***2. Sales by Channel and Location***

- Sales by Sales Channel: Compare performance across different sales channels (e.g., online, point of sale, boutique). This can help you determine which channels are driving the most sales and if any underperform.
- Sales by Region/City: Analyze sales by shipping or billing region/city to identify geographical hotspots or areas with weaker demand.
- POS Location: For physical stores, you can check which locations (if more than one) perform the best and which might need improvement.

***3. Time-Based Analysis***

- Sales by Day/Month/Season: Examine sales trends over time. Are there specific times of the year (e.g., holidays, sales events) that generate higher sales?
- Peak Sales Times: Analyze the time of day when most sales are made (if the dataset includes timestamp details), which could help in optimizing marketing campaigns or staffing in physical stores.

***4. Discounts and Promotions***

- Impact of Discounts: Look at how discounts affect sales. Do products with higher discounts sell more, and how do they impact overall profitability?
- Promotional Sales: Check if certain sales types (promotional campaigns) are driving higher transaction volumes but leading to lower profitability due to discounts.

***5. Customer Segmentation and Behavior***

- If you have customer-related data (even indirectly through the billing country/region), analyze the purchasing behavior of different segments.
   + New vs. Returning Customers: Identify patterns between first-time buyers and repeat customers. Do returning customers buy more, return less, or buy specific product types?
   + Average Transaction Value: Calculate the average transaction value per customer to understand customer behavior and how much they typically spend.

***6. Product Returns and Exchanges***

- Product Return Rate: Analyze return rates based on product types or variants. For example, are certain types of products like dresses returned more often than others?
- Returns by Sales Channel: Are returns more common in online sales than in-store sales? This could suggest issues with product descriptions or customer expectations online.

***7. Sales Efficiency Metrics***

- Net Quantity Sold: Calculate the total quantity of products sold (excluding returns) to understand the actual volume of products sold.
- Total Sales per Transaction: Analyze the average value of sales transactions, including taxes and shipping. Higher total sales values might suggest successful upselling strategies.

***8. Geographical Insights***

- Shipping vs. Billing Regions: Compare shipping locations with billing locations to identify where products are being purchased and delivered. Are there any discrepancies or patterns (e.g., frequent gift purchases)?
- International Sales: If the dataset includes multiple countries, analyze international sales trends. Identify the countries with the highest demand and examine potential barriers (e.g., shipping costs, taxes).

***9. Product Vendor and Supplier Performance***

- Sales by Vendor: Analyze which product vendors are performing the best in terms of sales. This can help in managing vendor relationships and inventory decisions.
- Variants by Vendor: Check if certain vendors provide more successful product variants (e.g., popular colors, sizes).

***10. Shipping and Tax Analysis***

- Impact of Shipping Costs: Assess whether shipping costs impact total sales. Are products with higher shipping fees less likely to sell? Are customers willing to pay extra for shipping?
- Taxes Impact on Sales: Analyze if taxes influence customer purchasing decisions, especially for customers in different regions with varying tax rates.

***11. Sales Growth***

- Sales Growth over Time: Track sales growth over time, month-to-month, or year-to-year, to determine if the business is expanding or experiencing downturns.
- Product Lifecycle: Analyze how sales change over a product's lifecycle (e.g., new product launches vs. end-of-life products on clearance).

***12. Operational Efficiency***

- Transaction Type Analysis: Identify different types of transactions (e.g., orders, returns, etc.) to understand the flow of operations.
- POS System Effectiveness: If using different sales channels or point-of-sale systems, analyze how efficiently transactions are processed, and if any channel underperforms in terms of user experience.

## Work Assign:
**1. Eirlys**

**2. Shirsendu**


































