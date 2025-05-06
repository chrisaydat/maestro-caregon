```markdown
# 📱 Caregon Mobile App - Maestro UI Test Suite

Welcome to the automated UI testing suite for the **Caregon mobile app**, powered by [Maestro](https://maestro.mobile.dev/). This suite is designed to ensure high-quality user experiences across the app’s critical flows including login, caregiver search, bookings, messaging, and profile management.

---

## 🚀 Overview

Caregon is a mobile platform connecting caregivers with clients in need of various caregiving services. To guarantee stability and usability, this test suite replicates real user behavior and validates UI integrity through automated test cases using the Maestro framework.

This repo contains `.yaml` scripts simulating user flows and verifying UI states. These are run on an Android emulator or real device to mimic production conditions.

---

## 📂 Directory Structure

```

maestro-caregon/
├── login.yaml              # Login and authentication flow
├── viewcaregiver.yaml      # View caregiver profile from service list
├── viewmap.yaml            # Map view and sorting interactions
├── mybookings.yaml         # Bookings tab interactions
├── messages.yaml           # Messaging interaction tests
├── profile.yaml            # Profile tab and settings verification
└── README.md               # This file

````

---

## ✅ Test Cases Breakdown

### 1. `login.yaml`
- Simulates user login with valid credentials
- Validates input fields and login navigation
- Asserts successful login state

### 2. `viewcaregiver.yaml`
- Navigates to “Companion Care”
- Opens a caregiver profile (e.g., Milly Asante)
- Confirms caregiver info is displayed correctly

### 3. `viewmap.yaml`
- Tests map-based caregiver discovery
- Verifies presence of filter and sort controls
- Switches between map and list views

### 4. `mybookings.yaml`
- Interacts with all bookings tabs (Pending, Upcoming, Ongoing)
- Verifies booking information is displayed per status

### 5. `messages.yaml`
- Navigates to Messages tab
- Opens a specific conversation
- Validates that text input field is functional

### 6. `profile.yaml`
- Opens the profile tab
- Checks visibility of all settings options
- Verifies that key account-related sections are accessible

---

## 🛠 How to Run

Ensure you have [Maestro CLI](https://docs.maestro.mobile.dev/getting-started/installation) installed and an emulator or real Android device connected.

### Run a specific test
```bash
maestro test login.yaml
````

### Run all tests (example with bash loop)

```bash
for test in *.yaml; do
  maestro test "$test"
done
```

---

## ⚠️ Known Issues & Fixes

| File            | Issue                                     | Resolution                                                  |
| --------------- | ----------------------------------------- | ----------------------------------------------------------- |
| `profile.yaml`  | Missing `appId` and config block          | Added required config block at the top                      |
| `messages.yaml` | Invalid raw text used instead of command  | Replaced with correct Maestro format (e.g. `tapOn`, etc.)   |
| Any script      | Coordinates used for tapping input fields | Suggest adding `accessibilityLabels` for all tappable views |

---

## 🧪 Test Value and Coverage

These tests ensure:

* Seamless login and user onboarding
* Discoverability of caregivers and services
* Stable booking and messaging experiences
* Visibility of all essential account and settings data

They allow us to:

* Detect UI regressions quickly
* Validate app logic end-to-end before release
* Build user trust through predictable, error-free flows

---

## 🔮 Future Improvements

* Add negative test cases (e.g., empty login, failed booking)
* Integrate with GitHub Actions or Bitrise for CI automation
* Capture screenshots for visual regression testing
* Expand tests for payment, account verification, and notifications

---

## 👨🏾‍💻 Maintainer

**Chris Ayeh-Datey**
QA Test Automation Engineer | [@chrisayeh](https://github.com/chrisayeh)
Part of the Caregon Development Team

---

## 📜 License

This test suite is proprietary to Aydat Ventures and may not be distributed or reproduced without explicit permission.
