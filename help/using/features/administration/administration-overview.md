---
description: Mit den Optionen im Menü "Administration"können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen für Ansichten (Eigenschaften, Segmente, Ziele und Modelle) festlegen.
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Mit den Optionen im Menü "Administration"können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen für Ansichten (Eigenschaften, Segmente, Ziele und Modelle) festlegen.
seo-title: Administration
solution: Audience Manager
title: Administration
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 002429c74298ac34533225c105d5d71761ebf9c0
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---


# [!UICONTROL Administration] (RBAC-Steuerelemente) {#administration}

![](assets/rbac-controls.png)

Mit den Optionen im [!UICONTROL Administration] Menü können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen für Ansichten (Eigenschaften, Segmente, Ziele und Modelle) festlegen.

Unternehmenskunden, die eine Datenplattform verwenden, [!DNL Audience Manager] benötigen eine Data Management-Plattform für alle ihre Daten, müssen jedoch die Sichtbarkeit der verschiedenen Datenelemente für bestimmte Geschäftsbereiche steuern können. Dies können Sie mithilfe von Gruppenberechtigungen, auch [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]) genannt, erreichen.

[!DNL Audience Manager] verwendet Gruppen, um Berechtigungen zuzuweisen. Berechtigungen werden nicht auf Benutzerebene zugewiesen. Gruppenberechtigungen sind an Objekte ([!UICONTROL traits]Segmente usw.) gebunden. und für Aktionen, die Sie für diese Objekte ausführen können (Bearbeiten, Ansicht usw.). Diese Steuerelemente stehen auch über die Audience Manager-REST-APIs zur Verfügung. Siehe API-Methoden für [Benutzerverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gruppenverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)und [Berechtigungsverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) .

## Create Users {#create-users}

<!-- t_create_users.xml -->

Erstellen Sie Benutzer in [!DNL Audience Manager] und geben Sie Benutzerdetails an, melden Sie sich an und weisen Sie Benutzer Gruppen zu.

1. Klicken **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Klicken Sie auf ![](assets/icon_add.png) , um die [!UICONTROL Create New User] Seite anzuzeigen.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **[!UICONTROL Username]:**Geben Sie einen eindeutigen Benutzernamen für Audience Manager an.
   * **[!UICONTROL First Name]:**Geben Sie den Vornamen des Benutzers an.
   * **[!UICONTROL Last Name]:**Geben Sie den Nachnamen des Benutzers an.
   * **[!UICONTROL Email Address]:**Geben Sie die E-Mail-Adresse des Benutzers an.[!DNL Audience Manager]sendet keine regelmäßige Benachrichtigung an Benutzer.[!DNL Audience Manager]Administratoren haben Zugriff auf die E-Mail-Adressen der Benutzer und können die Benutzer bei Bedarf manuell per E-Mail versenden. Wenn ein Benutzer beispielsweise sein Kennwort vergisst, wird die in diesem Feld angegebene E-Mail-Adresse verwendet, um ein temporäres Kennwort und Anweisungen zum Zurücksetzen des Kennworts zu senden.
   * **[!UICONTROL Phone Number]:**Geben Sie die Telefonnummer des Benutzers an.
   * **[!UICONTROL Is Admin]:**Geben Sie an, ob dieser Benutzer ein[!DNL Audience Manager]Administrator ist. Administratoren können Benutzer verwalten (erstellen, bearbeiten usw.) und Gruppen (erstellen, Berechtigungen zuweisen usw.) Benutzer, die keine Administratoren sind, können nur ihre eigenen Profil steuern, einschließlich der Bearbeitung ihrer E-Mail-Adressen und des Zurücksetzens ihrer eigenen Kennwörter. Weitere Informationen finden Sie unter Kontoeinstellungen[bearbeiten](../../features/administration/edit-account-settings.md).
