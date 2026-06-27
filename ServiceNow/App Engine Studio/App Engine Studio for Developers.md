# App Engine Studio for Developers – Course Notes

---

## What is Full-Stack Development?

A **full-stack developer** builds software across all layers — database, server, and user interface.

### How the Dev Stack Maps to ServiceNow (Now AI Platform)

| Traditional Stack | ServiceNow Equivalent |
|---|---|
| UX/UI Design | UX/UI (same tools) |
| Front End (React, Angular, Vue) | Experience (Workspace, Mobile, Portal) |
| Back End (Java, .Net, APIs) | Logic & Automation (Flows, Business Rules) + Security (ACLs) |
| Database (MySQL, MongoDB) | Data (Tables, Integration Spokes) |
<img width="1680" height="964" alt="image" src="https://github.com/user-attachments/assets/f5d01a35-342d-4774-b710-679135371865" />


---

## Development Tools on the Now AI Platform

### 1. Studio (Traditional IDE)
<img width="1680" height="1141" alt="image" src="https://github.com/user-attachments/assets/0b988969-1cf7-49f7-bd57-238bb6c2d30a" />
- Works like a **standard code editor** (similar to VS Code)
- Best for **pro-code / advanced developers**
  

**What you can do in Studio:**
- View all app files in the **Application Explorer**
- Create new files from a single interface
- Search code by name or type
- Work on **multiple files and apps** at the same time using tabs
- Publish apps to your company instances or the **ServiceNow Store**

### 2. App Engine Studio (AES)
<img width="1680" height="840" alt="image" src="https://github.com/user-attachments/assets/c53a7593-bc2d-4a3d-8535-93a3fd08cc7a" />

- A **guided, low-code** tool for building apps fast
- Works for **all skill levels** — beginner to pro
- Build from scratch or **customize a template**
- Organized around the 4 app layers: Data, Experience, Logic & Automation, Security

> ServiceNow encourages **all developers** (including pro-code) to use AES to start building apps quickly.

---

## 4 Building Blocks of an App in AES

| Layer | What it Does |
|---|---|
| **Data** | Tables and fields to store information |
| **Experience** | What users see — portals, workspaces, mobile |
| **Logic & Automation** | Flows, business rules, automations |
| **Security** | Roles and access controls (ACLs) |

---

## Additional Tools Inside AES

| Tool | Purpose |
|---|---|
| **UI Builder** | Build custom user interfaces visually |
| **Table Builder** | Create and edit tables and fields |
| **Catalog Builder** | Build Service Catalog items and forms |
| **Flow Designer** | Automate processes without code |
| **Mobile App Builder** | Create mobile-friendly app experiences |

---

## App Development Lifecycle in AES
<img width="1680" height="534" alt="image" src="https://github.com/user-attachments/assets/f01afc33-8dbd-4335-bf38-490aed0300e0" />


Always follow this order — **never develop directly on Production**:

**Development Instance** → build and fix the app here
**Test Instance** → admin publishes app here for testing
**Production Instance** → live app for all users after testing passes

> Any bugs found in testing → fix in Dev → push back to Test → then publish to Prod

---

## Install and Configure AES

### Installation
- AES requires a **license** and is installed from the **ServiceNow Store**
- Install the **full AES product** (not just the basic app) to get all tools
- Includes: Table Builder, Flow Designer, Mobile App Builder, and more

### How to Configure After Install
- Go to: **All → App Engine → Configuration → Guided Setup**
- Guided Setup helps you:
  - Connect spokes for third-party integrations
  - Review Flow Designer and Service Catalog access settings
  - Set up **instance health scan schedule**
  - Create the **AES admin group**
  - Grant AES access to developers and users

---

## AES Related Applications (Optional but Recommended)

### 1. Application Intake
- Helps admins **approve and track app requests** from users
- Once approved → automatically **provisions the user** to the dev instance
- Configure via: **All → App Engine → Application Intake → Guided Setup**

### 2. Pipelines and Deployments
- Manages the **Dev → Test → Production** deployment pipeline
- Automates how apps move between environments

### 3. App Engine Management Center (AEMC)
- **Central hub** to manage all AES apps end to end
- Handles: development requests, approvals, collaboration, and production deployments

---

## Key Takeaways

- ServiceNow maps to a **full-stack development model** (Data, Logic, Experience, Security)
- **Studio** = traditional IDE for pro-code developers
- **AES** = low-code guided tool for all skill levels
- Always develop in **Dev → Test → Prod** — never on production directly
- Install the **full AES product** from the ServiceNow Store for all features
- Use **AEMC** to manage the full app lifecycle from one place
