# Lab: Create an Endpoint Security EDR Policy in Intune to Onboard Devices to Microsoft Defender for Endpoint

This lab walks you through creating an **Endpoint Security** policy in Microsoft Intune to onboard all Intune-managed devices into **Microsoft Defender for Endpoint** using the **Auto from connector** setting.

---

## Prerequisites

- You must be a **Global Administrator** or **Intune Administrator**.
- Microsoft Defender for Endpoint (or Defender for Business) must be provisioned in the tenant.
- The Microsoft Intune connection must be enabled in the Microsoft Defender portal.
- Devices must already be enrolled in Microsoft Intune.

---

## Step 1: Sign in to the Microsoft Intune Admin Center

1. Open a browser and go to:  
   https://intune.microsoft.com
2. Sign in with an account that has administrative permissions.

---

## Step 2: Navigate to Endpoint Security Policies

1. In the left navigation pane, select **Endpoint security**.
2. Select **Endpoint detection and response**.
3. Select **Create policy**.

---

## Step 3: Create the EDR Policy

1. In the **Create a policy** pane, configure:
   - **Platform**: Windows 10 and later
   - **Profile**: Endpoint detection and response

2. Select **Create**.

3. On the **Basics** page:
   - **Name**: `Onboard devices to Microsoft Defender for Endpoint`
   - **Description**: `Onboards Intune-managed devices to Microsoft Defender for Endpoint using Auto from connector`
4. Select **Next**.

---

## Step 4: Configure the Onboarding Settings

1. On the **Configuration settings** page, find the setting:
   - **Microsoft Defender for Endpoint client configuration package type**

2. Set the value to:
   - **Auto from connector**

3. Leave other settings at their default values unless your lab instructions require changes.

4. Select **Next**.

---

## Step 5: Assign the Policy

1. On the **Assignments** page:
   - Select **Add groups**.
   - Choose a group that contains **all Intune-managed devices** (for example, an “All Devices” or “All Windows Devices” group).

2. Select **Next**.

---

## Step 6: Review and Create

1. Review the configuration.
2. Select **Create** to deploy the policy.

---

## Step 7: Verify Policy Deployment

1. Go back to **Endpoint security > Endpoint detection and response**.
2. Confirm the new policy appears in the list.
3. Select the policy and review:
   - **Assignments**
   - **Device status**
4. After devices sync with Intune, verify onboarding status in the Microsoft Defender portal:  
   https://security.microsoft.com

5. another way to check if the MDE Sensor is active on you clients is to run the following powershell command on those clients: "Get-Service *sense*"

---

## Validation Checklist

- [ ] EDR policy exists in Intune under **Endpoint security > Endpoint detection and response**.
- [ ] The policy uses **Auto from connector** for the onboarding package type.
- [ ] The policy is assigned to a group containing Intune-managed devices.
- [ ] Devices begin appearing as onboarded in the Microsoft Defender portal.
- [ ] No onboarding script or manual package was required.

---

## Result

All assigned Intune-managed devices are automatically onboarded to Microsoft Defender for Endpoint using the Intune–Defender connector.
