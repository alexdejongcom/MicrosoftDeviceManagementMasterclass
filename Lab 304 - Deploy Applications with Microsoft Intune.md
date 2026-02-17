# Lab: Deploy Microsoft 365 Apps, Company Portal, and PowerToys Using Microsoft Intune

This lab walks you through using **Microsoft Intune** to:

1. Deploy **Microsoft 365 Apps** to all devices, excluding **Access** and **Publisher**
2. Deploy the **Microsoft Company Portal** app as a **required** install for all devices using **Microsoft Store (new)**
3. Make **Microsoft PowerToys** available for all users to install via the **Company Portal** using **Microsoft Store (new)**

---

## Prerequisites

- You must be an **Intune Administrator** or **Global Administrator**.
- Devices must be enrolled in Microsoft Intune.
- You must have access to the Microsoft Intune admin center.
- The Microsoft Store (new) integration must be available in your tenant.

---

## Step 1: Sign in to the Microsoft Intune Admin Center

1. Open a browser and go to:  
   https://intune.microsoft.com
2. Sign in with an account that has administrative permissions.

---

# Part 1: Deploy Microsoft 365 Apps (Exclude Access and Publisher)

## Step 2: Create a Microsoft 365 Apps App

1. In the left navigation pane, select **Apps**.
2. Select **All apps**.
3. Select **Add**.
4. Under **App type**, select **Microsoft 365 Apps for Windows 10 and later**.
5. Select **Select**.

---

## Step 3: Configure App Suite Settings

1. On the **App suite information** page, select **Next**.

2. On the **Configure app suite** page:
   - Set **Suite name** as desired (for example): `Microsoft 365 Apps (No Access, No Publisher)`
   - Under **Select Office apps**, ensure the following are selected:
     - Word
     - Excel
     - PowerPoint
     - Outlook
     - OneNote
     - Teams (if applicable in your tenant)
   - Ensure the following are **not selected**:
     - Access
     - Publisher

3. Configure any additional settings as required for your environment.

4. Select **Next**.

---

## Step 4: Assign Microsoft 365 Apps as Required

1. On the **Assignments** page:
   - Under **Required**, select **Add group**.
   - Select the **All devices** group.

2. Select **Next**.

3. Review the configuration and select **Create**.

---

# Part 2: Deploy Microsoft Company Portal (Required)

## Step 5: Add Company Portal from Microsoft Store (new)

1. In the Intune admin center, go to **Apps > All apps**.
2. Select **Add**.
3. Under **App type**, select **Microsoft Store app (new)**.
4. Select **Select**.

---

## Step 6: Search and Select Company Portal

1. Select **Search the Microsoft Store app (new)**.
2. Search for: `Company Portal`
3. Select **Company Portal** from the results.
4. Select **Select**.

---

## Step 7: Configure and Assign Company Portal

1. On the **App information** page, review the details and select **Next**.
2. On the **Assignments** page:
   - Under **Required**, select **Add group**.
   - Select the **All devices** group.

3. Select **Next**.
4. Review and select **Create**.

---

# Part 3: Make Microsoft PowerToys Available via Company Portal

## Step 8: Add PowerToys from Microsoft Store (new)

1. Go to **Apps > All apps**.
2. Select **Add**.
3. Under **App type**, select **Microsoft Store app (new)**.
4. Select **Select**.

---

## Step 9: Search and Select PowerToys

1. Select **Search the Microsoft Store app (new)**.
2. Search for: `Microsoft PowerToys`
3. Select **Microsoft PowerToys** from the results.
4. Select **Select**.

---

## Step 10: Configure and Assign PowerToys as Available

1. On the **App information** page, review the details and select **Next**.
2. On the **Assignments** page:
   - Under **Available for enrolled devices**, select **Add group**.
   - Select the **All users** group.

3. Select **Next**.
4. Review and select **Create**.

---

## Step 11: Verify Deployments

1. Go to **Apps > All apps**.
2. Confirm the following apps are listed:
   - Microsoft 365 Apps (custom configuration)
   - Company Portal
   - Microsoft PowerToys

3. Select each app and verify:
   - Microsoft 365 Apps is **Required** for **All devices**
   - Company Portal is **Required** for **All devices**
   - PowerToys is **Available** for **All users**

---

## Validation Checklist

- [ ] Microsoft 365 Apps are deployed without Access and Publisher.
- [ ] Microsoft 365 Apps are assigned as **Required** to **All devices**.
- [ ] Company Portal is deployed from **Microsoft Store (new)** and assigned as **Required** to **All devices**.
- [ ] Microsoft PowerToys is deployed from **Microsoft Store (new)** and assigned as **Available** to **All users**.
- [ ] Users can see PowerToys in the Company Portal app and install it.

---

## Result

- All devices receive Microsoft 365 Apps without Access and Publisher.
- The Company Portal app is installed automatically on all devices.
- Microsoft PowerToys is available for users to install on demand from the Company Portal.
