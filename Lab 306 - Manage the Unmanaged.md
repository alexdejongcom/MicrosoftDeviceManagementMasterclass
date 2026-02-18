# Lab: Secure Access to Office 365 with Conditional Access and App Protection Policies

This lab guides you through:

1. Configuring Conditional Access for Windows, macOS, and Linux devices
2. Creating policies to block client apps and restrict downloads from unmanaged devices
3. Testing the configuration
4. Implementing Mobile Application Management (MAM) using App Protection Policies in Microsoft Intune

---

## Part 1: Configure Conditional Access for Windows, macOS, and Linux

### Policy 1: Block Client Apps from Unmanaged Devices

This policy blocks non-browser client apps from accessing Office 365 on unmanaged devices.

#### Steps

1. Go to:  
   https://entra.microsoft.com

2. Navigate to:  
   **Protection > Conditional Access > Policies**

3. Select **New policy** and configure:

- **Name**: `Block client apps from unmanaged devices (Win/Mac/Lnx)`

- **Users**:  
  - Select the users **Aaron** and **Allan**

- **Target resources**:  
  - Select **Office 365**

- **Network**:  
  - Not configured

- **Conditions**:
  - **Device platforms**:  
    - Windows  
    - macOS  
    - Linux  
  - **Client apps**:  
    - Mobile apps and desktop clients  
    - Exchange ActiveSync clients  
    - Other clients  
  - **Filter for devices**:  
    - Exclude devices where:
      - Device Ownership equals **Personal**  
      - OR Device Ownership equals **Company**

- **Access controls (Grant)**:  
  - Select **Block access**

- **Enable policy**:  
  - **On**

4. Select **Create**.

---

### Policy 2: Allow Browser Access but Block Downloads

This policy allows browser-based access to Office 365 from unmanaged devices but blocks downloads.

#### Steps

1. Go to:  
   https://entra.microsoft.com

2. Navigate to:  
   **Protection > Conditional Access > Policies**

3. Select **New policy** and configure:

- **Name**: `Block downloads from unmanaged devices (Win/Mac/Lnx)`

- **Users**:  
  - Select the users **Aaron** and **Allan**

- **Target resources**:  
  - Select **Office 365**

- **Network**:  
  - Not configured

- **Conditions**:
  - **Device platforms**:  
    - Windows  
    - macOS  
    - Linux  
  - **Client apps**:  
    - Browser  
  - **Filter for devices**:  
    - Exclude devices where:
      - Device Ownership equals **Personal**  
      - OR Device Ownership equals **Company**

- **Access controls (Grant)**:  
  - Select **Block access**

- **Session**:  
  - Enable **Use Conditional Access App Control**  
  - Select **Block downloads (preview)**

- **Enable policy**:  
  - **On**

4. Select **Create**.

---

## Part 2: Test the Configuration

### Test from Sea-Svr1

1. Switch to **Sea-Svr1**.
2. Open **Microsoft Edge**.
3. Go to:  
   https://microsoft365.com  
4. Sign in as **Aaron**.
5. Open the following in separate tabs:
   - SharePoint
   - Outlook
   - Teams
6. In **Outlook**:
   - Look for an email with an attachment and try to download it.
   - If no such email exists, send an email with an attachment to Cody and try again.

### Test from Sea-WS1

1. Repeat all the steps above from the **Sea-WS1** device.
2. Observe the differences in behavior based on device state and policy enforcement.

 > Note: If you are not allowed to sign-in, you may need to remove the Conditional Access policy from lab **302**

---

## Part 3: Implement Mobile Application Management (MAM)

### Step 1: Create a Conditional Access Policy for Protected Apps (iOS/Android)

This policy allows access to Office 365 only from mobile apps that have an App Protection Policy applied.

#### Steps

1. Go to:  
   https://entra.microsoft.com

2. Navigate to:  
   **Protection > Conditional Access > Policies**

3. Select **New policy** and configure:

- **Name**: `Only allow protected client apps (iOS/Android)`

- **Users**:  
  - Select the group **Office Users**

- **Target resources**:  
  - Select **Office 365**

- **Network**:  
  - Not configured

- **Conditions**:
  - **Device platforms**:  
    - iOS  
    - Android  

- **Access controls (Grant)**:  
  - Select **Grant access**  
  - Check **Require app protection policy**

- **Enable policy**:  
  - **On**

4. Select **Create**.

---

### Step 2: Create an App Protection Policy in Microsoft Intune

#### Steps

1. Go to:  
   https://intune.microsoft.com

2. Navigate to:  
   **Apps > Manage apps > Protection**

3. Select **Create policy** and configure:

- **Platform**:  
  - Choose **iOS/iPadOS** or **Android**

- **Name**:  
  - `Application Protection for iOS/iPadOS` or `Application Protection for Android`

- **Target policy to**:  
  - **All apps**

- **Data protection settings**:
  - **Backup org data to cloud**: Block  
  - **Send org data to other apps**: Policy managed apps  

4. Complete the wizard and create the policy.

---

## Validation Checklist

- [ ] Client apps are blocked on unmanaged Windows, macOS, and Linux devices.
- [ ] Browser access is allowed but downloads are blocked on unmanaged devices.
- [ ] Behavior is verified from Sea-Svr1 and Sea-WS1.
- [ ] A Conditional Access policy exists requiring app protection on iOS/Android.
- [ ] An App Protection Policy exists in Intune for iOS/Android.
- [ ] Mobile access to Office 365 requires protected apps.

---

## Result

- Unmanaged devices are restricted from using client apps and from downloading data via browser.
- Mobile users can access Office 365 only through apps protected by Intune App Protection Policies.
- Data leakage paths are significantly reduced without blocking browser access entirely.
