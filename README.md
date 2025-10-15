# M365-Security Portfolio

## Contents:

### Entra ID
Typical infrastructure architecture for medium-size enterprise companies.
<img src="Entra-ID/Entra-ID-overview.png">

### Scenario 1. Invite a Guest User to Microsoft Entra ID
Step 1: 
- Sign into Microsoft Entra Admin Center. Go to: https://entra.microsoft.com

- Sign in with a Global Administrator or User Administrator account.
<img src="Entra-ID/Login-Entra-ID.png">

Step 2: Invite the Guest User

- Navigate to <strong>Entra ID > Users > All users</strong>

- Click <strong>+ New user</strong>

- Choose <strong>Invite external user</strong>

<img src="Entra-ID/New-Guest-User-Entra-ID.png">

- Fill out the form:

Name: (Optional, can be inferred from email)

Email address: example@example.com

(Optional) Add a personal message
<img src="Entra-ID/Invite-External-User-Basics.png">

<img src="Entra-ID/Invite-External-User-Properties.png">

- Click <strong>Review + Invite</strong>
<img src="Entra-ID/Invite-External-User-Review-Invite.png">

<img src="Entra-ID/Invitation-Notification.png">

- The user will receive an email invitation. Once they accept, a B2B guest account is created in your directory.
<img src="Entra-ID/Invitation-Email.png">

### Scenario 2. Complete an App Registration in Microsoft Entra ID
Step 1: Open App Registrations

- In the left menu, under "Manage", click on <strong>App registrations</strong>
- Click the "<strong>New registration</strong>" button at the top
<img src="Entra-ID/App-Registration1.png">

Step 2: Register a New Application

- Fill out the registration form:
- Name	- A friendly name for your app (e.g., MyApp Web Client)
- Supported account types. Choose who can sign in:
- Single tenant: Only users in your org
- Multi-tenant: Any Azure AD tenant
- Personal Microsoft accounts: Optional
- Redirect URI (optional) - URL where tokens are sent after authentication.
For web apps: https://localhost:3000/auth/callback.  You can leave this blank and add later.
- Click <strong>Register</strong>
<img src="Entra-ID/App-Registration2.png">
<img src="Entra-ID/App-Registration3.png">

Step 3: Define API Permissions

- Click <strong>API permissions</strong>

- Click <strong>Add a permission</strong>
<img src="Entra-ID/App-Registration4.png">

- Choose:

Microsoft Graph (commonly used)

Or your own/custom API
<img src="Entra-ID/App-Registration5.png">

- Choose permission type:

Delegated – acting as signed-in user

Application – app-only, no user interaction
<img src="Entra-ID/App-Registration6.png">

- Select the scopes you need (e.g., User.Read), then <strong>Add permissions</strong>
<img src="Entra-ID/App-Registration7.png">

### Scenario 3. Create the Conditional Access policy that grants access to a specific app on Windows, Android, and iOS devices, and requires MFA
Step 1: Sign in to Entra Admin Centre and navigate to <strong>Conditional Access</strong>
- Go to: https://entra.microsoft.com 
- In the left-hand navigation, go to <strong>Entra ID > Conditional Access</strong>
- Click <strong>+ Create new policy</strong>
<img src="Entra-ID/CA_new_policy.png">

Step 2: Create a policy
- Name the policy, e.g. "Require MFA and Restrict OS for MyApp"
- Add assignments. Choose <strong>Users</strong> - All users and <strong>Target Resources</strong> - MyApp
<img src="Entra-ID/CA_users_resources.png">

Step 3: Choose conditions
- Under <strong>Conditions</strong>, click <strong>Device platforms</strong>
- Enable the setting: <strong>Configure > Yes</strong>
- Under <strong>Include</strong>, select: Android, iOS, Windows
- Under <strong>Exclude</strong>, optionally exclude: macOS, Linux, or Other platforms if needed
<img src="Entra-ID/CA_conditions.png">

Step 4: Choose access controls
- Click <strong>Grant</strong>
- Choose:
✅ Grant access
✅ Require multi-factor authentication
- Click <strong>Select</strong>
<img src="Entra-ID/CA_grant.png">

Step 5: Enable the policy and save it
- Set <strong>Enable policy</strong> to: On
- Click <strong>Save</strong>
<img src="Entra-ID/CA_save.png">

### Scenario 4. Setting Session Controls, e.g. Sign-In Frequency
Step 1: Navigate to Conditional Access
- Go to: https://entra.microsoft.com 
- In the left-hand navigation, go to <strong>Entra ID > Conditional Access</strong>
- Click <strong>+ Create new policy</strong>
<img src="Entra-ID/CA_new_policy.png">

Step 2: Create a policy
- Name the policy, e.g. "Session Control - Sign-In Frequency"
- Assign users or groups under <strong>Assignments > Users</strong> 
<img src="Entra-ID/SC_users.png">

Step 3: Choose Cloud Apps or Actions
- Under <strong>Assignments > Target resources</strong> select <strong>Cloud apps</strong>
- Choose one or more apps (e.g., Microsoft 365, SharePoint Online)
<img src="Entra-ID/SC_resources.png">

Step 4: Configure Session Controls
- In the left pane, go to **Access controls** → **Session**
- Choose from the session control options: **Sign-in frequency**
- Set the frequency (e.g., every **4 hours**, **1 day**, etc.). This forces users to re-authenticate after the specified duration.
<img src="Entra-ID/SC_frequency.png">

Step 5: Enable the policy and click **Create**
<img src="Entra-ID/SC_end.png">

### Microsoft Defender for Endpoint
### Microsoft Defender for Office 365


