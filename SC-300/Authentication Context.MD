# New note
**AUTHENTICATION CONTEXT :DEMO**  
 

## **Task 1 — Create an Authentication Context**

1.  Sign in to the Azure portal:  
    `https://portal.azure.com`
2.  Navigate to:  
    **Microsoft Entra ID → Protection → Conditional Access → Authentication context**
3.  Select **\+ New authentication context**
4.  Configure the following:
    *   **Display name:**  
        `PIM – Require Strong Authentication`
    *   **Description:**  
        `Used to enforce MFA during PIM role activation.`
    *   **Publish to apps:**  
        ✔ Enabled (must be checked)
5.  Save the authentication context.

* * *

## **Task 2 — Create a Conditional Access Policy Using the Authentication Context**

1.  Go to:  
    **Microsoft Entra ID → Protection → Conditional Access → Policies**
2.  Select **\+ New policy**
3.  Name the policy:  
    `CA – Require MFA for PIM Activation`
4.  Under **Assignments → Users**, select:
    *   **All users**  
        _(or select only administrators, depending on the scenario)_
5.  Under **Assignments → Cloud apps or actions**:
    *   Choose **Select what this policy applies to**
    *   Select **Authentication context**
    *   Pick the context created in Task 1  
        (e.g., **PIM – Require Strong Authentication**)
6.  Under **Access controls → Grant**, configure:
    *   **Grant access**
    *   Check **Require multifactor authentication**
7.  Enable and save the policy.

* * *

## **Task 3 — Configure PIM to Require the Authentication Context**

1.  Navigate to:  
    **Microsoft Entra ID → Identity Governance → Privileged Identity Management**
2.  Select **Azure AD roles** (or **Azure roles**, depending on the assignment)
3.  Choose a privileged role to configure, for example:  
    **Global Administrator**
4.  Select **Settings** → **Edit**
5.  Under **Activation settings**, locate:  
    **Require Conditional Access authentication context**
6.  From the dropdown, select the authentication context created earlier:
    *   `PIM – Require Strong Authentication`
7.  Save the settings.

* * *

## **Task 4 — Test the Configuration**

1.  Sign in with a user eligible for the chosen PIM role.
2.  Navigate to **PIM → My roles**.
3.  Select **Activate** for the role.
4.  You should now be prompted for MFA (or any other requirements configured in the CA policy