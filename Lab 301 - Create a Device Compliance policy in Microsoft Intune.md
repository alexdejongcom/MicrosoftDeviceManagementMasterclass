# Lab: Create a Windows Device Compliance Policy in Intune

This lab walks you through creating a **Windows device compliance policy** in Microsoft Intune and assigning it to **all devices**. The policy will check for the following settings:

- BitLocker
- Firewall
- Secure Boot
- Microsoft Defender for Endpoint risk level (not higher than Medium)

---

## Prerequisites

- You must be an **Intune Administrator** or **Global Administrator**.
- Devices must be enrolled in Microsoft Intune.
- Microsoft Defender for Endpoint integration with Intune must be enabled.
- You must have access to the Microsoft Intune admin center.

---

## Step 1: Sign in to the Microsoft Intune Admin Center

1. Open a browser and go to:  
   https://intune.microsoft.com
2. Sign in with an account that has administrative permissions.

---

## Step 2: Navigate to Compliance Policies

1. In the left navigation pane, select **Devices**.
2. Select **Compliance**.
3. Select **Policies**.
4. Select **Create policy**.

---

## Step 3: Create the Compliance Policy

1. On the **Create a policy** page, configure:
   - **Platform**: Windows 10 and later
   - **Policy type**: Compliance

2. Select **Create**.

3. On the **Basics** page:
   - **Name**: `Windows Compliance - Security Baseline`
   - **Description**: `Checks BitLocker, Firewall, Secure Boot, and Defender for Endpoint risk level`
4. Select **Next**.

---

## Step 4: Configure Compliance Settings

On the **Configuration settings** page, configure the following:

### Device Health

- **Require BitLocker**: Require
- **Require Secure Boot to be enabled on the device**: Require

### System Security

- **Require a firewall**: Require

### Microsoft Defender for Endpoint

- **Require the device to be at or under the machine risk score**: Yes
- **Maximum allowed machine risk score**: Medium

> Note: The Defender for Endpoint settings appear only if the Intune–Defender integration is enabled.

After configuring the settings, select **Next**.

---

## Step 5: Assign the Policy to All Devices

1. On the **Assignments** page:
   - Under **Included groups**, select **Add groups**.
   - Select the **All devices** group.

2. Select **Next**.

---

## Step 6: Review and Create

1. Review the policy configuration.
2. Select **Create** to deploy the compliance policy.

---

## Step 7: Verify Policy Deployment

1. Go to **Devices > Compliance > Policies**.
2. Select the newly created policy.
3. Review:
   - **Assignments**
   - **Device status**
4. On a test device, force a sync:
   - Go to **Settings > Accounts > Access work or school**.
   - Select the connected account and choose **Info > Sync**.

---

## Validation Checklist

- [ ] A Windows compliance policy exists in Intune.
- [ ] The policy checks for BitLocker, Firewall, Secure Boot, and Defender for Endpoint risk level.
- [ ] The policy is assigned to **All devices**.
- [ ] Devices report a compliance state (Compliant or Not compliant).
- [ ] Devices with risk level higher than Medium are marked **Not compliant**.

---

## Result

All Windows devices in Intune are now evaluated for compliance based on BitLocker, Firewall, Secure Boot, and Microsoft Defender for Endpoint risk level.
