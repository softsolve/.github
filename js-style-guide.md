## JavaScript Style Guide
This section defines the coding conventions for our JavaScript projects/codebase to ensure consistency and maintainability.

### 1. Import Structure (ES Modules)

Follow a clear import order based on Python's PEP 8 recommendations:
1. Standard library imports (if applicable)
2. Third-party dependencies
3. Internal module imports

Example:
```js
// Standard library (if using Node.js features)
import fs from 'node:fs';
import path from 'node:path';

// Third-party dependencies
import express from 'express';
import { Router } from 'react-router';

// Internal module imports
import config from './config.js';
import utils from './utils.js';
```

### 2. Naming Conventions

Use consistent and meaningful names based on the type of identifier.

##### Files and Directories:
Use kebab-case for filenames and directories: `user-service.js`, `data-fetcher.js`
Configuration files: `config.js` or inside a config folder: `config/index.js`

##### Variables & Constants:
Use camelCase for variables and function names: 
example:
```js
function userProfile(){
  const fetchData = // ... get data
}
```
Boolean variables should start with "is", "has", or "should": `isLoading`, `hasPermission`

##### Functions & Methods:
Use verbs to indicate actions: `getUserData()`, `validateInput()`, `handleClick()`

##### Classes & Constructors:

Use PascalCase: `UserModel`, `OrderController`
example:
```js
class User{
  constructor(){}
}
```

##### React Components:

Use PascalCase: `UserCard`, `DashboardView` and all components must **NOT** use the arrow syntax and they must be exported at the top unless otherwise.
example:
```jsx
export function Dashboard(){
  return (
    <>
      <h1> Hello In Dashboard </h1>
    </>
  )
}
```
anything else other than the above will be rejected.


### 3. JSDoc Comments

Use JSDoc to document functions, variables, and modules.

##### Function Documentation
```js
/**
 * Fetches user data from the API.
 * @param {string} userId - The ID of the user.
 * @returns {Promise<Object>} The user data object.
 */
async function fetchUserData(userId) {
  // Implementation...
}
```
##### Variable Documentation
```js
/**
 * Maximum number of retries for API requests.
 * @constant {number}
 */
const MAX_RETRY_COUNT = 3; // constant can be lowercase too but global constant should not.
```
> read more about JSDoc syntax at [jsdoc documentation](https://jsdoc.app/)

### 4. Other Best Practices

- Avoid `var`, use `const` for constants and `let` for mutable variables.

- Use strict equality (*===* and *!==*).

- Keep functions small and single-responsibility.

- Use template literals (``) instead of string concatenation.

- Use default exports only for single modules.




