---
layout: page
title: Exchange Online
menu: abac
---

The ABAC settings for the Agency Exchange Online instance can be found below. This includes Connectors, Mail Exchange (MX) Records, SPF, DNS Records, Accepted and Remote Domains, Client Access Services (CAS) Mailbox Plan, Authentication Policy, Outlook Web Access Policy, Mailbox Archive and Auditing, Mail Flow Rules, Journaling, Mailbox Retention, Shared and Resource Mailboxes, Distribution, Dynamic and Microsoft 365 groups. Please note, if a setting is not mentioned in the below, it should be assumed to have been left at its default setting.

## Connectors

`Exchange admin center > Mail flow > Connectors`

Table 9a describes the Exchange Online inbound mail connectors

Item | Configuration
--- | ---
From | Your Organization's email server
To | Office 365
Description | None
Status | On
Retain internal Exchange email headers (recommended) | Enable
How to identify your organization | Identify the organization by verifying that messages are coming Inbound from xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Security restrictions | Reject messages if they aren’t encrypted using Transport Layer Security ‎(TLS)‎, or the subject name on the certificate that the organization uses to authenticate with Office 365 doesn’t‎ match this domain name: *.Agency.gov.au

Table 9b describes the Exchange Online outbound mail connectors

Item | Configuration
--- | ---
From | Office 365
To | Your Organization’s email server
Description | None
Status | On
Retain internal Exchange email headers (recommended) | Enable
How to identify your organization | Identify the organization by verifying that messages are going outbound from xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
When to use the connector | Only when email messages are sent to these domains: *
Routing method | Route email messages through these smart hosts: Agency.gov.au
Security restrictions | Always use Transport Layer Security ‎(TLS)‎ and connect only if the recipient’s email server certificate is issued by a trusted certificate authority ‎(CA)‎, and the subject name matches this domain: mail.Agency.gov.au

## MX records

Table 10 describes the MX records that have been configured.

These records are not set within Azure or Exchange and have been configured with the hosting provider.

Domain | MX Preferences | Mail Exchanger
--- | --- | ---
Agency.onmicrosoft.com | `0` | `Agency.mail.protection.outlook.com`

## SPF records

Table 11 describes the SPF records have been configured.

These records are not set within Azure or Exchange and have been configured with the hosting provider.

