# Module 1: Using Flow Designer — Notes

## Objectives
By the end of this module you should be able to:
- Open and use Flow Designer
- Create and edit flows
- Add actions and flow logic to a flow
- Configure actions
- Use variables in a flow
- Test and debug a flow
- View flow execution details
- Activate a flow

> **About this module:** Uses the **Asset Management Spoke** app to demonstrate concepts (you don't build it). You build the **NeedIt** app hands-on in the exercises. Exercises are marked with an Exercise icon / the word "Exercise" or "Challenge" in the page title.

---

## Setup Exercises

### Exercise: Fork Repository and Import Application
1. **Fork the repo** on github.com (NeedIt repository) → uncheck "Copy the main branch only" → set Owner to your account → Create fork.
2. **Copy the fork URL** (Code button → HTTPS tab → copy).
3. **Create a Credential record** in your PDI (once only): All menu → Connections & Credentials → Credentials → New → Basic Auth Credentials
   - Name: `GitHub Credentials - <username>`
   - User name: `<GitHub username>`
   - Password: `<GitHub personal access token>` (not your real password)
4. **Import into Studio**: All menu → System Applications → Studio → Import From Source Control → enter fork URL, credential, Branch = `main` → Import → Select Application.

### Exercise: Create a Branch
1. Open the NeedIt app in Studio.
2. Source Control menu → Create Branch.
3. Branch Name: `FlowDesigner`, Create from Tag: `LoadForFlowDesignerModule`.
4. Create Branch → Close → reload the main browser tab to load the files.

---

## What Is a Flow?
A **flow** = a **trigger** + one or more **actions**, used to automate processes on the Now Platform.

**Triggers** — what starts a flow:
- Record creation and/or update
- Date
- Service Catalog request
- Inbound email
- Service Level Agreements (SLA)
- MetricBase (plugin required — not on PDIs)

**Core actions** (examples): Ask for Approval, Create Task, Look Up Records, Send Email, Update Record.

---

## Flow Designer User Interface

Open via **All menu → Process Automation → Flow Designer**.

**Roles:**
| Role | Capability |
|---|---|
| `flow_designer` | Create and edit flows |
| `flow_operator` | View execution details, dashboards, logs |
| `action_designer` | Create and edit custom actions |

**Landing page** gives access to flows, subflows, actions, executions, connections, and Help (docs, videos, community, integrations, Developer Site content).

**Tab types:**
- **Flow tabs** – configure triggers & actions
- **Subflow tabs** – configure subflow inputs/outputs/actions
- **Action tabs** – configure action inputs, error evaluation, outputs, steps
- **Operation tabs** – view execution details

To create anything: **New button → Flow / Subflow / Action**.

### Opening Flows
- From the landing page: click the flow name.
- Flows open in the **application scope** they were created in (shown in the flow list and flow footer).
- **Read-only** indicator = can't edit (dev marked it read-only, or another dev has uncommitted changes).
- Can also open a flow from **Studio** via Application Explorer → Flow Designer > Flows.

### Deleting Flows
On the landing page's Flows tab: check the box → Actions on selected rows... → Delete. Only flows in the **same application scope** as the landing page can be deleted.

---

## Creating Flows
- **From Flow Designer:** New button → Flow (or the Create flow/subflow/action icon from other tabs).
- **From Studio:** Create Application File → Flow Designer category → Flow → Create → (opens Flow Designer) → select Flow → Next.

### Configuring Flow Properties
| Field | Purpose |
|---|---|
| Flow name | Unique, readable name (spaces OK) |
| Description | Documents what the flow does |
| Application | Application scope |
| Protection | Make the flow read-only |
| Run As | User who initiates session, or System user |
| Run with role(s) | Roles applied at execution (only if Run As = User who initiates session) |

First-time flow creation triggers a **Guided Tour** (can disable via "Don't show me this again").

### Flow Tab Anatomy
- **Flow header:** name, activation status (Inactive/Active), Test, Deactivate/Activate, Save, More Actions menu (properties, execution list, copy flow, options)
- **Trigger section:** configure the trigger
- **Actions section:** configure actions
- **Data Panel:** shows outputs from trigger/actions
- **Flow footer:** Status (draft/modified/published) + Application
- **Help Panel toggle**

---

## Triggering Flows

Every flow **requires a trigger**, added via "Add a trigger" link. Three trigger types:

### 1. Record Triggers
Fires on record create/update. Types: **Created**, **Updated**, **Created or Updated**.
- Select trigger → specify **Table** → optional **Add filters** for conditions.
- **Run Trigger** options (Updated/Created or Updated only):
  - **Once** – runs only once for the record
  - **For each unique change** – runs for each unique change
  - **Only if not currently running** – skips if a flow instance is already running for the record
  - **For every update** – runs every time, unless already active
  - ⚠️ Flows using approvals should be set to **Once** to avoid over-approving.
- **Advanced Options:**
  - *When to run*: interactive/non-interactive sessions; specific users allowed/blocked; current table only vs. current + extended tables
  - *Where to run*: **Background** (async, default) vs **Foreground** (sync, may block user input)

### 2. Date Triggers
For scheduled/recurring flows (e.g., overdue-task notifications). Types: **Daily, Weekly, Monthly, Run Once, Repeat**.
- Config varies by type (e.g., Weekly needs Day of Week + Time, 24-hour clock).
- 💡 **Tip:** Configure Monthly trigger for day **31** to always run on the last day of any month.

### 3. Application Triggers
Types: **SLA Task**, **Inbound Email**, **Service Catalog**.
- **SLA Task** – no config; select the flow in the SLA Definition record.
- **Inbound Email** – fires on received email; uses conditions from the Email `[sys_email]` table (see Notifications module for detail).
- **Service Catalog** – fires when a catalog item is requested; has a Background/Foreground option; select the flow in the Catalog Item's Process Engine section.

---

## Adding Actions to a Flow
Actions = the "work" a flow performs (e.g., Create Record, Update Record, Send Email, Ask for Approval, Send SMS, Wait For Condition, attachment actions, catalog actions, etc.).

- Add via **Add an Action, Flow Logic, or Subflow → Action** button; actions are grouped by application/category.
- Each action has its own configuration fields (e.g., Create Record needs Table + field values; Send Email needs recipients, subject, message body).

**Managing actions:**
- **Annotate** actions (💡 always document actions for your team/future self)
- **Duplicate** an action to reuse/reconfigure it
- **Delete** an action
- **Reorder**: drag the handle, or hover the transition line between actions to insert a new one at that spot

---

## Saving Flows
- A **green dot** + Status "Modified" = unsaved changes.
- Flow Designer does **not auto-save** — click **Save**.
- Saved flow → Status becomes **Draft**.

---

## Using Flow Variables (Data Pills)
Triggers and actions produce variables, visually shown as **data pills** in the **Data panel**.

- Only data pills from the **trigger and prior actions** are usable (later actions are grayed out).
- 💡 If a pill from a previous action isn't available, **save the flow** first.
- Add a variable to a field by: dragging from the Data panel, OR using the **Data Pill Picker** button on the field.
- Expand Record/Reference pills to **dot-walk** into their fields.
- Incompatible field types are grayed out / blocked.
- **Data pill syntax:** `Trigger` for trigger vars; the action number for action vars; dot-walked path for referenced fields.
- Some fields support concatenating multiple data pills with static text (cursor position matters).

---

## Using Error Handler
Enable Error Handler to catch and react to errors within a flow.

- Adds an **Error Handler section** + variables to the Data panel:
  - **Error Handler switch** – enable/disable
  - **Error Status**
  - **Code** – `1` = error, `0` = success by default (customizable)
  - **Message** – the error message
- Add up to **10** actions/logic/subflows to run when an error occurs.
- **Error states:**
  - *Completed (error caught)* – error identified and Error Handler ran successfully
  - *Completed (error skipped)* – action continues after a failed step
  - *Error* – error not identified (Error Handler disabled, or the Error Handler itself errors)
- To test: create an action designed to error, enable Error Handler, run the flow, inspect Execution Details.

---

## Testing Flows
- Any user with `flow_designer` or `admin` role can click **Test** — this **ignores the trigger** and just runs the actions.
- 💡 Only test in non-production environments.
- **Record triggers**: pick/create a test record in the Test Flow dialog (lookup, create-new, or preview icons). Tests run in **foreground** by default; check "Run test in background" to change.
  - For Updated/Created or Updated triggers, you can simulate a **Changed Fields** array (Field Name, Previous/Current Value, Previous/Current Display Value — all strings). This doesn't change the actual record.
- **Date triggers**: no record needed — just click Run Test.
- **Application triggers**: Inbound Email needs an Email record; Service Catalog needs a Requested Item record.
- After running: click the link to **view flow execution details**, then Cancel/Close the dialog.

---

## Viewing Flow Execution Details
A **flow execution (context)** = the flow's runtime instance, created at execution time and locked to the flow config as of that moment (later flow edits don't affect it).

