---
description: Mit den Optionen im Menü "Administration"können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen für Ansichten (Eigenschaften, Segmente, Ziele und Modelle) festlegen.
keywords: rbac;RBAC;rollenbasiert;rollenbasierte;rollenbasierte Zugriffskontrollen
seo-description: Mit den Optionen im Menü "Administration"können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen für Ansichten (Eigenschaften, Segmente, Ziele und Modelle) festlegen.
seo-title: Administration
solution: Audience Manager
title: Administration
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 2%

---

# [!UICONTROL Administration] (RBAC-Steuerelemente)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html). Um die Benutzermigration Beginn, müssen alle Audience Manager unverzüglich die in diesem Artikel beschriebenen erforderlichen Maßnahmen ergreifen: [Benutzermigration von Audience Managern zu Admin Console](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert haben, verschwinden die Benutzerverwaltungsbereiche dieses Dokuments.


Mit den Optionen im Menü [!UICONTROL Administration] können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen für Ansichten (Eigenschaften, Segmente, Ziele und Modelle) festlegen.

Enterprise-Kunden, die [!DNL Audience Manager] verwenden, benötigen eine Data Management-Plattform für alle ihre Daten, müssen jedoch die Sichtbarkeit der verschiedenen Datenelemente für bestimmte Geschäftsbereiche steuern können. Dazu können Sie Gruppenberechtigungen verwenden, die auch als [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]) bezeichnet werden.

