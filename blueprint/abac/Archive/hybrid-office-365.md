---
layout: page
title: Hybrid - Office 365
menu: abac
---


### Licensing

`Microsoft 365 Admin center > Billing`

Table 3 describes the Microsoft 365 Licensing settings.

Item | Configuration
--- | ---
Name | Quantity
Microsoft 365 E5 | 100,000
Microsoft Power Automate Free | 10,000
Office 365 E5 | 3
Microsoft Power Apps Plan 2 Trial | 10,000

### Licensing manual groups

`Azure Active Directory > Licenses > Microsoft 365 E5 > Licensed groups `

Table 4 describes the configuration for the manual allocation of Microsoft 365 E5 licenses.

Name | State
--- | ---
rol-Agency-Administrators | Active
rol-Agency-Users | Active
Office365_AssignLicense_StandUsers | Active





### Dynamic security groups

These settings have been configured using PowerShell.

* Naming Policy: `grp-[Department]-[Group Name]`
* Display Name: `Grp-<Agency Acronym>0365-Outlook`
  * Welcome Email: `Disabled`
* Display Name: `Grp-<Agency Acronym>O365-Teams`
  * Welcome Email: `Disabled`

### Office 365 groups

`Azure Active Directory > Groups > General`

* Self Service Group Management
  * Owners can manage group membership requests in the Access Panel: `No`
  * Restrict user ability to access groups features in the Access Panel. Administrators (Global, Group and User Admin) will have access regardless of the value of this setting.: `Yes`
* Security Groups
  * Users can create security groups in Azure portals: `No`
  * Owners who can assign members as group owners in Azure portals: `All`
* Office 365 Groups
  * Users can create Office 365 groups in Azure portal: `No`
  * Owners who can assign members as group owners in Azure portal: `All`

`Azure Active Directory > Groups > Naming policy`

* Group naming policy: `Grp-<Department>-<Group name>`

`Azure Active Directory > Groups > Expiration`

* Group lifetime (in days): `365`
* Email contact for groups with no owners: `Office365_Group_Expiration@<Agency>.gov.au`
* Enable expiration for these Office 365 groups: `All`

`Azure Active Directory > Groups`

* Group Name: `ADMIN_O365_Admin`
  * Membership type: `Assigned`
  * Source: `Windows server AD`
  * Type: `Security`
  * Members: `Admin accounts`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `ADMIN_O365_DCA_Accounts`
  * Membership type: `Assigned`
  * Source: `Windows server AD`
  * Type: `Security`
  * Members: `Admin accounts`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `ADMIN_O365_GlobalAdmins`
  * Membership type: `Assigned`
  * Source: `Windows server AD`
  * Type: `Security`
  * Members: `Admin accounts`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `Grp-<Agency Acronym>O365-Outlook`
  * Membership type: `Assigned`
  * Source: `Cloud`
  * Type: `Office`
  * Email: `Grp-<Agency Acronym>o365-outlook@<Agency>.gov.au`
  * Members: `<Agency User>`
  * Owners: `<Agency User>`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `Grp-<Agency Acronym>O365-Teams`
  * Membership type: `Assigned`
  * Source: `Cloud`
  * Type: `Office`
  * Email: `Grp-<Agency Acronym>o365-teams@<Agency>.gov.au`
  * Members: `<Agency User>`
  * Owners: `<Agency User>`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `Grp-<Agency Acronym>O365-Teams`
  * Membership type: `Assigned`
  * Source: `Cloud`
  * Type: `Office`
  * Email: `Grp-<Agency Acronym>o365-teams@<Agency>.gov.au`
  * Members: `<Agency User>`
  * Owners: `<Agency User>`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `rol-Agency-Users`
  * Membership type: `Assigned`
  * Source: `Cloud`
  * Type: `Security`
  * Members: `None admin accounts`
  * Owners: `<Agency Owner> (Admin)`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `Microsoft 365 E5`
  * Azure role assignment: `None`
* Group Name: `rol-Agency-Users`
  * Membership type: `Assigned`
  * Source: `Windows server AD`
  * Type: `Security`
  * Members: `None admin accounts`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `Microsoft 365 E5`
  * Azure role assignment: `None`
