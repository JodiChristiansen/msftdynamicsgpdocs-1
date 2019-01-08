---
title: "Purchasing module setup"
description: "Purchasing for Dynamics GP"
keywords: "purchase order"
author: tnistler
manager: edupont

ms.prod: dynamics-gp
ms.topic: article
ms.reviewer: edupont
ms.author: tnistler
ms.date: 01/08/2019

---
# Purchasing Module Setup

Use this information to learn about and set up Purchase Order Processing. The setup procedures are organized in an order that will ensure Purchase Order Processing is set up properly.

When you set up Purchase Order Processing, you can open each setup window and enter information, or you can use the Setup Checklist window (Administration \>\> Setup \>\> Setup Checklist) to guide you through the setup process. See your System Setup Guide (Help \>\> Contents \>\> select Setting up the System) for more information about the Setup Checklist window.  

## Purchase Order Processing document types

Use Purchase Order Processing to track your company’s purchasing activity. You can enter and manage purchase orders, track shipments and invoices received, and match shipments to invoices that were received separately. There are seven types of documents in Purchase Order Processing.

- Standard purchase orders list items that will be shipped to your business to be received into your inventory. For more information, see *Entering a standard purchase order* on page 40. If you are using Project Accounting, see *Entering a standard purchase order for projects* on page 75 for more information.

- Drop-ship purchase orders list items that will be shipped directly to the customer. The vendor sends you an invoice and you, in turn, send an invoice to the customer. For more information, see *Entering a drop-ship purchase order* on page 44. If you are using Project Accounting, see *Entering a drop-ship purchase order for projects* on page 78 for more information.

- Blanket purchase orders list a single item and the quantities that will be delivered in a series of shipments, usually on specific dates. The items will be shipped to your business to be received into your inventory. For more information, see *Entering a blanket purchase order* on page 48. If you are using Project Accounting, you can’t enter blanket purchase orders for projects.

- Drop-Ship blanket purchase orders list a single item and the quantities that will be delivered to the customer in a series of shipments, usually on specific dates. The vendor sends you an invoice and you, in turn, send an invoice to the customer. For more information, see *Entering a drop-ship blanket purchase order* on page 53. If you are using Project Accounting, you can’t enter drop-ship blanket purchase orders for projects.

- Shipment/invoice receipts record the receipt of goods and services accompanied by an invoice. For more information, see *Receiving a shipment/invoice* on page 129. If you are using Project Accounting, see *Receiving a shipment/invoice for projects* on page 149 for more information.

- Shipment receipts record the receipt of goods and services without an invoice. For more information, see *Receiving a shipment* on page 133. If you are using Project Accounting, see *Receiving a shipment for projects* on page 153 for more information.

- Invoice receipts record an invoice received for a shipment you received and posted earlier, or an invoice received for a shipment that you have not yet received. For more information, see *Entering an invoice receipt* on page. If you are using Project Accounting, see *Entering an invoice receipt for projects* on page 199 for more information.  

## Purchase Order Processing history types

When setting up Purchase Order Processing, you’ll have the option to maintain the following types of history. If you are using Project Accounting, historical information for project line items will be maintained in Project Accounting.

- **Purchase Order**
    This option keeps a detailed copy of each purchase order in history. When you transfer a purchase order to history using the Remove Completed Purchase Orders window, or when you void a purchase order using the Purchase Order Entry window, purchase order history will include line-by-line detail of all information entered for each purchase order.

- **Account Distributions**
    This option keeps a detailed record of transaction distributions that are posted to General Ledger. Account distribution history will be updated when each receipt is posted. Distribution history includes the audit trail code, account, account description, debit or credit amount, and other information about each transaction.

- **Receipt**
    This option keeps a detailed copy of each receipt in history. When you post or void a receipt using the Receivings Transaction Entry window or the Purchasing Invoice Entry window, receipt history will include line-by-line detail of all the information entered for each receipt, including serial numbers, lot numbers, and bin information.

