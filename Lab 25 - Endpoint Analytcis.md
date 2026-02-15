# Lab: Create a Windows Health Monitoring Policy and Explore Endpoint Analytics in Microsoft Intune

This lab walks you through:

1. Creating a **Windows Health monitoring** policy in Microsoft Intune
2. Assigning the policy to **All devices**
3. Exploring the **Endpoint analytics** section in Intune to review device health and performance insights

---

## Prerequisites

* You must be an **Intune Administrator** or **Global Administrator**
* Devices must be enrolled in Microsoft Intune
* You must have access to the Microsoft Intune admin center:
  [https://intune.microsoft.com](https://intune.microsoft.com)

---

## Step 1: Sign in to the Intune Admin Center

1. Open a browser and go to:
   [https://intune.microsoft.com](https://intune.microsoft.com)
2. Sign in with an account that has administrative permissions.

---

## Part 1: Create a Windows Health Monitoring Policy

## Step 2: Navigate to Health Monitoring

1. In the left navigation pane, select **Devices**.
2. Select **Monitor** (or **Configuration** depending on your portal layout).
3. Select **Health monitoring**.
4. Select **Create policy**.

> If you don’t see **Health monitoring** directly, look under **Devices > Windows > Health monitoring** or use the search bar at the top of the portal.

---

## Step 3: Configure the Health Monitoring Policy

1. On the **Basics** page, configure:

   * **Name**: `Windows Health Monitoring - All Devices`
   * **Description**: `Monitors Windows device health and performance metrics`

2. Select **Next**.

3. On the **Configuration settings** page:

   * Leave the default settings enabled (or review the available health signals such as startup performance, crashes, and reliability metrics).

4. Select **Next**.

---

## Step 4: Assign the Policy to All Devices

1. On the **Assignments** page:

   * Under **Included groups**, select **Add groups**.
   * Select **All devices**.

2. Select **Next**.

---

## Step 5: Review and Create

1. Review the policy configuration.
2. Select **Create** to deploy the Windows Health monitoring policy.

---

## Step 6: Verify Policy Deployment

1. Go to **Devices > Health monitoring**.
2. Select the policy **Windows Health Monitoring - All Devices**.
3. Review:

   * **Assignments**
   * **Device status**

---

## Part 2: Explore Endpoint Analytics

Endpoint analytics provides insights into device performance, reliability, and user experience.

---

## Step 7: Open Endpoint Analytics

1. In the Intune admin center, select **Reports** (or **Tenant administration** depending on your UI).
2. Select **Endpoint analytics**.

---

## Step 8: Explore Key Endpoint Analytics Areas

Review the following sections:

* **Overview**

  * High-level insights into device performance and user experience.

* **Startup performance**

  * Metrics related to boot times and sign-in performance.

* **Application reliability**

  * Information about app crashes and hangs.

* **Device performance**

  * CPU, memory, and resource utilization insights.

* **Work from anywhere / Remoting performance** (if available)

  * Performance metrics for remote work scenarios.

---

## Step 9: Review Device and Model Insights

1. In **Endpoint analytics**, select one of the reports (for example, **Startup performance**).
2. Drill down into:

   * A specific device
   * A device model
3. Review the detailed metrics and trends.

---

## Validation Checklist

* [ ] A Windows Health monitoring policy exists in Intune.
* [ ] The policy is assigned to **All devices**.
* [ ] Devices show status for the Health monitoring policy.
* [ ] The **Endpoint analytics** section is accessible in Intune.
* [ ] At least one Endpoint analytics report has been reviewed.

---

## Result

You have created and assigned a **Windows Health monitoring** policy to all devices and explored **Endpoint analytics** to understand how Intune provides insights into device health, performance, and user experience.