* Group Name: `Office365_Conditional_Access_Exclude`
  * Membership type: `Assigned`
  * Source: `Cloud`
  * Type: `Security`
  * Members
    * Break Glass account
      * TenantAdmin
      * TenantAdmin2
    * AAD Connect Synchronization accounts
      * `Sync_<AAD Server 1>_144f9a623d47`
      * `Sync_<AAD Server 2>_b49bd30fb398`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `Office365_Grant_AzureAD_Join`
  * Membership type: `Assigned`
  * Source: `Windows server AD`
  * Type: `Security`
  * Members: `Admin accounts`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`
* Group Name: `Office365_Grant_CreateGroups`
  * Membership type: `Assigned`
  * Source: `Cloud`
  * Type: `Security`
  * Members: `<Agency User>`
  * Owners: `None`
  * Group membership: `None`
  * Applications: `None`
  * Licenses: `None`
  * Azure role assignment: `None`

## Exchange Online Protection



## SharePoint Online & OneDrive

The ABAC settings for the Agency SharePoint Online and OneDrive instances can be found below. This includes the Sharing Configuration, Access Control and SharePoint Settings. Please note, if a setting is not mentioned in the below, it should be assumed to have been left at its default setting.

### Sharing

`SharePoint admin center > Policies > Sharing > External Sharing`

* Content can be shared with:
```
SharePoint: New and existing guests
OneDrive: Only people in your organization
```

* Limit external sharing by domain:
```
Agency.gov.au
microsoft.com
```

* Allow only users in specific security groups to share externally: `False`
* Guests must sign in using the same account to which sharing invitations are sent: `True`
* Allow guests to share items they don’t own: `False`
* People who use a verification code must reauthenticate after this many days : `Not configured`

`SharePoint admin center > Policies > Sharing > File and Folder links`

* Default link type: `Specific people (only the people the user specifies)`
* Default link permission : `Edit`

`SharePoint admin center > Policies > Sharing > Other settings`

* Show owners the names of people who viewed their files in OneDrive: `True`
* Let site owners choose to display the names of people who viewed files or pages in SharePoint: `True`
* Use short links for sharing files and folders : `True`

### Access control

`SharePoint admin center > Policies > Access control > Unmanaged devices`

* Allow access from unmanaged devices: `Block access`

`SharePoint admin center > Policies > Access control > Idle session sign-out`

* Sign out inactive users automatically: `On`
* Sign out users after:: `1 hours`
* Give users this much notice before signing them out: `5 minutes`

`SharePoint admin center > Policies > Access control > Network location`

* Allow access only from specific IP address ranges: `Off`

`SharePoint admin center > Policies > Access control > Apps that don’t use modern authentication`

* Allow or block access from applications that don’t user modern authentication: `Block access`

### SharePoint settings

`SharePoint admin center > Settings > Default admin center`

* New SharePoint admin center: `True`

`SharePoint admin center > Settings > Pages`

* Allow users to create new modern pages on sites that don’t already have site pages: `True`
* Allow commenting on modern pages : `True`

`SharePoint admin center > Settings > SharePoint notifications`

* Allow notifications: `True `

`SharePoint admin center > Settings > Site creation`

* Let users create sites from the SharePoint start page and OneDrive: `False`
* Create team sites under: `https://<Agency>.sharepoint.com/sites/`
* Default time zone : `(UTC+10:00) Canberra, Melbourne, Sydney`
* Default storage limit for new sites: `200 GB`

`SharePoint admin center > Settings > Site storage limits`

Share storage among all sites or control storage limits: `Manual`

## Security and compliance

The ABAC settings for the Agency Office 365 Security and Compliance instance can be found below. This includes the Alerts, Labels, Data Loss Prevention, Retention Policies, Audit Logging, and Customer Key configuration. Please note, if a setting is not mentioned in the below, it should be assumed to have been left at its default setting.

### Audit logging

`Microsoft 365 compliance > Audit > Audit Retention Policies`

* Enabled: `True`
* Policy name: `10 year audit log`
* Policy description: `Retains all audit log records for 10 years`
* Record Type: `All`
* Duration: `10 years`
* Priority: `1`

### Retention policies

`Office 365 Security & compliance > Information governance > Retention | Exchange 3 Years Hold`