> [!NOTE]
> Keeping history will increase the amount of hard disk space needed. You should periodically remove the historical records you no longer need. For more information, see Chapter 27, “Purchase order history removal.”

## Before you set up Purchase Order Processing

You should complete setup procedures in Payables Management and Inventory Control before you set up Purchase Order Processing. If you haven’t completed all of the following tasks, be sure to do so before continuing.

- Set up Payables Management

- Create vendor cards

- Enter beginning inventory quantities

- Set up item records (be sure to assign price lists and vendor items)

- Set up item sites

- Set up inventory and purchasing accounts in the Posting Accounts Setup window

To view the Posting Accounts Setup window, choose Administration \>\> Setup \>\> Posting \>\> Posting Accounts and then select to view Inventory or Purchasing accounts.

Be sure you’ve also completed the setup procedures for your company, currency, checkbooks, and posting options. Tax schedules and tax details also should be set up. For more information about completing these procedures, refer your System Setup instructions.

If you’re using landed costs, be sure to set up landed cost records and groups before you set up Purchase Order Processing. For details, see the Inventory Control documentation.

If you’re using Multicurrency Management, be sure to set up currencies, exchange rate tables, and rate types before you set up Purchase Order Processing. For details, see the Multicurrency Management documentation.  

## Setting up Purchase Order Processing preferences and default entries

Use the Purchase Order Processing Setup window to set preferences and default entries that appear throughout Purchase Order Processing.

**To set up Purchase Order Processing preferences and default entries:**

1. Open the Purchase Order Processing Setup window. (Purchasing \>\> Setup \>\> Purchase Order Processing)

2. Accept or change the default document code and enter the next document number you want to use for purchase orders.

    The document code can be used to identify the documents on reports and inquiries. The next number will be the starting document number when receipts are entered. You can reuse a document number if the document has been deleted or removed from history (if you’re keeping history).

    By defining the next document number, you also are determining the number of unique document numbers that will be available. For example, if you enter PO001 as the next purchase order number, you’ll be able to enter up to 999 purchase orders; if you enter PO0001 as the next purchase order number, you’ll be able to enter up to 9,999 purchase orders. Be sure to enter a next number that will accommodate your business volume.

3. Select the format you want to use when purchase orders are printed. If you are using Project Accounting, the default document format for a purchase order with project information will be the document format specified for the vendor record in the PA Vendor Options window.

    To use purchase order forms other than the suggested forms, you may want to use Report Writer to be sure the information is printed on your forms correctly. For more information, refer to Report Writer help.

4. Accept or change the default document code that appears and enter the next document number you want to use for receipts.

    The document code can be used to identify the documents on reports and inquiries. The next number will be the starting document number when receipts are entered. You can reuse a document number if the document has been deleted or removed from history (if you’re keeping history).

5. Enter the number of decimal places to use when displaying and entering quantity and currency amounts for non-inventoried items.

    If you’re using Multicurrency Management, choose the expansion button to open the Purchasing Non-Inventoried Currency Decimals Setup window. Use this window to define currency decimal places for each currency to which you have access. For more information, see *Setting up currency decimal places for non-inventoried items* on page 15.

6. Mark Shortage and then enter the percentage to use when the quantity received is less than the quantity ordered for non-inventoried items when receiving against a standard or blanket purchase order. If the difference between the quantity received and quantity ordered falls within the quantity shortage percentage, the difference between the quantities is canceled and the status of a line item is automatically changed to change order, received, or closed. The status of the line item depends on whether or not the line item has been invoiced.

7. Mark Overage and then enter the percentage to use when the quantity received is more than the quantity ordered for non-inventoried items when receiving against a standard or blanket purchase order. If the quantity received is over the overage tolerance, you will receive a message that you can't enter a quantity greater than the combined total of the Remaining to Receive quantity and the overage tolerance set up for the item.

8. Select which date to use as a default date each time that you open the Purchase Order Entry window to work with purchase orders. You can use the date from the last document you entered or the user date.

