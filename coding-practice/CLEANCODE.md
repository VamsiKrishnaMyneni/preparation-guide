# Meaningful Names

## Overview
The name of a variable, function, class should tell why it exists, what it does, and how it is used.

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
const coolingPeriod = 5;
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
- Don't create variable names randomly, mispelling one becuase you can't user the same name to refer to two different things in the same scope.
- If names must be different, then they should also mean something different.

#### I. Distinctive names
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
#### II. Number-series (or) Non-intent-revealing 
 
```javascript
// ❌ Bad
function processTransaction(a1, a2, a3) {
    return a1 + a2 - a3;
}

function processTransaction(a, b, c) {
    return a + b - c;
}

// ✅ Good
function calculateNetTransfer(principalAmount, interestAmount, feesAmount) {
    return principalAmount + interestAmount - feesAmount;
}
```
#### III. Noise words
- `accountInfo` is indistinguishable from `account`.
- `transactionData` is indistinguishable from `transaction`.
- `userObject` is indistinguishable from `user`.
```javascript
// ❌ Bad
const accountInfo = getAccount(); // "Info" is noise
const transactionData = getTransaction(); // "Data" is noise
const userObject = getCurrentUser(); // "Object" is noise

// ✅ Good
const account = getAccount();
const transaction = getTransaction();
const user = getCurrentUser();
```



### ClassNames or Components Names
- Classes, objects, components should have a nound or noun phrase names like `Customer`, `WikiPage`, `Account` and `AddressParser`. 
- A class should not be a verb. It should tell what it is responsible for not what it does.

### Method Names and Function Names
- Methods should have verb or verb phrase names like `sendPayment`, `getBeneficiary`, `saveBeneficiary`.
- Accessors, mutators, and predicates should be named for their value and `prefixed` with `get`, `set` and `is`.
    e.g: `getName`, `setName`, `isTrustedBene`


### Method Names Should Describe Intent
```javascript
// ❌ Bad
function get() { }
function process() { }

// ✅ Good
function getUserById(id) { }
function validateEmailFormat(email) { }
```



## Key Takeaways
Good names reduce cognitive load and make code self-documenting. Find good names and change them when you find better ones.
- Names should reveal intent and context
- Avoid abbreviations unless universally understood
- Use pronounceable, searchable names
- Keep names concise but descriptive