Domain | SPF Record | DMARC Policy
--- | --- | ---
Agency.onmicrosoft.com | `"v=spf1 include:spf.protection.outlook.com -all"` | Not configured`

## DNS records

Table 12a describes the DNS record settings for Agency.gov.au (default)

Type | Priority | Host name | Points to address or value | TTL
--- | --- | --- | --- | ---
MX | 0 | Agency Domain | Agency-gov-au.mail.protection.outlook.com | 1 hour
TXT | - | Agency Domain | v=spf1 include:spf.protection.outlook.com -all | 1 hour
CNAME | - | Autodiscover.Agency Domain | Autodiscover.outlook.com | 1 hour

Table 12b describes the DNS record settings for Agency.onmicrosoft.com

Type | Host name | Points to address or value | TTL
--- | --- | --- | ---
TXT | `selector1-Agency-mail-onmicrosoft-com._domainkey.Agency.onmicrosoft.com` | `v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCff/x+ZR9dYMl+d137AAu0aM7u0keutv/J+YdV1vegammbcwgnu7IrFFuS1WpOWiyc1IUp/XoskpKPHpA9k6L/UafJjTxI+KI2nrx7qgY7DXFqTsHIEVZDpdnMZOHmooW24i7HZ/0Yh/ZSkUYr1mE/MoUnS77PgYRDT+BjuG5lnQIDAQAB;` | 1 hour
TXT | `selector1-Agency-onmicrosoft-com._domainkey.Agency.onmicrosoft.com` | `v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDaUXUBDLyhaVehWKVTyJHQA1TIpu34b9dh3dZaaEMfiq5vHV2Mrs5r+H+nfNtxIfxAaOPyMLTEPhIipmeie2qQSbm+pUCAj09s/fOZqjwYZ0Y4/6RfNe0VzawvX4Fls9NbuZaiEe6PN5kqABzEq755bfJMLqVT+gzXZuea+K5SIQIDAQAB;` | 1 hour
TXT | `selector1-Agency-gov-au._domainkey.Agency.onmicrosoft.com` | `v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDejs4tfJJ9cwb/aCteu+IPMEjoJI4z5Jir3Y5eK0vREh0FSpir/qBk6tH5xPMSDFsH8qWErOTN57mZ6E8IB4CTgxI0kakYmZJr9USAoyUJNCrgjuwcJ9cNcKqJmkYAo4/dUO6B80SKT8pNIzkSrhq92Y6CejFPm1zUYTL8CZOypQIDAQAB;` | 1 hour
TXT | `selector2-Agency-mail-onmicrosoft-com._domainkey.Agency.onmicrosoft.com `| `v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQC9HlySKa1sSUdHI8WkaUEiINtRLExcis6p+R7p3DKzTEe3Ir0k9IPj3o0hp0mNfWZ62b8uOBhTir9ZTwdGP6Yr2UehFDWgz+nrEXQA0XFOfXiU+BHPW3XVy6rLRD/9jFqmnLuZi3I2CVmsVO/cdiMjoDwj5qbCvD3DCwWXkGHK5QIDAQAB;` | 1 hour
TXT | `selector2-Agency-onmicrosoft-com._domainkey.Agency.onmicrosoft.com` | `v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCvReE2Is6fDDFtKI/JEcNDOrIuEm3ry+PACwEEwzHuu5UW0nv1nQfQqnR61xz/o+HOR7GZLgu1DjfMWB9EUaub/yaNGrt/qn7X9rcaLRiK9UW+c/TuC4DkSuH+Ks0MmfUYp7UhiBIWaBTCx47qkvVE6qU8AZuwvt7hB8TF4Cyr9QIDAQAB;` | 1 hour
TXT | `selector2-Agency-gov-au._domainkey.Agency.onmicrosoft.com` | `v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCsk8uDLWkqiD80eR5aNtnwZgH31CqWFHpF2hYd8FEIeWfJtYwQ77JhHNBVsPc1IxwuHYSH1DN0xn9CZ8eLaKiyykOZpLWhozMSYLNB944+FCDZzT8rKhrBAOQ0Gsv1CKYbNHkOwvIePmy2eFQOS0CfFNU7dIHnnqPfjFxfs9ErQQIDAQAB;` | 1 hour

## Accepted domains

`Exchange Admin Centre > mail flow > Accepted domains`

Table 13 describes the Accepted Domains settings.

Name | Accepted Domain | Domain Type
--- | --- | ---
Agency.gov.au (default) | Agency.gov.au | Authoritative
Agency.onmicrosoft.com | Agency.onmicrosoft.com | Authoritative
Agency.mail.onmicrosoft.com | Agency.mail.onmicrosoft.com | Authoritative

## Remote domains

Table 14 describes the Remote Domains have been configured.

Item | Configuration
--- | ---
Name | Default
Remote Domain | *
Allowed Out Of Office Type | External only
Automatic Reply | False
Automatic Forward | False
Delivery Reports | True
Non-Delivery Reports | True
Meeting Forward Notifications | False
Display Sender Name | True
Trusted Mail Outbound Enabled | False
Trusted Mail Inbound Enabled | False
Use Simple Display Name | False
Non-Delivery Report Diagnostic Info Enabled | True
Use rich-text format | Follow users’ settings
MIME character set | None
Non-MIME character set | None

## CAS mailbox plan

Table 15 describes the CAS Mailbox Plans that have been configured. These settings have been configured with PowerShell.

Item | Configuration
--- | ---
Name | ExchangeOnlineEnterprise
ActiveSyncMailboxPolicy | --
ActiveSyncDebugLogging | False
ActiveSyncEnabled | True
ActiveSyncSuppressReadReceipt | False
DisplayName | ExchangeOnlineEnterprise
ECPEnabled | True
ImapEnabled | False
ImapUseProtocolDefaults | True
ImapMessagesRetrievalMimeFormat | BestBodyFormat
ImapEnableExactRFC822Size | False
ImapProtocolLoggingEnabled | False
ImapSuppressReadReceipt | False
ImapForceICalForCalendarRetrievalOption | False
MAPIEnabled | True
MapiHttpEnabled | --
MAPIBlockOutlookNonCachedMode | False
MAPIBlockOutlookVersions | --
MAPIBlockOutlookRpcHttp | False
PublicFolderClientAccess | False
MAPIBlockOutlookExternalConnectivity | False
OwaMailboxPolicy | OwaMailboxPolicy-Default
OWAEnabled | True
OWAforDevicesEnabled | True
PopEnabled | False
PopMessageDeleteEnabled | True
PopUseProtocolDefaults | True
PopMessagesRetrievalMimeFormat | BestBodyFormat
PopEnableExactRFC822Size | False
PopProtocolLoggingEnabled | False
PopSuppressReadReceipt | False
PopForceICalForCalendarRetrievalOption | True
RemotePowerShellEnabled | True
UniversalOutlookEnabled | True
OutlookMobileEnabled | True
MacOutlookEnabled | True
EwsEnabled | True
EwsAllowOutlook | --
EwsAllowMacOutlook | --
EwsAllowEntourage | --
EwsApplicationAccessPolicy | --
EwsAllowList | --
EwsBlockList | --
IsValid | True
Name | ExchangeOnlineDeskless
ActiveSyncDebugLogging | False
ActiveSyncEnabled | True
ActiveSyncMailboxPolicy | --
ActiveSyncSuppressReadReceipt | False
DisplayName | ExchangeOnlineDeskless
ECPEnabled | True
EwsAllowEntourage | --
EwsAllowList | --
EwsAllowMacOutlook | --
EwsAllowOutlook | --
EwsApplicationAccessPolicy | --
EwsBlockList | --
EwsEnabled | False
ImapEnabled | False
ImapEnableExactRFC822Size | False
ImapForceICalForCalendarRetrievalOption | False
ImapMessagesRetrievalMimeFormat | BestBodyFormat
ImapProtocolLoggingEnabled | False
ImapSuppressReadReceipt | False
ImapUseProtocolDefaults | True
IsValid | True
MacOutlookEnabled | True
MAPIBlockOutlookExternalConnectivity | False
MAPIBlockOutlookNonCachedMode | False
MAPIBlockOutlookRpcHttp | False
MAPIBlockOutlookVersions | --
MAPIEnabled | False
MapiHttpEnabled | --
OutlookMobileEnabled | True
OWAEnabled | True
OWAforDevicesEnabled | True
OwaMailboxPolicy | OwaMailboxPolicy-Default
PopEnabled | False
PopEnableExactRFC822Size | False
PopForceICalForCalendarRetrievalOption | True
PopMessageDeleteEnabled | True
PopMessagesRetrievalMimeFormat | BestBodyFormat
PopProtocolLoggingEnabled | False
PopSuppressReadReceipt | False
PopUseProtocolDefaults | True
PublicFolderClientAccess | False
RemotePowerShellEnabled | True
UniversalOutlookEnabled | True
Name | ExchangeOnlineEssentials
ActiveSyncMailboxPolicy |  --
ActiveSyncDebugLogging  | False
ActiveSyncEnabled | True
ActiveSyncSuppressReadReceipt | False
ECPEnabled  | True
ImapEnabled | False
ImapUseProtocolDefaults | True
ImapMessagesRetrievalMimeFormat | BestBodyFormat
ImapEnableExactRFC822Size | False
ImapProtocolLoggingEnabled | False
ImapSuppressReadReceipt | False
ImapForceICalForCalendarRetrievalOption  | False
MAPIEnabled | True
MapiHttpEnabled |  --
MAPIBlockOutlookNonCachedMode | False
MAPIBlockOutlookVersions  |  --
MAPIBlockOutlookRpcHttp | False
PublicFolderClientAccess  | False
MAPIBlockOutlookExternalConnectivity  | False
OwaMailboxPolicy  | OwaMailboxPolicy-Default
OWAEnabled  | True
OWAforDevicesEnabled | True
PopEnabled  | False
PopMessageDeleteEnabled | True
PopUseProtocolDefaults  | True
PopMessagesRetrievalMimeFormat  | BestBodyFormat
PopEnableExactRFC822Size  | False
PopProtocolLoggingEnabled | False
PopSuppressReadReceipt  | False
PopForceICalForCalendarRetrievalOption | True
RemotePowerShellEnabled | True
UniversalOutlookEnabled | True
OutlookMobileEnabled | True
MacOutlookEnabled | True
EwsEnabled  | True
EwsAllowOutlook | --
EwsAllowMacOutlook | --
EwsAllowEntourage | --
EwsApplicationAccessPolicy | --
EwsAllowList | --
EwsBlockList | --
IsValid  | True
Name | ExchangeOnline
ActiveSyncMailboxPolicy | --
ActiveSyncDebugLogging  | False
ActiveSyncEnabled | True
ActiveSyncSuppressReadReceipt | False
ECPEnabled | True
ImapEnabled | False
ImapUseProtocolDefaults | True
ImapMessagesRetrievalMimeFormat | BestBodyFormat
ImapEnableExactRFC822Size | False
ImapProtocolLoggingEnabled | False
ImapSuppressReadReceipt | False
ImapForceICalForCalendarRetrievalOption | False
MAPIEnabled | True
MapiHttpEnabled | --
MAPIBlockOutlookNonCachedMode | False
MAPIBlockOutlookVersions | --
MAPIBlockOutlookRpcHttp | False
PublicFolderClientAccess | False
MAPIBlockOutlookExternalConnectivity | False
OwaMailboxPolicy | OwaMailboxPolicy-Default
OWAEnabled | True
OWAforDevicesEnabled | True
PopEnabled | False
PopMessageDeleteEnabled | True
PopUseProtocolDefaults | True
PopMessagesRetrievalMimeFormat | BestBodyFormat
PopEnableExactRFC822Size | False
PopProtocolLoggingEnabled | False
PopSuppressReadReceipt | False
PopForceICalForCalendarRetrievalOption | True
RemotePowerShellEnabled | True
UniversalOutlookEnabled | True
OutlookMobileEnabled | True
MacOutlookEnabled | True
EwsEnabled | True
EwsAllowOutlook | --
EwsAllowMacOutlook | --
EwsAllowEntourage | --
EwsApplicationAccessPolicy | --
EwsAllowList | --
EwsBlockList | --
IsValid | True

## Mailbox attributes

Below describes the Mailbox attribute that have been configured. These settings have been configured with PowerShell.

`Exchange Admin Center > recipients > mailboxes > <username> > mailbox features`

* Litigation hold: `False` (configured as true only when required)`

