# Design
## Modules
- Quotation
- Sales Order
- Recurring Order
- Delivery Order
- Work Order
- Sales Return
- Invoice
- Sales Receipt
- Customer Credit
- Product
- Customer
- Contact
## Features
### Quotation Management
1. Create a quotation with a list of products with unit price and quantity
2. Each line can offer a discount, or each quotation can offer a lumpsum discount, or a payment discount
3. Quotation should have an expiry date
4. Quotation can be created with contact or customer
5. Product lines can be hidden from a summary line which sum up all hidden product lines
6. Each line should have a contract duration and a recurring billing duration
7. Quotation status (Draft, Active, Expired, Confirmed, Cancelled)
8. A sales order will be generated in the confirmed status, the order will be void in cancelled status

### Sales Order Management
1. Maintain a sales order with a list of products with unit price, line amount and quantity
2. Each line stores a discount and SRP for display only
3. Each order line may have a service start date, recurring billing duration and contract duration
4. A recurring order will be create if the above information provided
5. Delivery charge and tax will be calculated based on the products
6. Product lines can be hidden from a summary line which sum up all hidden product lines
7. Sales order status (Draft, Pending Payment, Confirmed, Processing, Completed, Closed), Void
8. Order line status (Confirmed, Allocated, Picked, Closed)
9. The order lines will be converted to a work order or a delivery order

### Product
1. Unique model number
2. Each product contains one or more variants