**Where to find executions:**
- Test Flow dialog result link
- Flow's own **Executions** button
- Landing page **Executions** tab
- All menu → Process Automation → Flow Administration → **Today's Executions**
- All menu → Process Automation → Flow Administration → **Active Flows**

**Execution Details tab sections:** Flow statistics, Trigger execution results, Actions execution results.
Buttons: **Cancel Flow** (only if Waiting), **Open Flow**, **Open Context Record**.

**Flow states:**
- **Completed** – all actions ran successfully
- **Waiting** – paused, waiting on something (e.g., an approval)
- **Error** – execution stopped with an error

- **Trigger details**: who/what triggered it (test vs. real trigger), config details (table/conditions or schedule), and trigger output variables (record links show sys_ids).
- **Action details**: state, timing, input config values, and output data (record/reference outputs are clickable links).

---

## Activating Flows
- A flow only fires on its trigger once **Activated** (Activate button in the header → confirm in dialog).
- **Logging**: active-flow executions are **not logged by default** — enable via All menu → Process Automation → Flow Administration → Properties (⚠️ can be resource-intensive; use non-production for full logging).
- **Deactivating**: click Deactivate → confirm. Currently-running executions finish/cancel normally; new triggers stop firing.

### Flow Status values
| Status | Meaning |
|---|---|
| Draft | Saved changes, not yet activated |
| Modified | Unsaved changes exist |
| Published | Flow is active |

