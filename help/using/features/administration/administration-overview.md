---
description: Mit den Optionen im Menü Administration können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen anzeigen (Eigenschaften, Segmente, Ziele und Modelle).
keywords: rbac; RBAC; rollenbasiert; rollenbasiert; rollenbasierte Zugriffskontrollen
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administration
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 2%

---

# [!UICONTROL Administration] (RBAC-Steuerelemente) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html). Um die Benutzermigration zu starten, müssen alle Audience Manager unverzüglich die in diesem Artikel beschriebenen erforderlichen Maßnahmen ergreifen: [Benutzermigration zu Admin Console durch Audience Manager](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert wurden, werden die Benutzerverwaltungsabschnitte dieses Dokuments entfernt.

>[!IMPORTANT]
>
> Bevor Sie [!DNL RBAC]festgelegt ist, muss diese Funktion von der Adobe für Ihre Organisation aktiviert werden. Wenden Sie sich an Ihr Account-Team, um eine Anfrage zu stellen [!DNL RBAC] Aktivierung oder wenden Sie sich an die Kundenunterstützung.


Die Optionen unter [!UICONTROL Administration] können Sie Audience Manager erstellen und Gruppen zuweisen. Sie können auch Einschränkungen anzeigen (Eigenschaften, Segmente, Ziele und Modelle).

