# Lab: Deploy the Windows Security Baseline to the MDM-Pilot-Devices Group Using Microsoft Intune

This lab walks you through using **Microsoft Intune** to deploy the **Windows Security Baseline** to a device group named **MDM-Pilot-Devices**.

---

## Prerequisites

- You must be an **Intune Administrator** or **Global Administrator**.
- The group **MDM-Pilot-Devices** must already exist in Microsoft Entra ID and contain devices.
- Devices in the group must be enrolled in Microsoft Intune.
- You must have access to the Microsoft Intune admin center.

---

## Step 1: Sign in to the Microsoft Intune Admin Center

1. Open a browser and go to:  
   https://intune.microsoft.com
2. Sign in with an account that has administrative permissions.

---

## Step 2: Navigate to Security Baselines

1. In the left navigation pane, select **Endpoint security**.
2. Select **Security baselines**.
3. In the list of available baselines, select **Windows** (for example, *Windows Security Baseline for Windows 10 and later*).
4. Select **Create policy**.

---

## Step 3: Create the Baseline Profile

1. On the **Basics** page, configure:
   - **Name**: `Windows Security Baseline - MDM Pilot`
   - **Description**: `Deploys the Windows Security Baseline to the MDM-Pilot-Devices group`

2. Select **Next**.

---

## Step 4: Review and Configure Baseline Settings

1. On the **Configuration settings** page:
   - Review the baseline settings.
   - Leave the default values, or modify settings if required by your lab scenario.

2. Select **Next**.

---

## Step 5: Assign the Baseline to the Group

1. On the **Assignments** page:
   - Select **Add groups**.
   - Search for and select the group **MDM-Pilot-Devices**.

2. Select **Next**.

---

## Step 6: Review and Create

1. Review the summary of the profile.
2. Select **Create** to deploy the baseline.

---

## Step 7: Verify Deployment

1. Go to **Endpoint security > Security baselines**.
2. Select the newly created baseline profile.
3. Review:
   - **Assignments**
   - **Device status**
   - **Per-setting status**

4. On a device that is a member of **MDM-Pilot-Devices**, force a sync:
   - Go to **Settings > Accounts > Access work or school**.
   - Select the connected account and choose **Info > Sync**.

---

## Validation Checklist

- [ ] A Windows Security Baseline profile exists in Intune.
- [ ] The profile is assigned to the **MDM-Pilot-Devices** group.
- [ ] Devices in the group show as **Succeeded** or **In progress**.
- [ ] Baseline settings are applied to at least one device in the group.
- [ ] No blocking errors are reported for the profile.

---

## Result

The Windows Security Baseline is now deployed to the **MDM-Pilot-Devices** group using Microsoft Intune and is being applied to the targeted devices.
