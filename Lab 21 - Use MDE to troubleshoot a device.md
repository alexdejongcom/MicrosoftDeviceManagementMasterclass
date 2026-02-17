# Lab: Isolate SEA-WS1, Test Isolation, Use Live Response, and Remove Isolation in Microsoft Defender for Endpoint

This lab walks you through using **Microsoft Defender for Endpoint** to:

1. Isolate the device **SEA-WS1** from the network  
2. Test and verify the isolation  
3. Start a **Live response** session and perform four tasks to demonstrate its capabilities  
4. Remove **SEA-WS1** from isolation  

---

## Prerequisites

- You must have access to the Microsoft Defender portal with permissions to manage devices (for example, Security Administrator or Global Administrator).
- The device **SEA-WS1** must be onboarded to Microsoft Defender for Endpoint.
- The device **SEA-WS1** must be online.

---

## Step 1: Sign in to the Microsoft Defender Portal

1. Open a browser and go to:  
   https://security.microsoft.com
2. Sign in with an account that has permissions to manage Microsoft Defender for Endpoint.

---

## Step 2: Locate the SEA-WS1 Device

1. In the left navigation, select **Assets**.
2. Select **Devices**.
3. Search for:  
   `SEA-WS1`
4. Select the device **SEA-WS1** to open the device details page.

---

## Step 3: Isolate SEA-WS1 from the Network

1. On the **SEA-WS1** device page, select **Take action**.
2. Select **Isolate device**.
3. In the isolation pane:
   - Choose **Full isolation** (if prompted).
   - Enter a comment such as: `Isolating device for investigation lab`.
4. Select **Confirm**.

5. Wait a few minutes for the isolation action to be applied.

---

## Step 4: Test and Verify Device Isolation

1. On the **SEA-WS1** device page, verify that the **Isolation status** shows the device is isolated.
2. From the **SEA-WS1** device (if you have access):
   - Attempt to browse to an external website.
   - Attempt to access a network resource.
3. Confirm that network access is blocked, except for communication with Microsoft Defender for Endpoint services.

> The device should be unable to reach normal network resources while isolated.

---

## Step 5: Start a Live Response Session

1. In the Microsoft Defender portal, return to the **SEA-WS1** device page.
2. Select **Take action**.
3. Select **Initiate live response session**.
4. Wait for the live response session to connect and open the command interface.

---

## Step 6: Perform Live Response Tasks

In the live response session, perform the following four tasks to demonstrate functionality:

### Task 1: List Running Processes

1. Run the command to list running processes, for example:
   - `processes`
2. Review the list of active processes on the device.

---

### Task 2: List Files in a Directory

1. Run a command to list files in a directory, for example:
   - `dir C:\Windows\Temp`
2. Review the output to confirm directory contents are displayed.

---

### Task 3: Collect a File from the Device

1. Choose a small, non-sensitive file to collect (for example, a log file).
2. Run the command to collect the file, for example:
   - `getfile C:\Windows\Temp\example.log`
3. Confirm that the file is collected and available in the Microsoft Defender portal for download.

---

### Task 4: Run a Basic Investigation Command

1. Run another built-in command, for example:
   - `whoami`
   or  
   - `ipconfig`
2. Review the output to confirm commands execute successfully on the device.

> These tasks demonstrate visibility, file collection, and command execution through Live Response.

---

## Step 7: End the Live Response Session

1. When finished, close the live response session from the Defender portal.
2. Confirm the session is terminated.

---

## Step 8: Remove SEA-WS1 from Isolation

1. On the **SEA-WS1** device page, select **Take action**.
2. Select **Release from isolation**.
3. Enter a comment such as: `Ending investigation lab`.
4. Select **Confirm**.

5. Wait a few minutes for the device to regain normal network access.

---

## Step 9: Verify Device Is No Longer Isolated

1. Confirm that the **Isolation status** for **SEA-WS1** shows the device is no longer isolated.
2. From the device, test access to:
   - An external website
   - A network resource
3. Confirm that normal network connectivity is restored.

---

## Validation Checklist

- [ ] SEA-WS1 was successfully isolated from the network.
- [ ] Network access was blocked while the device was isolated.
- [ ] A Live response session was started successfully.
- [ ] At least four Live response tasks were executed.
- [ ] SEA-WS1 was successfully released from isolation.
- [ ] Normal network connectivity was restored.

---

## Result

You used Microsoft Defender for Endpoint to isolate **SEA-WS1**, verified the isolation, performed an investigation using **Live response**, and safely returned the device to normal network operation.
