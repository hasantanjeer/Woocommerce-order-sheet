#  Google Sheets Courier Status Tracker

This project is a lightweight automation solution built using **Google Apps Script**, designed specifically for order management workflows within Google Sheets. It provides dynamic data management by automatically sorting, updating, and maintaining order records based on their courier statuses such as `Pending`, `Processing`, `Completed`, and `Cancelled`.

---

##  Key Features:

- **Status-Based Sheet Management**: Automatically detects changes in the courier status column and moves the corresponding row to the appropriate status-specific sheet.
  
- **Automatic Sheet Creation**: Creates individual sheets for each courier status on-the-fly if they do not already exist.
  
- **Row Migration with De-duplication**: Removes the order entry from any other status sheets to avoid duplication and maintain data integrity.
  
- **Timestamp Logging**: Updates a designated timestamp column (`Column R`) with the latest modification date/time for easy tracking.
  
- **Order ID Matching**: Uses Order ID from `Column A` to uniquely identify and manage row movements between sheets.
  
- **Header Preservation**: Automatically copies and maintains the column headers in all status-specific sheets.

---

##  Usage:

- Sheet Name must be `All Orders`.
- Column A should contain **Order IDs**.
- Column M (13th column) is used for **Courier Status**.
- Column R (18th column) is used to log the **Last Updated Time**.
- Courier Status must be one of the following:
  - `Pending`
  - `Processing`
  - `Completed`
  - `Cancelled`

When a user updates the **Courier Status** in Column M of the `All Orders` sheet:
1. The script sets a timestamp in Column R.
2. It removes the row (by matching Order ID) from all other status sheets.
3. Appends the row to the correct sheet (creating it if needed).

---

##  File Structure

| File Name   | Description                             |
|------------|-----------------------------------------|
| `main.gs`  | The core Google Apps Script code        |
| `README.md`| Documentation for understanding & setup |

---

##  Installation

1. Open your Google Sheet
2. Go to **Extensions → Apps Script**
3. Paste the contents of `main.gs` into the code editor
4. Save the script

---

##  Application

- **Small businesses** tracking online orders
- **E-commerce teams** managing status-based delivery pipelines
- **Customer support** teams that need a structured and automated view of orders
- Google Workspace users looking for no-code/low-code automation inside Sheets

---

##  Benefits

- No need for complex tools — 100% within Google Sheets  
- Avoids duplication and human errors by automatically syncing data  
- Easy to set up, maintain, and adapt  
- Makes your order sheet look organized and professional

---

##  Notes

- The `onEdit` trigger is **bound to the sheet**, so it runs automatically when an edit occurs.
- All status-based sheets will have the same column headers as the main sheet.

---

##  License

This project is open-source and available under the [MIT License](LICENSE).

---

##  Author

Created by Hasan Tanjeer(https://github.com/yourusername)  
Google Apps Script | Workflow Automation | Sheet Optimization

---