[!DNL Audience Manager] verwendet Gruppen, um Berechtigungen zuzuweisen. Berechtigungen werden nicht auf Benutzerebene zugewiesen. Gruppenberechtigungen sind an Objekte ([!UICONTROL traits], Segmente usw.) gebunden. und für Aktionen, die Sie für diese Objekte ausführen können (Bearbeiten, Ansicht usw.). Diese Steuerelemente stehen auch über die Audience Manager-REST-APIs zur Verfügung. Siehe die API-Methoden [Benutzerverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gruppenverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) und [Berechtigungsverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Erstellen von Benutzern {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Um die Benutzermigration Beginn, müssen alle Audience Manager unverzüglich die in diesem Artikel beschriebenen erforderlichen Maßnahmen ergreifen: [Benutzermigration von Audience Managern zu Admin Console](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert haben, wird der Benutzerverwaltungsabschnitt dieses Dokuments entfernt.

Erstellen Sie Benutzer in [!DNL Audience Manager] und geben Sie Benutzerdetails und den Anmeldestatus an und weisen Sie Benutzer Gruppen zu.

1. Klicken **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Klicken Sie auf ![](assets/icon_add.png), um die Seite [!UICONTROL Create New User] anzuzeigen.
1. Füllen Sie die Felder unter **[!UICONTROL User Details]** aus:
   * **[!UICONTROL Username]:** Geben Sie einen eindeutigen Benutzernamen für den Audience Manager an.
   * **[!UICONTROL First Name]:** Geben Sie den Vornamen des Benutzers an.
   * **[!UICONTROL Last Name]:** Geben Sie den Nachnamen des Benutzers an.
   * **[!UICONTROL Email Address]:** Geben Sie die E-Mail-Adresse des Benutzers ein. [!DNL Audience Manager] sendet keine regelmäßige Benachrichtigung an Benutzer. [!DNL Audience Manager] Administratoren haben Zugriff auf die E-Mail-Adressen der Benutzer und können die Benutzer bei Bedarf manuell per E-Mail versenden. Wenn ein Benutzer beispielsweise sein Kennwort vergisst, wird die in diesem Feld angegebene E-Mail-Adresse verwendet, um ein temporäres Kennwort und Anweisungen zum Zurücksetzen des Kennworts zu senden.
   * **[!UICONTROL Phone Number]:** Geben Sie die Telefonnummer des Benutzers ein.
   * **[!UICONTROL Is Admin]:** Geben Sie an, ob dieser Benutzer ein  [!DNL Audience Manager] Administrator ist. Administratoren können Benutzer verwalten (erstellen, bearbeiten usw.) und Gruppen (erstellen, Berechtigungen zuweisen usw.) Benutzer, die keine Administratoren sind, können nur ihre eigenen Profil steuern, einschließlich der Bearbeitung ihrer E-Mail-Adressen und des Zurücksetzens ihrer eigenen Kennwörter. Weitere Informationen finden Sie unter [Kontoeinstellungen bearbeiten](../../features/administration/edit-account-settings.md).
1. Wählen Sie unter **[!UICONTROL Login]** den gewünschten Status aus:
   * **[!UICONTROL Active]:**  Aktive Benutzer können auf die Berechtigungen zugreifen  [!DNL Audience Manager] und die ihnen durch die Gruppenmitgliedschaft gewährt werden.
   * **[!UICONTROL Deactivated]:**  Deaktivierte Benutzer können nicht zugreifen  [!DNL Audience Manager] und haben keine Berechtigungen. Wenn Sie Benutzer deaktivieren, bleiben ihre Benutzerinformationen in [!DNL Audience Manager] und Sie können sie bei Bedarf einfach reaktivieren. Wenn Sie Benutzer entfernen, müssen Sie sie neu erstellen, wenn sie [!DNL Audience Manager] in Zukunft erneut verwenden müssen.
   * **[!UICONTROL Expired]:** Das Kennwort eines Benutzers ist älter als 90 Tage.
   * **[!UICONTROL Pending]:** Der Benutzer hat ein temporäres Kennwort, entweder nach dem Zurücksetzen des Kennworts oder als neues Konto, und er hat noch kein permanentes Kennwort festgelegt.
   * **[!UICONTROL Locked Out]:** 5 Durch falsche Anmeldeversuche wird ein Benutzer gesperrt.
1. Wählen Sie unter **[!UICONTROL Assigned Groups]** aus der Dropdown-Liste die gewünschten Benutzergruppen aus, denen Sie diesen Benutzer zuweisen möchten.
Weitere Informationen zu Gruppen und Berechtigungen finden Sie unter [Gruppe erstellen](../../features/administration/administration-overview.md#create-group).
1. Klicken **[!UICONTROL Save]**.

## Erstellen Sie eine [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Um die Benutzermigration zu Beginn zu ermöglichen, empfehlen wir allen Audience Manager, unverzüglich die in diesem Artikel beschriebenen Maßnahmen zu ergreifen: [Benutzermigration von Audience Managern zu Admin Console](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert haben, wird dieser Abschnitt verschwinden.

Eine *Gruppe* ist eine Sammlung von Benutzern, die Zugriffsrechte auf [!UICONTROL destination]-, [!UICONTROL segment]- und [!UICONTROL trait]-Objekte teilen. Sie können Gruppen auf einzelne Objekte beschränken oder ihnen einen umfassenden Zugriff auf Kombinationen verschiedener Objekte gewähren.

<!-- t_create_groups.xml -->

So erstellen Sie eine Gruppe:

1. Klicken **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Klicken Sie auf ![](assets/icon_add.png), um die Seite [!UICONTROL Group Settings] zu öffnen.
3. Mit [!UICONTROL Group Details]:
   * Benennen Sie die Gruppe.
   * Geben Sie eine kurze Gruppenbeschreibung ein.
4. Klicken Sie unter [!UICONTROL Group Members] auf einen Benutzer aus den Optionen **[!UICONTROL Add Users]**, um ihn der Gruppe hinzuzufügen.
5. Wählen Sie unter [!UICONTROL Group Permissions] eine [Eigenschaft](../../features/traits/trait-details-page.md), [Segment](../../features/segments/segments-purpose.md) oder [Ziel](../../features/destinations/destinations.md) aus **[!UICONTROL Add Object]**.
Dadurch wird ein Berechtigungsfenster für das ausgewählte Objekt geöffnet.
6. Aktivieren Sie das Kontrollkästchen für die Berechtigungen, die Gruppenmitglieder haben sollen.
7. *(Optional)* Weisen Sie der Gruppe  [Wildcard-](../../features/administration/administration-overview.md#wild-card-permissions) Berechtigungen zu.
8. Klicken **[!UICONTROL Save Group]**.

## Grundlagen zu [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Um die Benutzermigration zu Beginn zu ermöglichen, empfehlen wir allen Audience Manager, unverzüglich die in diesem Artikel beschriebenen Maßnahmen zu ergreifen: [Benutzermigration von Audience Managern zu Admin Console](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert haben, wird dieser Abschnitt verschwinden.

Vereinfachen Sie die Verwaltung von Gruppenrechten mit [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] Gewähren Sie den Gruppenmitgliedern automatischen Zugriff auf jede Datenquelle, die mit einer  [!UICONTROL segment],  [!UICONTROL destination]oder  [!UICONTROL trait]Verbindung verbunden ist. Im Vergleich dazu können Sie mit regulären Berechtigungen dem Objekt nur bestimmte [!UICONTROL data sources] zuweisen. Und wenn Sie neue [!UICONTROL data sources] hinzufügen, erhalten Gruppenmitglieder keinen Zugriff auf diese neuen Quellen.

Sie müssen die Gruppenberechtigungen öffnen und der Gruppe diese neuen [!UICONTROL data sources] zuweisen. [!UICONTROL Wild Card Permissions] können Sie diesen manuellen  [!UICONTROL data source] Aktualisierungsprozess vermeiden. Gruppen mit [!UICONTROL Wild Card Permissions] erhalten ohne explizite Autorisierung Zugriff auf neue [!UICONTROL data sources].

![](assets/wild-card.png)

Nachfolgend finden Sie eine Beschreibung der Bedeutung der einzelnen [!UICONTROL wildcard permission]:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Benutzer können  [!UICONTROL traits] als Grundlage  [!UICONTROL models]auswählen.
* `EDIT_ALL_TRAITS` - Die Benutzer können alle  [!UICONTROL traits] eingerichteten Firmen bearbeiten.
* `VIEW_ALL_TRAITS` - Ansichten können alle in ihrem Firmen-Konto  [!UICONTROL traits] eingerichtet werden.
* `DELETE_ALL_TRAITS` - Benutzer können alle  [!UICONTROL traits] eingerichteten Elemente in ihrem Benutzerkonto löschen.
* `CREATE_ALL_ALGO_TRAITS` - Benutzer können eine Datei erstellen  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Benutzer können beliebige  [!UICONTROL traits] ihrer Firma hinzufügen  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Benutzer können eine Datei erstellen  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Dies  [!UICONTROL wildcard permission] bezieht sich auf veraltete Funktionen und wird in Kürze aus der Benutzeroberfläche des Audience Managers entfernt.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Benutzer haben Zugriff auf Ansichten, die zu ihrer Firma  [!UICONTROL models] gehören.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Benutzer können alle  [!UICONTROL derived signals] ihrer Firma angehörenden Ansichten durchführen.
* `CREATE_DERIVED_SIGNALS` - Benutzer können eine Datei erstellen  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Benutzer können alle  [!UICONTROL derived signals] ihrer Firma gehörenden Elemente bearbeiten.
* `DELETE_DERIVED_SIGNALS` - Benutzer können die  [!UICONTROL derived signals] ihrer Firma angehörenden Elemente löschen.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Die Benutzer können alle  [!UICONTROL destinations] eingerichteten Elemente innerhalb ihres Benutzerkontos bearbeiten.
* `CREATE_DESTINATIONS` - Benutzer können eine Datei erstellen  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Benutzer können alle  [!UICONTROL destinations] eingerichteten Firmen in ihrem Benutzerkonto Ansicht haben.
* `DELETE_ALL_DESTINATIONS` - Benutzer können alle  [!UICONTROL destinations] eingerichteten Elemente in ihrem Benutzerkonto löschen.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Benutzer können alles (Ansicht, Erstellen, Bearbeiten, Löschen) auf ihrer  [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Die Benutzer können alles (Ansicht, Erstellen, Bearbeiten, Löschen) in ihren  [!UICONTROL Audience Lab] Testgruppen tun.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Benutzer können Segmente erstellen.
* `DELETE_ALL_SEGMENTS` - Benutzer können alle in ihrem Firmen-Konto eingerichteten Segmente löschen.
* `MAP_ALL_TO_DESTINATIONS` - Benutzer können beliebige Segmente ihrer Firma Zielen zuordnen.
* `EDIT_ALL_SEGMENTS` - Benutzer können alle in ihrem Firmen-Konto eingerichteten Segmente bearbeiten.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Benutzer können Segmente als Grundlage für Modelle auswählen.
* `VIEW_ALL_SEGMENTS` - Die Benutzer können alle in ihrem Firmen-Konto eingerichteten Segmente Ansichten durchführen.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Benutzer können alle in  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md) erfassten Signale Ansicht werden.

## Nutzungsszenarios {#use-cases}

### Überwachen des Benutzerzugriffs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] Sie können den Anmeldestatus des Audience Managers überwachen, um sich einen Überblick darüber zu verschaffen, wer auf Ihre Benutzerinstanz zugreifen kann.

Je nach Ihren Geschäftsanforderungen können Sie Benutzerkonten bei Bedarf aktivieren und deaktivieren.

![monitor-user-access](assets/monitor-user-access.png)

### Sicherstellen des Zugriffsschutzes für sensible [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Sie können [!UICONTROL Role-Based Access Control] auf der Ebene [!UICONTROL trait], Segment und [!UICONTROL destination] für jede Benutzergruppe konfigurieren.

Diese Funktion hilft Ihnen dabei, die Ansicht, Erstellung, Lesen, Schreiben und Bearbeiten bestimmter Datensätze zu verwalten und sogar den Zugriff auf Datensätze zu beschränken, die für die Benutzer nicht verfügbar sein sollten.

![Zugangsschutz](assets/access-protection.png)
