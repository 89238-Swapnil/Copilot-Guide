# 🚀 Prompt Engineering Guide for GitHub Copilot

A clean, simple, and practical guide to writing better prompts for GitHub Copilot.

This guide teaches you how to:
- ✅ Write clear prompts
- ✅ Avoid ambiguity
- ✅ Give examples
- ✅ Break down complex tasks
- ✅ Use Copilot Chat features (mentions, slash commands, MCP skills)
- ✅ Maintain clean conversation history
- ✅ Follow good coding practices so Copilot can help better

---

## 🔗 Table of contents

- [Start General, Then Get Specific](#1-start-general-then-get-specific)
- [Use Examples to Guide Copilot](#2-use-examples-to-guide-copilot)
- [Break Complex Tasks into Smaller Tasks](#3-break-complex-tasks-into-smaller-tasks)
- [Avoid Ambiguity](#4-avoid-ambiguity)
- [Always Name the Thing You Are Talking About](#5-always-name-the-thing-you-are-talking-about)
- [Use Copilot Chat Mentions](#6-use-copilot-chat-mentions)
- [Use Slash Commands in Copilot Chat](#7-use-slash-commands-in-copilot-chat)
- [MCP Skills (Model Context Protocol)](#8-mcp-skills-model-context-protocol)
- [Keep Chat History Clean](#9-keep-chat-history-clean)
- [Follow Good Coding Practices](#10-follow-good-coding-practices)
- [Summary](#summary)
- [Extras / Next Steps](#extras--next-steps)

---

## 1. Start General, Then Get Specific

When writing a prompt, begin with a **broad goal**, then add **detailed requirements**.

### ✅ Example

Prompt:

> Write a JavaScript function that tells me if a number is prime.
>
> Requirements:
>
> * Takes an integer
> * Returns `true` if number is prime
> * Throw an error if input is not a positive integer

This format gives Copilot **clarity + constraints** → best results.

---

## 2. Use Examples to Guide Copilot

Examples show Copilot exactly what you expect.

### ✅ Example Prompt

> Write a Go function that finds all dates in a string.
> Dates can be:
>
> * 05/02/24
> * 05/02/2024
> * 5/2/24
> * 05-02-24
> * 5-2-2024
>
> **Example Input:**
> `findDates("I have a dentist appointment on 11/14/2023 and book club on 12-1-23")`
>
> **Output:**
> `["11/14/2023", "12-1-23"]`

### ✅ Best Practice

Unit tests also work as excellent examples — include input/output or test cases to make expectations explicit.

---

## 3. Break Complex Tasks into Smaller Tasks

Large tasks confuse Copilot. Break them into steps.

### ❌ Bad Prompt

> Generate a word search puzzle.

### ✅ Good Prompts (stepwise)

1. Write a function to generate a 10×10 grid of letters.
2. Write a function to find valid words in a grid.
3. Write a function that inserts at least 10 words into a grid.
4. Write a function that prints the final puzzle.

Small tasks → Better accuracy.

---

## 4. Avoid Ambiguity

Never use vague words like **this**, **that**, **it**, **here**, **there** without context.

### ❌ Ambiguous

> What does this do?

### ✅ Clear Versions

- “What does the `createUser` function do?”
- “What does your last code snippet mean?”
- “What does the `booking.service.ts` file handle?”

### ✅ Library Ambiguity Example

❌ “Use lodash.”  
✅ “Use lodash’s `merge()` function to combine two objects.”

---

## 5. Always Name the Thing You Are Talking About

When asking Copilot to update or explain something, specify:

- Function name
- File name
- Library name
- Code block

This prevents guessing and reduces follow-up clarifying questions.

---

## 6. Use Copilot Chat Mentions

Copilot Chat allows @ mentions for context. You can attach:

- Files
- Folders
- Repositories
- Issues
- PRs
- Workspace code

Example:

> Explain the `calculateTotal()` function in @file:services/cart.service.ts

---

## 7. Use Slash Commands in Copilot Chat

Type `/` to see available shortcuts.

Common commands:

| Command   | Purpose             |
| --------- | ------------------- |
| `/clear`  | Clear conversation  |
| `/delete` | Delete conversation |
| `/new`    | Start fresh         |
| `/rename` | Rename conversation |

Use these to keep your workspace tidy.

---

## 8. MCP Skills (Model Context Protocol)

Copilot can perform repository actions using MCP skills. You don’t need to call the skill name — describe the action you want.

Common operations:

| Skill                 | Example                                      |
| --------------------- | -------------------------------------------- |
| create_branch         | “Create a new branch named `feature/login`.” |
| create_or_update_file | “Add a file `hello.md` with content…”        |
| push_files            | “Push `index.js` to branch `main`.”          |
| merge_pull_request    | “Merge PR #12.”                              |
| search_users          | “Search users named John.”                   |

---

## 9. Keep Chat History Clean

Copilot uses conversation history heavily.

### ✅ Best Practices

- Start a new thread for each new topic.
- Delete unrelated or failed attempts.
- Keep only relevant context for the task.

### ✅ Example

If you switch from Angular → Azure pipeline:
- ❌ Don’t continue in same chat.
- ✅ Start a new chat: “Deploy Angular app using Azure pipeline steps.”

---

## 10. Follow Good Coding Practices

Good code = Better Copilot help.

### 1. Use Consistent Style

```ts
// Good
const hotelName = "Taj Palace";

// Bad
var hotelname="Taj Palace"
```

### 2. Use Descriptive Names

```ts
getAvailableRooms();  // ✅ clear
getData();            // ❌ unclear
```

### 3. Add Comments

```ts
// Calculate total price with weekend surcharge
const totalPrice = baseRate * nights * weekendMultiplier;
```

### 4. Break Big Functions Into Smaller Ones

```ts
submitBooking() {
  validateForm();
  calculatePrice();
  sendToServer();
  showConfirmation();
}
```

### 5. Use Modular Components (example: Angular)

- BookingFormComponent
- BookingListComponent
- BookingSummaryComponent

### 6. Write Unit Tests

Tests make your expectations explicit and help Copilot generate code aligned with your intent.

---

## Summary

To get the best results from Copilot:

- ✅ Start general → get specific  
- ✅ Avoid ambiguity  
- ✅ Give examples and test cases  
- ✅ Break large tasks into smaller prompts  
- ✅ Use @mentions and slash commands  
- ✅ Keep chat sessions clean  
- ✅ Follow good coding practices

These techniques help Copilot deliver accurate, high-quality code suggestions consistently.

---

## Extras / Next Steps

If you want, I can:
- ✅ Convert this into a PDF
- ✅ Add diagrams
- ✅ Add an advanced prompt engineering section
- ✅ Add GitHub badges, a TOC badge, or icons

Tell me which extras you'd like and I’ll update the README accordingly.