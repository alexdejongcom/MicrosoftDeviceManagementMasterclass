# Lab: Verify Microsoft Intune Connection and Enable Advanced Features in Microsoft Defender for Endpoint

This lab walks you through verifying that the **Microsoft Intune connection** is enabled in Microsoft Defender for Endpoint and enabling all available **Advanced features** in the Defender portal.

---

## Prerequisites

- You must be a **Global Administrator** or have equivalent permissions in Microsoft Defender and Microsoft Intune.
- Microsoft Defender for Endpoint (or Defender for Business) must be provisioned in the tenant.
- Devices do not need to be onboarded yet to verify or change these settings.

---

## Step 1: Sign in to the Microsoft Defender Portal

1. Open a browser and go to:  
   https://security.microsoft.com
2. Sign in with an account that has administrative permissions for Microsoft Defender and Intune.

---

## Step 2: Verify the Microsoft Intune Connection

1. In the Microsoft Defender portal, go to:  
   **Settings > Endpoints > Advanced features**

2. Scroll through the list of features until you find **Microsoft Intune connection**.

3. Verify that the toggle is set to **On**.
   - If it is **Off**, switch it to **On**.

4. Scroll to the bottom of the page and select **Save preferences**.

5. Wait a few minutes for the setting to propagate across services.

> This setting enables the service-to-service integration between Microsoft Defender for Endpoint and Microsoft Intune.

---

## Step 3: Enable All Advanced Features

1. Stay on the **Settings > Endpoints > Advanced features** page.

2. Review the list of all available advanced features.

3. For each feature:
   - Set the toggle to **On**.

   Examples of features you may see include:
   - Microsoft Intune connection  
   - Allow or block file  
   - Hide potential duplicate device records  
   - Other Defender for Endpoint advanced features available in your tenant

4. After enabling all desired features, scroll to the bottom and select **Save preferences**.

---

## Step 4: Confirm the Configuration in Intune

1. Open the Microsoft Intune admin center:  
   https://intune.microsoft.com

2. Go to **Endpoint security > Microsoft Defender for Endpoint**.

3. Verify that the **Connection status** shows **Enabled**.

4. If the status does not update immediately, wait several minutes and refresh the page.

---

## Validation Checklist

- [ ] Microsoft Intune connection is set to **On** in Defender for Endpoint.
- [ ] All available Advanced features are enabled.
- [ ] Changes have been saved successfully.
- [ ] Intune shows the Defender for Endpoint connection status as **Enabled**.
