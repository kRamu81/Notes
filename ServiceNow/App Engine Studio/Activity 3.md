# Activity 3 – Update Table Fields and Form

## Scenario
Add and configure fields in the **Issues table** using Table Builder.
Also edit the **form layout** using Form Designer in App Engine Studio.

> ✅ Complete Activity 2 before starting this one.

---

## Part A – Configure Fields

**1.** Go to **App Home → Issues table → Additional actions (⋯) → Edit**
<img width="1680" height="491" alt="image" src="https://github.com/user-attachments/assets/3ff35d1f-4b2b-4a4f-92c9-1bd4c44d30c1" />


**2.** Select **More actions (⋯)** → ensure **Fields** is selected
<img width="1170" height="924" alt="image" src="https://github.com/user-attachments/assets/b3cec772-a4f5-4c50-9320-8ffd73b8f545" />


**3.** Select the **Gear icon** next to the **Number** field to open the side panel
<img width="1680" height="1024" alt="image" src="https://github.com/user-attachments/assets/d8bc9e74-7440-4042-887c-ed2f0060131f" />


**4.** Check **Read only** checkbox → Number field will always be read-only
<img width="1680" height="1005" alt="image" src="https://github.com/user-attachments/assets/836be747-b5c0-440e-b0b7-f8a769f01a6f" />


**5.** Click **Save** (top right) → then **X** to close the dialog

**6.** Set default value for **State** field:
- Select **Gear icon** next to State
- Expand **Default value** section
- Type `open` in the Default value text box
  <img width="1680" height="1400" alt="image" src="https://github.com/user-attachments/assets/1c6efd79-1b0d-4bbb-8573-3796155b1b32" />


**7.** Click **Save**

**8.** Set dynamic default value for **Opened by** field:
- Select **Gear icon** next to Opened by
- Expand **Default value** section
- Toggle **Use dynamic default value → ON**
- Select **Me** as the Dynamic default value
  <img width="1680" height="1280" alt="image" src="https://github.com/user-attachments/assets/5c05c571-223e-48e4-b674-982ad6530498" />


**9.** Click **Save**

**10.** Click **Preview** → opens the Issues list in a new tab

**11.** Select **New** to create a new record
<img width="1680" height="645" alt="image" src="https://github.com/user-attachments/assets/e93de8cc-b79d-4ea0-904e-07b20a008bf4" />


**12.** Confirm:
- **State** = Open ✓
- **Opened by** = System Administrator ✓
  <img width="1680" height="524" alt="image" src="https://github.com/user-attachments/assets/743b7762-795f-4290-ac20-89e764492eb2" />


**13.** Close the Preview tab → go back to **Data Table and Forms** tab

**14.** Select **+ Add new field**
<img width="1680" height="1265" alt="image" src="https://github.com/user-attachments/assets/a5bddc0b-4630-4a1f-952c-ce02ac807ef9" />


**15.** Fill in the new field:
| Field | Value |
|---|---|
| Column label | Notes |
| Type | HTML |

**16.** Click **Save**
<img width="1680" height="1477" alt="image" src="https://github.com/user-attachments/assets/8faac443-e4af-4949-8e34-8bacbaf88559" />


---

## Part B – Configure the Form Layout

**1.** In Table Builder → **Additional actions (⋯) → Form designer**
<img width="1680" height="511" alt="image" src="https://github.com/user-attachments/assets/0c3518fd-af19-400c-bfb5-13c8b4c39008" />


**2.** Select **Try Form Builder**
<img width="1680" height="1106" alt="image" src="https://github.com/user-attachments/assets/ad23e714-e614-408c-a02d-a702908d7b6e" />


**3.** Select **+ Add section** at the bottom
<img width="1680" height="1074" alt="image" src="https://github.com/user-attachments/assets/4d71deb5-6524-4935-9a25-5f25ab58c1b1" />


**4.** Rename the new section: click **New Section 1** → type `Details`
<img width="1324" height="434" alt="image" src="https://github.com/user-attachments/assets/6c877b0e-2e32-4e3c-8f97-cc6b0f089e96" />


**5.** *(Step 5 not listed — proceed to step 6)*

**6.** Select the **+** in the Details section → double-click **Notes HTML** tile to add it
<img width="1642" height="1476" alt="image" src="https://github.com/user-attachments/assets/c47babde-a9a5-44d7-9a59-64b090da0eed" />


**7.** Drag **Short description** field above Notes in the Details section
<img width="1680" height="1396" alt="image" src="https://github.com/user-attachments/assets/52d21e76-d9ea-494e-9bca-51c1fe702cb7" />


**8.** Click **Save**

**9.** Click **Preview** → open any Issue record to view the updated form
<img width="1680" height="1197" alt="image" src="https://github.com/user-attachments/assets/332382e2-7e10-4401-9a3a-1d089846ce64" />


**10.** Select **Open form in Platform** to view the full form
<img width="1680" height="1310" alt="image" src="https://github.com/user-attachments/assets/03d29f3a-f823-4b2a-b6c9-b9d6bc342b66" />
<img width="1680" height="866" alt="image" src="https://github.com/user-attachments/assets/0e14649c-08b8-4a3a-b3ad-3a7f68e22f8c" />


**11.** Close the Issues tabs


---

## Part C – Add a UI Policy

**1.** Go back to the **Data Table and Forms** tab


**2.** Select **Policies and rules** in the header → click **+ Add new policy**
<img width="1680" height="749" alt="image" src="https://github.com/user-attachments/assets/04c831c5-4219-4290-ab24-8b11fd3c33d7" />


**3.** Configure the UI Policy:
| Field | Value |
|---|---|
| Short description | Make fields read-only when Issue is Closed |
| Condition | State is Closed |

**4.** In the **Do the following** section → click **+ Add** 5 times and set these fields to **Read only = true**:
- State
- Category
- Priority
- Location
- Short description

**5.** Click **Add UI Policy**
<img width="1680" height="1436" alt="image" src="https://github.com/user-attachments/assets/52f22cd5-c598-45b0-9009-b2a8f26f4dd2" />


**6.** Click **Save**

**7.** Click **Preview** → open an Issues record

**8.** Change **State → Closed**

**9.** Confirm these fields are now **grayed out and read-only** ✓
- State, Category, Priority, Location, Short description
  <img width="1680" height="1277" alt="image" src="https://github.com/user-attachments/assets/bcb07c68-b43b-4b93-92a8-bf6489f2dee2" />


---

## Key Takeaways
- Use **Table Builder** to add fields and set default values (static or dynamic)
- Use **Form Builder** to visually arrange form sections and fields
- Use **UI Policies** to make fields read-only based on conditions (e.g. State = Closed)
- Always **Preview** to test your changes before finishing
