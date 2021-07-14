---
layout: page
title: Teams
menu: abac
---

The ABAC settings for the Agency Teams instance can be found below. This includes the Teams Policy, Meetings Policy, Live Events Policy, Meetings Settings, Live Events Policy, Messaging Settings, Manage Apps, App Permission Policy, App Setup Policy, Calling Policy, Caller ID Policy, External Access Settings, Guest Access, and Team Settings. Please note, if a setting is not mentioned in the below, it should be assumed to have been left at its default setting.

## Teams policy

`Teams admin center > Teams > Teams policies`

Table 31 describes the Teams Policies configuration.

Item | Configuration
--- | ---
Name | Global
Discover private teams | Off
Create private channels | Off

## Meeting policy

`Teams admin center > Teams > Meeting policies`

* Name: `Global`
  * Custom policy: `No`
  * General
    * Allow Meet Now in channels: `On`
    * Allow the Outlook add-in: `On`
    * Allow scheduling private meetings: `On`
    * Allow channel meeting scheduling: `On`
  * Audio & Video
    * Allow transcription: `Off`
    * Allow cloud recording: `On`
    * Allow IP Video: `On`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `EntireScreen`
    * Allow Participant Give/Request Control: `On`
    * Allow External Participant Give/Request Control: `Off`
    * Allow PowerPoint Sharing: `On`
    * Allow Whiteboard: `Off`
    * Allow Shared Notes: `On`
  * Participants & guests
    * Let anonymous people to start a meeting: `Off`
    * Automatically admit users: `Everyone in your organization`
    * Allow dial-in users to bypass the lobby: `Off`
    * Allow Meet now in private messages: `On`
    * Enable live captions: `Disable but the organizer can override`
    * Allow chat in meetings: `Enable`
* Name: `AllOn`
  * Custom policy: `No`
  * General
    * Allow Meet Now in channels: `On`
    * Allow the Outlook add-in: `On`
    * Allow scheduling private meetings: `On`
    * Allow channel meeting scheduling: `On`
  * Audio & Video
    * Allow Transcription: `Off`
    * Allow cloud recording: `On`
    * Allow IP Video: `On`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `EntireScreen`
    * Allow Participant Give/Request Control: `On`
    * Allow External Participant Give/Request Control: `Off`
    * Allow PowerPoint Sharing: `On`
    * Allow Whiteboard: `On`
    * Allow Shared Notes: `On`
  * Participants & guests
    * Let anonymous people start a meeting: `Off`
    * Automatically admit people: `Everyone in your organization`
    * Allow dial-in users to bypass the lobby: `Off`
    * Allow meet now in private meetings: `On`
    * Enable live captions: `Disabled but the organizer can override`
    * Allow chat in meetings: `Enabled`
* Name: `RestrictedAnonymousAccess`
    * Custom policy: `No`
  * General
    * Allow Meet Now in channels: `On`
    * Allow the Outlook add-in: `On`
    * Allow scheduling private meetings: `On`
    * Allow channel meeting scheduling: `On`
  * Audio & Video
    * Allow Transcription: `Off`
    * Allow cloud recording: `On`
    * Allow IP Video: `On`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `EntireScreen`
    * Allow Participant Give/Request Control: `On`
    * Allow External Participant Give/Request Control: `Off`
    * Allow PowerPoint Sharing: `On`
    * Allow Whiteboard: `On`
    * Allow Shared Notes: `On`
  * Participants & guests
    * Let anonymous people start a meeting: `Off`
    * Automatically admit people: `Everyone in your organization`
    * Allow dial-in users to bypass the lobby: `Off`
    * Allow meet now in private meetings: `On`
    * Enable live captions: `Disabled`
    * Allow chat in meetings: `Enabled`