9. Select a default site ID for purchase order line items. You can select either the default site ID set up for the item in Item Quantities Maintenance window or the previous purchase order line’s site ID.

10. Select which item numbers to use during transaction entry—the item numbers your company uses or the item numbers used by your vendors.

    If you are using Project Accounting and select Vendor Items, you can’t enter a project number and a cost category for purchase orders, shipment receipts, shipment/invoice receipts, or invoice receipts.

11. Indicate whether you want New purchase orders generated in Sales Order Processing to be placed on hold when they appear in the Purchase Order Entry window. If you mark this option, committing a Sales Order Processing line item to an existing purchase order line item will not cause the purchase order to be placed on hold.

    If you mark this option and you’ve assigned a password to the option “Allow Hold/Remove Hold of Purchase Orders,” you will not need to enter the password during the purchase order generation process in Sales Order Processing. However, the password to remove holds will apply when a purchase order is viewed in the Purchase Order Entry window.

    If you are using Project Accounting, you can’t create purchase orders for projects from Sales Order Processing.

12. Indicate whether you want the system to search for uncommitted purchase order quantities when you attempt to create a link between a sales line and a purchase order. If you don’t mark the option, you’ll be able to create a new purchase order for the sales document, but you won’t be able to link the sales line to an existing purchase order. Refer to the Sales Order Processing documentation for information about linking an item to an existing purchase order.

    If you are using Project Accounting, you can’t commit purchase orders for projects to sales documents.

13. Indicate whether you want to transfer line item comments from sales documents to new purchase orders. If you mark this option, existing purchase order line comments will not change if linked to sales line items with comments.

    If you are using Project Accounting, you can’t transfer line comments from sales line items to purchase order line items that are assigned to projects.

14. Indicate whether the release by date for a purchase order line item should be calculated by subtracting the vendor’s planning lead time from the required date. By marking this option, you can use the PO Line Items to Release Report to identify purchase order line items that should be released to the vendor. If you don’t mark this option, the release by date isn’t calculated automatically.

    If you are using Project Accounting, the release by date isn’t calculated for purchase order line items that are assigned to projects.

15. Select the types of historical information you want to maintain for your purchase transactions. If you are using Project Accounting, historical information for project line items will be maintained in Project Accounting. For information about history types, see *Purchase Order Processing history types* on page 10.

    If you’ve selected to reprint Purchase Order Processing posting journals in the Audit Trail Codes Setup window, the system will maintain the history necessary to reprint posting journals whether or not you’ve marked to maintain history in the Purchase Order Processing Setup window.

16. Mark Allow Purchase Order Prepayments to enter a prepayment amount for a purchase order and generate the prepayment as computer check in Payables Management.

    Payables Management and Purchase Order Processing must be registered for this option to be available, but Project Accounting, Multidimensional Analysis, and Analytical Accounting must not be registered.

17. To enter manual prepayments for purchase orders, mark the Create manual prepayment from Purchase Order Processing option.

    This option is available when the Allow Purchase Order Prepayments option is marked.

18. Enter a password to limit the users who can enter prepayments for purchase orders.

    This option is available when the Allow Purchase Order Prepayments option is marked.

19. Enter or select the account to be used as the default posting account when you post prepayments.

    This option is available when the Allow Purchase Order Prepayments option is marked.

