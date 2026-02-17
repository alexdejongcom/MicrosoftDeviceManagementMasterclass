# Lab: Enable and Configure Windows Autopatch for SEA-WS1 and SEA-WS2

## Objective

In this lab, you will:
- Enable Windows Autopatch in Microsoft Intune
- Prepare Microsoft Entra ID and Intune for Autopatch
- Create and configure the required Autopatch groups
- Assign SEA-WS1 and SEA-WS2 to Windows Autopatch
- Verify devices are managed by Autopatch and receiving update policies

---

## Prerequisites

- Microsoft 365 tenant with licenses that include Windows Autopatch
- Global Administrator or Intune Administrator permissions
- Microsoft Intune is already set up in the tenant
- Devices SEA-WS1 and SEA-WS2:
  - Windows 10 or Windows 11 Enterprise/Education/Pro
  - Azure AD (Microsoft Entra ID) joined or Hybrid joined
  - Enrolled in Microsoft Intune
- Devices have internet access and are reporting to Intune

---

## Part 1: Verify Devices Are Enrolled and Healthy

### Task 1: Check Device Enrollment in Intune

1. Open the Microsoft Intune admin center.
2. Go to **Devices** > **All devices**.
3. Confirm that **SEA-WS1** and **SEA-WS2** both appear in the list.
4. Open each device and verify:
   - Managed by: Microsoft Intune
   - Azure AD joined or Hybrid Azure AD joined
   - Compliance state is not in an error state

If either device is missing, enroll it into Intune before continuing.

---

## Part 2: Enable Windows Autopatch

### Task 2: Turn On Windows Autopatch

1. In the Intune admin center, go to **Tenant administration**.
2. Select **Windows Autopatch**.
3. Choose **Get started** or **Enable Windows Autopatch**.
4. Review the prerequisites screen and continue.
5. Confirm the configuration and enable Windows Autopatch for the tenant.
6. Wait for the initial setup to complete.

This process creates the Autopatch service connection and prepares Intune to manage update rings, feature updates, and quality updates automatically.

---

## Part 3: Review Autopatch Configuration

### Task 3: Open the Windows Autopatch Blade

1. In Intune, go to **Tenant administration** > **Windows Autopatch**.
2. Review the overview page, which shows:
   - Service status
   - Deployment rings
   - Managed devices count
3. Confirm that Windows Autopatch reports as **Active** or **Ready**.

---

## Part 4: Create or Verify Autopatch Device Groups

Windows Autopatch uses device groups to control which devices are managed.

### Task 4: Verify or Create the Autopatch Device Group

1. Go to **Microsoft Entra ID** > **Groups**.
2. Look for a group created for Windows Autopatch devices (for example, a group used to onboard devices to Autopatch).
3. If no suitable group exists:
   1. Create a new **Security** group.
   2. Name it: `Windows Autopatch Devices`.
   3. Set membership type to **Assigned**.
   4. Create the group.

---

## Part 5: Add SEA-WS1 and SEA-WS2 to the Autopatch Group

### Task 5: Assign Devices to the Group

1. Open the **Windows Autopatch Devices** group.
2. Select **Members** > **Add members**.
3. Add the following devices:
   - SEA-WS1
   - SEA-WS2
4. Save the changes.

These devices are now targeted for management by Windows Autopatch.

---

## Part 6: Register the Group with Windows Autopatch

### Task 6: Onboard the Group into Autopatch

1. Go back to **Intune** > **Tenant administration** > **Windows Autopatch**.
2. Find the option to **Add devices** or **Register devices**.
3. Select the **Windows Autopatch Devices** group.
4. Confirm the assignment.
5. Wait for the service to process the group.

Autopatch will now:
- Assign devices to deployment rings
- Create and manage update policies automatically
- Begin managing updates for these devices

---

## Part 7: Verify Device Assignment to Autopatch Rings

### Task 7: Check Autopatch Device Status

1. In **Windows Autopatch**, go to **Devices** or **Reports**.
2. Search for **SEA-WS1** and **SEA-WS2**.
3. Confirm that each device:
   - Is listed as managed by Autopatch
   - Is assigned to a deployment ring (Test, First, Fast, Broad, or similar)
4. Open each device record and verify it shows as **Active** or **Onboarded**.

---

## Part 8: Verify Policies in Intune

### Task 8: Review Autopatch-Created Policies

1. In Intune, go to **Devices** > **Windows** > **Update rings for Windows**.
2. Confirm that Autopatch-managed update rings exist.
3. Go to **Devices** > **Windows** > **Feature updates for Windows**.
4. Confirm that Autopatch-managed feature update policies exist.
5. Go to **Devices** > **Windows** > **Quality updates**.
6. Confirm that Autopatch-managed quality update policies exist.

These policies are maintained automatically by Windows Autopatch.

---

## Part 9: Validate on the Devices

### Task 9: Check Update Management on SEA-WS1 and SEA-WS2

1. Sign in to SEA-WS1.
2. Open **Settings** > **Windows Update**.
3. Confirm the device is managed by your organization and receiving update policies.
4. Repeat the same steps on SEA-WS2.
5. Optionally, trigger a **Check for updates** to confirm updates are being offered under management.

---

## Part 10: Expected Outcome

- Windows Autopatch is enabled in the tenant.
- SEA-WS1 and SEA-WS2 are members of the Autopatch device group.
- Both devices are onboarded into Windows Autopatch.
- Devices are assigned to Autopatch deployment rings.
- Update rings, feature updates, and quality updates are managed automatically by Autopatch.
- Devices receive updates without manual policy management.

---

## Cleanup (Optional)

- Remove SEA-WS1 and SEA-WS2 from the Autopatch group if this is a temporary lab.
- Disable Windows Autopatch if you do not want to keep it enabled in the tenant.