⚠️ A flow can't go directly Modified → Published; it must be **saved** first.
- An active flow with Draft/Modified status still runs the **last published config** when triggered normally, but runs the **draft/modified config** when started via Test.

---

## Running Flows with Alternate Permissions
By default a flow runs **as the triggering user** — that user needs sufficient permissions, or the flow errors out.

**Run As** (set via More Actions → Properties):
- **User who initiates session** (default, safer — but must test with a realistic/minimum-privilege user)
- **System User** – a non-restricted service account (not a real user record)

⚠️ Flows with an **Inbound Email** trigger always run as the emailing user (or Guest) — Run As can't be changed for these.

**Run with role(s):** an alternative to System User — grants specific roles to the initiating user just for this flow's execution (e.g., add `asset` + `itil` roles so a low-privilege user can update hardware/incident records).

Execution details show who the flow ran as and what roles (if any) were applied; record updates show as being made by that identity.

---

## Configuring the Ask for Approval Action
Requests approval on any record. Requires:
- **Record** to approve
- **Approve/Reject rules**
- **Due date** (optional)
- Returns the **Approval State** output data pill.

**Approval tracking fields:**
- **Approval Field** – status field (defaults to `Approval` for Task and Task-extended tables)
- **Journal Field** – history field (defaults to `Approval history` for Task tables)
- For non-Task tables, create your own Choice field (approval) + Journal field (history).