20. In the Options scrolling window, mark the check boxes next to the options you want to enable. You can assign passwords to the options to restrict who has access to them. If an option is marked, but no password is entered, anyone with access to the affected window can perform the action. You can select to allow the following:

    **Receiving items without a purchase order** Select this option to allow line items not assigned to a purchase order to be entered on a shipment, shipment/invoice or invoice receipt. If the option isn’t selected, you won’t be able to receive or invoice line items not associated with a purchase order.

    **Changing the site ID in receiving** Select this option to allow receiving line items to different locations than indicated on the original purchase order.

    **Allowing/removing holds on purchase orders** Select this option to allow users to place and remove holds on New, Released or Change Order purchase orders of either type—standard or drop-ship.

    When you mark this option, you also can indicate whether you want to allow editing of purchase orders on hold. If you don’t allow editing on-hold purchase orders, you will be able to view purchase orders that have been placed on hold, but you won’t be able to edit, delete or void them.

    **Editing costs in receiving** Select this option to allow changing an item’s Unit Cost and Extended Cost in the Receivings Transaction Entry window.

    *When deciding whether to allow the editing of costs in receiving, keep in mind that purchase price variances are calculated by comparing the cost posted from receiving with the standard cost for items with periodic valuation methods. For more information about standard cost and valuation methods, see the Inventory Control documentation.*

    If you allow receiving without a purchase order, you should allow editing of costs in receiving, or you won’t be able to enter costs for items without purchase orders. To restrict access, you can require a password.

    **Warning when purchase order line item is not fully Invoiced** Select this option to receive a warning message that a purchase order line item has a remaining quantity to invoice when closing a purchase order or a purchase order line item in the Edit Purchase Order Status window.

21. If you are using Project Accounting, choose Project to open the PA Purchase Order Processing Setup Options window, where you can select preferences and default entries for purchase orders, shipment receipts, shipment/invoice receipts, and invoice receipts for projects. See *Setting up project preferences and default entries in Purchase Order Processing* on page 30 for more information.

22. Choose Options to open the Purchase Order Processing Setup Options window, where you can set up tax calculations in Purchase Order Processing. See *Setting up Purchase Order Processing tax options* on page 16 for more information. If you are using purchase order generator, you can use the Purchase Order Processing Setup Options window select options for generating purchase orders. See *Setting up purchase order generator default entries* on page 23 for more information.

23. Choose Receivings User-Defined to enter labels for user-defined fields, lists, and dates that will be used when entering shipments and shipment/invoices. See *Setting up user-defined fields for receivings* on page 17 for more information.

24. Choose OK to save the entries you’ve made in the Purchase Order Processing Setup window.

25. Print a Purchase Order Processing Setup List (optional).

    Choose File \>\> Print while the Purchase Order Processing Setup window is displayed to print a Purchase Order Processing Setup List to review the setup options you’ve entered. If you’ve identified errors in the setup list, simply enter or select the correct information.

    This report also can be printed using the Purchasing Setup Reports window.

## Setting up currency decimal places for non-inventoried items

Use the Purchasing Non-Inventoried Currency Decimals Setup window to define currency decimal places for non-inventoried items for each currency to which your company has access. This window is available only if you are using Multicurrency Management. If you aren’t using Multicurrency Management, use the Purchase Order Processing Setup window to define the number of decimal places when displaying currency amounts for non-inventoried items.

The default number of decimal places for each currency was determined when the currencies were set up. Use this window to change the number of decimal places used to display currency amounts for non-inventoried items. You can change the non-inventoried currency decimal places for a currency at any time.

Changing the decimal place setting for a currency won’t change the decimal place settings of non-inventoried items already entered on existing documents. Only new items added to existing transactions or new transactions will use the new settings.

**To set up currency decimal places for non-inventoried items:**

1. Open the Purchasing Non-Inventoried Currency Decimals Setup window. (Purchasing \>\> Setup \>\> Purchase Order Processing \>\> Currency expansion button)

2. In the Currency Decimals column, change the number of currency decimal places to use for non-inventoried items. Amounts will appear in the format defined in this window whenever a non-inventoried item is entered for a specific currency.

3. Continue this process until you define the decimal places for all the currencies displayed in the window.

4. Choose File \>\> Print to print the Non-Inventoried Currency Decimals Setup List.

5. Choose OK to close the window.

## Setting up Purchase Order Processing tax options

Use the Purchase Order Processing Setup Options window to set up the tax calculations that will be used on documents. Depending on the tax calculation selected, you can enter default tax schedules for non-inventoried items, freight, and miscellaneous items. For information about setting up the purchase order generator, see *Chapter 3, “Purchase order generator setup.”*

