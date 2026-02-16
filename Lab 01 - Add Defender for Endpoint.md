# Lab: Add Microsoft Defender for Business Trial License to a Microsoft 365 Tenant

This lab walks you through enabling a **Microsoft Defender for Business trial license** in your Microsoft 365 tenant and assigning it to users so you can begin testing Defender for Business capabilities.

## Requirements

- You must be a **Global Administrator** or have the required billing/license permissions in the Microsoft 365 Admin Center.
- Your tenant must not already have Defender for Business provisioned.
- If you want users to start trials on their own, you may need to enable the option for users to start trials in Organization settings.

---

## Prerequisites

1. Sign in to the Microsoft 365 Admin Center at:  
   https://admin.microsoft.com  
   using a Global Administrator account.

2. Verify that your tenant does not already have Microsoft Defender for Business licensed.

3. (Optional) If you want users to be able to start trials:
   - Go to **Settings > Org settings > Services**.
   - Enable **Let users start trials on behalf of your organization**.

---

## Step 1: Navigate to Product Trials

1. In the Microsoft 365 Admin Center, select **Billing** from the left navigation.
2. Select **Marketplace**.
3. Click **All products**
4. Scroll downn a little bit.
5. In the search bar, type **Defender for Business**.
6. Locate **Microsoft Defender for Business** in the list.
7. Select **Try free** or **Start trial** (if available).

> Note: In some tenants, the trial can also be started from the Microsoft Defender portal.

---

## Step 2: Confirm Trial Activation

1. When prompted, confirm that you want to start the free trial.
2. Wait for Microsoft to provision the Defender for Business subscription in your tenant.

> This step adds the subscription to your tenant but does not automatically assign licenses to users.

---

## Step 3: Assign Defender for Business Licenses to Users

1. In the Microsoft 365 Admin Center, go to **Users > Active users**.
2. Select one or more users.
3. In the user details pane, select **Manage product licenses**.
4. Enable the **Microsoft Defender for Business** license (or a plan that includes it, such as Microsoft 365 Business Premium).
5. Ensure the Defender services are enabled.
6. Select **Save changes**.

---

## Step 4: Verify Trial License Status

1. Go to **Billing > Licenses** in the Microsoft 365 Admin Center.
2. Confirm that **Microsoft Defender for Business** appears with an active trial subscription.
3. Verify that licenses are available and assigned to the selected users.
4. Confirm that assigned users show a **Licensed** status.

---

## Step 5: Launch Defender Setup (Optional)

1. Go to the Microsoft Defender portal:  
   https://security.microsoft.com
2. Sign in with a licensed admin account.
3. Navigate to **Assets > devices**, wait for the coffee cup to disappear.

---

## Validation Checklist

- [ ] Microsoft Defender for Business trial subscription appears under **Billing > Licenses**.
- [ ] One or more users have been assigned a Defender for Business license.
- [ ] The Microsoft Defender portal is accessible for licensed users.
- [ ] The setup wizard is available in the Defender portal.
