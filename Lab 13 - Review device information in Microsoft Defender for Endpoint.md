# Lab: Review Device Information for LON-CL1 in Microsoft Defender for Endpoint

This lab walks you through using **Microsoft Defender for Endpoint** to review detailed device information for **LON-CL1**, with a focus on:

- Inventory
- Vulnerabilities
- Security recommendations

---

## Prerequisites

- You must have access to the Microsoft Defender portal.
- The device **LON-CL1** must be onboarded to Microsoft Defender for Endpoint.
- You must have sufficient permissions (for example, Security Administrator or Global Administrator).

---

## Step 1: Sign in to the Microsoft Defender Portal

1. Open a browser and go to:  
   https://security.microsoft.com
2. Sign in with an account that has permissions to view devices and security data.

---

## Step 2: Locate the LON-CL1 Device

1. In the left navigation, select **Assets**.
2. Select **Devices**.
3. In the device list, use the search box to search for:  
   `LON-CL1`
4. Select the device **LON-CL1** from the results to open the device details page.

---

## Step 3: Review Inventory Information

1. On the **LON-CL1** device page, select the **Inventory** tab.
2. Review the available inventory data, which may include:
   - Installed software
   - Hardware information
   - Operating system details
3. Select individual inventory items to view more detailed information where available.

---

## Step 4: Review Vulnerabilities

1. On the **LON-CL1** device page, select the **Vulnerabilities** tab.
2. Review the list of detected vulnerabilities for the device.
3. For one or more vulnerabilities:
   - Select the vulnerability to open its details.
   - Review the severity, affected software, and remediation guidance.
4. Note any high or critical vulnerabilities that require attention.

---

## Step 5: Review Security Recommendations

1. On the **LON-CL1** device page, select the **Security recommendations** tab.
2. Review the list of recommended actions for improving the security posture of the device.
3. Select a recommendation to view:
   - The security impact
   - The suggested remediation steps
   - The affected resources
4. Identify which recommendations could be remediated through Intune or other management tools.

---

## Step 6: Validate Findings

1. Confirm that inventory data is visible for **LON-CL1**.
2. Confirm that vulnerability information is available and populated.
3. Confirm that security recommendations are listed for the device.
4. Optionally, take notes on:
   - High-risk vulnerabilities
   - High-impact security recommendations

---

## Validation Checklist

- [ ] The **LON-CL1** device is visible in Microsoft Defender for Endpoint.
- [ ] Inventory information is available and populated.
- [ ] Vulnerabilities are listed for the device.
- [ ] Security recommendations are visible and can be reviewed.
- [ ] At least one vulnerability and one recommendation were inspected in detail.

---

## Result

You have reviewed the **Inventory**, **Vulnerabilities**, and **Security recommendations** for the **LON-CL1** device in Microsoft Defender for Endpoint and understand its current security posture.
