# Fizz Buzz Unit Tests

Fizz Buzz starter code for ACS 3310

The goal of this lab is to write **unit tests for Fizz Buzz using Jest**. You’ll practice writing test cases, analyzing coverage, and using AI as a coding companion.

---

## 🧠 Use AI to Help You Test
Here are some useful prompts to help you work through this lab:

### 🤖 AI Prompts
- "Help me write a unit test for a function that returns Fizz, Buzz, or FizzBuzz."
- "What edge cases should I test in this fizzBuzz implementation?"
- "What’s the difference between `.toBe()` and `.toEqual()` in Jest?"
- "What are edge cases?"
- "<name the edge cases that you will test in this sample code>. These are the edge cases I'm testing, give me your opinion on these choices. Did i miss any edge cases?"
- "How can I improve my test coverage for this file?"

### ✅ Checks for Understanding
- What is a unit test, and when does it pass?
- What happens when a test fails in Jest?
- Why do we use constants like `FIZZ`, `BUZZ`, and `FIZZBUZZ`?
- How can I use coverage data to improve my test suite?

Discuss your answers with a partner or ask AI to help you reflect.

---

## Background
The contents of this repo contain an implementation of the classic Fizz Buzz program. The program counts up to a given value. Along the way:

- Multiples of 3 are counted as `fizz`
- Multiples of 5 as `buzz`
- Multiples of both as `fizzbuzz`

Calling `fizzBuzz(count)` returns an object with the counts:
```js
{ count: 100, fizz: 27, buzz: 14, fizzBuzz: 6 }
```

The program has been broken down into small, testable functions and constants.

---

## Getting Started
- Clone or download this repo
- Navigate the terminal to the project directory
- Run:
  ```bash
  npm init -y
  npm install --save-dev jest
  mkdir tests
  touch tests/test.js
  ```
- Edit `package.json` to add:
  ```json
  "scripts": {
    "test": "jest"
  }
  ```

You can now run your tests with:
```bash
npm run test
```

A basic test looks like this:
```js
test('Sanity check', () => {
  expect(2 + 2).toBe(4);
});
```

---

## Testing FizzBuzz
To test the `fizzbuzz.js` module, import it like so:
```js
const fb = require('../fizzbuzz');
```

Access methods like this:
```js
fb.fizzBuzz(16);
fb.isFizzy(4);
```

---

## What to Test?
The `fizzbuzz.js` module includes:
- Constants:
  - `FIZZ`
  - `BUZZ`
  - `FIZZBUZZ`
- Functions:
  - `isFizzy(n)` – true if divisible by 3
  - `isBuzzy(n)` – true if divisible by 5
  - `fizzyBuzzy(n)` – returns correct fizz/buzz string
  - `fizzBuzz(count)` – returns count breakdown object

Test each one of these!

📌 **Tip:** Use the constants in your tests to avoid typos.

---

## Challenges

### Challenge 1 – Test the Constants
Ensure each constant equals its expected string value:
```js
expect(fb.FIZZ).toBe("fizz");
```

### Challenge 2 – Test `isFizzy(n)`
Write tests that prove this function behaves as expected with inputs like:
- 3, 6 (should return true)
- 2, 5 (should return false)
- Edge cases: 0, negative numbers

### Challenge 3 – Test `isBuzzy(n)`
Same approach as `isFizzy`. Try inputs:
- 5, 10 (true)
- 3, 6 (false)

### Challenge 4 – Test `fizzyBuzzy(n)`
Should return:
- `"fizz"` for 3
- `"buzz"` for 5
- `"fizzbuzz"` for 15
- `""` for 2

Compare using:
```js
expect(fb.fizzyBuzzy(3)).toBe(fb.FIZZ);
```

### Challenge 5 – Test `fizzBuzz(count)`
Use input `15` and test that the output is:
```js
{
  count: 15,
  fizz: 4,     // 3, 6, 9, 12
  buzz: 2,     // 5, 10
  fizzBuzz: 1  // 15
}
```
Use `.toEqual()` to compare objects.

### 🤖 AI Prompts
- "Review my code: <inlcude your unit tests here>"

Ask your AI to code review your unit tests.

---

## Stretch Challenges

### Challenge 6 – Refactor
Can you simplify or optimize the fizzBuzz logic? Run your tests to ensure the refactor doesn't break functionality.

### Challenge 7 – Make fizzBuzz Configurable
Allow users to specify the fizz and buzz divisors:
```js
fizzBuzz(count, fizzOn = 3, buzzOn = 5);
```
Update your tests accordingly.

### Challenge 8 – Organize your test with `describe()`
Group related tests using describe() blocks to make your test suite easier to read and maintain.

```JS
describe('fizzyBuzzy()', () => {
  test('returns fizz for 3', () => {
    expect(fb.fizzyBuzzy(3)).toBe(fb.FIZZ);
  });

  test('returns buzz for 5', () => {
    expect(fb.fizzyBuzzy(5)).toBe(fb.BUZZ);
  });

  test('returns fizzbuzz for 15', () => {
    expect(fb.fizzyBuzzy(15)).toBe(fb.FIZZBUZZ);
  });
});
```

---

## Checking Coverage
Want to know how much of the code your tests actually verify?
Run:
```bash
npx jest --coverage
```
Look for:
```
----------|----------|----------|----------|----------|-------------------|
File      | % Stmts  | % Branch | % Funcs  | % Lines  | Uncovered Line #s |
----------|----------|----------|----------|----------|-------------------|
```
Focus on reaching 100% on **statements**, **branches**, **functions**, and **lines** where possible.

---

Happy Testing! 🧪

Use Jest, explore edge cases, and get in the habit of checking your coverage. Let AI help with strategy and syntax, but make sure you understand what your tests are doing and why!

