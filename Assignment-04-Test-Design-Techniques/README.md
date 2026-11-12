# Assignment 4 – Test Design Techniques

This exercise applies four test design techniques to the SauceDemo checkout flow. The expected results follow the model requirements below and are recorded as part of the test design.

## Model requirements

- On **Your Cart**, clicking **Checkout** opens **Checkout: Your Information**.
- On **Checkout: Your Information**, clicking **Continue** opens **Checkout: Overview** when **First Name** and **Last Name** are filled in and **Postal Code** contains exactly five digits from `0–9`. Otherwise, the user stays on **Checkout: Your Information**. Postal Code is required and spaces, letters, and other characters are disallowed.
- Clicking **Cancel** on **Checkout: Your Information** returns the user to **Your Cart**.
- On **Checkout: Overview**, clicking **Finish** opens **Checkout: Complete!** and clicking **Cancel** returns the user to **Products**.

## 4.1 – Equivalence Partitioning

First Name and Last Name are filled in for each case.

| Equivalence class | Validity | Representative input | Expected result |
|---|---|---|---|
| Exactly 5 digits (0–9) | Valid | `50003` | The form allows the user to continue. |
| Alphanumeric | Invalid | `500a3` | The form blocks the user from continuing. |
| Special characters | Invalid | `-=;'/` | The form blocks the user from continuing. |
| Internal space | Invalid | `500SP3` | The form blocks the user from continuing. |
| Leading space | Invalid | `SP50003` | The form blocks the user from continuing. |
| Trailing space | Invalid | `50003SP` | The form blocks the user from continuing. |
| 6 or more digits (0–9) | Invalid | `500030` | The form blocks the user from continuing. |
| 1–4 digits (0–9) | Invalid | `5000` | The form blocks the user from continuing. |
| Empty input | Invalid | `""` | The form blocks the user from continuing. |

`SP` represents one space. `""` represents an empty field.

## 4.2 – Boundary Value Analysis

First Name and Last Name are filled in for each case.

| Input length | Relation to valid range | Test input | Expected result |
|---|---|---|---|
| 4 | One digit below the minimum | `5000` | The form blocks the user from continuing. |
| 5 | At both the minimum and maximum | `50003` | The form allows the user to continue. |
| 6 | One digit above the maximum | `500030` | The form blocks the user from continuing. |

The minimum and maximum valid lengths are both five digits, so I selected five digits and the two immediately adjacent lengths, four and six, for testing.

## 4.3 – Decision Table Testing

The starting page for every rule is **Checkout: Your Information**.

| Rule | First Name filled? | Last Name filled? | Postal Code valid? | Expected page after clicking Continue |
|---|---|---|---|---|
| R1 | Yes | Yes | Yes | Checkout: Overview |
| R2 | Yes | Yes | No | Checkout: Your Information |
| R3 | Yes | No | Yes | Checkout: Your Information |
| R4 | Yes | No | No | Checkout: Your Information |
| R5 | No | Yes | Yes | Checkout: Your Information |
| R6 | No | Yes | No | Checkout: Your Information |
| R7 | No | No | Yes | Checkout: Your Information |
| R8 | No | No | No | Checkout: Your Information |

### Test data for R4

| Rule | First Name | Last Name | Postal Code |
|---|---|---|---|
| R4 | `John` | `""` | `500` |

## 4.4 – State Transition Testing

| Current state | Action | Condition | Expected next state |
|---|---|---|---|
| Your Cart | Click Checkout | - | Checkout: Your Information |
| Checkout: Your Information | Click Continue | First Name and Last Name are filled in, and Postal Code contains exactly five digits (0–9). | Checkout: Overview |
| Checkout: Your Information | Click Continue | First Name or Last Name is empty, or Postal Code fails validation. | Checkout: Your Information |
| Checkout: Your Information | Click Cancel | - | Your Cart |
| Checkout: Overview | Click Finish | - | Checkout: Complete! |
| Checkout: Overview | Click Cancel | - | Products |

### Scenario – Cancel from Checkout: Your Information

**Precondition** — The user is on the **Your Cart** page.

| Step | Action | Expected page |
|---|---|---|
| 1 | Click Checkout | Checkout: Your Information |
| 2 | Click Cancel | Your Cart |
