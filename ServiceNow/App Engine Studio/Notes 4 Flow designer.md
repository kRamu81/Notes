# Create Automation with Flow Designer – Course Notes

---

## What is Flow Designer?

Flow Designer lets you **automate work without writing code** — using simple graphical flows.

**What it offers:**
- Maximize efficiency with **repeatable processes**
- Visualize and automate **how work gets done**
- Easily connect to **other apps and cloud services**
- Built-in **notifications and chat** capabilities
- Everything recorded in **one place** — a single source of truth

---

## What Does a Flow Consist Of?

Every flow has **2 main parts**:

### 1. Trigger
- Defines **when** the flow should start
- Can be based on:
  - **Record changes** (created or updated)
  - **A schedule** (set time)
  - **A Service Catalog request**

### 2. Actions
- Define **what happens** after the trigger fires
- Reusable building blocks — like **record updates** or **sending a chat message**
- ServiceNow provides **built-in actions**, and you can also create your own

---

## Adding a Trigger

**Steps:**
**1.** Select **+ icon** or **Add a Trigger**
**2.** Choose what the trigger is based on (record change, schedule, or catalog request)
**3.** Use the **condition builder** to define exact conditions

**Example Trigger:**
> When a new record is **Created** or an existing record is **Updated**
> on the **Issues table**
> and **Category is Big**
> → Run the flow **For each unique change**

### Run Trigger Options
| Option | What it Does |
|---|---|
| For each unique change | Triggers every time, even if flow is already running |
| Once | Triggers only the **first time** the condition is met |
| Only if not currently running | Triggers only if the flow **isn't already running** |

---

## Adding an Action

Actions are **building blocks** that snap together to build your flow logic — no coding needed.

**Example actions:** Update Record, Send Email, Create Task, Send Notification

---

## Using the Data Pane

As you build a flow, all data from your Trigger and Actions appears in the **Data pane** for reuse.

### Method 1 – Drag and Drop
- Drag a **data pill** (light blue oval) from the Data pane directly into an Action field
- Example: Drag the **Issue Record** pill into the **Target Record** field of a Send Email action

### Method 2 – Data Pill Picker
- Click the data pill picker icon
- **Column 1:** Select the Trigger or Action where the data came from
- **Column 2:** Select the specific data value
- Use the **search bar** to quickly find data if the list is long

---

## Example: Update a Record Action

**Goal:** Automatically assign safety issues marked "Big" to a specific employee

**Steps:**
**1.** Add an **Update Record** action
**2.** Set: **Assigned to → Joe Employee**
**3.** Click **Done**

---

## Save, Test, and Activate the Flow

### 1. Save
- Click **Save** once your flow is complete
- Compare it against your original requirements

### 2. Test
- Flow Designer lets you **test the flow** and view results for each action
- Results open in a separate **Executions** tab
- Shows detailed analysis of what happened at each step

### 3. Activate
- Once tested and confirmed working → click **Activate**
- This tells ServiceNow to **start checking for the Trigger condition**

### 4. Deactivate (if needed)
- Click **Deactivate** anytime to **stop** the flow from running

---

## Key Takeaways

- A flow = **Trigger** (when to start) + **Actions** (what to do)
- Triggers can be based on **record changes, schedules, or catalog requests**
- Use the **Data pane** and **data pills** to reuse information across actions
- Always **test** a flow before activating it
- **Activate** the flow to make it live, **deactivate** to pause it anytime
- Flow Designer = **automation without code**
