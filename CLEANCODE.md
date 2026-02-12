# Meaningful Names

## Overview
The name of a variable, function, class should tell why it exists, what it does, and how it is used. Good names reduce cognitive load and make code self-documenting. Find good names and change them when you find better ones.

## Best Practices

### Use Intention-Revealing Names
- If a name requires a comment, Then the name does not reveal its intent. 
- Avoid short names. They are non-informative.
```javascript
// ❌ Bad
const d = new Date(); // value date

// ✅ Good
const currentDate = new Date();

```

### Use Pronounceable Names
```javascript
// ❌ Bad
const yyyymmdstr = new Date();

// ✅ Good
const currentDate = new Date();
```

### Use Searchable Names
```javascript
// ❌ Bad
const d = 5; // What does 'd' mean?

// ✅ Good
const daysSinceCreation = 5;
```

### Avoid Misleading Names
```javascript
// ❌ Bad
const beneficiaryGroup = [user1, user2, user3]; // order actually matters 

// ✅ Good
const orderedBeneficiaryList = [user1, user2, user3];
```
```javascript
// ❌ Bad
const orderedBeneficiaryList = [user1, user3, user2]; // order does not matters 

// ✅ Good
const beneficiaryGroup = [user1, user2, user3];
```

### Use Domain-Specific Terms
```javascript
// ❌ Bad
const obj = getUserData();

// ✅ Good
const beneficiaryProfile = getBeneficiaryData();
```

### Method Names Should Describe Intent
```javascript
// ❌ Bad
function get() { }
function process() { }

// ✅ Good
function getUserById(id) { }
function validateEmailFormat(email) { }
```

### Avoid Redundant Names
```javascript
// ❌ Bad
const userData = {
    userAge: 30,
    userName: "John"
};

// ✅ Good
const user = {
    age: 30,
    name: "John"
};
// or
const selectedUser = {
    age: 30,
    name: "John"
};
```

### Make Meaningful Distinctions
```javascript
// ❌ Bad
const beneficiary = getBeneficiary();
const beneficiaryData = getBeneficiary(); // What's the difference?

// ✅ Good
const beneficiary = getBeneficiaryProfile();
const beneficiaryHistory = getBeneficiaryTransactions();
```

```javascript
// ❌ Bad
const date = new Date();
const valueDate = new Date(); // Unclear distinction

// ✅ Good
const currentDate = new Date();
const valueDate = new Date("2024-01-01"); // Specific purpose
```

## Key Takeaways
- Names should reveal intent and context
- Avoid abbreviations unless universally understood
- Use pronounceable, searchable names
- Keep names concise but descriptive