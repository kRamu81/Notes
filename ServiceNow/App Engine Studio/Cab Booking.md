# Project 3: Cab Booking Automation
### Built using App Engine Studio, Service Catalog, Flow Designer, Notifications & Reports

---

## Project Overview

**Goal:** Build an app where employees can request a cab for office commute, airport drops, or business travel. The system collects trip details, assigns a driver/vendor, notifies the transport team, and tracks the booking status — all with **no code**.

**Departments involved:** Employee (Requester), Transport/Admin Team, Driver/Vendor

**App Name:** `Cab Booking`

---

## Project Structure (5 Activities)

| Activity | What You Build | Tool Used |
|---|---|---|
| 1 | Application framework | App Engine Studio |
| 2 | Cab Booking table with data | Table Builder |
| 3 | Table fields, form layout, UI policy | Table Builder + Form Builder |
| 4 | Cab booking request form | Catalog Builder (Record Producer) |
| 5 | Automation + Notifications | Flow Designer |
| Bonus | Cab booking dashboard | Reports |

---

## Activity 1: Create the Application Framework

### Scenario
As an Admin/Facilities Business Process Analyst, you want to automate the cab booking process — currently done manually over phone calls and emails to the transport desk.

### Steps

**1.** Log into your ServiceNow instance

**2.** Go to **All menu** → search `engine`

**3.** Select **App Engine → App Engine Studio**

**4.** Click **Get Started** (first-time welcome dialog)

**5.** Click **Create app**

**6.** Fill in app details:
| Field | Value |
|---|---|
| Name | Cab Booking |
| Description | This application allows employees to request cabs and helps the transport team track and assign bookings. |
| Logo | Upload your own logo (optional) |

**7.** Click **Continue**

**8.** Keep the default **Admin** and **User** roles → click **Continue**

**9.** Click **Go to app dashboard**

---

## Activity 2: Create the Cab Booking Table

### Scenario
You need a central table to store every cab booking request and its status.

### Steps

**1.** From App Home → select **+ Add a table or upload a spreadsheet or PDF**

**2.** Select **Create a new table from scratch** → Continue

**3.** Set table properties:
| Property | Value |
|---|---|
| Table label | Cab Bookings |
| Table name | auto-populated, leave as is |
| Make extensible | unchecked |
| Auto-number | checked, Prefix: `CAB`, Starting number: `1000` |

**4.** Click **Continue**

**5.** Set permissions:
| Role | Permission |
|---|---|
| admin | All |
| user | Read + Write |

**6.** Click **Continue** → **Edit table**

### Add Fields in Table Builder

| Field Label | Type | Notes |
|---|---|---|
| Requested By | Reference → User [sys_user] | Employee booking the cab |
| Trip Type | Choice | Office Pickup, Office Drop, Airport, Outstation, Local Visit |
| Pickup Location | String | Address or landmark |
| Drop Location | String | Destination address |
| Pickup Date | Date | Date of travel |
| Pickup Time | Date/Time | Exact pickup time |
| Number of Passengers | Integer | How many people traveling |
| Vehicle Type | Choice | Sedan, SUV, Mini Van |
| Driver/Vendor Assigned | Reference → User [sys_user] | Filled by transport team |
| Status | Choice | Pending, Assigned, In Progress, Completed, Cancelled |
| Notes | HTML | Special instructions |

**7.** Set **Status** field default value = `Pending`

**8.** Set **Requested By** field dynamic default value = `Me`

**9.** Click **Save**

---

## Activity 3: Configure Fields and Form Layout

### A. Configure Fields
**1.** Open **Cab Bookings** table → Table Builder

**2.** Set **Trip Type** choice values:
| Label | Value |
|---|---|
| Office Pickup | office_pickup |
| Office Drop | office_drop |
| Airport | airport |
| Outstation | outstation |
| Local Visit | local_visit |

**3.** Set **Vehicle Type** choice values:
| Label | Value |
|---|---|
| Sedan | sedan |
| SUV | suv |
| Mini Van | mini_van |

**4.** Set **Status** choice values:
| Label | Value |
|---|---|
| Pending | pending |
| Assigned | assigned |
| In Progress | in_progress |
| Completed | completed |
| Cancelled | cancelled |

**5.** Save your work

### B. Configure Form Layout (Form Builder)

**1.** In Table Builder → **Additional actions (⋯) → Form designer**

**2.** Select **Try Form Builder**