**Approval rule options** (combine with AND/OR):
- Approve: Anyone approves / All users approve / All responded and anyone approves / % of users approve / # of users approve
- Reject: Anyone rejects / All users reject / All responded and anyone rejects / % of users reject / # of users reject
- ⚠️ Configure **both** Approve and Reject rules (or an Approve-or-Reject rule) so the action returns the state you expect — Approve-only configs can return "cancelled" instead of "rejected."

**Due Date** (prevents an action from waiting forever):
- **Actual date** – a specific date from a data pill
- **Relative date** – an offset before/after a date pill, optionally using a schedule (e.g., "8-5 weekdays") to skip weekends/holidays

---

## Flow Logic

### Branching Logic
| Type | Purpose |
|---|---|
| **If** | Run a block when a condition is true |
| **Else / Else If** | Run alternate block(s) when the If condition is false |
| **For Each** | Run a block once per record from a Look Up Records action (input must be type Records or Array.Object) |
| **Do the following until** | Repeat a block until a stop condition is met (max iterations configurable; errors after 1000 by default; outputs only available inside the block) |
| **Do the following in Parallel** | Run multiple branches simultaneously; waits for all to finish before continuing (outputs from one parallel branch aren't visible to others) |

- If no Condition label is set, Flow Designer auto-generates a description from the conditions; otherwise your label is used.
- Add actions/logic to any branch via its own "Add Action, Flow Logic, or Subflow" button.

### Non-Branching Logic
| Type | Purpose |
|---|---|
| **Wait for a duration of time** | Pause the flow — Explicit, Relative, or Percentage duration, optionally against a schedule |
| **Call a Workflow** | Run an existing published (legacy) Workflow inside the flow; can wait for completion; pass a matching record via **Current** |
| **End** | Stops execution within a branch; nothing can follow it |
| **Dynamic Flow** | Run a flow/subflow dynamically at runtime (out of scope for this module) |
| **Get Flow Outputs** | Retrieve outputs from an embedded/dynamic flow (out of scope) |
| **Set Flow Variables** | Create/store variables for use across the flow, similar to workflow scratchpad variables (out of scope) |

---

## Hands-On Exercise Flow (NeedIt Fulfillment)
Rough shape of the exercises, in order:
1. **Create a Flow** – "NeedIt Fulfillment," triggered on NeedIt record **Created**, with an Update Record action setting State = Awaiting Approval and Assigned to = Beth Anglin.
2. **Test the Flow** – test with a real NeedIt record, inspect execution details, try Run As = System User.
3. **Activate the Flow** – activate, create a real record to confirm it fires, check executions, then deactivate; add/remove a Log action to see Draft/Modified/Published status changes; optional Challenge to activate + test with the Log action.
4. **Add Approval** – add a manager to a test user, add an **Ask for Approval** action (approver = requester's manager), remove the static Assigned-to value.
5. **Add Flow Logic** – add **If** (Approval State is Approved) → Update Record to State = Approved; add **Else** → Update Record to State = Closed Complete; test both branches by impersonating the approver to approve one request and reject another, then verify results.

### Exercise: Save Your Work (Optional)
1. Open the app in Studio → Source Control → Commit Changes.
2. Select all Update Sets to commit → Continue.
3. Enter a commit comment (e.g., "Using Flow Designer Module Completed") → Commit Files → Close.

---

## Module Recap — Core Concepts
- Flow Designer **automates processes**.
- Flows trigger on **record creation/update** or a **schedule**.
- A **flow** = sequence of actions + flow logic defining a process.
- **Data pills** = variables from triggers/actions.
- **Flow logic** branches on a **condition** or **for each record** in a set.
- Actions/logic within a branch form a **block**.
- Flows should be **tested in non-production** before activation.
- A **flow execution** is the runtime instance of a flow.
- **Activation** makes the flow run automatically when its trigger condition is met.

---

## What's Next
- **Developing for Flow Designer** – build custom Actions and Subflows.
- **Notifications in Flow Designer** – send emails/notifications, configure inbound/outbound email, respond to inbound email with a flow.