* Name: `AllOff`
    * Custom policy: `No`
  * General
    * Allow Meet Now in channels: `Off`
    * Allow the Outlook add-in: `Off`
    * Allow scheduling private meetings: `Off`
    * Allow channel meeting scheduling: `Off`
  * Audio & Video
    * Allow Transcription: `Off`
    * Allow cloud recording: `Off`
    * Allow IP Video: `Off`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `Disabled`
    * Allow Participant Give/Request Control: `Off`
    * Allow External Participant Give/Request Control: `Off`
    * Allow PowerPoint Sharing: `Off`
    * Allow Whiteboard: `Off`
    * Allow Shared Notes: `Off`
  * Participants & guests
    * Let anonymous people start a meeting: `Off`
    * Automatically admit people: `Everyone in your organization`
    * Allow dial-in users to bypass the lobby: `Off`
    * Allow meet now in private meetings: `Off`
    * Enable live captions: `Disabled`
    * Allow chat in meetings: `Disabled`
* Name: `RestrictedAnonymousNoRecording`
    * Custom policy: `No`
  * General
    * Allow Meet Now in channels: `On`
    * Allow the Outlook add-in: `On`
    * Allow scheduling private meetings: `On`
    * Allow channel meeting scheduling: `On`
  * Audio & Video
    * Allow Transcription: `Off`
    * Allow cloud recording: `Off`
    * Allow IP Video: `On`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `EntireScreen`
    * Allow Participant Give/Request Control: `On`
    * Allow External Participant Give/Request Control: `Off`
    * Allow PowerPoint Sharing: `On`
    * Allow Whiteboard: `On`
    * Allow Shared Notes: `On`
  * Participants & guests
    * Let anonymous people start a meeting: `Off`
    * Automatically admit people: `Everyone in your organization`
    * Allow dial-in users to bypass the lobby: `Off`
    * Allow meet now in private meetings: `On`
    * Enable live captions: `Disabled`
    * Allow chat in meetings: `Enabled`
* Name: `Kiosk`
    * Custom policy: `No`
  * General
    * Allow Meet Now in channels: `On`
    * Allow the Outlook add-in: `Off`
    * Allow scheduling private meetings: `Off`
    * Allow channel meeting scheduling: `Off`
  * Audio & Video
    * Allow Transcription: `Off`
    * Allow cloud recording: `Off`
    * Allow IP Video: `On`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `EntireScreen`
    * Allow Participant Give/Request Control: `On`
    * Allow External Participant Give/Request Control: `Off`
    * Allow PowerPoint Sharing: `On`
    * Allow Whiteboard: `On`
    * Allow Shared Notes: `On`
  * Participants & guests
    * Let anonymous people start a meeting: `Off`
    * Automatically admit people: `Everyone in your organization`
    * Allow dial-in users to bypass the lobby: `Off`
    * Allow meet now in private meetings: `On`
    * Enable live captions: `Disabled`
    * Allow chat in meetings: `Enabled`
* Name: `Custom All On Policy`
    * Custom policy: `Yes`
  * General
    * Allow Meet Now in channels: `On`
    * Allow the Outlook add-in: `On`
    * Allow scheduling private meetings: `On`
    * Allow channel meeting scheduling: `On`
  * Audio & Video
    * Allow Transcription: `On`
    * Allow cloud recording: `On`
    * Allow IP Video: `On`
    * Media bit rate: `50000`
  * Content sharing
    * Screen Sharing Mode: `EntireScreen`
    * Allow Participant Give/Request Control: `On`
    * Allow External Participant Give/Request Control: `On`
    * Allow PowerPoint Sharing: `On`
    * Allow Whiteboard: `On`
    * Allow Shared Notes: `On`
  * Participants & guests
    * Let anonymous people start a meeting: `Off`
    * Automatically admit people: `Everyone`
    * Allow dial-in users to bypass the lobby: `On`
    * Allow meet now in private meetings: `On`
    * Enable live captions: `Disabled but the organizer can override`
    * Allow chat in meetings: `Enabled`

## Live events policy

`Teams admin center > Live events policies > Global`

* Custom policy: `No`
* Allow scheduling: `On`
* Allow transcription for attendees: `On`
* Who can join scheduled live events: `Everyone in the organization`
* Who can record an event: `Always record`

`Teams admin center > Live events policies > Live Events Organisers`

* Custom policy: `Yes`
* Allow scheduling: `On`
* Allow transcription for attendees: `On`
* Who can join scheduled live events: `Everyone in the organization`
* Who can record an event: `Always record`

## Meeting settings

`Teams admin center > Meetings > Meeting settings > participants`

