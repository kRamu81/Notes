# Activity 4 – Create a Record Producer

## Scenario
Employees find the Safety Issue form **confusing**.
Goal: build a **simplified form** (record producer) using easy, human-readable questions instead of field labels.

> ✅ Complete Activity 3 before starting this one.

---

## Part A – Create a Record Producer

**1.** On Safety App Home → select **+Add** in the Experience section
<img width="1680" height="993" alt="image" src="https://github.com/user-attachments/assets/54eb175c-db67-4cb9-983c-37a2932a0120" />


**2.** Select **Record producer**
<img width="1584" height="838" alt="image" src="https://github.com/user-attachments/assets/39de72d7-8bd2-41d3-b49f-f6fcdb4bce8d" />


**3.** In the dialog box → click **Begin**
<img width="1353" height="834" alt="image" src="https://github.com/user-attachments/assets/5f0a38d1-1e42-406f-b633-605fe6b70d17" />


**4.** Fill in the details:
| Field | Value |
|---|---|
| Name | Report a Safety Issue |
| Short description | See something, report something – be safe! |
<img width="1680" height="997" alt="image" src="https://github.com/user-attachments/assets/904c8860-5563-4722-b6c0-c38bb4e2014b" />


**5.** Click **Continue**

**6.** On success → click **Edit record producer**
<img width="1332" height="672" alt="image" src="https://github.com/user-attachments/assets/a59e0823-84e3-4ec0-bc0c-68424958db59" />


---

## Part B – Configure Record Producer Details

**1.** Catalog Builder opens with Name and Short description already filled in

**2.** Scroll to **Item details** → click **Attach File**
<img width="1680" height="734" alt="image" src="https://github.com/user-attachments/assets/b235295e-4ad7-4b87-a061-af4311b6d330" />


**3.** Upload `safety_logo.png`

**4.** In the Description field, enter:
`Report a big, medium, or small safety issue.`
<img width="1680" height="817" alt="image" src="https://github.com/user-attachments/assets/960ceba9-ad88-4984-8b0c-19f75c98a363" />


**5.** Click **Save**

---

## Part C – Configure the Destination

**1.** Select **Destination** on the left pane
<img width="1680" height="714" alt="image" src="https://github.com/user-attachments/assets/4d715f80-a20b-47ae-9a27-2e8a48812cac" />


**2.** Set **Record submission table** = `Issues table`
<img width="1680" height="737" alt="image" src="https://github.com/user-attachments/assets/07386da4-3144-46f7-9151-e9b70ef371bc" />


**3.** Click **Save**

---

## Part D – Configure the Location

**1.** Select **Location** on the left pane
<img width="1680" height="764" alt="image" src="https://github.com/user-attachments/assets/f3338f5d-bcae-4c9f-a050-f53966a302cf" />


**2.** Under **Catalogs**, click **Browse**

**3.** Move **Service Catalog** to Selected catalogs
<img width="1680" height="758" alt="image" src="https://github.com/user-attachments/assets/a5d6ba72-694f-404a-a647-027b9d4907c1" />


**4.** Click **Save selections**

**5.** Under **Categories**, click **Browse**

**6.** Move **Can We Help You?** to Selected categories
<img width="1680" height="760" alt="image" src="https://github.com/user-attachments/assets/df6488fa-4e2c-4f34-90d4-9ea87195a60c" />


**7.** Click **Save**
<img width="1680" height="1255" alt="image" src="https://github.com/user-attachments/assets/90b0392a-5b36-4f5b-9683-e7320ff2f435" />


---

## Part E – Configure Catalog Item Questions

You will create **4 questions**, one for each field:

| Field | Question Type | Subtype | Question Label |
|---|---|---|---|
| Category | Choice | Dropdown (fixed values) | What is the size of this issue? |
| Due date | Date/Time | Date | When do you need this resolved? |
| Location | Choice | Record reference | Where did this issue take place? |
| Short description | Text | Multi-line | Please provide a brief description of the issue. |

### Question 1 – Category (Step-by-step example)

**1.** Select **Questions** on the left pane → click **Insert new question**

**2.** Set **Question type** = Choice
<img width="1680" height="722" alt="image" src="https://github.com/user-attachments/assets/8479ce35-5cef-4b87-850d-6a212a193d29" />


**3.** Set **Question subtype** = Dropdown (fixed values)

**4.** Check **Map to a specific field on the table**
<img width="1680" height="725" alt="image" src="https://github.com/user-attachments/assets/f2502eb5-922e-4287-a9c4-5210f9c63f63" />


**5.** Set **Table field** = Category

**6.** Set **Question label** = `What is the size of this issue?`

**7.** Set **Name** = `category`

