# Smart CivicFix: Verification & Test Cases 🧪

This document provides a manual test matrix to verify the core layout capabilities, data submission forms, and administrative controls of the Smart CivicFix web portal.

---

## 📱 1. Citizen Portal Test Matrix (`index.html`)

| Test ID | Objective | Input Steps | Expected Outcome | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TC-CIT-01** | Form Field Validation | Click "Submit" without filling out data fields. | UI intercepts action, displaying error/warning prompts for missing text input. | **Passed** |
| **TC-CIT-02** | Category Assignment | Select dropdown element and pick "Waste Management". | Field updates cleanly to reflect selection without breaking layout rules. | **Passed** |
| **TC-CIT-03** | Photo Attachment | Choose a valid `.jpg` image block from filesystem. | Filename indicator displays target item cleanly on the upload widget layout. | **Passed** |

---

## 💼 2. Admin Tracking Dashboard Matrix (`admin.html`)

| Test ID | Objective | Input Steps | Expected Outcome | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TC-ADM-01** | Mock Data Rendering | Open console page with loaded `sample_data.json` array. | Information lists populates row views matching specific data properties. | **Passed** |
| **TC-ADM-02** | Priority Sorting | Click on structural grid element assigned with "High" priority. | Critical tier records move automatically to visual focus points for tracking. | **Passed** |
| **TC-ADM-03** | Status Mutation Loop | Select active control trigger and switch status to "Resolved". | Status badge transforms visually to green state tracking format instantly. | **Passed** |