`Exchange Admin Center > recipients > mailboxes > <username> > mailbox usage`

* Exchange Mailbox Size: `100GB per user`

`Exchange Admin Center > recipients > mailboxes > three dots > Set default message size restrictions`

* Maximum szie for sent messages (KB): `90MB`
* Maximum size for received messages (KB): `90MB`

`Exchange Admin Center > recipients > mailboxes > <username> > email address`

* Custom Primary SMTP Addressing: `FirstName.LastName@<Agency>.gov.au`
* Language: `English (en-au)`
* Default Time Zone: `GMT +10 (AUS Eastern Standard Time)`
* Exchange Online PowerShell
  * Disabled for standard users: `True`

## Authentication policy

Table 17 describes the Authentication Policies that have been configured. These settings have been configured using PowerShell.

Item | Configuration
--- | ---
Name | Block Basic Auth
Allow Basic Authentication ActiveSync | False
Allow Basic Authentication Autodiscover | False
Allow Basic Authentication IMAP | False
Allow Basic Authentication MAPI | False
Allow Basic Authentication Offline AddressBook | False
Allow Basic Authentication Outlook Service | False
Allow Basic Authentication POP | False
Allow Basic Authentication Reporting Web Services | False
Allow Basic Authentication Rest | False
Allow Basic Authentication RPC | False
Allow Basic Authentication SMTP | False
Allow Basic Authentication Web Services | False
Allow Basic Authentication PowerShell | False
Admin Display Name | --
Is Valid | True