**8.** Check **Mandatory**
<img width="1680" height="1375" alt="image" src="https://github.com/user-attachments/assets/3a4a1c1f-b584-41b0-b8ce-3872dd060e55" />


**9.** Go to **Choices** tab → check **Include none choice**
<img width="1260" height="761" alt="image" src="https://github.com/user-attachments/assets/f40e446c-df5a-4e46-9b1e-1aa73838935f" />


**10.** Click **+ Insert** and add 3 choices:
| Display Name | Value |
|---|---|
| Big | big |
| Medium | medium |
| Small | small |
<img width="1680" height="1378" alt="image" src="https://github.com/user-attachments/assets/25992ac2-1b8e-4c7a-87fc-a90da74cf60f" />


**11.** Go to **Annotation** tab → check **Show instructions**

**12.** Type: `If this is a life-or-death situation, call 911.`
<img width="1680" height="1391" alt="image" src="https://github.com/user-attachments/assets/2978187e-2f36-4279-b125-2cfc92e94fc2" />



**13.** Check the **Question Preview** panel — confirm question, choices, and instructions appear correctly

**14.** Click **Insert Question**

**15.** Click **Save**, then **Preview** to verify the question in Portal view
<img width="1680" height="688" alt="image" src="https://github.com/user-attachments/assets/4c913f39-3fa0-475e-9cc2-ca794cd761fe" />

**16.** Close the preview (X)
<img width="1680" height="1225" alt="image" src="https://github.com/user-attachments/assets/bfc62077-f551-48a8-839f-2a4741975967" />



### Repeat for the Remaining 3 Questions

Follow the same process (Insert new question → fill in type/subtype/label/name → Mandatory → Insert) for:
- **Due date** (Date/Time → Date)
- **Location** (Choice → Record reference, Source table = `Location [cmn_location]`)
- **Short description** (Text → Multi-line)
- 

> Tip: For the Location question, set **Source table** to `cmn_location` in Additional details.

**Once all 4 questions are added:**
<img width="1254" height="781" alt="image" src="https://github.com/user-attachments/assets/2a0df812-0d76-4234-b6fe-e5c0226a5451" />
<img width="1680" height="1401" alt="image" src="https://github.com/user-attachments/assets/4307d93c-0cfa-4123-bc23-f01668ed6c36" />


- Click **Save**, then **Preview** to confirm everything looks correct in Portal view
- Close the preview (X)
- <img width="1680" height="943" alt="image" src="https://github.com/user-attachments/assets/893f1b6b-5be5-4b61-8639-339b2bc675d2" />


---

## Part F – Review and Submit

**1.** Select **Review and Submit** on the left pane

**2.** Double-check: Details, Destination, Location, Questions, Settings — all correct
<img width="1404" height="888" alt="image" src="https://github.com/user-attachments/assets/b7460c11-9e50-4da8-aec1-021509022da6" />


**3.** Click **Submit**
<img width="1680" height="885" alt="image" src="https://github.com/user-attachments/assets/d0643ab3-d027-48fd-97a5-e57e773b139e" />


**4.** On success → click **Return to my application**

---

## Part G – Test the Record Producer

**1.** Go to the main ServiceNow browser window

**2.** All menu → search `service catalog`

**3.** Select **Self-Service → Service Catalog**
<img width="495" height="545" alt="image" src="https://github.com/user-attachments/assets/eff7b780-1287-4c91-9777-fb3a51f7af26" />


**4.** Select the **Can We Help You?** category
<img width="1680" height="716" alt="image" src="https://github.com/user-attachments/assets/edcaa494-9fb1-4196-a8a9-2f8ddfb903ae" />

**5.** Select **Report a Safety Issue** item
<img width="1680" height="1566" alt="image" src="https://github.com/user-attachments/assets/3eb4064d-6670-4857-83d0-bf7aed28ceb3" />


**6.** Fill out the form → click **Submit**
<img width="1680" height="1212" alt="image" src="https://github.com/user-attachments/assets/ccd8c2ee-5aaa-46cf-88c0-c1cc0e405df4" />


**7.** Confirm a new **Issues record** is created with the correct values
<img width="1680" height="1212" alt="image" src="https://github.com/user-attachments/assets/7b63f3b0-36b0-4260-9444-53e0417b4c8d" />


**8.** Navigate back to the **Safety App Home** in App Engine Studio
<img width="1680" height="1178" alt="image" src="https://github.com/user-attachments/assets/6309b37a-73bb-4bfe-8146-1cd963f094ee" />


---

## Key Takeaways
- A **record producer** simplifies data entry using clear, human-readable questions
- Configure it in order: **Details → Destination → Location → Questions → Review & Submit**
- Use **Mandatory** to ensure key questions are always answered
- Add **Annotations** to give users helpful instructions (e.g. emergency notices)
- Always **Preview and Test** in the Service Catalog before considering it complete
