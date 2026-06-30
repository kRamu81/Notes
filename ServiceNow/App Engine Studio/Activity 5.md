# Activity 5 – Create a Flow to Assign Safety Issue Records

## Scenario
The Safety department wants all **major (Big) safety issues** automatically assigned to a specific person — **Joe Employee**.

Goal: Use **Flow Designer** to build this automation.

---

## Part A – Create a Flow

**1.** On Safety App Home → select **+Add** in the Logic and Automation section
<img width="1482" height="249" alt="image" src="https://github.com/user-attachments/assets/6628d87e-0ca7-48ef-aa76-81b80628807b" />


**2.** Select **Flow**
<img width="1680" height="752" alt="image" src="https://github.com/user-attachments/assets/5ebc1f9b-b516-49be-92b3-afbdbac28282" />


**3.** Select **+ Build from scratch**
<img width="1680" height="832" alt="image" src="https://github.com/user-attachments/assets/f93211c3-8832-415c-a1fc-fba19a8e8b12" />


**4.** Fill in flow properties:
| Field | Value |
|---|---|
| Name | Safety Issue Assignment Flow |
| Description | Assign Safety Issues based on Category |
<img width="1680" height="748" alt="image" src="https://github.com/user-attachments/assets/a1d96516-4735-484c-b3b8-d9319ff3b83f" />


**5.** Click **Continue**
<img width="1094" height="704" alt="image" src="https://github.com/user-attachments/assets/334e00e5-3fdb-4065-b8f9-36063668700a" />


**6.** On success → click **Edit this flow**

**7.** On the tour dialog → select **Skip tour** or **Take tour**

---

## Part B – Configure a Trigger

**1.** Click **Edit flow** button
<img width="1680" height="1370" alt="image" src="https://github.com/user-attachments/assets/b6299fbe-2d2d-4812-affb-317b07c99594" />


**2.** Click **Add a trigger**
<img width="630" height="574" alt="image" src="https://github.com/user-attachments/assets/e4c154e4-2bc9-4e8a-ab96-6c356be023a9" />


**3.** Configure the conditions:
| Setting | Value |
|---|---|
| Trigger | Created or Updated |
| Table | Issues |
| Condition | Category is Big |
| Run Trigger | For each unique change |

**4.** Click **Done**
<img width="1680" height="935" alt="image" src="https://github.com/user-attachments/assets/51d0220a-07b1-45fa-9db3-d14c7bb2a2af" />


---

## Part C – Configure an Action

**1.** Click **+Add an Action, Flow Logic, or Subflow**
<img width="654" height="413" alt="image" src="https://github.com/user-attachments/assets/3ab94312-623a-4682-8249-8b1c2f17f253" />


**2.** Select **Action**
<img width="694" height="408" alt="image" src="https://github.com/user-attachments/assets/c293881b-9899-4cfd-8f6c-330636f348f7" />


**3.** Choose **ServiceNow Core** → **Update Record**
<img width="792" height="828" alt="image" src="https://github.com/user-attachments/assets/e15184bd-8bae-41d9-81fb-e16a7039aa72" />


**4.** Click the **Data Pill Picker** next to the Record field
<img width="1406" height="704" alt="image" src="https://github.com/user-attachments/assets/b09e4e86-82bd-47f3-82ae-23c7432a3b5f" />


**5.** Select **Trigger – Record Created or Updated**

**6.** Select **Issues Record**
*(Table field auto-fills to "Issues")*
<img width="1284" height="824" alt="image" src="https://github.com/user-attachments/assets/fc39006f-c32c-4097-8bee-74e1d8fb6d14" />


**7.** Click **+ Add field value** → set:
- Field: **Assigned to**
- Value: **Joe Employee**

**8.** Click **Done**
<img width="1445" height="764" alt="image" src="https://github.com/user-attachments/assets/23787805-02a8-4cba-88ad-e5119704fe08" />


---

## Part D – Test and Activate the Flow

### Test the Flow

**1.** Click **Test**
<img width="1680" height="122" alt="image" src="https://github.com/user-attachments/assets/86e5bb74-5aff-4ece-bcd5-bacf48aea541" />


**2.** Next to Issue Record dropdown → click **Create new record (+)**
<img width="1135" height="434" alt="image" src="https://github.com/user-attachments/assets/061facb2-d8c8-43e1-a625-ec748f6b8ee3" />


**3.** Fill in test record:
| Field | Value |
|---|---|
| Short description | Broke my coffee cup! |
| Category | Big |
<img width="1680" height="1088" alt="image" src="https://github.com/user-attachments/assets/e4c1b99f-2487-441e-a527-e755a270dca2" />


**4.** Click **Submit**

**5.** Click **Run Test**
<img width="1131" height="431" alt="image" src="https://github.com/user-attachments/assets/6655f009-43c7-4b91-8545-bd3e8c2bbe8c" />


**6.** Click **'Your test has finished running. View the flow execution details.'**
<img width="1126" height="515" alt="image" src="https://github.com/user-attachments/assets/d3cd954a-cac9-480d-b7a9-c595282a581b" />


**7.** Confirm Test Run = **Completed, no errors** → click **Update Record** action to expand details
<img width="1680" height="460" alt="image" src="https://github.com/user-attachments/assets/20263e4f-4372-419d-897c-a477b286df9c" />


**8.** Check that the variable values match the submitted record

**9.** Click the **Record link (SAFT000XXXX)** → verify **Assigned to = Joe Employee**
<img width="793" height="156" alt="image" src="https://github.com/user-attachments/assets/eaf3107a-7ee9-4da6-9c10-d14b9260b2a0" />


**10.** Click **X** to close the record preview

**11.** Click **X** on the Executions tab to close execution details
<img width="1680" height="1396" alt="image" src="https://github.com/user-attachments/assets/f53328c2-4912-4471-9273-f4a74421d98b" />


**12.** Click **X** on the Test Flow window to return to Flow Designer
<img width="1131" height="501" alt="image" src="https://github.com/user-attachments/assets/ea230348-f51a-4845-a728-cbed99a582bd" />


### Activate the Flow

**13.** Click **Save**, then click **Activate**
<img width="1666" height="120" alt="image" src="https://github.com/user-attachments/assets/25fd8f68-bc2f-47d8-823d-f5acd26b2e69" />


**14.** Confirm by clicking **Activate** in the popup dialog
<img width="620" height="377" alt="image" src="https://github.com/user-attachments/assets/7415f52f-31e6-41a9-889e-3815c6687112" />


**15.** Flow is now **Active** → click **X** to close the Flow window
<img width="857" height="162" alt="image" src="https://github.com/user-attachments/assets/3c43148c-ed46-490d-9f0a-22de8b536c0f" />


**16.** Click **Save**

**17.** Verify the **Safety Issue Assignment Flow** appears correctly on the Safety App Home page
![Uploading image.png…]()

---

## Key Takeaways

- A flow needs both a **Trigger** (when to start) and an **Action** (what to do)
- Use the **condition builder** to define exactly when the flow should run
- Use the **Data Pill Picker** to connect trigger data into your action fields
- Always **test before activating** — check for errors and verify field values
- **Activate** the flow to make it live and start automatically assigning records
- Confirm the flow shows up correctly on the **App Home page** after activation
