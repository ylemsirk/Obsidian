### Active Directory Fundamentals & Architecture

1. What is Active Directory, and what problem does it solve that a workgroup (peer-to-peer) network cannot? Explain in simple terms why a company with 500 employees needs AD instead of just 500 local accounts.
    
2. Define the following AD objects and give a real-world example of each: domain, forest, tree, organizational unit (OU), site, domain controller, user, group, computer.
    
3. What is the difference between a forest and a domain? Why would an organization create multiple domains inside one forest instead of a single domain?
    
4. Explain what an Organizational Unit (OU) is and how it differs from a container. Why do administrators organize users and computers into OUs rather than leaving them in the default Users and Computers containers?
    
5. What is a Domain Controller (DC)? What roles and services does it provide (authentication, LDAP directory, Kerberos KDC, DNS integration, Group Policy distribution), and why is losing a DC a critical event?
    
6. Explain the concept of an AD "site." How does site awareness help a user in a branch office authenticate faster and use local resources instead of crossing a slow WAN link?
    
7. What is the AD schema? Why is it risky to modify the schema, and who is typically authorized to do it?
    
8. What is a trust relationship between domains or forests? Give one scenario where a trust is needed (e.g., a company acquiring another company), and explain in general terms how it lets users from one domain access resources in another.
    
9. Describe the Global Catalog and its role. Why does a Help Desk agent sometimes see a "Global Catalog unavailable" error during a search in Active Directory Users and Computers, and what does that mean for the user?
    
10. What is the AD Recycle Bin, and how does it differ from restoring from a backup? Why is it important that a Tier I agent never deletes AD objects without an approved ticket?
    

---

### Domain Controllers, Replication & DNS

11. What is AD replication, and why must changes (like a new user or a password reset) propagate to all domain controllers? Why might a user experience inconsistent behavior depending on which DC they authenticate against?
    
12. What is the difference between inbound and outbound replication? A user reports that a new group membership took an hour to take effect. How would you explain this and what would you check?
    
13. Why is DNS considered the "backbone" of Active Directory? Explain the role of the SRV records that AD relies on, and what happens to domain authentication if DNS is broken.
    
14. A remote user's laptop cannot find a domain controller to authenticate against. What DNS-related troubleshooting would you perform remotely (ipconfig /all, nslookup for the domain name, checking DNS server settings)?
    
15. What is the SYSVOL folder, and why is it important for Group Policy and logon scripts? Why might a Tier I agent escalate a SYSVOL replication issue instead of trying to fix it?
    
16. Explain the concept of Flexible Single Master Operations (FSMO) roles at a high level. Why should a Tier I agent know these exist but never attempt to modify them?
    
17. What is a Read-Only Domain Controller (RODC), and why would a branch office deploy one? What are the limitations for users authenticating against an RODC?
    
18. A user reports that they were able to log in yesterday but cannot today, and they are in a different office than usual. How could a DC replication delay or a site configuration issue explain this, and how would you verify before escalating?
    

---

### User Accounts & Attributes

19. Explain the difference between a domain user account and a local user account. Why does a Help Desk agent reset the domain password and not the local one when a user forgets their password at work?
    
20. What is the User Principal Name (UPN) and how does it differ from the sAMAccountName (pre-Windows 2000 logon name)? A user says "my username is jsmith but the login box rejects it." How would you determine the correct logon format remotely?
    
21. Describe the purpose of the following AD user attributes: Display Name, First/Last Name, Email, Telephone, Department, Title, Manager, Description. Why does accurate data in these fields matter for security and auditing?
    
22. What is the difference between enabling, disabling, and deleting a user account? Which one would you use for an employee on long-term leave versus an employee who has left the company, and why?
    
23. What is an account expiration date, and why would a Help Desk agent check it when a user suddenly cannot log in? Walk through the remote steps to verify this in Active Directory Users and Computers.
    
