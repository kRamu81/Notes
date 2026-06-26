# REST Integration – Inbound REST Requests
### ServiceNow Web Services Course Notes

---

## What is a Web Service?

A web service lets apps **connect and exchange data** over a network.

- **Consumer (Client)** → sends a request
- **Provider (Server)** → processes it and sends back a response

**ServiceNow as Provider:** A third-party app requests data or an action through a ServiceNow API.

---

## Common ServiceNow APIs

| API | What it Does |
|---|---|
| **Table API** | Create, Read, Update, Delete records in a table |
| **Attachment API** | Upload and query file attachments |
| **Email API** | Send and receive emails using REST |

> REST API is **active by default** on all ServiceNow instances.

---

## REST API Explorer

A built-in tool to **build and test API requests** without writing code.

**Who can use it:** Users with `rest_api_explorer` or `admin` role

**How to open:** All menu → System Web Services → REST → REST API Explorer

> ⚠️ The REST API Explorer works directly on your instance — it can **create, update, and delete** real records. Use on a **non-production instance only**.

### Key Selections in REST API Explorer

| Field | What to Choose |
|---|---|
| **Namespace** | `now` = ServiceNow APIs, `global` = global scope |
| **API Name** | Pick the API (e.g. Table API) |
| **API Version** | Choose version or `latest` |
| **Method** | GET / POST / PUT / PATCH / DELETE |

---

## Request Parameters

### 1. Path Parameters
- Filled directly **into the endpoint URL**
- Example: `tableName = incident` goes into the URL path

### 2. Query Parameters
- Added to the end of the URL
- Common ones:

| Parameter | What it Does |
|---|---|
| `sysparm_query` | Filter records (use encoded query) |
| `sysparm_fields` | Return only specific fields |
| `sysparm_limit` | Limit number of results returned |
| `sysparm_exclude_reference_link` | Set `true` to remove extra reference links |

### 3. Request Headers
- Define the **format** of request and response

| Header | Value |
|---|---|
| Request format | application/json |
| Response format | application/json |
| Authorization | Send as me |

**Useful extra headers:**
- `X-WantSessionDebugMessages: true` → returns session debug logs
- `X-WantSessionNotificationMessages: true` → returns session notifications

---

## Encoded Queries

Some parameters like `sysparm_query` need an **encoded query** — don't write it manually.

**How to get it:**
1. Go to the table list (e.g. Incident → Open)
2. Use the filter to build your condition
3. Click **Run**, then right-click the breadcrumb → **Copy query**
4. Paste it into `sysparm_query` in REST API Explorer

---

## Field Name Tips

- Always use the **field name** (e.g. `caller_id`), not the field label (e.g. "Caller")
- **Dot-walking** is allowed: `caller_id.title`
- For reference fields, set return value:
  - `true` = display value (human-readable name)
  - `false` = sys_id only
  - `all` = both display value and sys_id

---

## API Response

Every API call returns 3 things:

**1. HTTP Status Code**
| Code | Meaning |
|---|---|
| 2xx | Success |
| 4xx | Client Error (bad request, no permission) |
| 5xx | Server Error |

**2. Response Headers** — metadata about the response

**3. Response Body** — the actual data returned (in JSON format)

### Data Type Notes
| Field Type | Database Value | Display Value |
|---|---|---|
| Reference | sys_id | Human-readable name |
| Date | UTC format | User's time zone |
| Choice | Number | Descriptive label |
| Encrypted | Encrypted | Unencrypted (if user has access) |

---

## Security for Inbound API Requests

### 1. Create a Dedicated API User
- Create a separate user just for API requests
- Set **Identity Type** to `Machine` (integration-only account)
- Grant only the roles needed to access the required records

### 2. Disallow Web Service Access to Tables
- Go to **System Definition → Tables**
- Open the table record → Application Access section
- Uncheck **"Allow access to this table via web services"**
- ⚠️ REST API Explorer **ignores** this setting — it applies only to external requests

### 3. CORS Rules
- Controls which **external domains** can call your REST APIs
- Go to: All menu → System Web Services → REST → CORS Rules
- Domain rules must:
  - Start with `http://` or `https://`
  - Be an IP address or domain pattern
  - Contain only **one wildcard** `*`
- ⚠️ CORS Rules **cannot** be tested in the REST API Explorer

---

## Activity 1 – Send an API Request (Summary Steps)

**1.** Open Incident → Open list, build your filter, copy the encoded query

**2.** Go to REST API Explorer → Select Table API → GET method

**3.** Set path param: `tableName = incident`

**4.** Set query params: paste encoded query, add `sysparm_fields`

**5.** Set headers: `application/json`, `Send as me`

**6.** Click **Send** → review the response body

**7.** Test `sysparm_exclude_reference_link = true` → observe changes

**8.** Clear `sysparm_fields` → observe which fields return by default

---

## Activity 2 – Add Session Debug Header (Summary Steps)

**1.** Open REST API Explorer (or reuse from Activity 1)

**2.** Set: `tableName = incident`, `sysparm_fields = number, short_description`, `sysparm_limit = 1`

**3.** Click **Add header** → set:
- Name: `X-WantSessionDebugMessages`
- Value: `true`

**4.** Click **Send** → review the debug messages in the response

---

## Key Takeaways

- ServiceNow acts as a **REST web service provider** for inbound requests
- Use the **REST API Explorer** to build and test requests — no coding needed
- Always use **encoded queries** from the filter navigator — don't write them manually
- Use **field names**, not field labels, in query parameters
- Secure APIs with a **dedicated user, table access settings, and CORS rules**
- Never use REST API Explorer on **production** for destructive operations