## Outlook Web Access policy

Table 18 describes the Outlook Web Access Policies have been configured. These settings have been configured using PowerShell.

Item | Configuration
--- | ---
Name | OwaMailboxPolicy-Default
WacEditingEnabled | True
PrintWithoutDownloadEnabled | True
OneDriveAttachmentsEnabled  | True
ThirdPartyFileProvidersEnabled | False
AdditionalStorageProvidersAvailable  | False
ClassicAttachmentsEnabled | True
ReferenceAttachmentsEnabled | True
SaveAttachmentsToCloudEnabled  | True
InternalSPMySiteHostURL  | --
ExternalSPMySiteHostURL  | --
ExternalImageProxyEnabled | True
NpsSurveysEnabled | False
MessagePreviewsDisabled  | False
PersonalAccountCalendarsEnabled | True
TeamsnapCalendarsEnabled | True
BookingsMailboxCreationEnabled | True
DirectFileAccessOnPublicComputersEnabled | True
DirectFileAccessOnPrivateComputersEnabled | True
WebReadyDocumentViewingOnPublicComputersEnabled | True
WebReadyDocumentViewingOnPrivateComputersEnabled | True
ForceWebReadyDocumentViewingFirstOnPublicComputers | False
ForceWebReadyDocumentViewingFirstOnPrivateComputers | False
WacViewingOnPublicComputersEnabled | True
WacViewingOnPrivateComputersEnabled  | True
ForceWacViewingFirstOnPublicComputers  | False
ForceWacViewingFirstOnPrivateComputers | False
ActionForUnknownFileAndMIMETypes | Allow
WebReadyFileTypes | {.xlsx, .pptx, .docx, .xls...}
WebReadyMimeTypes | {application/vnd.openxmlformats-officedocument.presentationml.presentation, application/vnd.openxmlformats-officedocument.wordprocessingml.document, application/vnd.openxmlformats-officedocument.spreadsheetml.sheet, application/vnd.ms-powerpoint...}
WebReadyDocumentViewingForAllSupportedTypes  | True
WebReadyDocumentViewingSupportedMimeTypes | {application/msword, application/vnd.ms-excel,application/x-msexcel, application/vnd.ms-powerpoint...}
WebReadyDocumentViewingSupportedFileTypes | {.doc, .dot, .rtf, .xls...}
AllowedFileTypes | {.rpmsg, .xlsx, .xlsm, .xlsb...}
AllowedMimeTypes | {image/jpeg, image/png, image/gif, image/bmp}
ForceSaveFileTypes | {.svgz, .html, .xml, .swf...}
ForceSaveMimeTypes | {Application/x-shockwave-flash, Application/octet-stream,Application/futuresplash, Application/x-director...}
BlockedFileTypes | {.settingcontent-ms, .printerexport, .appcontent-ms,.appref-ms...}
BlockedMimeTypes | {application/x-javascript, application/javascript,application/msaccess, x-internet-signup...}
PhoneticSupportEnabled | False
DefaultTheme | 
IsDefault | True
DefaultClientLanguage | 0
LogonAndErrorLanguage | 0
UseGB18030 | False
UseISO885915 | False
OutboundCharset | AutoDetect
GlobalAddressListEnabled | True
OrganizationEnabled | True
ExplicitLogonEnabled | True
OWALightEnabled | True
DelegateAccessEnabled | True
IRMEnabled | True
CalendarEnabled | True
ContactsEnabled | True
TasksEnabled | True
JournalEnabled | True
NotesEnabled | True
OnSendAddinsEnabled | False
RemindersAndNotificationsEnabled  | True
PremiumClientEnabled | True
SpellCheckerEnabled | True
SearchFoldersEnabled | True
SignaturesEnabled | True
ThemeSelectionEnabled | True
JunkEmailEnabled | True
UMIntegrationEnabled | True
WSSAccessOnPublicComputersEnabled | True
WSSAccessOnPrivateComputersEnabled | True
ChangePasswordEnabled | True
UNCAccessOnPublicComputersEnabled | True
UNCAccessOnPrivateComputersEnabled | True
ActiveSyncIntegrationEnabled | True
AllAddressListsEnabled | True
RulesEnabled | True
PublicFoldersEnabled | True
SMimeEnabled | True
RecoverDeletedItemsEnabled | True
InstantMessagingEnabled | True
TextMessagingEnabled | True
ForceSaveAttachmentFilteringEnabled | False
SilverlightEnabled | True
InstantMessagingType | Ocs
DisplayPhotosEnabled | True
SetPhotoEnabled | True
AllowOfflineOn | Always
SetPhotoURL | --
PlacesEnabled | True
WeatherEnabled | True
LocalEventsEnabled | False
InterestingCalendarsEnabled | True
AllowCopyContactsToDeviceAddressBook | True
PredictedActionsEnabled | False
UserDiagnosticEnabled | False
FacebookEnabled | False
LinkedInEnabled | True
WacExternalServicesEnabled  | True
WacOMEXEnabled | False
ReportJunkEmailEnabled | True
GroupCreationEnabled | True
SkipCreateUnifiedGroupCustomSharepointClassification  | True
WebPartsFrameOptionsType | SameOrigin
UserVoiceEnabled | True
SatisfactionEnabled | False
FreCardsEnabled | True
ConditionalAccessPolicy | Off
ConditionalAccessFeatures | {}
OutlookBetaToggleEnabled | True
AdminDisplayName | --
DistinguishedName | CN=OwaMailboxPolicy-Default,CN=OWA Mailbox Policies,CN=Configuration, ,CN=Agency.onmicrosoft.com, CN=ConfigurationUnits,DC=exchange server,DC=PROD, DC=OUTLOOK,DC=COM
Identity | OwaMailboxPolicy-Default
IsValid | True
ObjectState | Unchanged
Third party file provider integration | Disabled
Office 365 group creation by users | Disabled