1. Wählen Sie unter **[!UICONTROL Login]** den gewünschten Status aus:
   * **[!UICONTROL Active]:**Aktive Benutzer können auf die Gruppenmitgliedschaft zugreifen[!DNL Audience Manager]und die ihnen zugeteilten Berechtigungen erhalten.
   * **[!UICONTROL Deactivated]:**Deaktivierte Benutzer können nicht zugreifen[!DNL Audience Manager]und haben keine Berechtigungen. Wenn Sie Benutzer deaktivieren, bleiben ihre Benutzerinformationen in erhalten[!DNL Audience Manager]und Sie können sie bei Bedarf einfach reaktivieren. Wenn Sie Benutzer entfernen, müssen Sie sie neu erstellen, wenn sie in Zukunft[!DNL Audience Manager]erneut verwendet werden müssen.
   * **[!UICONTROL Expired]:**Das Kennwort eines Benutzers ist älter als 90 Tage.
   * **[!UICONTROL Pending]:**Der Benutzer hat ein temporäres Kennwort, entweder nach dem Zurücksetzen des Kennworts oder als neues Konto, und er hat noch kein permanentes Kennwort festgelegt.
   * **[!UICONTROL Locked Out]:**5 Fehlerhafte Anmeldeversuche sperren einen Benutzer.
