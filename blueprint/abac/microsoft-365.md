---
layout: page
title: Microsoft 365
menu: abac
---

# Organisation 

The ABAC settings for the Agency organisation can be found below. This includes Residency, Licensing and Licensing Manual Groups, Theme, Add-ins and Security and Privacy settings.

Please note, if a setting is not mentioned in the below, it should be assumed to have been left at its default setting.

## Residency

`Azure Active Directory > Properties`

Table 2 describes the Office 365 Region settings.

Item | Configuration
--- | ---
Name | Agency Name
Country or region | Australia
Location | Australia datacenters

`Microsoft 365 Admin center > Settings > Org settings > Organization profile`

Item | Configuration
--- | ---
Name | Agency Name
Street address | Agency Street Address
City | Canberra
State  | ACT
ZIP or postal code | Agency Post Code
Country or region | Australia
Phone | Agency Phone Number
Technical Contact | Agency@outlook.com
Preferred Language | English

## Theme

`Microsoft 365 Admin Center > Settings > Org settings > Organisation Profile > Custom themes`

Table 5 describes the Custom Theme settings.

Item | Configuration
--- | ---
Use a custom logo image | Use an image from a URL
Use an image from a URL | https://Agency.sharepoint.com/:i:/r/sites/AdminTeamsandLicensing/SiteAssets/UX/Agency Acronym%20Logo%20Inline%20White.png?csf=1&e=VqNfLh
Make the logo clickable | https://Agency.sharepoint.com/
Select background image | --
Navigation bar colour | #005A70
Text and icon colour | #FFFFFF
Accent colour | #B1E4E3
Prevent users from overriding their theme | Enabled
Show the user’s display name | Enabled

`Endpoint Manager Admin Center > Tenant administration > Customization`

* Branding
  * Organization name: `<Agency Name>`
  * Theme color: `#512876`
  * Show in header: `Organization logo only`
  * Upload logo for theme color background: Agency supplied
  * Upload logo for theme color light background: Agency supplied
  * Upload brand image: Agency supplied
* Support information
  * Contact name: `<Agency Acronym> IT Service Desk`
  * Phone number: `<Agency Support Telephone Number>`
  * Email address: `ITServiceDesk@Agency.gov.au`
  * Website name: -
  * Website URL: -
  * Additional information: -
* Configuration
  * Device enrollment: `Available, with prompts`
  * Privacy messages in Company Portal for iOS/iPadOS: `Default`
  * Privacy statement URL: - 
  * Send a push notification to users when their device ownership type changes from personal to corporate (Android and iOS/iPadOS only): `No`
  * Hide remove button on corporate Windows devices: `Yes`
  * Hide reset button on corporate Windows devices: `No`
  * Hide remove button on corporate iOS/iPadOS devices: `No`
  * Hide reset button on corporate iOS/iPadOS devices: `No`

## Add-ins

`Microsoft 365 Admin Center > Settings > Org settings > Services`

Item | Configuration
--- | ---
Azure Speech Services | Disabled
Power Automate (Flow) | Disabled
Power Apps | Disabled
Power Bi | Disabled
Bookings | Disabled
Calendar | Disabled
Cortana | Disabled
Integrated Apps | Disabled
Microsoft Forms | Send a link to the form and collect responses (enabled)<br>Share to collaborate on the form layout and structure (enabled)<br>Share the form as a template that can be duplicated (enabled)<br>Share form results summary (disabled)<br>Record names by default (disabled)<br>Include Bing search, YouTube videos (disabled)<br>Add internal phishing protection
Microsoft Graph Data Connect | Enabled
Microsoft Planner | Enabled
Microsoft Search in Bing | Disabled
Office What’s New management preview | Disabled
Modern Authentication | Enabled
MyAnalytics | Insights dashboard (enabled)<br>Weekly digest (enabled)<br>Insights Outlook add-in (enabled)<br>Allow Microsoft to contact me (Disabled)
External Office 365 group content sharing | Let group members outside your organization access content (Enabled)<br><br>Let group owners add people outside your organization (Enabled)
‎Office‎ software download settings | Disabled
Office on the web | Disabled
Reports | Disabled
SharePoint | New and existing guests – guests must sign in or provide a verification code – Enabled
Skype for Business | Disabled
Sway  | Disabled
User owned apps and services | Disabled
Whiteboard | Turn on Whiteboard for everyone in your org (enabled) <br>Level of diagnostic data to send to Microsoft (Neither)<br>Allow the use of optional connected experiences in Whiteboard (disabled)<br>Enable easy sharing of Whiteboard from Surface Hub (enabled)


## Security and privacy

Table 8 describes the Microsoft 365 Security and Privacy settings.

`Microsoft 365 admin center > Org Settings > Security & Privacy`

Item | Configuration
--- | ---
Customer lockbox | Enabled
Password expiration policy | Not configured
Privacy profile | Not configured
Self-service password reset | Not configured
Sharing | Not configured