## Mailbox archive

`Exchange Admin Center > recipients > mailboxes > <username> > mailbox features`

Table 19 describes the mailbox archive settings. These settings can only be configured using the On-Premises Exchange Administrator console.

Item | Configuration
--- | ---
Archiving | Enabled
Auto-Expanding Archive (via Powershell command) | Enabled
Archive Configuration | Configured

## Mailbox auditing

Table 20 describes the mailbox archive settings. These settings have been configured using PowerShell.

Item | Configuration
--- | ---
Mailbox Auditing | Enabled
Centralized Logging | Not configured

User Mailbox and Shared Mailbox Audit Configuration

Item | Configuration
--- | ---
Admin Audit Actions | ApplyRecord<br>Copy<br>Create<br>FolderBind<br>HardDelete<br>MessageBind<br>Move<br>MoveToDeletedItems<br>RecordDelete<br>SendAs<br>SendOnBehalf<br>SoftDelete<br>Update<br>UpdateCalendarDelegation<br>UpdateFolderPermissions<br>UpdateInboxRules
Delegated Audit Actions | ApplyRecord<br>Create<br>FolderBind<br>HardDelete<br>Move<br>MoveToDeletedItems<br>RecordDelete<br>SendAs<br>SendOnBehalf<br>SoftDelete<br>Update<br>UpdateFolderPermissions<br>UpdateInboxRules
Owner Audited Actions | ApplyRecord<br>Create<br>HardDelete<br>MailboxLogin<br>Move<br>MoveToDeletedItems<br>RecordDelete<br>SoftDelete<br>Update<br>UpdateCalendarDelegation<br>UpdateFolderPermissions<br>UpdateInboxRules

