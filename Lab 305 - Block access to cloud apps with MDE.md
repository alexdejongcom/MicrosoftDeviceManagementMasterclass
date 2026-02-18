# Lab: Block Web Access Using Microsoft Defender for Endpoint and Microsoft Defender for Cloud Apps

This lab walks you through configuring web access controls using Microsoft security services:

1. Use **Microsoft Defender for Endpoint** to block access to https://wetransfer.com  
2. Use **Microsoft Defender for Cloud Apps** to block access to **Generative AI** applications with a **risk score below 6** using **Create policy from search**  
3. Use **Microsoft Defender for Endpoint** Web Content Filtering to block access to **Social networking** applications  

---

## Prerequisites

- You must have access to the Microsoft Defender portal with sufficient permissions (for example, Security Administrator or Global Administrator).
- Devices must be onboarded to Microsoft Defender for Endpoint.
- Microsoft Defender for Cloud Apps must be enabled in your tenant.
- Network protection and web content filtering must be supported and enabled on endpoints.

---

## Step 1: Sign in to the Microsoft Defender Portal

1. Open a browser and go to:  
   https://security.microsoft.com
2. Sign in with an account that has administrative permissions.

---

# Part 1: Block Access to https://wetransfer.com Using Microsoft Defender for Endpoint

## Step 2: Create an Indicator to Block the URL

1. In the Microsoft Defender portal, go to **Settings**.
2. Select **Endpoints**.
3. Select **Indicators** (or **Rules > Indicators** depending on your portal layout).
4. Select **Add indicator**.
5. Configure the indicator:
   - **Indicator type**: URL or domain
   - **URL or domain**: `wetransfer.com`
   - **Action**: Block
   - **Title**: `Block WeTransfer`
   - **Description**: `Block access to wetransfer.com`
   - **Severity**: Medium (or as appropriate)

6. Set the scope to the desired device group (or **All devices** for lab purposes).
7. Select **Save**.

## Step 3: Verify the Block

1. On a managed device, attempt to browse to:  
   https://wetransfer.com
2. Confirm that access is blocked by Microsoft Defender for Endpoint.

---

# Part 2: Block Generative AI Apps with Risk Score Below 6 Using Microsoft Defender for Cloud Apps

## Step 4: Open Defender for Cloud Apps

1. In the Microsoft Defender portal, go to **Cloud apps**.
2. Select **Cloud App Catalog**.

---

## Step 5: Search for Generative AI Apps with Low Risk Score

1. In **Cloud App Catalog**, use the filters:
   - **Category**: Generative AI
   - **Risk score**: 0 - 6

2. Review the list of applications that match the filter.

---

## Step 6: Create Policy from Search

1. With the filtered results still applied, select **Create policy from search**.
2. Configure the policy:
   - **Policy name**: `Block low-risk-score Generative AI apps`
   - **Policy template**: no template
   - **Governance Actions**: Tag app as unsanctioned
   - Ensure the filter conditions include:
     - Category = Generative AI
     - Risk score < 6

3. create the policy.

---

## Step 7: Verify the Cloud App Policy

1. Go to **Cloud apps > Policies**.
2. Confirm the new policy appears and is enabled.
3. Verify that access to matching Generative AI apps is now blocked for users.

---

# Part 3: Block Social Networking Apps Using Web Content Filtering in Defender for Endpoint

## Step 8: Configure Web Content Filtering

1. In the Microsoft Defender portal, go to **Settings**.
2. Select **Endpoints**.
3. Select **Web content filtering**.

---

## Step 9: Create or Edit a Web Content Filtering Policy

1. Select **Add policy** (or edit an existing policy used for the lab).
2. Configure the policy:
   - **Name**: `Block Social Networking`
   - Under **Categories**, locate and select:
     - **Social networking**
   - Set the action for this category to **Block**.

3. Assign the policy to the appropriate device group (or **All devices** for lab purposes).
4. Save the policy.

---

## Step 10: Verify the Web Content Filtering Block

1. On a managed device, attempt to access a social networking site (for example, a popular social media site).
2. Confirm that access is blocked by Microsoft Defender for Endpoint.

---

## Validation Checklist

- [ ] Access to https://wetransfer.com is blocked by Defender for Endpoint.
- [ ] A Defender for Cloud Apps policy exists that blocks Generative AI apps with a risk score below 6.
- [ ] The Cloud App policy was created using **Create policy from search**.
- [ ] Web Content Filtering blocks the **Social networking** category.
- [ ] Users are prevented from accessing social networking sites on managed devices.

---

## Result

- Users cannot access **wetransfer.com** due to a Defender for Endpoint indicator.
- Users cannot access **Generative AI** applications with a **risk score below 6** due to a Defender for Cloud Apps access policy.
- Users cannot access **Social networking** applications due to Defender for Endpoint Web Content Filtering.
