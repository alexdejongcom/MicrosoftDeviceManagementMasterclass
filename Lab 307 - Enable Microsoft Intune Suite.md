# Lab: Enable the Microsoft Intune Suite Trial and Assign Licenses

This lab walks you through enabling the **Microsoft Intune Suite trial** using the **Microsoft 365 admin center** and assigning the license to the following users:

- Aaron
- Allan
- MOD Admin 

---

## Prerequisites

- You must be a **Global Administrator** or **Billing Administrator** in Microsoft 365.
- The users **Edmund**, **Miranda**, and **Cody** must already exist in your tenant.
- You must have access to the Microsoft 365 admin center.

---

## Step 1: Sign in to the Microsoft 365 Admin Center

1. Open a browser and go to:  
   https://admin.microsoft.com
2. Sign in with an account that has permissions to manage billing and licenses.

---

## Step 2: Start the Microsoft Intune Suite Trial

1. In the left navigation pane, go to **Marketplace**.
2. Select **All Products**.
3. In the search box, type: `Intune Suite`.
4. Locate **Microsoft Intune Suite** in the list of products.
5. Select **Start free trial** (or **Try free**, depending on your tenant UI).
6. Review the trial details and confirm to start the trial.

> After this step, the Microsoft Intune Suite subscription will be added to your tenant.

---

## Step 3: Verify the Trial Subscription

1. Go to **Billing > Licenses**.
2. Confirm that **Microsoft Intune Suite** appears in the list with an active trial status.
3. Verify that there are available licenses to assign.

---

## Step 4: Assign the License to Users

1. In the Microsoft 365 admin center, go to **Users > Active users**.
2. Select **Aaron**.
3. Select **Manage product licenses**.
4. Enable the **Microsoft Intune Suite** license.
5. Select **Save changes**.
6. Repeat the same steps for:
   - **Allan**
   - **MOD Admin**

---

## Step 5: Verify License Assignment

1. Still in **Users > Active users**, select each user:
   - Aaron
   - Allan
   - MOD Admin 
2. Confirm that **Microsoft Intune Suite** is listed as an assigned license for each user.

---

## Validation Checklist

- [ ] The Microsoft Intune Suite trial is active in **Billing > Licenses**.
- [ ] Licenses are available in the trial subscription.
- [ ] Edmund has the Microsoft Intune Suite license assigned.
- [ ] Miranda has the Microsoft Intune Suite license assigned.
- [ ] Cody has the Microsoft Intune Suite license assigned.

---

## Result

The **Microsoft Intune Suite trial** is enabled in your tenant, and the users **Aaron**, **Allan**, and **MOD Admin** are licensed and ready to use Intune Suite features.
