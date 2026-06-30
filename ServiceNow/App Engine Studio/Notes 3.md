# Create App Experiences & Record Producer – Course Notes

---

## 5 User Experience Options in AES

When building an app in AES, you can offer users **5 different experiences**:

| Experience | Built With |
|---|---|
| Standard Catalog Item | Catalog Builder |
| Record Producer | Catalog Builder |
| Workspace | UI Builder |
| Portal | UI Builder |
| Mobile Experience | Mobile App Builder |

---

## Experiences Built with Catalog Builder

### 1. Standard Catalog Item
- A form users fill out to **request a product or service**
- Self-service and user-friendly
- Automates workflows and approvals
- Ensures data accuracy and standardization

### 2. Record Producer
- A **simplified form** that inserts a record into a table
- Think of it as an easier way to add records — using questions instead of field labels
- Shows only the **minimum questions needed** to start the process
- Can add helpful info text to guide the user
- Exposes the request instantly in the **Service Catalog**

> Key difference: Catalog items create **requested items**. Record producers create **records in a table**.

---

## Experiences Built with UI Builder

### 3. Workspace
- A single-screen view for **agents and managers**
- Includes: integrated email, communication channels, agent assistance, playbooks
- Best for: resolving issues and managing cases

### 4. Portal
- A **website-like experience** for end users
- Modern, responsive, works on any device
- Easy to design with reusable components

> ⚠️ UI Builder cannot build or edit **base ServiceNow portals** (like Employee Center) — use **Service Portal Designer** for those.

---

## Experience Built with Mobile App Builder

### 5. Mobile Experience
- Build screens for the **ServiceNow mobile app**
- Works on **iOS and Android**
- Supports **offline availability**
- Users can manage records on-the-go

---

## What is the Service Catalog?

A listing of all **products and services** users can order or request — organized into **categories**.

- **Catalog items** → create requested items (orders)
- **Record producers** → create or modify records in a database table

---

## Create a Record Producer with Catalog Builder

Catalog Builder has **6 sections** to guide you through creation:

---

### Section 1 – Details
- **Item name** — the name users see in the catalog
- **Short description** — extra info about the record producer

---

### Section 2 – Destination
- Set the **table** where submitted records will be saved
- Example: Issues table for the Safety app

---

### Section 3 – Location
- Choose which **catalog** the record producer appears in
- Default catalogs: **Resources, Service Catalog, Technical Catalog**
- Also choose the **category** it lives under

---

### Section 4 – Questions
- Questions collect data from the user (instead of field labels)
- Each question maps to a **variable** → which maps to a **field on the table**
- Click **Insert new question** to add questions

**5 Question Types:**

| Type | Subtypes |
|---|---|
| **Text** | Single-line, Multi-line, Rich text |
| **Option** | Checkbox, Yes/No |
| **Choice** | Dropdown (fixed), Dropdown (from table), Record reference, Radio, Multi-select |
| **Date/Time** | Date, Time |
| **Display Label** | Plain text, Rich text (info only — no input) |

**When creating a question:**
- Check **Map to a specific field** to save the answer directly into a table field
- Set if the question is **Mandatory, Hidden, or Read-only**

**Preview options:** Portal, Now Mobile, Virtual Agent

---

### Section 5 – Settings
- Hide **Add to wishlist** button
- Hide **attachment** button
- Make attachment **mandatory**

---

### Section 6 – Access
- Set which **groups or users** can see and use the record producer
- Work with your **System Administrator** for access and security settings

---

### Final Step – Review and Submit
- Review all details → click **Submit**
- Record producer is now available for **testing in the Service Catalog**
- Select **Return to my application** to go back to App Home

---

## Test the Record Producer
- Open the **Service Catalog** from anywhere in ServiceNow
- Find your record producer and submit a test entry
- Check that the record is created correctly in the **Issues table**

---

## Key Takeaways
- AES supports **5 experience types** — catalog, workspace, portal, mobile, record producer
- **Record producers** = simplified forms that insert records into a table
- Use **Catalog Builder** to build record producers in **6 guided steps**
- Questions replace field labels to make forms **user-friendly**
- Always **preview and test** before publishing to users