* Anonymous users can join a meeting: `On`

`Teams admin center > Meetings > Meeting settings > Email invitation`

* Logo URL: `Not configured`
* Legal URL: `Not configured`
* Help URL: `Not configured`
* Footer: `Not configured`

`Teams admin center > Meetings > Meeting settings > Network`

* Insert Quality of Service (QoS) markers for real-time media traffic: `Off`
* Select a port range for each type of real time media traffic: `Specify port ranges`

Media traffic type | Starting port | Ending port | Total ports
--- | --- | --- | ---
Audio | 50000 | 50019 | 20
Video | 50020 | 50039 | 20
Screen sharing | 50040 | 50059 | 20

## Live events settings

`Teams admin center > Meetings > Live events settings`

* Support URL
  * Customize the support URL if a user needs to contact support during a live event: `https://support.office.com/home/contact`
* Third party video distribution providers
  * Use a third party distribution provider: `Off`

## Messaging policy

`Teams admin center > Messaging policies \ Global`

* Name: `Global (Org-wide default)`
* Description: `Global Teams Messaging Policy`
* Owners can delete sent messages: `Off`
* Delete sent messages: `On`
* Edit sent message: `On`
* Read receipts: `User Controlled`
* Chat: `On`
* Use Giphys in conversation : `On`
* Giphy content rating : `Strict`
* Use Memes in conversations: `On`
* Use Stickers in conversations: `On`
* Allow URL previews: `On`
* Translate messages: `Off`
* Allow Immersive Reader for viewing messages: `On`
* Send urgent messages using priority notifications: `On`
* Create voice messages: `Allowed in chats and channels`
* On mobile devices, display favorite channels above recent chats: `Disabled`
* Remove users from group chats: `On`

## Manage apps

`Teams admin center > Team apps > Manage apps > Org-wide app settings > Third party apps`

* Allow third party apps: `Off`
* Allow any new third party apps published to the store by default: `Off`

`Teams admin center > Team apps > Manage apps > Org-wide app settings > Custom apps`

* Allow interaction with custom apps: `Off`

## App permission policy

`Teams admin center > Team apps > Permission policies \ Global > Microsoft apps`

* Choose which Teams apps published by Microsoft or its partners can be installed by your users: `Allow all apps`

`Teams admin center > Team apps > Permission policies \ Global > Third party apps`

* Choose which Teams apps published by a third-party that can be installed by your users: `Block all apps`

`Teams admin center > Team apps > Permission policies \ Global > Custom apps`

* Choose which custom apps can be installed by your users: `Block all apps`

`Teams admin center > Team apps > Permission policies \ App Reviewers > Microsoft apps`

* Choose which Teams apps published by Microsoft or its partners can be installed by your users: `Allow all apps`

`Teams admin center > Team apps > Permission policies \ App Reviewers > Third party apps`

* Choose which Teams apps published by a third-party that can be installed by your users: `Allow all apps`

`Teams admin center > Team apps > Permission policies \ App Reviewers > Custom apps`

* Choose which custom apps can be installed by your users: `Allow all apps`

## App setup policy

`Teams admin center > Team apps > Setup policies \ FirstLineWorker`

* Upload custom apps: `Off`
* Allow user pinning: `On`

`Teams admin center > Team apps > Setup policies \ FirstLineWorker > Pinned apps`

Name | Distributor
--- | ---
Activity | Microsoft
Shifts | Microsoft Corp.
Chat | Microsoft
Calling | Microsoft

`Teams admin center > Team apps > Setup policies \ Global`

* Upload custom apps: `Off`
* Allow user pinning: `On`

`Teams admin center > Team apps > Setup policies \ Global > Pinned apps`

Name | Distributor
--- | ---
Activity | Microsoft
Chat | Microsoft
Teams | Microsoft
Calendar | Microsoft
Calling | Microsoft
Files | Microsoft

## Calling policy

`Teams admin center > Voice > Calling polices > Global (org-wide default)`

