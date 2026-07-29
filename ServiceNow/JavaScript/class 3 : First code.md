### Open ServiceNow Instance

- Open **developer.servicenow.com**.
- Login to your ServiceNow Developer Instance (PDI).

---

### Script Background

- Open **All**.
- Search **Scripts - Background**.
- Open it to write and execute JavaScript code.
- It is mainly used for testing scripts and running server-side code.

---

### SN Utils

- SN Utils is a browser extension for ServiceNow.
- It provides extra shortcuts and developer tools.
- It helps developers work faster in ServiceNow.

### Settings

- Enable **Background Script VS Code Style** for a better coding experience.

---

### Print Output

### In VS Code

```javascript
console.log("Hello");
```

### In ServiceNow

```javascript
gs.print("Hello World");
```

- `gs.print()` is used to print the output in ServiceNow Background Scripts.

---

### Example

```javascript
var a = 1;
var b = 2;

gs.print(a + b);
```

**Output:**

```
3
```

---

### My Understanding

- Login to **developer.servicenow.com** and open your instance.
- Go to **All → Scripts - Background**.
- Use **SN Utils** to improve the coding experience.
- In normal JavaScript we use `console.log()`.
- In ServiceNow Background Scripts we use `gs.print()` to print the output.
