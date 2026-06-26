# Activity 2 – Create a Table with a Spreadsheet

## Scenario
You have been tracking safety issues in an **Excel spreadsheet**.
Now you want to import that data into the **Safety app** so your team can work on them together.

---

## Part A – Create a Table via Spreadsheet

**1.** From the Safety App Home, select **+ Add a table or upload a spreadsheet or PDF**
<img width="1680" height="518" alt="image" src="https://github.com/user-attachments/assets/da85c1a6-aebc-4bf9-b8f6-e42cd6b19e50" />


**2.** Select **Import a spreadsheet** → click **Continue**
<img width="1680" height="1139" alt="image" src="https://github.com/user-attachments/assets/29054d20-104b-4b53-8a87-76247d7d4dc6" />


**3.** Upload the file: `safety-issues.xlsx`

**4.** Check the **Import spreadsheet data** checkbox *(to bring data into the new table)*
<img width="1680" height="1600" alt="image" src="https://github.com/user-attachments/assets/00730d42-28d1-4ce8-bf51-c67d721a8860" />


**5.** Click **Continue**

**6.** Select **A new table** → Select **Create new table** → click **Continue**
<img width="1680" height="949" alt="image" src="https://github.com/user-attachments/assets/1f584f18-54d4-4c51-9108-a772041330d3" />


**7.** Confirm all **8 column headings** transferred correctly from the spreadsheet
<img width="1090" height="562" alt="image" src="https://github.com/user-attachments/assets/a2ee0868-7779-4986-817d-daee357cf845" />
<img width="1186" height="728" alt="image" src="https://github.com/user-attachments/assets/49c48923-abce-4e8b-955c-1b17eef6bc2d" />



**8.** Compare the field data types with the IT requirements *(most come in as String — you will fix them next)*
<img width="455" height="239" alt="image" src="https://github.com/user-attachments/assets/ea744c86-c1fa-49dd-beac-c9740f613173" />


**9.** Change **Opened by** field:
- Type → **Reference**
- Reference table → **User [sys_user]**
  <img width="1680" height="1156" alt="image" src="https://github.com/user-attachments/assets/a03b6fe6-4eb5-4493-922a-6021cea55dc4" />


**10.** Repeat for the remaining Reference fields:
| Field | Type | Reference Table |
|---|---|---|
| Assigned to | Reference | User [sys_user] |
| Location | Reference | Location [cmn_location] |
<img width="589" height="103" alt="image" src="https://github.com/user-attachments/assets/d972a328-fe9f-4d16-8df1-b407e2bbf139" />
<img width="589" height="103" alt="image" src="https://github.com/user-attachments/assets/49bb9195-6e45-4201-b9e5-dfeecd5f7daa" />
<img width="1680" height="164" alt="image" src="https://github.com/user-attachments/assets/4cef5aaf-3658-4087-b560-036a5975ea33" />




**11.** Change **State**, **Category**, and **Priority** fields:
- Type → **Choice** *(leave Choice type as-is)*
  <img width="1680" height="308" alt="image" src="https://github.com/user-attachments/assets/304ed65e-ded1-4eee-8971-1c1a75353a82" />
  <img width="1680" height="167" alt="image" src="https://github.com/user-attachments/assets/029a2205-3ad2-430c-91dd-d59fb9cbb161" />


**12.** Click **Continue**
<img width="1680" height="1147" alt="image" src="https://github.com/user-attachments/assets/8d62d225-dd39-45bd-a45d-fb05c54e6a06" />


**13.** Set the table properties:
| Property | Value |
|---|---|
| Table label | Issues |
| Table name | auto-populated — leave as is |
| Make extensible | unchecked |
| Auto-number | checked |
| Prefix | SAFT |
| Starting Number | 1000 |
| Number of digits | 7 |

**14.** Click **Continue**
<img width="1680" height="1479" alt="image" src="https://github.com/user-attachments/assets/90aed788-2e64-4880-ac11-fc21ff52692f" />


**15.** Set table permissions:
| Role | Permissions |
|---|---|
| admin | All |
| user | Read + Write |
<img width="1680" height="1012" alt="image" src="https://github.com/user-attachments/assets/4c8bf40d-fdae-462e-8503-fcd5bbaceff3" />


**16.** Click **Continue**

**17.** Click **Edit table** to open Table Builder
<img width="1680" height="707" alt="image" src="https://github.com/user-attachments/assets/c069e253-dc98-4826-a6a1-0b352cbf3162" />


---

## Part B – Edit Table Fields in Table Builder

**1.** Go through the **Introduction to Table Builder** dialog → click **Get started**
<img width="1680" height="844" alt="image" src="https://github.com/user-attachments/assets/6deba984-ef37-4d0e-8c10-c5025fd7afc1" />


**2.** Review and close the **Choose how to view data** dialog

**3.** Switch to **Fields view** on the Data tab
<img width="1680" height="754" alt="image" src="https://github.com/user-attachments/assets/7ab6d8e1-5d73-43f3-8d13-56c53464f6bb" />


**4.** Examine the fields — system fields + 8 fields from the spreadsheet

**5.** Toggle **Display value ON** for the **Number** field *(makes it the primary record identity)*
<img width="1680" height="756" alt="image" src="https://github.com/user-attachments/assets/2a755ce1-92b5-41ee-b5cf-e27454563449" />


**6.** Configure the **Category** Choice field:
| Label | Value |
|---|---|
| Big | big |
| Medium | medium |
| Small | small |
→ Click **Done**
<img width="1680" height="706" alt="image" src="https://github.com/user-attachments/assets/f98221ad-a777-4cdb-a378-50b26c277f79" />


**7.** Configure **Priority** and **State** Choice fields:

**Priority:**
| Label | Value |
|---|---|
| 1 - Critical | critical |
| 2 - High | high |
| 3 - Moderate | moderate |
| 4 - Low | low |

**State:**
| Label | Value |
|---|---|
| Pending | pending |
| Open | open |
| Working | working |
| Closed | closed |
<img width="604" height="182" alt="image" src="https://github.com/user-attachments/assets/9e28de88-fb19-4d5b-b1ac-2d7b6fc5604d" />


**8.** Click **Save** (top right) to save all configurations
<img width="1680" height="763" alt="image" src="https://github.com/user-attachments/assets/8438d7a4-7c7a-4aae-a91d-6d76e38fd15d" />


**9.** Close Table Builder by selecting the **X** on the Data Table and Forms Issues tab
<img width="1680" height="92" alt="image" src="https://github.com/user-attachments/assets/ad8f00da-b114-4c59-8d07-024aeebf09c7" />


**10.** Review the Safety app home page — the default Issues form was auto-created ✓
<img width="1680" height="627" alt="image" src="https://github.com/user-attachments/assets/3b5ff70b-0ed5-499f-a14a-f1003c15f603" />


---

## Key Takeaways
- Data is the **foundation** of every app
- Always **verify field types** after import — spreadsheets default most fields to String
- Use **Reference** for user/location fields, **Choice** for dropdowns
- Set **Auto-number** so every record gets a unique ID (e.g. SAFT0001000)