* Name: `Global`
* Description: `Not Configured`
* Make private calls: `On`
* Call forwarding and simultaneous ringing to people in your organization: `On`
* Call forwarding and simultaneous ringing to external phone numbers: `On`
* Voicemail is available for routing inbound calls: `User controlled`
* Inbound calls can be routed to call groups: `On`
* Allow delegation for inbound and outbound calls: `On`
* Prevent toll bypass and send calls through the PSTN: `Off`
* Busy on busy is available when in a call: `Off`
* Allow web PSTN calling: `On`

`Teams admin center > Voice > Calling policies > AllowCalling`

* Name: `Tag:AllowCalling`
* Description: `Not Configured`
* Make private calls: `On`
* Call forwarding and simultaneous ringing to people in your organization: `On`
* Call forwarding and simultaneous ringing to external phone numbers: `On`
* Voicemail is available for routing inbound calls: `User controlled`
* Inbound calls can be routed to call groups: `On`
* Allow delegation for inbound and outbound calls: `On`
* Prevent toll bypass and send calls through the PSTN: `Off`
* Busy on busy is available when in a call: `Off`
* Allow web PSTN calling: `On`

`Teams admin center > Voice > Calling policies > DisallowCalling`

* Name: `Tag:DisallowCalling`
* Description: `Not Configured`
* Make private calls: `Off`
* Call forwarding and simultaneous ringing to people in your organization: `Off`
* Call forwarding and simultaneous ringing to external phone numbers: `Off`
* Voicemail is available for routing inbound calls: `Disabled`
* Inbound calls can be routed to call groups: `Off`
* Allow delegation for inbound and outbound calls: `Off`
* Prevent toll bypass and send calls through the PSTN: `Off`
* Busy on busy is available when in a call: `Off`
* Allow web PSTN calling: `On`

## Caller ID policy

`Teams admin center > Voice > Caller ID policies > Global`

* Block incoming caller ID: `Off`
* Override the caller ID policy: `Off`
* Replace the caller ID with : `User’s Number`
* Replace the caller ID with this service number : `Not configured`

## External access settings

`Teams admin center > Org-wide settings > External access`

* Users can communicate with other Skype for Business and Teams users: `On`
* Users can communicate with Skype users: `Off`
* Domain:

```
<Agency>.gov.au: Allowed
microsoft.com: Allowed
```

## Guest access

`Teams admin center > Org-wide settings > Guest Access`

* Allow guest access in Teams: `On`

`Teams admin center > Org-wide settings > Guest Access > Calling`

* Make private calls: `Off`

`Teams admin center > Org-wide settings > Guest Access > Meeting`

* Allow IP video: `On`
* Screen sharing mode: `Entire screen`
* Allow Meet Now : `On`

`Teams admin center > Org-wide settings > Guest Access > Messaging`

* Edit sent messages: `Off`
* Delete sent messages: `Off`
* Chat: `On`
* Use Giphys in conversation: `On`
* Giphy content rating: `Moderate`
* Use Memes in conversations : `On`
* Use Stickers in conversations : `On`
* Allow immersive reader for viewing messages : `On`

## Team settings

`Teams admin center > Org-wide settings > Team settings > Notifications and feeds`

* Suggested feeds can appear in a user's activity feed: `On`

`Teams admin center > Org-wide settings > Team settings > Tagging`

* Tagging is enabled for:: `Team owners
* Team owner can override who can apply tags: `On`
* Members can add additional tags: `On`
* Suggested default tags: -

`Teams admin center > Org-wide settings > Team settings > Email integration`

* Allow users to send emails to a channel email address: `On`
* Accept channel email from these SMTP domains: `<Agency>.gov.au`

`Teams admin center > Org-wide settings > Team settings > Files`

* Turn on or turn off file sharing and cloud file storage options for the Files tab:

```
Citrix files: off
DropBox: off
Box: off
Google Drive: off
```

`Teams admin center > Org-wide settings > Team settings > Organization`

* Show Organization tab in chats: `On`

`Teams admin center > Org-wide settings > Team settings > Devices`

* Require a secondary form of authentication to access meeting content: `No access`
* Set content PIN: `Required for outside scheduled meeting`
* Resource accounts can send messages: `On`

`Teams admin center > Org-wide settings > Team settings > Search by name`

* Scope directory search using an Exchange address book policy: `Off`
