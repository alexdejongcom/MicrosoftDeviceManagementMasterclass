# Lab: Configure Endpoint Privilege Management (EPM) for Allan Deyoung to Request Elevation for Process Explorer

## Objective

In this lab, you will:
- Enable Endpoint Privilege Management (EPM) in Microsoft Intune
- Create an elevation rule that requires user confirmation before elevation
- Scope the policy to the user **Allan Deyoung**
- Download and install Sysinternals on Allan’s device
- Verify that **Process Explorer** requires a permission request before running elevated

---

## Prerequisites

- Microsoft Intune tenant with Endpoint Privilege Management licensing
- You are an Intune Administrator or Global Administrator
- Allan Deyoung has a Windows 10 or Windows 11 device enrolled in Intune
- The device is online and reporting to Intune

---

## Part 1: Enable Endpoint Privilege Management

### Task 1: Turn On EPM in Intune

1. Open the Microsoft Intune admin center.
2. Go to **Tenant administration**.
3. Select **Endpoint Privilege Management**.
4. Set **Enable Endpoint Privilege Management** to **On**.
5. Save the setting.

---

## Part 2: Create an EPM Policy

### Task 2: Create a New EPM Policy

1. In Intune, go to **Endpoint security**.
2. Select **Endpoint Privilege Management**.
3. Select **Create policy**.
4. Platform: **Windows 10 and later**.
5. Profile: **Endpoint Privilege Management**.
6. Select **Create**.

---

### Task 3: Name the Policy

1. Name: `EPM - Process Explorer Requires Approval`
2. Description: `Allows Process Explorer to run only after user confirms elevation`
3. Select **Next**.

---

## Part 3: Create the Elevation Rule

### Task 4: Add an Elevation Rule

1. On the Configuration settings page, select **Add** to create a rule.
2. Configure the rule:
   - Rule name: `Process Explorer - User confirmation`
   - Description: `Require user confirmation to run Process Explorer elevated`
   - Elevation type: **User confirmed**
3. In the file information section:
   - Detection type: **File path**
   - File path: Path to Process Explorer executable (for example, where it will be extracted, such as `C:\Sysinternals\procexp.exe`)
4. Set the behavior:
   - Run with elevated privileges: **Yes**
   - Require user confirmation: **Yes**
5. Save the rule.
6. Select **Next**.

---

## Part 4: Assign the Policy to Allan Deyoung

### Task 5: Assign the Policy

1. On the Assignments page, select **Add groups**.
2. Choose a group that contains **Allan Deyoung** or create a user group for him if needed.
3. Assign the policy to that group.
4. Select **Next**.
5. Review the settings and select **Create**.

---

## Part 5: Wait for Policy to Apply

### Task 6: Sync the Device

1. On Allan’s Windows device, open **Settings**.
2. Go to **Accounts** > **Access work or school**.
3. Select the connected work account.
4. Select **Info** > **Sync**.
5. Wait a few minutes for the EPM policy to apply.

---

## Part 6: Download Sysinternals on Allan’s Device

### Task 7: Download Sysinternals Suite

1. Sign in to Allan’s Windows device.
2. Open a web browser.
3. Download the **Sysinternals Suite** ZIP file.
4. Create a folder on the device, for example: `C:\Sysinternals`.
5. Extract the contents of the ZIP file into `C:\Sysinternals`.

---

### Task 8: Locate Process Explorer

1. Open the `C:\Sysinternals` folder.
2. Locate the file:
   - `procexp.exe` (and/or `procexp64.exe` depending on the system)
3. Confirm the file exists in the folder path used in the EPM rule.

---

## Part 7: Test the Elevation Request

### Task 9: Run Process Explorer

1. While signed in as Allan Deyoung, double-click `procexp.exe`.
2. When the app attempts to run elevated, confirm that:
   - A privilege management prompt appears
   - The prompt asks Allan to confirm the elevation request
3. Approve the request.
4. Confirm that Process Explorer opens with elevated privileges.

---

## Part 8: Verify Behavior

### Task 10: Confirm EPM Is Working

1. Close Process Explorer.
2. Run it again.
3. Verify that:
   - The elevation prompt appears each time elevation is required
   - The app does not silently elevate without user interaction

---

## Expected Outcome

- Endpoint Privilege Management is enabled in the tenant.
- Allan Deyoung is targeted by an EPM policy.
- Process Explorer is blocked from silent elevation.
- Allan must explicitly confirm the elevation request to run Process Explorer with admin privileges.
- The tool runs successfully only after approval.

---

## Cleanup (Optional)

- Remove the EPM policy assignment if this was a temporary lab.
- Delete the Sysinternals folder from the device if no longer needed.