**To set up Purchase Order Processing tax options:**

1. Open the Purchase Order Processing Setup Options window.
(Purchasing \>\> Setup \>\> Purchase Order Processing \>\> Options button)

2. Mark the type of tax calculation to use on documents.

    **Advanced** Mark Advanced to specify a tax schedule to use for noninventoried items, freight, and miscellaneous charges. For inventory items, the tax schedule you chose for each item in the Item Maintenance window will be used.

    **Single Schedule** Mark Single Schedule to specify one tax schedule for all items on all documents. Items on each document will be taxed using the tax details in the schedule you specify here, even if the item is nontaxable or if the vendor is tax exempt. Taxes won‘t be calculated on freight or miscellaneous charges.

3. If you marked Advanced in step 2, enter or select tax options for non-inventoried items, freight, and miscellaneous charges. You can change the tax schedules used for a transaction in a tax schedule entry window during transaction entry. The tax options are:

    **Taxable** The tax details that are assigned to the vendor or site will be compared to the tax details in the tax schedule you specify here.

    **Nontaxable** No taxes will be calculated.

    **Base on vendor** The tax schedule assigned to the vendor’s purchase address will be used calculating taxes.

5. Choose OK.

To print the Purchase Order Processing Setup List, choose File \>\> Print in the Purchase Order Processing Setup window.

## Setting up user-defined fields for receivings

Use the Receivings User-Defined Fields Setup window to enter labels for up to 35 user-defined fields to further track additional information for shipment and shipment/invoice receipts. Later, when you enter receivings transactions, the labels will appear in the Receivings User-Defined Fields Entry window, where you can enter information that is unique to the transaction. You can set up the following types of user-defined fields.

- **List**
    Use list fields to predefine options to track information that is specific to your business. For example, to track the origin of orders, you could name a list Order Origin and enter Fax, Phone, and Mail as values for the list. When you enter transactions, Order Origin will appear as a title in the Receivings User-Defined Fields Entry window and you can select where the order originated from the list you created or include additional values.

- **Text**
    Use text fields to record additional information about the transactions you enter in the Receivings Transaction Entry window. For example, to track special ID numbers for shipped equipment, you can enter Shipping ID in a text field.

- **Dates**
    Use date fields to record additional dates that affect your documents. For instance, if you want to track the date that an installation was complete, enter Install Date in a date field.

**To set up user-defined fields for receivings:**

1. Open the Receivings User-Defined Fields Setup window. (Purchasing \>\> Setup \>\> Purchase Order Processing \>\> Receivings UserDefined button)

2. Enter as many as five list fields. Choose the expansion button next to each list name you‘ve entered; the Receivings User-Defined List Setup window will appear. Use this window to enter values for each list.

3. Enter as many as 10 text fields to track additional information about your customers.

4. Enter as many as 20 date fields to record additional dates that affect your documents.

5. Choose File \>\> Print to print the Receivings User-Defined Fields Setup List.

6. Choose OK to return to the Purchase Order Processing Setup window. Your changes are saved when you choose OK in the Purchase Order Processing Setup window.

## Setting up comments

You can add comments to purchase orders or to individual line items on a purchase order or receipt. Comments are printed automatically on the purchase order and line item comments are printed below the item on the purchase order or receipt.

Use the Comment Setup window to define comments for each company. You can use these comments on Sales Order Processing, Invoicing or Purchase Order Processing documents. You also can modify standard comments for a particular document or item, or create one-time comment.

**To set up comments:**

1. Open the Comment Setup window. (Administration \>\> Setup \>\> Company \>\> Comments)

2. Enter a short identifier for the comment.

3. Select a series this comment will be associated with.

4. Enter the comment text.

    You can enter up to 200 characters, which will appear on the purchase order or receipt as four lines of 50 characters each. If you want longer comments to appear, use Report Writer to modify the document layout.

5. Choose Save.