1. Wählen Sie unter **[!UICONTROL Assigned Groups]**der Dropdown-Liste die gewünschten Benutzergruppen aus, denen Sie diesen Benutzer zuweisen möchten.
Weitere Informationen zu Gruppen und Berechtigungen finden Sie unter Gruppe [erstellen](../../features/administration/administration-overview.md#create-group).
1. Klicken **[!UICONTROL Save]**.

## Erstellen Sie eine [!UICONTROL Group] {#create-group}

Eine *Gruppe* ist eine Sammlung von Benutzern, die Zugriffsrechte auf [!UICONTROL destination], [!UICONTROL segment]und [!UICONTROL trait] Objekte gemeinsam haben. Sie können Gruppen auf einzelne Objekte beschränken oder ihnen einen umfassenden Zugriff auf Kombinationen verschiedener Objekte gewähren.

<!-- t_create_groups.xml -->

So erstellen Sie eine Gruppe:

1. Klicken **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. Klicken Sie auf ![](assets/icon_add.png) , um die [!UICONTROL Group Settings] Seite zu öffnen.
1. Mit [!UICONTROL Group Details]:
   * Benennen Sie die Gruppe.
   * Geben Sie eine kurze Gruppenbeschreibung ein.
1. Klicken Sie [!UICONTROL Group Members]**[!UICONTROL Add Users]** in den Optionen auf einen Benutzer, um ihn der Gruppe hinzuzufügen.
1. Wählen Sie [!UICONTROL Group Permissions]in eine [Eigenschaft](../../features/traits/trait-details-page.md), ein [Segment](../../features/segments/segments-purpose.md)oder ein [Ziel](../../features/destinations/destinations.md) aus **[!UICONTROL Add Object]**.
Dadurch wird ein Berechtigungsfenster für das ausgewählte Objekt geöffnet.
1. Aktivieren Sie das Kontrollkästchen für die Berechtigungen, die Gruppenmitglieder haben sollen.
1. *(Optional)* Weisen Sie der Gruppe [Wildcard-Berechtigungen](../../features/administration/administration-overview.md#wild-card-permissions) zu.
1. Klicken **[!UICONTROL Save Group]**.

## Understanding [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

Vereinfachen Sie die Verwaltung von Gruppenrechten mit [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] Gewähren Sie den Gruppenmitgliedern automatischen Zugriff auf jede Datenquelle, die mit einer [!UICONTROL segment], [!UICONTROL destination]oder [!UICONTROL trait]Verbindung verbunden ist. Im Vergleich dazu können Sie mit regulären Berechtigungen nur bestimmte Objekte [!UICONTROL data sources] zuweisen. Und wenn Sie neue hinzufügen [!UICONTROL data sources], erhalten Gruppenmitglieder keinen Zugriff auf diese neuen Quellen.

Sie müssen die Gruppenberechtigungen öffnen und der Gruppe diese neuen Berechtigungen zuweisen [!UICONTROL data sources] . [!UICONTROL Wild Card Permissions] können Sie diesen manuellen [!UICONTROL data source] Aktualisierungsprozess vermeiden. Gruppen mit [!UICONTROL Wild Card Permissions] Zugriff auf neue [!UICONTROL data sources] ohne explizite Autorisierung.

![](assets/wild-card.png)

Nachfolgend finden Sie eine Beschreibung der [!UICONTROL wildcard permission] Bedeutung der einzelnen Komponenten:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Benutzer können [!UICONTROL traits] als Grundlage für [!UICONTROL models]auswählen.
* `EDIT_ALL_TRAITS` - Die Benutzer können alle [!UICONTROL traits] eingerichteten Firmen bearbeiten.
* `VIEW_ALL_TRAITS` - Ansichten können alle in ihrem Benutzerkonto [!UICONTROL traits] eingerichtet werden.
* `DELETE_ALL_TRAITS` - Benutzer können alle [!UICONTROL traits] eingerichteten Firmen löschen.
* `CREATE_ALL_ALGO_TRAITS` - Benutzer können eine Datei erstellen [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Benutzer können beliebige der [!UICONTROL traits] ihrer Firma hinzufügen [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Benutzer können eine Datei erstellen [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Dies [!UICONTROL wildcard permission] bezieht sich auf veraltete Funktionen und wird in Kürze aus der Benutzeroberfläche des Audience Managers entfernt.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Benutzer haben die Berechtigung zur Ansicht, die zu ihrer Firma [!UICONTROL models] gehört.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Benutzer können alle [!UICONTROL derived signals] ihrer Firma angehörenden Ansichten durchführen.
* `CREATE_DERIVED_SIGNALS` - Benutzer können eine Datei erstellen [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Die Benutzer können alle [!UICONTROL derived signals] Zugehörigkeiten zu ihrer Firma bearbeiten.
* `DELETE_DERIVED_SIGNALS` - Benutzer können die [!UICONTROL derived signals] ihrer Firma angehörenden Elemente löschen.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Benutzer können alle [!UICONTROL destinations] eingerichteten Elemente innerhalb ihres Benutzerkontos bearbeiten.
* `CREATE_DESTINATIONS` - Benutzer können eine Datei erstellen [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Die Benutzer können alle [!UICONTROL destinations] eingerichteten Firmen in ihrem Benutzerkonto Ansichten durchführen.
* `DELETE_ALL_DESTINATIONS` - Benutzer können alle [!UICONTROL destinations] eingerichteten Elemente in ihrem Benutzerkonto löschen.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Benutzer können alles (Ansicht, Erstellen, Bearbeiten, Löschen) auf ihrer [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Die Benutzer können alles (Ansicht, Erstellen, Bearbeiten, Löschen) in ihren [!UICONTROL Audience Lab] Testgruppen tun.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Benutzer können Segmente erstellen.
* `DELETE_ALL_SEGMENTS` - Benutzer können alle in ihrem Firmen-Konto eingerichteten Segmente löschen.
* `MAP_ALL_TO_DESTINATIONS` - Benutzer können beliebige Segmente ihrer Firma Zielen zuordnen.
* `EDIT_ALL_SEGMENTS` - Benutzer können alle in ihrem Firmen-Konto eingerichteten Segmente bearbeiten.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Benutzer können Segmente als Grundlage für Modelle auswählen.
* `VIEW_ALL_SEGMENTS` - Die Benutzer können alle in ihrem Firmen-Konto eingerichteten Segmente Ansichten durchführen.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Benutzer können alle in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md)erfassten Signale Ansicht werden.

## Nutzungsszenarios {#use-cases}

### Überwachen des Benutzerzugriffs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] Sie können den Anmeldestatus des Audience Managers überwachen, um sich einen Überblick darüber zu verschaffen, wer auf Ihre Benutzerinstanz zugreifen kann.

Je nach Ihren Geschäftsanforderungen können Sie Benutzerkonten bei Bedarf aktivieren und deaktivieren.

![monitor-user-access](assets/monitor-user-access.png)

### Sicherstellen des Zugriffs für sensible [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Sie können für jede Benutzergruppe [!UICONTROL Role-Based Access Control] eine Konfiguration für [!UICONTROL trait]Segment und [!UICONTROL destination] Ebene vornehmen.

Diese Funktion hilft Ihnen dabei, die Ansicht, Erstellung, Lesen, Schreiben und Bearbeiten bestimmter Datensätze zu verwalten und sogar den Zugriff auf Datensätze zu beschränken, die für die Benutzer nicht verfügbar sein sollten.

![Zugangsschutz](assets/access-protection.png)
