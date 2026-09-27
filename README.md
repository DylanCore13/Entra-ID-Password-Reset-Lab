

<img width="600" height="533" alt="Entra-ID-logo" src="https://github.com/user-attachments/assets/78596069-87c9-4718-ad1c-492bb8a68e2e" />





# Microsoft Entra ID Password Reset & Sign-In Troubleshooting Lab

## Overview

In this lab, I used the Microsoft 365 Admin Center and Microsoft Entra ID to create a test user and troubleshoot a simulated sign-in issue.

The purpose of this lab was to practice common Tier 1 Help Desk tasks involving user account management, authentication troubleshooting, password resets, and sign-in log analysis.

---

## Technologies Used

- Microsoft 365 Admin Center
- Microsoft Entra ID
- Microsoft Entra Sign-In Logs
- Microsoft 365 Test Tenant
- Web Browser / InPrivate Session

---

## Lab Environment

For this lab, I created a fictional employee account:

**User:** Emily Rodriguez  
**Job Title:** Accounting Specialist  
**Department:** Accounting  
**User Type:** Member  

The account was created without administrative privileges.

---

# — Create the User in Microsoft 365

I opened the **Microsoft 365 Admin Center** and navigated to:

`Users > Active users > Add a user`

I created the test employee account and configured the user's profile information.

The user was kept as a standard user with no administrative role.

<img width="1875" height="655" alt="Screenshot 2026-09-27 112734" src="https://github.com/user-attachments/assets/5316c91c-d478-44ff-9ab1-c776333db5ef" />


---

# — Verify the User in Microsoft Entra ID

After creating the account in Microsoft 365, I opened the **Microsoft Entra Admin Center**.

I navigated to:

`Identity > Users > All users`

I located **Emily Rodriguez** and reviewed the account.

I verified:

- Account status was enabled
- User type was Member
- No administrative roles were assigned
- No groups were currently assigned
- No product license was assigned

This demonstrated how a user created through Microsoft 365 is represented and managed through Microsoft Entra ID.


<img width="1631" height="1135" alt="Screenshot 2026-09-27 112716" src="https://github.com/user-attachments/assets/55ea634d-e35d-4d58-be87-4cb8a28b887c" />



---

# — Simulate a Failed Sign-In

To create a troubleshooting scenario, I opened a separate InPrivate browser session and attempted to sign in as the test user using incorrect credentials.

I then returned to Microsoft Entra ID and navigated to:

`User > Sign-in logs`

The failed authentication attempt appeared in the user's sign-in history.

<img width="1967" height="211" alt="Screenshot 2026-09-27 113312" src="https://github.com/user-attachments/assets/e14a5243-3206-48b9-944a-856082802b82" />


---

# — Investigate the Sign-In Failure

I opened the failed sign-in event and reviewed the authentication information.

The event showed:

**Status:** Failure  
**Sign-in Error Code:** 50126  
**Failure Reason:** Invalid username or password

This confirmed that the problem was related to the user's credentials rather than immediately assuming another account or service issue.



<img width="2275" height="1312" alt="Screenshot 2026-09-27 112823" src="https://github.com/user-attachments/assets/27aa946a-a550-4da8-8af6-8f69bed1bd0c" />




---

# — Reset the User Password

After identifying the credential issue and simulating confirmation that the user had forgotten their password, I returned to the user's Entra profile.

I selected:

`Reset password`

Microsoft Entra generated a temporary password for the account.

In a real Help Desk environment, temporary credentials would be provided to the verified user through an approved secure method.

> **Security Note:** Passwords and temporary credentials should never be included in screenshots or public documentation.


<img width="867" height="100" alt="Screenshot 2026-09-27 112920" src="https://github.com/user-attachments/assets/f03f2e9c-cf01-444c-8406-c058c2bc61b9" />

<img width="307" height="183" alt="Screenshot 2026-09-27 112949" src="https://github.com/user-attachments/assets/be5d0843-c1b5-43c5-b5cd-fe6b2bf09265" />


---

# — User Changes Temporary Password

I signed in as the test user using the temporary credentials.

Microsoft required the user to create a new private password before continuing.

After changing the password, the user was able to authenticate successfully.


<img width="1900" height="1018" alt="Screenshot 2026-09-27 113050" src="https://github.com/user-attachments/assets/2a24ecd6-241f-4231-8d32-ce6bbf17cc6f" />


<img width="821" height="792" alt="Screenshot 2026-09-27 113059" src="https://github.com/user-attachments/assets/96f3256a-3ddc-4373-a399-f90289d33da2" />



---

# — Verify Successful Authentication

I returned to Microsoft Entra ID and refreshed the user's sign-in logs.

The logs now showed a successful authentication event.

**Status:** Success  
**Sign-in Error Code:** 0

This verified that the password reset resolved the authentication problem.


<img width="1967" height="211" alt="Screenshot 2026-09-27 113312" src="https://github.com/user-attachments/assets/6308d982-1df8-4057-8c28-e35934410854" />


<img width="1959" height="63" alt="Screenshot 2026-09-27 113325" src="https://github.com/user-attachments/assets/45a044a1-f2a5-4461-9778-566ce30ddcca" />


---

# Troubleshooting Workflow

The troubleshooting process used during this lab was:

1. Verify the user's identity.
2. Confirm the account is enabled.
3. Gather information about the sign-in problem.
4. Review Microsoft Entra sign-in logs.
5. Identify the authentication failure.
6. Confirm that the user forgot their password.
7. Reset the password.
8. Have the user change the temporary password.
9. Verify successful authentication.
10. Document the resolution.

---



# Example Help Desk Ticket Documentation

**Issue:**  
User reported being unable to sign in to their account.

**Investigation:**  
Verified the user's identity and confirmed that the account was enabled. Reviewed Microsoft Entra sign-in logs and identified failed authentication attempts caused by invalid credentials.

**Resolution:**  
The user confirmed that they had forgotten their password. Reset the user's password and provided temporary credentials according to procedure. The user changed the temporary password and successfully signed in.

**Verification:**  
Confirmed successful authentication through Microsoft Entra sign-in logs.

**Status:**  
Resolved.

---

# Skills Demonstrated

- Microsoft 365 user administration
- Microsoft Entra ID user management
- User account provisioning
- Password resets
- Authentication troubleshooting
- Microsoft Entra sign-in log analysis
- Error-code investigation
- Account-status verification
- Tier 1 Help Desk troubleshooting
- Technical documentation

---



## Key Takeaway

This lab demonstrated the importance of investigating an authentication problem before making changes to a user's account.

Instead of immediately resetting the password, I first verified the user's identity, checked the account status, and reviewed the sign-in logs to identify the cause of the authentication failure. After resetting the password, I verified the resolution by confirming a successful sign-in event.