## Mail flow rules

`Exchange Admin Centre > mail flow > rules`

### Disclaimer

* Apply this rule if: The recipient is located `Outside the organization`
* Do the following actions: Append the message with the disclaimer

```
'<br/>
<br/>
<p style="font-size:8pt; line-height:10pt; font-family: 'Cambria','times roman',serif;">The content of this email is confidential and intended for the recipient specified in message only. It is strictly forbidden to share any part of this message with any third party, without a written consent of the sender. If you received this message by mistake, please reply to this message and follow with its deletion, so that we can ensure such a mistake does not occur in the future.</p>'. 
```

* If the disclaimer can't be applied, reject the message.
* ExceptIfSubjectMatchesPatterns: -
* FromScope: -
* HeaderContainsMessageHeader: -
* HeaderContainsWords: -
* Mode: `Enforce`
* Name: `Disclaimer`
* PrependSubject: -
* Priority: `0`
* SentToScope: `NotInOrganization`
* State: `Enabled`

### UNOFFICIAL

* If the message: Is sent to `Inside the organization` **and** `msip_labels` header contains `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true` **and** Is received from `Inside the organization`
* Take the following actions: Prepend the subject with `[SEC=UNOFFICIAL]`
* Except if the message: Includes these patterns in the message subject: `(SEC=UNOFFICIAL)`
* ExceptIfSubjectMatchesPatterns: `(SEC=UNOFFICIAL)`
* FromScope: `InOrganization`
* HeaderContainsMessageHeader: `msip_labels`
* HeaderContainsWords: `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true`
* Mode: `Enforce`
* Name: `UNOFFICIAL`
* PrependSubject: `[SEC=UNOFFICIAL]`
* Priority: `1`
* SentToScope: `InOrganization`
* State: `Enabled`