* Status: `On`
* Policy Name: `Exchange 3 Years Hold`
* Description: `Exchange 3 Years Hold`
* Applies to content in these locations:
```
Exchange email
Exchange Public Folders
```

* Retention period: `Keep content for 3 years`
* Turn on preservation lock: `No`

`Office 365 Security & compliance > Information governance > Retention | Microsoft 365 groups 3 Years Hold`

* Status: `On`
* Policy Name: `Microsoft 365 groups 3 Years Hold`
* Description: `Microsoft 365 groups 3 Years Hold`
* Applies to content in these locations: `Microsoft 365 groups`
* Retention period: `Keep content for 3 years`
* Turn on preservation lock: `No`

`Office 365 Security & compliance > Information governance > Retention | OneDrive 3 Years Hold`

* Status: `On`
* Policy Name: `OneDrive 3 Years Hold`
* Description: `OneDrive 3 Years Hold`
* Applies to content in these locations: `OneDrive Accounts`
* Retention period: `Keep content for 3 years`
* Turn on preservation lock: `No`

`Office 365 Security & compliance > Information governance > Retention | SharePoint 3 Years Hold`

* Status: `On`
* Policy Name: `SharePoint 3 Years Hold`
* Description: `SharePoint 3 Years Hold`
* Applies to content in these locations: `SharePoint sites`
* Retention period: `Keep content for 3 years`
* Turn on preservation lock: `No`

`Office 365 Security & compliance > Information governance > Retention | Teams Channel Messages 3 Years Hold`

* Status: `On`
* Policy Name: `Teams Channel Messages 3 Years Hold`
* Description: `Teams Channel Messages 3 Years Hold`
* Applies to content in these locations: `Teams channel messages`
* Retention period: `Keep content for 3 years`
* Turn on preservation lock: `No`

`Office 365 Security & compliance > Information governance > Retention | Teams Chats 3 Years Hold`

* Status: `On`
* Policy Name: `Teams Chats 3 Years Hold`
* Description: `Teams Chats 3 Years Hold`
* Applies to content in these locations: `Teams chats`
* Retention period: `Keep content for 3 years`
* Turn on preservation lock: `No`

### Retention labels

`Office 365 Security & compliance > Information governance > Labels`

Not Configured

### Sensitivity labels

`Office 365 Security & compliance > Information protection > Labels`

* UNOFFICIAL: `0 – lowest`
* OFFICIAL: `1`
* OFFICIAL Sensitive: `2`
* OFFICIAL Sensitive ACCESS=Legal-Privilege: `3`
* OFFICIAL Sensitive ACCESS=Legislative-Secrecy: `4`
* OFFICIAL Sensitive ACCESS=Personal-Privacy: `5`
* PROTECTED: `6`
* PROTECTED ACCESS=Legal-Privilege: `7`
* PROTECTED ACCESS=Legislative-Secrecy: `8`
* PROTECTED ACCESS=Personal-Privacy: `9`
* PROTECTED CAVEAT=SH CABINET: `10`
* PROTECTED ACCESS=Legal-Privilege CAVEAT=SH CABINET: `11`
* PROTECTED ACCESS=Legislative-Secrecy CAVEAT=SH CABINET: `12`
* PROTECTED ACCESS=Personal-Privacy CAVEAT=SH CABINET: `13 – highest`

### Sensitivity label policy

`Office 365 Security & compliance > Information protection >Label polices > <Agency Acronym> sensitivity labels`

