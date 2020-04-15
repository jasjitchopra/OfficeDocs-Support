---
title: Teams defaults to domain-joined account
ms.author: v-todmc
author: todmccoy
ms.date: 4/9/2020
audience: ITPro
ms.topic: article
manager: dcscontentpm
ms.service: msteams
localization_priority: Normal
search.appverid:
- SPO160
- MET150
appliesto:
- Microsoft Teams
ms.custom: 
- CI 113425
- CSSTroubleshoot 
ms.reviewer: scapero
description: Describes how to resolve an issue where Teams uses a domain-joined account if another is available when connecting. 
---

# Microsoft Teams will always log into the domain-joined PC account

## Symptom
If a user has two different Microsoft Teams accounts and has a domain-joined machine, Teams uses the domain-joined profile on the machine to automatically log the user into Teams.

## Resolution
To switch to the other Teams account, the user must manually log out of the app and enter credentials to the second account to log in. If the user logs out of Teams and restarts the machine, upon restart, Teams will automatically log in using the domain-joined profile.

## More information
If users are signed in to a domain-joined computer and don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name:

```
 (UPN) Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams SkipUpnPrefill(REG_DWORD) 0x00000001 (1). 
```

> [!NOTE]
> Skipping the user name pre-fill for user names that end in ".local" or ".corp" is activated by default, so a registry key does not need to be set to turn these off. 
For more information, see [Sign in to Microsoft Teams using modern authentication](https://docs.microsoft.com/microsoftteams/sign-in-teams).

## More information

Still need help? Go to [Microsoft Community](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fanswers.microsoft.com%2F&data=02%7C01%7Cv-todmc%40microsoft.com%7C98910814456c474880f108d7cf62d97d%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637205895885805857&sdata=9%2FYStDGvrU5ZIYXB7guowmaPlKazab0U%2BTpiBIItDaQ%3D&reserved=0).