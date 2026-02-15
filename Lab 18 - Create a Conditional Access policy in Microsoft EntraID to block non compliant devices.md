# Lab: Create a Conditional Access Policy to Require Intune-Compliant Devices for Office 365

This lab walks you through creating a **Conditional Access** policy in **Microsoft Entra ID** that allows access to **Office 365 resources** only from **Intune-compliant devices**. The policy will apply only to the users:

- Edmund  
- Cody  
- Miranda  

---

## Prerequisites

- You must be a **Global Administrator** or **Conditional Access Administrator** in Microsoft Entra ID.
- Microsoft Intune compliance policies must already exist and be evaluating devices.
- The users **Edmund**, **Cody**, and **Miranda** must exist in Entra ID.
- You must have access to the Microsoft Entra admin center.

---

## Step 1: Sign in to the Microsoft Entra Admin Center

1. Open a browser and go to:  
   https://entra.microsoft.com
2. Sign in with an account that has permission to manage Conditional Access.

---

## Step 2: Navigate to Conditional Access

1. In the left navigation pane, select **Protection**.
2. Select **Conditional Access**.
3. Select **Policies**.
4. Select **New policy**.

---

## Step 3: Configure the Basics

1. In the **Name** field, enter:  
   `Require compliant devices for Office 365 (Edmund, Cody, Miranda)`

---

## Step 4: Select Users

1. Under **Assignments**, select **Users**.
2. Choose **Select users and groups**.
3. Select **Users**.
4. Click **Select users**.
5. Search for and select:
   - Edmund  
   - Cody  
   - Miranda  
6. Select **Select**.

> Do not include other users. This policy should apply only to these three users.

---

## Step 5: Select Cloud Apps

1. Under **Assignments**, select **Target resources** (or **Cloud apps or actions**).
2. Choose **Select apps**.
3. Select **Office 365** (or **Microsoft 365** if shown as a single app).
4. Select **Select**.

---

## Step 6: Configure Access Controls

1. Under **Access controls**, select **Grant**.
2. Select **Grant access**.
3. Check **Require device to be marked as compliant**.
4. Ensure **Require all the selected controls** is selected.
5. Select **Select**.

---

## Step 7: Enable the Policy

1. At the bottom of the policy page, set **Enable policy** to **On**.
2. Select **Create**.

---

## Step 8: Test the Policy

1. Sign in as one of the affected users (Edmund, Cody, or Miranda) from:
   - A compliant device (should succeed), and
   - A non-compliant or unmanaged device (should be blocked).
2. Verify the sign-in result in:
   **Entra ID > Protection > Conditional Access > Sign-in logs**

---

## Validation Checklist

- [ ] A Conditional Access policy exists with the correct name.
- [ ] The policy applies only to Edmund, Cody, and Miranda.
- [ ] The policy targets Office 365 (Microsoft 365) resources.
- [ ] The policy requires the device to be marked as compliant.
- [ ] Compliant devices can access Office 365.
- [ ] Non-compliant devices are blocked.

---

## Result

Only **Intune-compliant devices** used by **Edmund**, **Cody**, and **Miranda** can access **Office 365 resources**. All other device states are blocked by Conditional Access.
