# Lab: Deploy a Script to All Devices Using Remediations in Microsoft Intune

In this lab, you will deploy a PowerShell script to **All devices** using **Remediations** (formerly “Proactive remediations”) in Microsoft Intune. Remediations run a **detection script** first and then run a **remediation script** only when detection indicates a fix is needed. :contentReference[oaicite:0]{index=0}

---

## Prerequisites

- Access to the Microsoft Intune admin center: https://intune.microsoft.com
- Windows devices enrolled in Intune (Remediations are for Windows endpoints)
- Permissions to create and assign Remediations (Intune Administrator or equivalent)
- You have the script(s) ready as files on your admin workstation:
  - Detection script: `Detect-<Something>.ps1`
  - Remediation script: `Remediate-<Something>.ps1`

**For this lab, download the script:** https://msftuniversity.blob.core.windows.net/intunelabs/createRandomfile.ps1

> Tip: remember where you are downloading this file.

---

## Step 1: Enable Windows Data Collection and Go to Remediations

1. Sign in to the Intune admin center:  
   https://intune.microsoft.com
2. Navigate to: **Tenant administration > Connectors and tokens > Windows data**
3. Enable **Enable features that require Windows diagnostic data in processor configuration**
4. Open **Windows license verification**
5. Enable **I confirm that my tenant owns one of these licenses**
6. Navigate to:  
   **Devices > Scripts and remediations > Remediations**

---

## Step 2: Create a Remediation Script Package

1. Select **Create** (or **Create script package**).
2. On **Basics**, enter:
   - **Name**: `Remediation - Deploy Script to All Devices`
   - **Description**: `Runs detection and (if needed) remediation across all devices`
3. Select **Next**.

---

## Step 3: Upload Detection and Remediation Scripts

1. On the **Scripts** page:
   - Upload your **Detection script file** (`Detect-*.ps1`)
   - Upload your **Remediation script file** (`Remediate-*.ps1`)   **NOT NEEDED FOR THIS LAB**
2. Select **Next**.

> Remediations require both a detection and remediation script. Detection runs first; remediation runs only when necessary. :contentReference[oaicite:2]{index=2}

---

## Step 4: Configure Script Settings

On the **Settings** page, configure (typical lab defaults):

- **Run this script using the logged-on credentials**: `No` (System context)
- **Run script in 64-bit PowerShell**: `Yes`
- **Enforce script signature check**: `No` (lab)
- **Script timeout**: leave default (or adjust for your script)

Select **Next**.

---

## Step 5: Assign to All Devices and Schedule

1. On the **Assignments** page:
   - Under **Included groups**, select **Add groups**
   - Choose **All devices**
2. Set the schedule (example):
   - **Run schedule**: Daily (or the interval required by your lab)
   - Choose an execution time
3. Select **Next**.

---

## Step 6: Review and Create

1. Review the configuration summary.
2. Select **Create** to deploy the remediation to all devices.

---

## Step 7: Monitor Results

1. Go to:  
   **Devices > Scripts and remediations > Remediations**
2. Select your remediation package.
3. Review:
   - **Device status**
   - **Detection status/output**
   - **Remediation status/output** (if remediation ran)

---

## Optional: Manually Trigger the Remediation for a Single Device

You can manually run a remediation against a specific device using the **Run remediation** device action. :contentReference[oaicite:3]{index=3}

1. Go to: **Devices > All devices**
2. Select a device.
3. Choose **… (More)** > **Run remediation**
4. Select the remediation package and confirm.

---

## Validation Checklist

- [ ] A remediation package exists with both detection and remediation scripts uploaded
- [ ] The package is assigned to **All devices**
- [ ] Devices report detection results in the remediation status view
- [ ] Devices requiring changes show remediation results (where applicable)

---

## Result

You deployed a script package to **All devices** using **Remediations** in Microsoft Intune, with reporting that shows detection and remediation outcomes.