24. Explain what happens to a user's account when it is "locked out" versus "disabled" versus "expired." A user calls and says "I'm locked out." What three checks would you perform before resetting anything?
    
25. What is a Service Account, and how does it differ from a regular user account? Why should a Tier I agent be cautious about resetting a service account's password, and who should be involved before doing so?
    
26. What is an unmanaged or non-person account (like a shared mailbox or kiosk account)? Why does the security team often want these tracked, and what risks do they pose if not managed?
    
27. How would you remotely verify the last logon time and last password change for a user account? Why is this information useful when investigating a suspected compromise or an abandoned account?
    
28. What is a UPN suffix, and why might a company use a different UPN suffix than its internal domain name (e.g., [contoso.com](https://contoso.com/) instead of contoso.local)? How would this affect a user's login experience?
    

---

### Groups & Permissions Model

29. Explain the difference between a security group and a distribution group. Which one grants access to resources, and which one is only for email distribution?
    
30. Describe the scope of the three AD group types: Global, Domain Local, and Universal. Give a simple example of when each is appropriate.
    
31. What is the AGDLP model (Accounts, Global groups, Domain Local groups, Permissions)? Why is it considered best practice, and how does it simplify Help Desk group membership requests?
    
32. What is a group nesting? Why might a user suddenly get access to a resource because they were added to a nested group, and how would you trace which group is granting the access?
    
33. A user submits a ticket asking to be added to the "Finance Reports" group. What information would you require before making the change, and why should you not add users to groups based solely on a phone request?
    
34. Explain the difference between direct group membership and role-based access. Why do mature organizations prefer adding users to role groups rather than directly assigning permissions on folders?
    
35. What is the "Domain Admins" group, and why is adding a user to it considered extremely high risk? What alternative groups exist for delegated administrative tasks?
    
36. What is the Protected Users group, and what extra security does it enforce? Why would a Help Desk agent need to be aware of it when troubleshooting a user who cannot use cached credentials or NTLM?
    
37. A user complains they lost access to a shared folder they used to open. How would you remotely determine if their group membership changed, and how would you find out who made the change?
    
38. What is the difference between removing a user from a group and disabling their account? In an offboarding scenario, which would you do first and why?
    

---

### Authentication: Kerberos, NTLM & Logon

39. Explain, at a high level, how a user authenticates to Active Directory when they log in. What role does the domain controller play, and what is the Kerberos Ticket Granting Ticket (TGT)?
    
40. What is Kerberos, and why is it the default authentication protocol in modern Windows domains? How does it differ from NTLM, and why is NTLM considered weaker?
    
41. Why is accurate time synchronization critical for Kerberos authentication? A user's clock is 10 minutes off and they cannot log in. Explain remotely why this breaks Kerberos and how to fix it.
    
42. What is a "cached credential," and why can a user log in to their laptop with their domain password when they are at home and not connected to the corporate network?
    
43. Explain Windows logon types and why a Tier I agent should distinguish between an interactive logon (Type 2), a network logon (Type 3), and a Remote Desktop logon (Type 10) when reading logon events.
    
44. What is Single Sign-On (SSO) in the context of AD? Why does a user get automatically logged into internal applications after signing into Windows, and what could break this experience?
    
45. What is the "Trust Relationship Between This Workstation and the Primary Domain Has Failed" error? Explain what causes it, what impact it has on the user, and what steps a Help Desk agent should take (and what to escalate).
    
46. A user says "my password works on the webmail portal but not on my laptop." How could this happen in a domain environment, and what would you check first?
    
47. What is a Kerberos ticket lifetime, and why might a user be asked to reauthenticate after a certain period? What is the difference between a TGT and a service ticket (TGS)?
    
48. Describe the difference between interactive logon, network logon, and service logon in practical terms. Why does this matter when diagnosing "Access Denied" errors versus "Logon Failure" errors?
    

---

### Password, Lockout & Account Policies

49. Explain the difference between a password policy, an account lockout policy, and a fine-grained password policy. Why might a company enforce different password rules for administrators than for standard users?
    
50. What is the default account lockout threshold in many organizations, and how does it protect against brute force? What risks does a very low threshold create for legitimate users?
    
51. A user is locked out because an attacker (or a misconfigured mobile device) is repeatedly trying their password. How would you identify the source of the lockouts remotely using lockout tools and domain controller event logs?
    
52. What is the difference between unlocking an account and resetting a password? Which one would you do when a user calls about repeated lockouts, and why?
    
53. What is the "User must change password at next logon" flag, and how would you remotely set it when onboarding a new user or resetting a compromised account's password?
    
54. What is the "Password never expires" setting, and why is it generally discouraged? What exceptions exist (e.g., service accounts), and how would a Tier I agent handle a request to enable it?
    
55. Explain what happens to a user's account when their password expires. What advance warning do they get, and how would you remotely walk them through changing it if they are working from home without VPN?
    
56. What is a Password Reset Disk, and why is it rarely used in domain environments? What is the correct method for a domain user to recover access when they forget their password?
    
57. What is the difference between a self-service password reset (SSPR) and a Help Desk reset? How would you explain to a frustrated user why they should enroll in SSPR if their company offers it?
    
58. A user reports they get locked out every Monday morning. What could cause this recurring pattern (cached credentials on a mobile device, mapped drive with old password, scheduled task), and how would you investigate remotely?
    

---

### Group Policy

59. What is Group Policy, and what is the difference between a Local Group Policy and a domain Group Policy Object (GPO)? Why can a setting on a user's PC be overridden by the domain even if the user changes it locally?
    
60. Describe the main sections of a GPO: Computer Configuration versus User Configuration. Why is it important to know which section a setting lives in when troubleshooting?
    
61. What is GPO scope, and how do the following affect which GPOs apply to a user or computer: site, domain, OU, security filtering, and WMI filters?
    
62. Explain GPO inheritance and the "Enforced" and "Block Inheritance" options. A user says a setting that should be applied by policy is not taking effect. How would you remotely determine whether inheritance or blocking is the cause?
    
63. What is Group Policy Loopback Processing, and in what scenario would an administrator enable it (e.g., kiosk or shared computer)? How does it affect the user experience?
    
64. What is the difference between computer-side and user-side Group Policy processing, and when does each occur (boot vs logon, background refresh)?
    
65. How would you remotely force a Group Policy update on a user's computer, and why is `gpupdate /force` sometimes not enough? What logs would you check afterward?
    
66. Explain the purpose of `gpresult /r` and `gpresult /h`. A user's mapped drive is missing. How would you use these tools remotely to determine if the drive mapping GPO applied or was filtered out?
    
67. What is Resultant Set of Policy (RSoP), and how does it differ from a simple gpresult? In what troubleshooting scenario would RSoP give you better insight than gpresult alone?
    
68. What is a Group Policy Preferences (GPP) item, and how does it differ from a traditional GPO setting? Why was the "cpassword" vulnerability in GPP such a serious issue, and what does it mean for Tier I escalation?
    
69. A user complains that a desktop shortcut keeps reappearing after they delete it. Explain how a GPO could cause this and what information you would gather before escalating.
    
70. A user is in the "Sales" OU and does not receive a drive mapping that other Sales users have. What would you check first: group membership, security filtering on the GPO, OU placement, or WMI filter? Walk through your reasoning.
    
71. Explain the difference between applying a GPO to users versus computers for software deployment. Why would a user need to log off and back on, or the computer need a restart, for a change to take effect?
    
72. What is the default GPO processing order (LSDOU: Local, Site, Domain, OU)? Why does the last-applied policy usually win when there is a conflict?
    

---

### Computer Accounts & Domain Join

73. What is a computer account in Active Directory, and why does every domain-joined machine need one? What happens when a computer account's password goes out of sync with the domain?
    
74. Explain the "Secure Channel" between a workstation and the domain. What is the `Test-ComputerSecureChannel` or equivalent check, and why is it useful for diagnosing the trust relationship error?
    
75. A user's laptop was renamed by IT last week and now they cannot log in with their domain account. What would you check remotely, and how would the computer account in AD factor into the problem?
    
76. What is the difference between a domain-joined computer and a workgroup computer? What capabilities does the user lose if their computer is not domain-joined (Group Policy, SSO, access to domain resources)?
    
77. What is the process of joining a computer to the domain, and why is it typically performed by IT rather than the end user? What credentials are required, and what are the risks of an unauthorized domain join?
    
78. A user receives an old laptop from a colleague who left the company. It is still registered under the previous user's name in AD. Why is renaming and re-registering the computer account important, and how would you coordinate this with the sysadmin team?
    
79. What is the computer account password reset interval in a Windows domain (default 30 days), and why does this cause the "trust relationship failed" error in some cases? How is the fix performed, and why is it usually a Tier II task?
    
80. A user is trying to log in from a non-domain-joined device (a personal laptop) and cannot access domain resources. Explain why this fails, what options exist (VPN + domain join, published apps, web portals), and how you would guide the user.
    

---

### File Shares, Drive Mappings & Printers in a Domain

81. What is the difference between share permissions and NTFS permissions? When both apply, which one wins (most restrictive), and how does this affect troubleshooting "Access Denied" errors?
    
82. A user's mapped network drive (H:) shows a red X. What are the possible causes (network connectivity, VPN not connected, GPO not applied, share offline), and how would you troubleshoot remotely in order of likelihood?
    
83. Explain the difference between a user's home folder (usually H:) and a departmental shared folder (usually S: or similar). Why would a Help Desk agent check which drive is failing before assuming the network is down?
    
84. What is Access-Based Enumeration (ABE), and why might a user see an empty folder even though other users see many files inside it? How would you explain this to the user without exposing information they should not see?
    
85. How do printers get deployed to users in a domain environment via Group Policy? A user's department printer is missing. What would you check: group membership, printer GPO, print server reachability, or local driver issues?
    
86. What is a print server, and why is it preferred over direct IP printing in a domain environment? A user's print job is stuck in the queue on the print server. What remote steps would you take?
    
87. A user can access a shared folder but cannot modify files inside it. What permission level might they have (Read vs Modify vs Full Control), and how would you verify without directly changing permissions?
    
88. What is Offline Files (CSC), and how does it affect a user who works remotely? A user sees "Offline Files" errors on their laptop. What are the implications, and when would you escalate?
    

---

### Profiles, Folder Redirection & User Data

89. Explain the difference between a local profile, a roaming profile, and a mandatory profile. Why do some organizations use folder redirection instead of roaming profiles, and what problem does each solve?
    
90. What is Folder Redirection, and how does it protect user data if a laptop is lost? A user's Documents folder is redirected to a server share and they are offline. Explain what they see and how to help them.
    
91. What is the difference between Folder Redirection and OneDrive Known Folder Move? In a hybrid environment, why might an organization use both, and how would this affect a Tier I troubleshooting approach?
    
92. A user logs into a different computer and sees a "temporary profile" message. How does this relate to AD (profile path, permissions on the profile share) even though it feels like a local issue?
    
93. What is a logon script, and how does it differ from a GPO Preferences drive mapping? A user is missing a mapped drive that comes from a logon script. What would you check first: script execution, permission to the script, or network access?
    
94. Why is it important that a Tier I agent never deletes a user's profile folder from a server or local machine without approval? What data could be lost, and how would this affect the user and the company?
    

---

### Tools for Tier I

95. What is Active Directory Users and Computers (ADUC), and what are the most common tasks a Tier I agent performs there (password resets, unlocks, group membership, account status checks)?
    
96. What is Active Directory Administrative Center (ADAC), and how does it differ from ADUC? Why might a company standardize on one over the other?
    
97. What is the Remote Server Administration Tools (RSAT) package, and why would a Help Desk agent need it installed to manage AD from their own workstation?
    
98. What is `dsquery` and `dsget`, and how are they used in a Help Desk context? Give an example of a query that would help you find all users in a specific OU or a specific group.
    
99. What is the `net user`, `net group`, and `netdom` family of commands, and how can they help diagnose domain logon and group membership issues remotely?
    
100. What is the ADUC "Find" feature, and how would you use it to locate a user by partial name, email, or description? Why is accurate attribute data critical for this to work well?
    
101. Why should a Tier I agent use only approved administrative consoles and never modify AD via direct LDAP or PowerShell scripts they do not fully understand? What could go wrong with an incorrect bulk change?
    

---

### Event Logs & Auditing

102. Which Windows Security Event IDs are most relevant to a Tier I Help Desk agent when troubleshooting AD issues, and what does each one indicate: 4624 (successful logon), 4625 (failed logon), 4740 (account locked out), 4767 (account unlocked)?
    
103. What does Event ID 4740 tell you, and how would you use it remotely to identify the source of repeated account lockouts (which computer or device is generating them)?
    
104. What does Event ID 4720 (user account created) or 4726 (user account deleted) tell you, and why is it important that these events are monitored even though a Tier I agent does not typically perform these actions?
    
105. What does Event ID 4732 (member added to a security-enabled local group) or 4728 (member added to a global group) indicate? Why would an unexpected change here be a security concern?
    
106. Why is centralized log collection important in an AD environment? If an incident happens and logs are only stored locally on the affected computer, what problems does that create for investigation?
    
107. A user's account was locked out and you resolved it, but you want to know what caused the lockout. What evidence would you look for in the DC logs, and what would you document for the ticket?
    

---

### Troubleshooting Scenarios (Tier I Level)

108. **Scenario:** A remote user calls and says "I forgot my password." Walk through the entire process of verifying their identity, resetting the domain password, setting "must change at next logon," and confirming they can log in with VPN or Outlook Web App.
    
109. **Scenario:** A user is locked out and cannot log in. What are the first three things you would check before unlocking their account, and how would you ensure the same device does not immediately lock them out again?
    
110. **Scenario:** A user's password is correct but they keep getting "The user name or password is incorrect." They insist it worked yesterday. What AD-related causes would you investigate (account disabled, expired password, UPN vs sAMAccountName mismatch, domain selection error)?
    
111. **Scenario:** A user works from home and cannot log in because their laptop says "no logon servers available." They are not connected to VPN yet. Explain why cached credentials matter and what steps you would walk them through.
    
112. **Scenario:** A user connects to VPN but still cannot access a mapped drive. What would you check: whether the VPN is actually connected, whether the drive mapping GPO applied after VPN connection, and whether the share is reachable via ping or UNC path?
    
113. **Scenario:** A user is added to a new department and needs access to a shared drive. The ticket says "add to Marketing group." What verification do you need (manager approval, exact group name, effective date) before making the change, and how would you document it?
    
114. **Scenario:** A user reports a "trust relationship failed" error when logging in. What is the immediate user impact, what temporary workaround might exist (local admin account, cached credentials), and what do you escalate to Tier II?
    
115. **Scenario:** A user's account was disabled by mistake during an offboarding batch. The employee is still active. How would you handle this carefully: verify identity, get approval, re-enable the account, and ensure nothing else was changed?
    
116. **Scenario:** A user complains that a group policy is blocking them from changing their wallpaper. They want it removed. How would you explain the purpose of the policy to the user without changing the GPO, and how would you route this request appropriately?
    
117. **Scenario:** A user was on leave for three months and now cannot access anything. Their password expired and their account may be disabled. Walk through the step-by-step remote resolution while maintaining security.
    
118. **Scenario:** A user calls and says "someone else's name appears when I open Outlook." What could cause this in a shared or reused computer, and how would your AD checks (profile, Office account, mailbox configuration) help you diagnose this?
    
119. **Scenario:** You receive a ticket that a new employee has no access to anything. They have an AD account but nothing else. What steps would you take to onboard them: verify account enabled, add to correct groups, confirm computer is domain-joined, and confirm drive mappings apply?
    
120. **Scenario:** A user reports intermittent authentication failures when connecting to a file share, but their interactive login works fine. What Kerberos or cached credential issues could cause this, and how would you gather evidence before escalating?
    

---

### Operations: Onboarding, Offboarding & Change Management

121. Describe the standard process for onboarding a new user in AD: creating the account, setting attributes, assigning group membership, and configuring the initial password. What approvals should be required before creating any account?
    
122. Describe the standard process for offboarding a user in AD: disabling the account, removing group memberships, checking for direct reports or shared mailbox ownership, and coordinating with other teams (email, file shares, licenses).
    
123. Why is it important to never delete user accounts immediately during offboarding? What are the audit, legal, and technical reasons for disabling first and deleting later (if at all)?
    
124. What is a "role change" in AD terms, and why is it more than just adding or removing a single group? How would you coordinate with HR and the user's manager to ensure access matches the new role?
    
125. What is a change request, and why must a Tier I agent follow an approval process before modifying AD objects? Give an example of a request that should be denied without written approval.
    
126. What information should a Help Desk ticket documenting an AD change include (requester, approver, exact change, timestamp, evidence of verification), and why is this important for audits?
    
127. Why should a Tier I agent never make "small changes" outside of a ticket, even if the user is a friend or a senior manager? What are the professional and security implications?
    
128. What is the principle of separation of duties, and how does it apply to AD administration? Why might the same person not be allowed to both request and approve access?
    

---

### Scope, Escalation & Best Practices

129. What AD tasks are typically within Tier I scope (password resets, unlocks, group membership requests with approval, basic account status checks) versus Tier II (Group Policy changes, OU restructuring, service account work, domain controller issues, trust relationship fixes)?
    
130. When you receive a request that is outside your scope (e.g., "please give me Domain Admin access"), how would you respond professionally, and how would you route it to the correct team with the necessary justification?
    
131. Why is it dangerous for a Help Desk agent to "guess" at an AD solution without understanding the impact? Give an example where a wrong change (e.g., moving a computer to the wrong OU, removing a group membership) could break the user's access for days.
    
132. What is the difference between granting a user direct permission on a resource and adding them to an AD group? Why is the group approach preferred from a Help Desk perspective (less risk, easier to audit, easier to revert)?
    
133. Why should a Tier I agent never test AD changes on a production user account without approval? What alternative test methods exist (test account, sandbox OU, lab environment)?
    
134. What would you document in your knowledge base for the most common AD tickets you handle (password reset, account unlock, group request), and why does good documentation reduce future escalations?
    

---

### Hybrid & Modern Identity Awareness (Light Touch)

135. What is Microsoft Entra ID (formerly Azure AD), and how does it differ from on-premises Active Directory? Why might a modern company use both?
    
136. What is a hybrid identity, and how do user accounts sync between on-prem AD and Entra ID? A user changes their on-prem password, but their Microsoft 365 login still fails. What would you check?
    
137. What is the difference between a synced account and a cloud-only account? How would a Tier I agent determine which type a user has before attempting a password reset?
    
138. What is Conditional Access, and how could it cause a user to be blocked from logging in even though their password is correct? What information would you gather before escalating?
    
139. What is Self-Service Password Reset (SSPR) in Entra ID, and how does it help reduce Help Desk ticket volume? Why is user enrollment and MFA registration important for this to work?
    
140. A user says "MFA is asking for a code but my phone is broken." What would you do as a Tier I agent, and what approvals or escalation steps are needed before resetting their MFA methods?