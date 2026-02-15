# Lab: Demonstrate Microsoft Intune Suite Features

This lab demonstrates key features of the **Microsoft Intune Suite** license with a focus on:

- **Enterprise Application Management**
- **Remote Help**
- **Privileged Endpoint Management (EPM)**

You will verify licensing, explore each feature in the Intune admin center, and perform basic configuration or usage steps to understand how each capability works.

---

## Prerequisites

- The **Microsoft Intune Suite** license is enabled in the tenant.
- The following users are licensed for Intune Suite:
  - Edmund
  - Miranda
  - Cody
- You have access to the **Microsoft Intune admin center**: https://intune.microsoft.com
- You are signed in with an account that has Intune administrative permissions.
- Devices are enrolled in Intune (Windows 10/11 recommended for EPM and Remote Help demos).

---

## Step 1: Verify Intune Suite Features Are Available

1. Go to: https://intune.microsoft.com
2. In the left navigation, review the available nodes and confirm you can see:
   - **Apps > Enterprise App Management** (or Enterprise application management related options)
   - **Remote help**
   - **Endpoint security > Privileged Endpoint Management**

3. If any of these are not visible:
   - Go to **Tenant administration > Licenses**
   - Confirm **Microsoft Intune Suite** is active and assigned to your test users.

---

# Part 1: Enterprise Application Management (EAM)

Enterprise Application Management simplifies app packaging, deployment, and management.

## Step 2: Open Enterprise Application Management

1. In the Intune admin center, go to:
   **Apps**
2. Locate and select **Enterprise App Management** (or the Enterprise App Management entry under Apps).

3. Review the overview page and note:
   - The catalog of supported enterprise applications
   - Options to add or manage applications
   - Deployment and update capabilities

## Step 3: Explore the Application Catalog

1. Browse the available enterprise applications.
2. Select one application to view:
   - App details
   - Supported versions
   - Deployment options
3. Review how Intune handles:
   - App installation
   - Updates
   - Supersedence (if available in your tenant)

> This demonstrates how Enterprise Application Management reduces the effort needed to package and maintain common enterprise apps.

---

# Part 2: Remote Help

Remote Help allows secure, role-based remote assistance for Intune-managed devices.

## Step 4: Open Remote Help

1. In the Intune admin center, go to:
   **Tenant administration > Remote help**
2. Review the **Remote help** settings page.

3. Confirm that:
   - Remote Help is enabled
   - Permissions and roles are configured as needed

## Step 5: Review Remote Help Usage Flow

1. Go to **Devices > All devices**.
2. Select a Windows device.
3. Review the available **Remote help** actions (if available in your tenant UI).
4. Discuss or demonstrate:
   - How a helper requests a session
   - How the user accepts the session
   - How actions are audited and logged

> This demonstrates how Remote Help provides secure, auditable remote support integrated with Intune.

---

# Part 3: Privileged Endpoint Management (EPM)

Privileged Endpoint Management allows standard users to run specific apps with elevated privileges without giving them full admin rights.

## Step 6: Open Privileged Endpoint Management

1. In the Intune admin center, go to:
   **Endpoint security > Privileged Endpoint Management**

2. Select **Overview** and review:
   - The purpose of EPM
   - The current status of the feature in your tenant

## Step 7: Review EPM Policies

1. Go to **Endpoint security > Privileged Endpoint Management > Policies**.
2. Select **Create policy** (do not complete the wizard unless instructed in your lab).
3. Review the available options, such as:
   - Elevation rules
   - File or application-based elevation
   - User prompts and justification options

4. Cancel out of the wizard after reviewing the options.

> This demonstrates how EPM can replace full local admin rights with controlled, audited elevation.

---

## Validation Checklist

- [ ] Intune Suite features are visible in the Intune admin center
- [ ] Enterprise Application Management catalog and options were reviewed
- [ ] Remote Help settings and usage flow were reviewed
- [ ] Privileged Endpoint Management overview and policy options were reviewed
- [ ] You understand the purpose and value of each Intune Suite feature

---

## Result

You have explored and demonstrated the core **Microsoft Intune Suite** features:

- **Enterprise Application Management** for simplified app lifecycle management  
- **Remote Help** for secure, audited remote support  
- **Privileged Endpoint Management** for controlled privilege elevation without granting full admin rights  

These capabilities extend Intune beyond basic device management into advanced endpoint operations and security.
