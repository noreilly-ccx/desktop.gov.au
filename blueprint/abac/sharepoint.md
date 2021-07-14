---
layout: page
title: SharePoint
menu: abac
---

The ABAC settings for the Agency SharePoint Online instance can be found below. This includes the Sharing Configuration, Access Control and SharePoint Settings. Please note, if a setting is not mentioned in the below, it should be assumed to have been left at its default setting.

## Sharing

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

## Access control

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

## SharePoint settings

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