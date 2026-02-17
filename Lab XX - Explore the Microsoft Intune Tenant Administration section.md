# Lab: Explore Microsoft Intune Tenant Administration

## Objective

In this lab, you will:
- Explore the **Tenant administration** area in Microsoft Intune
- Understand the purpose of each major section
- Create example **assignment filters**
- Enable **device diagnostics**
- Learn how tenant-wide settings affect device and user management

---

## Prerequisites

- Access to the Microsoft Intune admin center
- At least Intune Administrator or Global Administrator role
- A Microsoft 365 tenant with Intune enabled

---

## Part 1: Open Tenant Administration

### Task 1: Sign in to Intune

1. Open the Microsoft Intune admin center.
2. Sign in with an account that has Intune administrative permissions.
3. In the left navigation pane, select **Tenant administration**.

You are now in the area used to configure **global, tenant-wide behavior** for Intune. These settings affect how Intune works across all devices, users, and administrators.

---

## Part 2: Explore Tenant Administration Sections

### Task 2: Review the Main Sections

In **Tenant administration**, review the following common sections. Do not change anything yet.

#### 1. Roles

- This is where you control **who can do what** in Intune.
- You can assign built-in roles (like Intune Administrator, Policy and Profile Manager).
- You can also create **custom roles** with very specific permissions.
- This helps follow the principle of least privilege and avoid giving everyone full admin rights.

#### 2. Connectors and Tokens

- This area manages **integrations** between Intune and other services.
- Examples include:
  - Apple MDM push certificates
  - Apple VPP and enrollment tokens
  - Managed Google Play
  - Certificate connectors
- Without these, certain platforms (iOS, Android, macOS) cannot be fully managed.

#### 3. Customization

- This controls **branding and user-facing text**.
- You can customize the Company Portal experience, such as:
  - Organization name
  - Support contact information
  - Logos and themes
- This helps users trust the portal and know who to contact for help.

#### 4. Intune Data Warehouse / Reports (if present)

- This is used for **reporting and analytics**.
- It allows exporting data to external reporting tools.
- Useful for long-term trend analysis and compliance reporting.

#### 5. Tenant Status / Tenant Details

- Shows **health, configuration state, and tenant info**.
- Useful for quick checks to see if core services are configured.

#### 6. Filters

- Filters are used to **dynamically target devices or users** based on properties.
- Instead of assigning policies to static groups, filters let you say things like:
  - “Only Windows 11 devices”
  - “Only corporate-owned devices”
  - “Only devices with a specific model or OS version”
- Filters are evaluated at assignment time, not by group membership.

#### 7. Diagnostics Settings (or Device Diagnostics)

- Controls whether **device diagnostics data** can be collected from managed devices.
- This is useful for troubleshooting, support, and deeper analysis of device issues.

---

## Part 3: Create Example Assignment Filters

### Task 3: Create a Filter for Windows 11 Devices

1. In **Tenant administration**, select **Filters**.
2. Select **Create**.
3. Configure the filter:
   - Name: `Windows 11 devices`
   - Platform: **Windows 10 and later**
4. In the rule builder, create this rule:
   - Property: `OS version`
   - Operator: `Starts with`
   - Value: `10.0.22`
5. Save the filter.

Explanation for students:
- This filter targets devices based on **device properties**, not groups.
- Windows 11 builds start with 10.0.22, so this rule effectively selects Windows 11 devices.
- You can use this filter when assigning policies, apps, or compliance rules.

---

### Task 4: Create a Filter for Corporate-Owned Devices

1. Select **Create** again.
2. Configure the filter:
   - Name: `Corporate-owned devices`
   - Platform: Choose a platform you manage (for example, Windows or Android)
3. In the rule builder, create this rule:
   - Property: `Device ownership`
   - Operator: `Equals`
   - Value: `Corporate`
4. Save the filter.

Explanation for students:
- This filter separates **company-owned** devices from **personal (BYOD)** devices.
- This is useful when you want stricter policies on corporate devices and lighter policies on personal ones.

---

## Part 4: Enable Device Diagnostics

### Task 5: Turn On Device Diagnostics

1. In **Tenant administration**, locate **Diagnostics settings** or **Device diagnostics**.
2. Open the diagnostics settings page.
3. Find the option to **Enable device diagnostics**.
4. Turn the setting **On**.
5. Save the configuration.

Explanation for students:
- Device diagnostics allows Intune and support teams to collect **detailed troubleshooting data** from devices.
- This can include logs, configuration states, and health information.
- Enabling this helps reduce troubleshooting time when devices have issues with policies, apps, or compliance.

---

## Part 5: Understand How These Settings Are Used

### Task 6: Concept Review

Discuss or review the following:

- **Roles** control admin access and prevent over-permissioning.
- **Connectors and tokens** enable platform integrations.
- **Customization** improves the end-user experience and trust.
- **Filters** make assignments smarter and more dynamic than static groups.
- **Diagnostics** improves supportability and troubleshooting.

---

## Part 6: Optional Exploration

- Open **Roles** and review built-in roles to see what permissions exist.
- Open **Connectors and tokens** and identify which platforms your tenant supports.
- Review **Customization** to see what users would experience in the Company Portal.

---

## Expected Outcome

By the end of this lab, you should:
- Understand the purpose of the Tenant administration area
- Be able to explain each major section to someone else
- Have at least two example filters created
- Have device diagnostics enabled
- Understand how tenant-wide settings influence Intune behavior