Unternehmenskunden mit [!DNL Audience Manager] benötigen eine Datenverwaltungsplattform für alle ihre Daten, müssen jedoch in der Lage sein, die Sichtbarkeit der verschiedenen Datenelemente für bestimmte Geschäftseinheiten zu steuern. Sie können dies mithilfe von Gruppenberechtigungen erreichen, die auch als [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] verwendet Gruppen zum Zuweisen von Berechtigungen. Berechtigungen werden nicht auf Benutzerebene zugewiesen. Gruppenberechtigungen sind an Objekte gebunden ([!UICONTROL traits], Segmenten usw.) und für Aktionen, die Sie für diese Objekte ausführen können (Bearbeiten, Ansicht usw.). Diese Steuerelemente sind auch über die Audience Manager-REST-APIs verfügbar. Siehe [Benutzerverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gruppenverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)und [Berechtigungsverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API-Methoden.

## Benutzer erstellen {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html). Um die Benutzermigration zu starten, müssen alle Audience Manager unverzüglich die in diesem Artikel beschriebenen erforderlichen Maßnahmen ergreifen: [Benutzermigration zu Admin Console durch Audience Manager](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert wurden, wird der Abschnitt zur Benutzerverwaltung dieses Dokuments entfernt.
> 
Benutzer erstellen in [!DNL Audience Manager] und geben Sie Benutzerdetails an, melden Sie sich an und weisen Sie Benutzer Gruppen zu.

1. Klicken **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Klicken ![](assets/icon_add.png) , um [!UICONTROL Create New User] Seite.
1. under **[!UICONTROL User Details]**, füllen Sie die Felder aus:
   * **[!UICONTROL Username]:** Geben Sie einen eindeutigen Benutzernamen für den Audience Manager an.
   * **[!UICONTROL First Name]:** Geben Sie den Vornamen des Benutzers an.
   * **[!UICONTROL Last Name]:** Geben Sie den Nachnamen des Benutzers an.
   * **[!UICONTROL Email Address]:** Geben Sie die E-Mail-Adresse des Benutzers an. [!DNL Audience Manager] sendet keine regelmäßige Benachrichtigung an Benutzer. [!DNL Audience Manager] -Administratoren haben Zugriff auf die E-Mail-Adressen von Benutzern und können Benutzer bei Bedarf manuell per E-Mail versenden. Wenn ein Benutzer beispielsweise sein Kennwort vergisst, wird die in diesem Feld angegebene E-Mail-Adresse verwendet, um ein temporäres Kennwort und Anweisungen zum Zurücksetzen des Kennworts zu senden.
   * **[!UICONTROL Phone Number]:** Geben Sie die Telefonnummer des Benutzers an.
   * **[!UICONTROL Is Admin]:** Geben Sie an, ob dieser Benutzer [!DNL Audience Manager] Administrator. Administratoren können Benutzer verwalten (erstellen, bearbeiten usw.) und Gruppen (erstellen, Berechtigungen zuweisen usw.). Benutzer ohne Administratorrechte können nur ihre eigenen Benutzerprofile steuern, einschließlich der Bearbeitung ihrer E-Mail-Adressen und des Zurücksetzens ihrer eigenen Passwörter. Weitere Informationen finden Sie unter [Bearbeiten Ihrer Kontoeinstellungen](../../features/administration/edit-account-settings.md).
1. under **[!UICONTROL Login]** wählen Sie den gewünschten Status aus:
   * **[!UICONTROL Active]:**  Aktive Benutzer können auf [!DNL Audience Manager] und erhalten die Berechtigungen, die von der Gruppenmitgliedschaft gewährt werden.
   * **[!UICONTROL Deactivated]:**  Deaktivierte Benutzer können nicht zugreifen [!DNL Audience Manager] und haben keine Berechtigungen. Wenn Sie Benutzer deaktivieren, bleiben ihre Benutzerinformationen in [!DNL Audience Manager] und Sie können sie bei Bedarf einfach reaktivieren. Wenn Sie Benutzer entfernen, müssen Sie sie neu erstellen, wenn sie [!DNL Audience Manager] wieder in der Zukunft.
   * **[!UICONTROL Expired]:** Das Kennwort eines Benutzers ist älter als 90 Tage.
   * **[!UICONTROL Pending]:** Der Benutzer hat ein temporäres Kennwort, entweder als nachdem das Kennwort zurückgesetzt wurde oder als brandneues Konto, und er hat noch kein permanentes Kennwort festgelegt.
   * **[!UICONTROL Locked Out]:** 5 falsche Anmeldeversuche werden einen Benutzer sperren.
1. under **[!UICONTROL Assigned Groups]**Wählen Sie aus der Dropdownliste die gewünschten Gruppen aus, denen Sie diesen Benutzer zuweisen möchten.
Weitere Informationen zu Gruppen und Berechtigungen finden Sie unter [Erstellen einer Gruppe](../../features/administration/administration-overview.md#create-group).
1. Klicken **[!UICONTROL Save]**.

## Erstellen Sie eine [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html). Um die Benutzermigration zu starten, empfehlen wir allen Audience Manager, unverzüglich die in diesem Artikel beschriebenen erforderlichen Maßnahmen zu ergreifen: [Benutzermigration zu Admin Console durch Audience Manager](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert wurden, wird dieser Abschnitt entfernt.

A *Gruppe* ist eine Sammlung von Benutzern, für die Zugriffsberechtigungen freigegeben sind. [!UICONTROL destination], [!UICONTROL segment]und [!UICONTROL trait] Objekte. Sie können Gruppen auf einzelne Objekte beschränken oder ihnen einen breiten Zugriff auf Kombinationen verschiedener Objekte gewähren.

<!-- t_create_groups.xml -->

So erstellen Sie eine Gruppe:

1. Klicken **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Klicken  ![](assets/icon_add.png) , um [!UICONTROL Group Settings] Seite.
3. Mit [!UICONTROL Group Details]:
   * Benennen Sie die Gruppe.
   * Geben Sie eine kurze Gruppenbeschreibung ein.
4. In [!UICONTROL Group Members]klicken Sie auf einen Benutzer von **[!UICONTROL Add Users]** Optionen, um sie der Gruppe hinzuzufügen.
5. In [!UICONTROL Group Permissions], wählen Sie eine [Eigenschaft](../../features/traits/trait-details-page.md), [Segment](../../features/segments/segments-purpose.md)oder [Ziel](../../features/destinations/destinations.md) von **[!UICONTROL Add Object]**.
Dadurch wird ein Berechtigungsfenster für das ausgewählte Objekt geöffnet.
6. Aktivieren Sie das Kontrollkästchen für die Berechtigungen, die Gruppenmitglieder erhalten sollen.
7. *(Optional)* Zuweisen [Wildcard-Berechtigungen](../../features/administration/administration-overview.md#wild-card-permissions) in die Gruppe ein.
8. Klicken **[!UICONTROL Save Group]**.

## Grundlagen [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> Die Benutzerkontoverwaltung wechselt zur [Admin Console](https://helpx.adobe.com/de/enterprise/using/admin-console.html). Um die Benutzermigration zu starten, empfehlen wir allen Audience Manager, unverzüglich die in diesem Artikel beschriebenen erforderlichen Maßnahmen zu ergreifen: [Benutzermigration zu Admin Console durch Audience Manager](admin-console-migration.md).
> 
> Nachdem alle Kunden migriert wurden, wird dieser Abschnitt entfernt.

Vereinfachen Sie die Verwaltung von Gruppenrechten mit [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] den Gruppenmitgliedern automatischen Zugriff auf jede Datenquelle gewähren, die mit einer [!UICONTROL segment], [!UICONTROL destination]oder [!UICONTROL trait]. Im Vergleich dazu können Sie mit regulären Berechtigungen nur bestimmte [!UICONTROL data sources] zu einem dieser Objekte hinzufügen. Und wenn Sie neue [!UICONTROL data sources], erhalten Gruppenmitglieder keinen Zugriff auf diese neuen Quellen.

Sie müssen die Gruppenberechtigungen öffnen und diese neuen [!UICONTROL data sources] in die Gruppe ein. [!UICONTROL Wild Card Permissions] vermeiden Sie dieses Handbuch [!UICONTROL data source] Aktualisierungsprozess. Gruppen mit [!UICONTROL Wild Card Permissions] Zugriff auf neue [!UICONTROL data sources] ohne ausdrückliche Genehmigung.

![](assets/wild-card.png)

Nachfolgend finden Sie eine Beschreibung der einzelnen [!UICONTROL wildcard permission] bedeutet:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Benutzer können [!UICONTROL traits] als Ausgangswert für [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Benutzer können alle [!UICONTROL traits] innerhalb ihres Unternehmenskontos eingerichtet werden.
* `VIEW_ALL_TRAITS` - Benutzer können alle [!UICONTROL traits] innerhalb ihres Unternehmenskontos eingerichtet werden.
* `DELETE_ALL_TRAITS` - Benutzer können alle [!UICONTROL traits] innerhalb ihres Unternehmenskontos eingerichtet werden.
* `CREATE_ALL_ALGO_TRAITS` - Benutzer können [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Benutzer können die [!UICONTROL traits] deren Unternehmen [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Benutzer können [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Benutzer haben die Berechtigung zum Anzeigen von [!UICONTROL models] deren Unternehmen gehört.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Benutzer können alle [!UICONTROL derived signals] deren Unternehmen gehört.
* `CREATE_DERIVED_SIGNALS` - Benutzer können [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Benutzer können alle [!UICONTROL derived signals] deren Unternehmen gehört.
* `DELETE_DERIVED_SIGNALS` - Benutzer können die [!UICONTROL derived signals] deren Unternehmen gehört.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Benutzer können alle [!UICONTROL destinations] innerhalb ihres Unternehmenskontos eingerichtet werden.
* `CREATE_DESTINATIONS` - Benutzer können [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Benutzer können alle [!UICONTROL destinations] innerhalb ihres Unternehmenskontos eingerichtet werden.
* `DELETE_ALL_DESTINATIONS` - Benutzer können alle [!UICONTROL destinations] innerhalb ihres Unternehmenskontos eingerichtet werden.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Benutzer können alles (Anzeigen, Erstellen, Bearbeiten, Löschen) für ihre [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Benutzer können alles (Anzeigen, Erstellen, Bearbeiten, Löschen) für ihre [!UICONTROL Audience Lab] Testgruppen.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Benutzer können Segmente erstellen.
* `DELETE_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente löschen.
* `MAP_ALL_TO_DESTINATIONS` - Benutzer können beliebige Segmente, die zu ihrem Unternehmen gehören, Zielen zuordnen.
* `EDIT_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente bearbeiten.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Benutzer können Segmente als Grundlage für Modelle auswählen.
* `VIEW_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente anzeigen.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Benutzer können alle in erfassten Signale anzeigen. [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Nutzungsszenarios {#use-cases}

### Überwachen des Benutzerzugriffs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] können Ihnen dabei helfen, den Anmeldestatus von Benutzern zu überwachen. So erhalten Sie ein klares Bild davon, wer auf Ihre Audience Manager-Instanz zugreifen kann.

Je nach Ihren Geschäftsanforderungen können Sie Benutzerkonten bei Bedarf aktivieren und deaktivieren.

![monitor-user-access](assets/monitor-user-access.png)

### Gewährleistung des Zugriffsschutzes für vertrauliche Personen [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Sie können [!UICONTROL Role-Based Access Control] at [!UICONTROL trait], Segment und [!UICONTROL destination] Ebene für jede Benutzergruppe.

Mit dieser Funktion können Sie verwalten, wie Ihre Benutzer bestimmte Datensätze anzeigen, erstellen, lesen, schreiben und bearbeiten, und sogar Benutzer daran hindern, auf Datensätze zuzugreifen, die ihnen nicht zur Verfügung stehen sollten.

![Zugangsschutz](assets/access-protection.png)