### OFFICIAL

* If the message: Is sent to `Inside the organization` **and** `msip_labels` header contains `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true` **and** Is received from `Inside the organization`
* Take the following actions: Prepend the subject with `[SEC=OFFICIAL]`
* Except if the message: Includes these patterns in the message subject: `(SEC=OFFICIAL)`
* ExceptIfSubjectMatchesPatterns: `(SEC=OFFICIAL)`
* FromScope: `InOrganization`
* HeaderContainsMessageHeader: `msip_labels`
* HeaderContainsWords: `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true`
* Mode: `Enforce`
* Name: `OFFICIAL`
* PrependSubject: `[SEC=OFFICIAL]`
* Priority: `2`
* SentToScope: `InOrganization`
* State: `Enabled`

### OFFICIAL:Sensitive

* If the message: Is sent to `Inside the organization` **and** `msip_labels` header contains `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true` **and** Is received from `Inside the organization`
* Take the following actions: Prepend the subject with `[SEC=OFFICIAL:Sensitive]`
* Except if the message: Includes these patterns in the message subject: `(SEC=OFFICIAL:Sensitive)`
* ExceptIfSubjectMatchesPatterns: `(SEC=OFFICIAL:Sensitive)`
* FromScope: `InOrganization`
* HeaderContainsMessageHeader: `msip_labels`
* HeaderContainsWords: `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true`
* Mode: `Enforce`
* Name: `OFFICIAL:Sensitive`
* PrependSubject: `[SEC=OFFICIAL:Sensitive]`
* Priority: `3`
* SentToScope: `InOrganization`
* State: `Enabled`

### PROTECTED

* If the message: Is sent to `Inside the organization` **and** `msip_labels` header contains `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true` **and** Is received from `Inside the organization`
* Take the following actions: Prepend the subject with `[SEC=PROTECTED]`
* Except if the message: Includes these patterns in the message subject: `(SEC=PROTECTED)`
* ExceptIfSubjectMatchesPatterns: `(SEC=PROTECTED)`
* FromScope: `InOrganization`
* HeaderContainsMessageHeader: `msip_labels`
* HeaderContainsWords: `MSIP_Label_XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX_Enabled=true`
* Mode: `Enforce`
* Name: `PROTECTED`
* PrependSubject: `[SEC=PROTECTED]`
* Priority: `4`
* SentToScope: `InOrganization`
* State: `Enabled`

### Double classification

* If the message: Includes these patterns in the message subject: `\[SEC\=.*\].*\[SEC\=.*\]` **and** Is received from `Inside the organization`
* Take the following actions: reject the message and include the explanation `Multiple Security Classifications in Subject Line` with the status code: `5.7.1`
* ExceptIfSubjectMatchesPatterns: -
* FromScope: `InOrganization`
* HeaderContainsMessageHeader: -
* HeaderContainsWords: -
* Mode: `Enforce`
* Name: `Double Classification`
* PrependSubject: -
* Priority: `5`
* SentToScope: -
* State: `Enabled`

## Journaling

`Exchange Admin Centre > compliance management > journal rules` is not configured.

## Mailbox retention

`Exchange Admin Centre > compliance management > retention polices`

Table 23 describes the Mailbox Retention settings for Default MRM Policy.

Name | Type | Retention Period | Retention Action
--- | --- | --- | ---
Never Delete | Personal | Unlimited | DeleteAndAllowRecovery
Recoverable Items 14 days move to archive | Recoverable items | 14 days | Archive
Junk Email | JunkEmail | 30 days | DeleteAndAllowRecovery
Deleted Items | DeletedItems | 30 days | DeleteAndAllowRecovery
Default 2 year move to archive | All | 730 days | Archive
Personal 1 year move to archive | Personal | 365 days | Archive
Personal never move to archive | Personal | Unlimited | Archive
1 Week Delete | Personal | 7 days | DeleteAndAllowRecovery
1 Month Delete | Personal | 30 days | DeleteAndAllowRecovery
Personal 5 year move to archive | Personal | 1825 days | Archive
6 Month Delete | Personal | 180 days | DeleteAndAllowRecovery
1 Year Delete | Personal | 365 days | DeleteAndAllowRecovery
5 Year Delete | Personal | 1825 days | DeleteAndAllowRecovery

