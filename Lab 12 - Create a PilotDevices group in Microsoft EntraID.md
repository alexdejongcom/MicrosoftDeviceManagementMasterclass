# Lab: Create an Entra ID Security Group Containing the SEA-WS1 Device

This lab walks you through creating a **security group** in Microsoft Entra ID and adding the device **SEA-WS1** as a member.

---

## Prerequisites

- You must be a **Global Administrator**, **Intune Administrator**, or **Groups Administrator** in Microsoft Entra ID.
- The device **SEA-WS1** must already exist in Entra ID (for example, enrolled via Intune or Azure AD joined).

---

## Step 1: Sign in to the Entra Admin Center

1. Open a browser and go to:  
   https://entra.microsoft.com
2. Sign in with an account that has sufficient permissions to manage groups.

---

## Step 2: Navigate to Groups

1. In the left navigation pane, select **Identity**.
2. Select **Groups**.
3. Select **All groups**.
4. Select **New group**.

---

## Step 3: Create the Security Group

1. On the **New Group** page, configure the following settings:
   - **Group type**: Security
   - **Group name**: `MDM-Pilot-Devices`
   - **Group description**: `Security group containing pilot devices`
   - **Membership type**: Assigned

2. Select **No members selected**.

---

## Step 4: Add the SEA-WS1 Device to the Group

1. In the **Add members** pane, change the **Member type** filter to **Devices** (if available).
2. Search for: `SEA-WS1`
3. Select the device **SEA-WS1** from the results.
4. Select **Select** to add it to the group.

---

## Step 5: Create the Group

1. Verify that **SEA-WS1** is listed as a selected member.
2. Select **Create** to create the group.

---

## Step 6: Verify Group Membership

1. Open the newly created group.
2. Go to **Members**.
3. Confirm that the device **SEA-WS1** is listed.

---

## Validation Checklist

- [ ] A security group named **Pilot-Devices** exists in Entra ID.
- [ ] The group membership type is **Assigned**.
- [ ] The device **SEA-WS1** is a member of the group.
- [ ] The group can be selected in Intune or Conditional Access assignments.

---

## Result

You now have a security group in Microsoft Entra ID that contains the **SEA-WS1** device that can be used for targeting policies.