**3.** Add a section labeled **Trip Details** with: Requested By, Trip Type, Pickup Location, Drop Location, Pickup Date, Pickup Time, Number of Passengers, Vehicle Type

**4.** Add a second section labeled **Assignment** with: Driver/Vendor Assigned, Status, Notes

**5.** Click **Save** → **Preview** to verify

### C. Add a UI Policy

**Goal:** Make all fields read-only once a trip is Completed or Cancelled (so historical records aren't accidentally edited)

**1.** Go to **Policies and rules → +Add new policy**

**2.** Configure:
| Field | Value |
|---|---|
| Short description | Make fields read-only when trip is Completed |
| Condition | Status is Completed |

**3.** Add fields and set Read only = true for: Trip Type, Pickup Location, Drop Location, Pickup Date, Pickup Time, Vehicle Type, Status

**4.** Click **Add UI Policy** → **Save**

**5.** Test by changing Status to Completed and confirming fields gray out

---

## Activity 4: Create a Cab Booking Request Form (Record Producer)

### Scenario
Employees need a **simple form** in the Service Catalog to request a cab — without seeing technical field names.

### Steps

**1.** On App Home → **+Add** in Experience section

**2.** Select **Record producer** → click **Begin**

**3.** Fill in:
| Field | Value |
|---|---|
| Name | Book a Cab |
| Short description | Request a cab for office commute, airport, or business travel |

**4.** Click **Continue** → **Edit record producer**

### Configure Details
**5.** Add a description: `Use this form to request a cab for your travel needs.`

**6.** Click **Save**

### Configure Destination
**7.** Select **Destination** → set **Record submission table** = `Cab Bookings`

**8.** Click **Save**

### Configure Location
**9.** Select **Location** → Browse Catalogs → select **Service Catalog** → Save

**10.** Browse Categories → select or create **Travel & Transport** → Save

### Configure Questions

Build these questions (repeat the question creation steps for each):

| Field | Question Type | Subtype | Question Label | Mandatory |
|---|---|---|---|---|
| Trip Type | Choice | Dropdown (fixed values) | What type of trip is this? | Yes |
| Pickup Location | Text | Single-line | Where should the cab pick you up? | Yes |
| Drop Location | Text | Single-line | Where do you need to go? | Yes |
| Pickup Date | Date/Time | Date | What date do you need the cab? | Yes |
| Pickup Time | Date/Time | Time | What time should the cab arrive? | Yes |
| Number of Passengers | Text | Single-line (numeric) | How many people are traveling? | Yes |
| Vehicle Type | Choice | Dropdown (fixed values) | What type of vehicle do you prefer? | No |

**For each question:**
- Check **Map to a specific field on the table**
- Select the matching **Table field**
- Set the **Question label**
- Mark **Mandatory** where required
- Click **Insert Question**

**Add an Annotation** (on the Pickup Date question):
> "Please submit cab requests at least 2 hours in advance for local trips and 24 hours for outstation trips."

### Review and Submit
**11.** Select **Review and Submit** → verify all sections → click **Submit**

**12.** Click **Return to my application**

### Test
**13.** Go to **Service Catalog → Travel & Transport → Book a Cab**

**14.** Fill out the form and submit

**15.** Confirm a new **Cab Bookings** record is created with Status = Pending

---

## Activity 5: Automate with Flow Designer + Notifications

### Scenario
When a new cab booking request is submitted, automatically:
1. Notify the **Transport Team** that a new booking needs to be assigned
2. Notify the **Employee** that their request was received
3. Update the **Status** to "Pending Assignment" (stays Pending until transport team assigns a driver)

Then, when a driver is assigned:
4. Notify the **Employee** with driver details
5. Update **Status** to "Assigned"

### A. Create the Flow

**1.** On App Home → **+Add** in Logic and Automation section

**2.** Select **Flow** → **+ Build from scratch**

**3.** Fill in:
| Field | Value |
|---|---|
| Name | Cab Booking Notification Flow |
| Description | Notify transport team and employee on booking creation and driver assignment |

**4.** Click **Continue** → **Edit this flow**

### B. Configure the Trigger

**1.** Click **Add a trigger**

**2.** Configure:
| Setting | Value |
|---|---|
| Trigger | Created |
| Table | Cab Bookings |
| Condition | Status is Pending |
| Run Trigger | For each unique change |

**3.** Click **Done**

### C. Action 1 – Notify Transport Team

**1.** Click **+Add an Action → ServiceNow Core → Send Email**

**2.** Use Data Pill Picker → select **Trigger Record**

**3.** Configure:
| Field | Value |
|---|---|
| To | Transport Team Group email |
| Subject | New Cab Booking Request – Action Needed |
| Message | Use data pills: Requested By, Trip Type, Pickup Location, Drop Location, Pickup Date, Pickup Time |

**4.** Click **Done**

### D. Action 2 – Notify Employee (Request Received)

**1.** Click **+Add an Action → ServiceNow Core → Send Email**

**2.** Use Data Pill Picker → select **Trigger Record → Requested By**

**3.** Configure:
| Field | Value |
|---|---|
| To | Requested By (data pill) |
| Subject | Your Cab Booking Request Has Been Received |
| Message | "Your cab booking request for [Pickup Date] has been received and is being processed by the Transport Team." |

**4.** Click **Done**

### E. Create a Second Flow – Notify on Driver Assignment

**1.** Create a new flow: **Cab Booking Assignment Notification**

**2.** Configure Trigger:
| Setting | Value |
|---|---|
| Trigger | Updated |
| Table | Cab Bookings |
| Condition | Driver/Vendor Assigned **changes** AND Status is Assigned |
| Run Trigger | For each unique change |

**3.** Add **Action → Update Record** → set Status = Assigned (if not already set by transport team)

**4.** Add **Action → Send Email**:
| Field | Value |
|---|---|
| To | Requested By (data pill) |
| Subject | Your Cab Has Been Assigned |
| Message | "Your cab for [Pickup Date] at [Pickup Time] has been assigned. Driver: [Driver/Vendor Assigned]." |

**5.** Click **Done**

### F. Test the Flow

**1.** Click **Test**

**2.** Create a new test record:
| Field | Value |
|---|---|
| Trip Type | Airport |
| Pickup Location | Office HQ |
| Drop Location | City Airport |
| Pickup Date | (tomorrow's date) |
| Pickup Time | 6:00 AM |

**3.** Click **Submit → Run Test**

**4.** Verify:
- Transport team notification was sent
- Employee notification was sent
- Status remains Pending

**5.** Click the Record link to confirm field values are correct

### G. Activate Both Flows

**1.** Click **Save → Activate** on each flow

**2.** Confirm **Activate** in the popup

**3.** Close the flow window → verify both flows appear on the App Home page

---

## Bonus: Build a Cab Booking Dashboard (Reports)

### Scenario
The Transport/Admin team wants visibility into booking volume, trip types, and pending assignments.

### Steps

**1.** From the main ServiceNow UI → All menu → search `Reports`

**2.** Select **Reports → Create New**

**3.** Configure the report:
| Field | Value |
|---|---|
| Name | Cab Bookings by Status |
| Table | Cab Bookings |
| Type | Pie chart |
| Group by | Status |

**4.** Click **Run** to preview → **Save**

### Add a Second Report – Bookings by Trip Type
| Field | Value |
|---|---|
| Name | Cab Bookings by Trip Type |
| Table | Cab Bookings |
| Type | Bar chart |
| Group by | Trip Type |

### Add a Third Report – Daily Booking Volume
| Field | Value |
|---|---|
| Name | Daily Cab Booking Trend |
| Table | Cab Bookings |
| Type | Line chart |
| Group by | Pickup Date |

### Add Reports to a Dashboard
**5.** Go to **All menu → Performance Analytics/Reporting → Dashboards**

**6.** Create a new dashboard: **Cab Booking Dashboard**

**7.** Add all three reports as widgets

**8.** Share the dashboard with the **Transport/Admin group**

---

## Final Project Summary

| Layer | What Was Built |
|---|---|
| **Data** | Cab Bookings table with 11 fields |
| **Experience** | Record producer form in Service Catalog (Travel & Transport) |
| **Logic & Automation** | 2 flows: booking notifications + driver assignment notifications |
| **Security** | Admin/User roles, UI Policy to lock Completed records |
| **Reports** | Status, Trip Type, and Daily Trend dashboard |

---

## Key Takeaways

- This project follows the **same 5-activity pattern** as the Safety Issue and Onboarding apps
- **App Engine Studio** = framework + data + security in one place
- **Catalog Builder** = simple, guided forms for employees who just need to book a cab
- **Flow Designer** = handles two key automation moments: booking creation and driver assignment
- Splitting automation into **two separate flows** (one for creation, one for assignment) keeps logic clean and easy to maintain
- **Reports/Dashboards** give the transport team real-time visibility into demand and pending work
- This entire project can be built **without writing a single line of code**
