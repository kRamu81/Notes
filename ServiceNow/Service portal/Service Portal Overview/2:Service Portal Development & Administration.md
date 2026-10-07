## Service Portal Development & Administration 

### 1. Service Portal Users
- **External users** → Public users.
- **Customers** → Users with a customer relationship.
- **Employees / Requesters** → Make requests.
- **Fulfillers** → Work on incidents, requests, changes, etc.
- **Approvers** → Managers/team leads who approve requests. Pasted markdown

### 2. Important Roles

**System Admin**
- Activates plugins.
- Has full system access.
- Can override ACLs.
- Should be given carefully.

**sp_admin (Service Portal Admin)**
- Full access **inside Service Portal**.
- Designs, builds and manages portals.
- Delegated from the System Admin. Pasted markdown

### 3. Development Levels

**No-Code**
- Drag & drop.
- No programming required.
- Branding and portal construction.

**Low-Code**
- Basic HTML, CSS and Bootstrap knowledge.

**Pro-Code**
- Developers.
- JavaScript + AngularJS.
- ServiceNow APIs.
- HTML, CSS, Bootstrap and scripting. Pasted markdown

### 4. Managed Developers
- Developers can be given **specific permissions** without giving full admin access.
- Managed through **Studio → File → Manage Developers**.
- Permissions can be given to individuals or groups. Pasted markdown

### 5. Source Control
Studio supports:
- Connect application to source control.
- Commit changes.
- Stash changes.
- Apply remote changes.
- Create/switch branches.
- Tag branches. Pasted markdown

### 6. Service Portal Plugin
- Service Portal is available in baseline instances.
- If unavailable, activate **Service Portal for Enterprise Service Management** plugin.
- **No license is required** to activate/use the Service Portal application. Pasted markdown

### 7. Baseline Resources
ServiceNow provides starting resources:
- **8 portals**
- **10+ themes & menus**
- **100+ pages**
- **250+ widgets** Pasted markdown

### 8. Example Portals
- Employee Center
- Traditional Service Portal
- Knowledge Portal → `/kb`
- CAB Workbench → `/cab` Pasted markdown

### 9. Service Portal Configuration
**Main workspace:** `sp_config`

Important modules:
- Properties
- Portal Tables
- Portal configuration
- Portal records/components

**Properties** = System configuration options for Service Portal. Pasted markdown

###  Remember

**No-Code → Drag & Drop**  
**Low-Code → HTML + CSS + Bootstrap**  
**Pro-Code → JavaScript + AngularJS + APIs**  
**sp_admin → Service Portal administration**  
**sp_config → Main Service Portal configuration**  
**Studio → Development & Manage Developers**  
**Service Portal → Requester/User experience**
