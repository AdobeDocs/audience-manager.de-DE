---
description: Die Benutzerverwaltung für Audience Manager wird auf Adobe Admin Console umgestellt. In diesem Artikel wird beschrieben, was Sie tun müssen, um sich auf die Benutzermigration vorzubereiten, und was sich nach Abschluss der Migration ändert.
keywords: rbac; RBAC; rollenbasiert; rollenbasiert; rollenbasierte Zugriffskontrollen
seo-description: Die Benutzerverwaltung für Audience Manager wird auf Adobe Admin Console umgestellt. In diesem Artikel wird beschrieben, was Sie tun müssen, um sich auf die Benutzermigration vorzubereiten, und was sich nach Abschluss der Migration ändert.
seo-title: Audience Manager-Benutzermigration zur Admin Console
solution: Audience Manager
title: Audience Manager-Benutzermigration zur Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# [!DNL Audience Manager] Benutzermigration zu  [!DNL Admin Console] {#user-migration}

## Überblick {#overview}

[!DNL Audience Manager] Die Benutzerkontoverwaltung wechselt zur  [Adobe Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html), um Ihre Adobe-Lösungen optimal zu gestalten.

Zu den Vorteilen der Verwendung von [!DNL Admin Console] gehören:

| Vorteil | Beschreibung |
|---|---|
| Single Sign-on Lösungen | [!DNL Audience Manager] -Benutzer können sich mit  [!DNL Experience Cloud] und allen anderen Lösungen über ihre  [!DNL Adobe ID] oder  [!DNL Enterprise ID] anmelden. Diese Anmeldung ermöglicht den Zugriff auf integrierte Lösungen und Hauptdienste über [!DNL Experience Cloud]. Nach der Migration werden Benutzer, die versuchen, sich über die bisherigen Anmeldedaten anzumelden (`bank.demdex.com`), zu `experiencecloud.adobe.com` umgeleitet. |
| Benutzer und Gruppen verwalten | Sobald die Migration abgeschlossen ist, verwalten [!DNL Audience Manager] -Administratoren Benutzer und Gruppen ausschließlich im Ordner [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Produkte und Dienste verwalten | Von [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/) aus können Administratoren: <ul><li>Benutzer erstellen, aktualisieren und entfernen</li><li>Zugriff auf Lösungen und Dienste gewähren</li></ul> |

Um die Benutzermigration zu erleichtern, bitten wir alle [!DNL Audience Manager] -Administratoren, so bald wie möglich mit der Migration ihrer Benutzerkonten auf [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) zu beginnen, indem Sie die in diesem Artikel beschriebenen Schritte ausführen.

## Was Benutzer tun müssen {#what-to-do-users}

Als Audience Manager müssen Sie sich lediglich an Ihren [!DNL Audience Manager]-Administrator wenden und ihn bitten, ein neues Benutzerkonto für Sie in [!DNL Admin Console] zu erstellen.

## Was Administratoren tun müssen {#what-to-do-admins}

Audience Manager-Administratoren sollten die folgenden Schritte ausführen, um Benutzer zu [!DNL Admin Console] zu migrieren.

1. Gehen Sie zu [https://adminconsole.adobe.com](https://adminconsole.adobe.com) und melden Sie sich mit Ihrer Adobe ID oder Enterprise ID an. Wenn Sie keinen Zugriff auf [!DNL Admin Console] haben, wenden Sie sich an die Kundenunterstützung oder Ihren Adobe-Berater.
2. Detaillierte Anweisungen zum Erstellen und Verwalten von Benutzerkonten finden Sie im [!DNL Adobe Admin Console] [Hilerhandbuch](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) .
3. Erstellen Sie neue Benutzerkonten für alle Ihre bestehenden Audience Manager-Benutzer.
4. Informieren Sie Ihre Benutzer über die neu erstellten Benutzerkonten. Nachdem Benutzer zu [!DNL Admin Console] migriert wurden, sollten sie die bisherigen Anmeldedaten nicht mehr verwenden.

## Überlegungen zur Benutzermigration {#considerations}

Bei der Benutzermigration sollten sowohl Audience Manager als auch Administratoren folgende Aspekte berücksichtigen:

* Sobald neue Benutzerkonten in Admin Console erstellt wurden, gelten ihre bestehenden Berechtigungen aus ihren alten Benutzerkonten weiterhin.
* Aktualisierungen von Benutzerberechtigungen werden weiterhin über [!DNL Audience Manager] verwaltet. Die [!DNL Admin Console] umfasst nur die Benutzer- und Gruppenverwaltung.
* Administratoren müssen ältere Benutzerkonten nicht deaktivieren. Alte Benutzerkonten werden automatisch mit den migrierten Konten zusammengeführt.