* Name: `<Agency Acronym> sensitivity labels`
* Description: Default sensitivity labels based on [PSPF infosec document](https://www.protectivesecurity.gov.au/sites/default/files/2019-12/pspf-infosec-08-sensitive-classified-information.pdf)
* Published Labels
```
UNOFFICIAL
OFFICIAL
OFFICIAL Sensitive
OFFICIAL Sensitive ACCESS=Legal-Privilege
OFFICIAL Sensitive ACCESS=Legislative-Secrecy
OFFICIAL Sensitive ACCESS=Personal-Privacy
PROTECTED
PROTECTED ACCESS=Legal-Privilege
PROTECTED ACCESS=Legislative-Secrecy
PROTECTED ACCESS=Personal-Privacy
PROTECTED CAVEAT=SH CABINET
PROTECTED ACCESS=Legal-Privilege CAVEAT=SH CABINET
PROTECTED ACCESS=Legislative-Secrecy CAVEAT=SH CABINET
PROTECTED ACCESS=Personal-Privacy CAVEAT=SH CABINET
```

* Published to: `All`
* Policy settings:
```
Label is mandatory
Users must provide justification to remove a label or lower its classification
```

### Data loss prevention

`Office 365 Security & compliance > Data Loss Prevention`

* Australia Financial Data: `0`
* Australia Health Records ACT (HRIP Act): `1`
* Australia Personally Identifiable Information (PII) Data: `2`
* Australia Privacy Act: `3`
* Locations to apply this policy: 
```
Exchange email
SharePoint sites
OneDrive accounts
Teams chat and channel messages
```

* Policy settings: 
```
Low volume of content detected
High volume of content detected
```

## Microsoft 365 Defender

The ABAC settings for Microsoft 365 Defender can be found below. This includes Safe Links, Safe Attachments, and Anti-phishing configuration.

Please note, if a setting is not mentioned below, it should be assumed to have been left at its default setting.

### Safe Links

* Name: `Default Safe Links Policy`
* Description: `This policy is the default Safe Links policy for the environment`
* Users and domains:
  * Users: `Not Configured`
  * Groups: `Not Configured`
  * Domains: `All Agency domains`
* Protection Settings:
  * Select the action for unknown potentially malicious URLs in messages: `On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link`
  * Select the action for unknown or potentially malicious URLs within Microsoft Teams: `On - Microsoft Teams will check against a list of known malicious links when user clicks on the link; URLs will not be rewreitten`
  * Apply real-time URL scanning for suspicious links and links that point to files: `Enabled`
    * Wait for URL scanning to complete before delivering the message: `Enabled`
  * Apply Safe Links to email messages sent within the organisation: `Enabled`
  * Do not track user clicks: `Disabled`
  * Do not let users click through to the original URL: `Enabled`
  * Display the organization branding on notification and warning pages: `Disabled`
  * Do not rewrite the following URLs: `Not Configured`
* Notification:
  * How would you like to notify your users: `Use the default notification text`

### Safe Attachments

#### Global Settings

* Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams: `Enabled`
* Turn on Safe Documents for Office Clients: `Enabled`
  * Allow people to click through Protected View even if Safe Documents has identified the file as malicious: `Disabled`

### Policy

* Name: `Default Safe Attachments Policy`
* Description: `This policy is the default Safe Attachments policy for the environment`
* Users and domains:
  * Users: `Not Configured`
  * Groups: `Not Configured`
  * Domains: `All Agency domains`
* Settings:
  * Safe Attachments unknown malware response: `Block - Block current and future messages and attachments with detected malware`
  * Enable Redirect: `Enabled`
    * Send messages that contain blocked, monitored, or replaced attachments to the specified email address: `quarantine@agency.gov.au`
  * Apply the Safe Attachments detection response if scanning can't complete (timeout or errors): `Enabled`

### Anti-phishing

* Name: `Office365 AntiPhish Default (Default)`
* Phishing email threshold: `2 - Aggressive`
* Enable users to protect: `Configured - agency executives added`
* Enabled domains to protect: `Enabled`
  * Include domains I own: `Enabled`
  * Include custom domains: `Disabled`
* Add trusted senders and domains: `Not configured`
* Enable mailbox intelligence: `Enabled`
  * Enable Intelligence for impersonation protection: `Enabled`
* Spoof
  * Enable spoof intelligence: `Enabled`
* Actions
* Message actions
  * If message is detected as an impersonated user:`Quarantine the message`
  * If message is detected as an impersonated domain: `Quarantine the message`
  * If Mailbox Intelligence detects an impersonated user: `Quarantine the message`
  * If message is detected as spoof: `Quarantine the message`
* Safety tips & indicators
  * Show user impersonation safety tip: `Enabled`
  * Show domain impersonation safety tip: `Enabled`
  * Show user impersonation unusual characters safety tip: `Enabled`
  * Show (?) for unauthenticated senders for spoof: `Enabled`