## Shared mailboxes and resource mailboxes

`Exchange Admin Centre > recipients`

None available

`Exchange Admin Centre > recipients > groups`

* Display name: `grp-<Agency Acronym>O365-Outlook`
  * Group email address: `grp-<Agency Acronym>0365-outlook@<Agency>.gov.au`
  * Privacy: `Private – Only members can see content`
  * Language: `English (Australia)`
  * Subscribe new members: `Enabled`
  * Let people outside the organization send email to the group: `Disabled`
  * Owners: `<Agency Owner> (Admin)`
  * Members: `<Agency Owner> (Admin)`
  * Delivery Management
    * Accept messages from: `All senders`
    * Reject message from: `No senders`
  * Group Delegation
    * Send As: `None`
    * Send on Behalf: `None`
* Display name: `Grp-<Agency Acronym>O365-Teams`
  * Group email address: `Grp-<Agency Acronym>0365-Teams@<Agency>.gov.au`
  * Privacy: `Private – Only members can see content`
  * Language: `English (Australia)`
  * Subscribe new members: `Disabled`
  * Let people outside the organization send email to the group: `Disabled`
  * Owners: `<Agency Owner> (Admin)`
  * Members: `<Agency Owner> (Admin)`
  * Delivery Management
    * Accept messages from: `All senders`
    * Reject message from: `No senders`
  * Group Delegation
    * Send As: `None`
    * Send on Behalf: `None`
* Display name: `Protected Desktop Experience`
  * Group email address: `ProtectedDesktopDemo@<Agency>.gov.au`
  * Privacy: `Private – Only members can see content`
  * Language: `English (Australia)`
  * Subscribe new members: `Disabled`
  * Let people outside the organization send email to the group: `Disabled`
  * Owners: `<Agency Exchange Owners>`
  * Members: `<Agency Exchange Administrators>`
  * Delivery Management
    * Accept messages from: `All senders`
    * Reject message from: `No senders`
  * Group Delegation
    * Send As: `None`
    * Send on Behalf: `None`

`Exchange Admin Centre > recipients > resources`

* Display name: `Equipment 1`
  * Email address: `equipment1@<Agency>.gov.au`
  * Capacity: -
  * Department: -
  * Company: -
  * Address book policy: `[No policy]`
  * Booking delegates
    * Booking requests: `Use customized setting to accept or decline booking requests.`
  * Booking options
    * Allow repeating meetings: `Enabled`
    * Allow scheduling only during working hours: `Disabled`
    * Always decline if the end date is beyond the limit: `Enabled`
    * Maximum booking lead time: `180 days`
    * Maximum duration: `24 hours`
  * Contact Information
    * Location: -
    * Phone: -
    * Street: -
    * City: -
    * State: -
    * Post Code: -
    * Country: -
  * Email address
    * Email address: `equipment1@<Agency>.gov.au`
  * Mailbox delegation
    * Send As: `NT AUTHORITY\SELF`
    * Send on Behalf: `None`
    * Full Access: `None`
* Display name: `Room1`
  * Email address: `Room1@<Agency>.gov.au`
  * Capacity: -
  * Department: -
  * Company: -
  * Address book policy: `[No policy]`
  * Booking delegates
    * Booking requests: `Use customized setting to accept or decline booking requests.`
  * Booking options
    * Allow repeating meetings: `Enabled`
    * Allow scheduling only during working hours: `Disabled`
    * Always decline if the end date is beyond the limit: `Enabled`
    * Maximum booking lead time: `180 days`
    * Maximum duration: `24 hours`
  * Contact Information
    * Location: -
    * Phone: -
    * Street: -
    * City: -
    * State: -
    * Post Code: -
    * Country: -
    * Email address
    * Email address: `Room1@<Agency>.gov.au`
  * Mailbox delegation
    * Send As: `NT AUTHORITY\SELF`
    * Send on Behalf: `None`
    * Full Access: `None`

## Distribution lists

`Exchange Admin Centre > recipients > groups > <three dots> > Configure group naming policy`

* Group Naming Policy: `grp-<Department>-<Group Name>`
* Blocked words: `None`
