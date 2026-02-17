# Lab: Create a DLP for Endpoint Policy in Microsoft Purview

## Objective

Configure Microsoft Purview Data Loss Prevention (DLP) for Endpoint to detect and protect sensitive data on Windows devices, including blocking or auditing actions such as copying to USB, printing, or uploading to cloud services.

---

## Prerequisites

- Microsoft 365 tenant with appropriate licensing for DLP for Endpoint
- You are a Global Administrator, Compliance Administrator, or Security Administrator
- Microsoft Defender for Endpoint is available in the tenant
- Windows 10/11 devices are available for testing
- Devices can be onboarded to Microsoft Defender for Endpoint

---

## Part 1: Initial Setup – Enable Required Services

### Task 1: Verify Microsoft Defender for Endpoint Is Enabled

1. Sign in to the Microsoft 365 admin portal.
2. Open the Microsoft Purview portal.
3. Go to **Settings**.
4. Navigate to **Device onboarding** or **Endpoints** settings.
5. Confirm that integration with Microsoft Defender for Endpoint is enabled.
6. If it is not enabled, turn it on and save the changes.

---

### Task 2: Onboard Devices to Microsoft Defender for Endpoint

1. Go to the Microsoft Defender portal.
2. Navigate to **Settings** > **Endpoints** > **Device onboarding**.
3. Choose the onboarding method that matches your environment (for example, local script, Group Policy, Intune, or Configuration Manager).
4. Download or configure the onboarding package.
5. Apply the onboarding method to at least one Windows device.
6. On the device, complete onboarding and confirm it appears as onboarded in the Defender portal.

---

### Task 3: Turn On DLP for Endpoint in Purview

1. Open the Microsoft Purview portal.
2. Go to **Settings** > **Data loss prevention**.
3. Locate the **Endpoint DLP** or **Devices** section.
4. Turn on **Enable DLP for devices**.
5. Save the setting.

---

## Part 2: Create a DLP Policy for Endpoint

### Task 4: Start the DLP Policy Wizard

1. In the Microsoft Purview portal, go to **Data loss prevention**.
2. Select **Policies**.
3. Choose **Create policy**.
4. Select a template (for example, a template for financial, personal, or confidential data) or choose **Custom**.
5. Select **Next**.

---

### Task 5: Name and Describe the Policy

1. Enter a policy name, for example: `Endpoint DLP – Sensitive Data Protection`.
2. Optionally add a description.
3. Select **Next**.

---

### Task 6: Choose Locations

1. On the locations page, select **Devices**.
2. Deselect other locations unless you want the policy to apply there as well.
3. Select **Next**.

---

### Task 7: Configure Policy Mode

1. Choose whether to start in **Test mode with notifications** or **Turn it on right away**.
2. For a lab, select **Test mode**.
3. Select **Next**.

---

## Part 3: Configure DLP Rules for Endpoint

### Task 8: Create or Edit a Rule

1. In the rule configuration screen, choose to create a new rule or edit the default rule.
2. Set the conditions for the rule, such as:
   - Content contains sensitive information types (for example, credit card numbers, personal data, or custom sensitive info types).
3. Define the threshold (for example, at least 1 instance of the sensitive info type).

---

### Task 9: Configure Endpoint Actions

1. In the actions section, configure what happens on devices when content matches:
   - Audit only, or
   - Block with override, or
   - Block outright
2. Choose the activities to control, such as:
   - Copy to removable storage
   - Copy to network shares
   - Print
   - Copy to clipboard
   - Upload to cloud services or browsers
3. Optionally enable user notifications and policy tips.

---

### Task 10: Configure User Overrides and Alerts

1. Decide whether users can override the block with business justification.
2. Configure alerting so admins are notified when the rule is triggered.
3. Set the alert severity if available.
4. Save the rule.

---

### Task 11: Finish and Create the Policy

1. Review the policy summary.
2. Select **Submit** or **Create** to finish the policy.
3. Wait for the policy to propagate to devices (this can take some time).

---

## Part 4: Validate the Policy

### Task 12: Test on an Onboarded Device

1. Sign in to a Windows device that is onboarded to Defender for Endpoint.
2. Create or obtain a file that matches the sensitive information condition.
3. Try one of the controlled actions, such as:
   - Copying the file to a USB drive
   - Uploading it to a cloud storage site
   - Printing the file
4. Confirm that the action is:
   - Audited, or
   - Blocked, or
   - Blocked with override, based on your rule configuration.

---

### Task 13: Review Alerts and Activity

1. Return to the Microsoft Purview portal.
2. Go to **Data loss prevention** > **Alerts** or **Activity explorer**.
3. Confirm that the test activity appears in the logs or alerts.

---

## Part 5: Move to Production

### Task 14: Switch from Test Mode to Enforced Mode

1. Go to **Data loss prevention** > **Policies**.
2. Open your endpoint DLP policy.
3. Edit the policy settings.
4. Change the mode from **Test** to **On**.
5. Save the policy.

---

## Cleanup (Optional)

- Disable or delete the policy if this is a temporary lab.
- Offboard test devices from Microsoft Defender for Endpoint if needed.

---

## Expected Outcome

- Devices are onboarded to Microsoft Defender for Endpoint.
- Endpoint DLP is enabled in Microsoft Purview.
- A DLP policy applies to devices.
- Sensitive data actions are audited or blocked according to the rule configuration.
- Events appear in alerts or activity logs.
