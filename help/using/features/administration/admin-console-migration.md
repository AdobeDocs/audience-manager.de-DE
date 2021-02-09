---
description: Audience Manager-Benutzerverwaltung wechselt zu Adobe Admin Console. In diesem Artikel wird beschrieben, was Sie zur Vorbereitung auf die Benutzermigration tun müssen und was sich nach Abschluss der Migration ändern wird.
keywords: rbac;RBAC;rollenbasiert;rollenbasierte;rollenbasierte Zugriffskontrollen
seo-description: Audience Manager-Benutzerverwaltung wechselt zu Adobe Admin Console. In diesem Artikel wird beschrieben, was Sie zur Vorbereitung auf die Benutzermigration tun müssen und was sich nach Abschluss der Migration ändern wird.
seo-title: Benutzermigration in Admin Console von Audience Manager
solution: Audience Manager
title: Benutzermigration in Admin Console von Audience Manager
feature: Administration
translation-type: tm+mt
source-git-commit: 04504d4561414f9558a1f1f4db33cbcf535d54af
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 3%

---


# [!DNL Audience Manager] Benutzermigration  [!DNL Admin Console] {#user-migration}

## Überblick {#overview}

[!DNL Audience Manager] Das Benutzerkonto-Management wechselt zum  [Adobe Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html), um Ihre Adobe-Lösungen zu optimieren.

Die Vorteile der Verwendung von [!DNL Admin Console] umfassen:

| Vorteil | Beschreibung |
|---|---|
| Single Sign-on Lösungen | [!DNL Audience Manager] Benutzer können sich bei  [!DNL Experience Cloud] und allen anderen Lösungen mit ihrer  [!DNL Adobe ID] oder  [!DNL Enterprise ID]anmelden. Diese Anmeldung ermöglicht den Zugriff auf integrierte Lösungen und Hauptdienste über [!DNL Experience Cloud]. Nach der Migration werden Benutzer, die versuchen, sich über veraltete Anmeldungen (`bank.demdex.com`) anzumelden, zu `experiencecloud.adobe.com` umgeleitet. |
| Benutzer und Gruppen verwalten | Nach Abschluss der Migration verwalten [!DNL Audience Manager]-Administratoren Benutzer und Gruppen ausschließlich im Ordner [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Produkte und Dienste verwalten | Von [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/) können Administratoren: <ul><li>Erstellen, Aktualisieren und Entfernen von Benutzern</li><li>Zugang zu Lösungen und Diensten gewähren</li><li>Gewähren von Benutzerberechtigungen</li></ul> |

Um die Benutzermigration zu erleichtern, bitten wir alle [!DNL Audience Manager]-Administratoren, so bald wie möglich Beginn zu erstellen, die ihre Benutzerkonten zu [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) migrieren. Befolgen Sie dazu die in diesem Artikel beschriebenen Schritte.

## Was Benutzer tun müssen{#what-to-do-users}

Als Audience Manager müssen Sie sich lediglich an Ihren [!DNL Audience Manager]-Administrator wenden und ihn bitten, ein neues Benutzerkonto für Sie in [!DNL Admin Console] zu erstellen.

## Was Administratoren tun müssen{#what-to-do-admins}

Audience Manager-Administratoren sollten die folgenden Schritte ausführen, um Benutzer zu [!DNL Admin Console] zu migrieren.

1. Wechseln Sie zu [https://adminconsole.adobe.com](https://adminconsole.adobe.com) und melden Sie sich mit Ihrem Adobe ID oder Ihrer Enterprise ID an. Wenn Sie keinen Zugriff auf das [!DNL Admin Console] haben, wenden Sie sich an den Kundendienst oder Ihren Adobe-Berater.
2. Detaillierte Anweisungen zum Erstellen und Verwalten von Benutzerkonten finden Sie im Handbuch [!DNL Adobe Admin Console] [help](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html).
3. Erstellen Sie neue Benutzerkonten für alle vorhandenen Audience Manager.
4. Informieren Sie Ihre Benutzer über die neu erstellten Benutzerkonten. Sobald Benutzer zu [!DNL Admin Console] migriert wurden, sollten sie die Verwendung älterer Anmeldevorgänge beenden.

## Überlegungen zur Benutzermigration {#considerations}

Bei der Migration von Audience Manager-Benutzern sollten sowohl Benutzer als auch Administratoren folgende Aspekte berücksichtigen:

* Sobald neue Benutzerkonten in Admin Console erstellt wurden, werden ihre bestehenden Berechtigungen aus ihren alten Benutzerkonten automatisch übernommen. Administratoren müssen keine neuen Berechtigungen in [!DNL Admin Console] zuweisen.
* Administratoren müssen ältere Benutzerkonten nicht deaktivieren. Alte Benutzerkonten werden automatisch mit migrierten Konten zusammengeführt.
* Aktualisierungen von Benutzerberechtigungen werden weiterhin von [!DNL Audience Manager] verwaltet. Die [!DNL Admin Console]-Variable deckt nur die Benutzer- und Gruppenverwaltung ab.