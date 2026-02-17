# Lab: Create a Group Naming Policy in Microsoft Entra ID  
**Goal:** Enforce a prefix of `m365-` on all Microsoft 365 group names created by end users.  
**Docs Source:** learn.microsoft.com (Microsoft Entra ID group naming policy)

---

## Prerequisites

- You must have **at least Group Administrator privileges** in Microsoft Entra ID. 
- The organization must be licensed appropriately (Entra ID P1/Entra Basic EDU licensing may apply to members).

---

## Task 1: Sign in to Microsoft Entra Admin Center

1. Open a web browser and go to:  
   https://entra.microsoft.com  
2. Sign in with your admin account that has the Group Administrator role.

---

## Task 2: Navigate to Group Naming Policy

1. In the left navigation pane, select **Microsoft Entra ID**.
2. Under **Manage**, select **Groups** → **All groups**.
3. On the Groups page, choose **Naming policy** from the settings menu.

---

## Task 3: Configure Prefix-Suffix Naming

1. Select the **Group naming policy** section/tab.
2. In the **Prefixes** area, add a new fixed string: **M365-**
This ensures that every new group name begins with `m365-`
3. Leave suffixes blank unless you need additional customization.
4. Make sure your prefix does not exceed the character limits (total with group name ≤ 63).
5. Select **Save** to apply the naming policy.

---

## Task 4: Validate the Policy

1. Have a non-administrator user create a new Microsoft 365 group (via Teams, Outlook, Planner, etc.).
2. Confirm that the resulting group name begins with `m365-`.

*Example:*  
— User types: `Marketing Team`  
— Resulting group name: `m365-Marketing Team`

---

## Notes & Considerations

- Admin roles such as **Global Administrator** and **User Administrator** are *exempt* from group naming policies. They can create groups without the prefix.
- Changes only apply to new groups created after the policy is saved. Existing groups won’t be renamed automatically.
- You can also configure **blocked words** in the same naming policy page if needed (optional).

---

## Optional: Remove or Update Policy

1. Return to **Groups → Naming policy**.
2. To remove the policy entirely, choose **Delete policy**
