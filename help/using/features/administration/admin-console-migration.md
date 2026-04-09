---
description: Die Benutzerverwaltung von Audience Manager wechselt zu Adobe Admin Console. In diesem Artikel wird erläutert, was Sie tun müssen, um sich auf die Benutzermigration vorzubereiten, und was sich nach Abschluss der Migration ändert.
keywords: rbac;RBAC;rollenbasiert;rollenbasiert;rollenbasierte Zugriffssteuerungen
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager-Benutzermigration zu Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
TQID: https://experienceleague.adobe.com/CE7RomA3PrbV9wwVnwehnZLdP-L73QzOyOlOGSQ0rSs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 391
ht-degree: 1%

---

# [!DNL Audience Manager] der Benutzermigration nach [!DNL Admin Console] {#user-migration}

## Überblick {#overview}

[!DNL Audience Manager] Benutzerkontenverwaltung wird in die [Adobe Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html) verschoben, um eine optimierte Nutzung Ihrer Adobe-Lösungen zu ermöglichen.

Die Verwendung der [!DNL Admin Console] bietet folgende Vorteile:

| Vorteil | Beschreibung |
|---|---|
| Single Sign-on für alle Lösungen | [!DNL Audience Manager] Benutzer können sich mit ihrer [!DNL Experience Cloud] oder [!DNL Adobe ID] bei [!DNL Enterprise ID] und allen anderen Lösungen anmelden. Diese Anmeldung ermöglicht den [!DNL Experience Cloud] Zugriff auf integrierte Lösungen und zentrale Services. Nach der Migration werden Benutzer, die versuchen, sich über die bisherigen Anmeldedaten anzumelden (`bank.demdex.com`), zu `experiencecloud.adobe.com` weitergeleitet. |
| Verwalten von Benutzern und Gruppen | Nach Abschluss der Migration verwalten [!DNL Audience Manager] Administratoren Benutzer und Gruppen ausschließlich in der [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Produkte und Services verwalten | Vom [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/) aus können Admins: <ul><li>Benutzer erstellen, aktualisieren und entfernen</li><li>Zugriff auf Lösungen und Services gewähren</li></ul> |

Um die Benutzermigration zu erleichtern, bitten wir alle [!DNL Audience Manager] Administratoren, so bald wie möglich mit der Migration ihrer Benutzerkonten zu [Adobe Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html) zu beginnen, indem sie die in diesem Artikel beschriebenen Schritte ausführen.

## Was Benutzer tun müssen {#what-to-do-users}

Als Audience Manager-Anwender müssen Sie sich nur an Ihren [!DNL Audience Manager] wenden und ihn bitten, in [!DNL Admin Console] ein neues Benutzerkonto für Sie zu erstellen.

## Was Administratoren tun müssen {#what-to-do-admins}

Audience Manager-Admins sollten die folgenden Schritte ausführen, um Benutzende zu [!DNL Admin Console] zu migrieren.

1. Navigieren Sie zu [https://adminconsole.adobe.com](https://adminconsole.adobe.com) und melden Sie sich mit Ihrer Adobe ID oder Enterprise ID an. Wenn Sie keinen Zugriff auf die [!DNL Admin Console] haben, wenden Sie sich an die Kundenunterstützung oder Ihren Adobe-Berater.
2. Lesen Sie das [!DNL Adobe Admin Console] [Hilfehandbuch](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html), um detaillierte Anweisungen zum Erstellen und Verwalten von Benutzerkonten zu erhalten.
3. Erstellen Sie neue Benutzerkonten für alle vorhandenen Audience Manager-Benutzer.
4. Informieren Sie Ihre Benutzer über die neu erstellten Benutzerkonten. Nach der Migration auf [!DNL Admin Console] sollten Benutzer keine bisherigen Anmeldedaten mehr verwenden.

## Überlegungen zur Benutzermigration {#considerations}

Sowohl Benutzende als auch Admins sollten die folgenden Überlegungen für die Audience Manager-Benutzermigration beachten:

* Sobald neue Benutzerkonten in Admin Console erstellt wurden, gelten weiterhin die bestehenden Berechtigungen aus den alten Benutzerkonten.
* Aktualisierungen von Benutzerberechtigungen werden weiterhin von [!DNL Audience Manager] aus verwaltet. Die [!DNL Admin Console] deckt nur die Benutzer- und Gruppenverwaltung ab.
* Administratoren müssen keine Legacy-Benutzerkonten deaktivieren. Alte Benutzerkonten werden automatisch mit den migrierten zusammengeführt.
