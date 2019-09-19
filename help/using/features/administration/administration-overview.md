---
description: Mit den Optionen im Menü "Administration"können Sie Audience Manager-Benutzer erstellen und sie Gruppen zuweisen. Sie können auch Beschränkungen (Eigenschaften, Segmente, Ziele und Modelle) anzeigen.
keywords: rbac;RBAC;rollenbasiert;rollenbasierte;rollenbasierte Zugriffssteuerung
seo-description: Mit den Optionen im Menü "Administration"können Sie Audience Manager-Benutzer erstellen und sie Gruppen zuweisen. Sie können auch Beschränkungen (Eigenschaften, Segmente, Ziele und Modelle) anzeigen.
seo-title: Administrations-
solution: Audience Manager
title: Administrations-
topic: DIL-API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Administration (RBAC-Steuerelemente) {#administration}

![](assets/rbac-controls.png)

Mit den Optionen im [!UICONTROL Administration] Menü können Sie Audience Manager-Benutzer erstellen und sie Gruppen zuweisen. Sie können auch Beschränkungen (Eigenschaften, Segmente, Ziele und Modelle) anzeigen.

Unternehmenskunden, die eine Datenverwaltungsplattform für alle ihre Daten verwenden, [!DNL Audience Manager] benötigen eine Datenverwaltungsplattform, müssen jedoch die Sichtbarkeit der verschiedenen Datenelemente für bestimmte Geschäftsbereiche steuern können. Dies können Sie mit Gruppenberechtigungen, auch [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]) genannt, erreichen.

[!DNL Audience Manager] verwendet Gruppen, um Berechtigungen zuzuweisen. Berechtigungen werden nicht auf Benutzerebene zugewiesen. Gruppenberechtigungen sind an Objekte (Eigenschaften, Segmente usw.) gebunden. und Aktionen, die Sie für diese Objekte ausführen können (Bearbeiten, Ansicht usw.). Diese Steuerelemente stehen auch über die Audience Manager REST-APIs zur Verfügung. Siehe API-Methoden für [Benutzerverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gruppenverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)und [Berechtigungsverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) .

## Create Users {#create-users}

<!-- t_create_users.xml -->

Erstellen Sie Benutzer in [!DNL Audience Manager] und geben Sie Benutzerdetails an, melden Sie sich an und weisen Sie Benutzer Gruppen zu.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Klicken Sie auf ![](assets/icon_add.png) , um die [!UICONTROL Create New User] Seite anzuzeigen.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **** Benutzername: Geben Sie einen eindeutigen Benutzernamen für Audience Manager an.
   * **** Vorname: Geben Sie den Vornamen des Benutzers an.
   * **** Nachname: Geben Sie den Nachnamen des Benutzers an.
   * **** E-Mail-Adresse: Geben Sie die E-Mail-Adresse des Benutzers an. [!DNL Audience Manager] sendet keine regelmäßige Benachrichtigung an Benutzer. [!DNL Audience Manager] Administratoren haben Zugriff auf die E-Mail-Adressen der Benutzer und können die Benutzer bei Bedarf manuell per E-Mail versenden. Wenn ein Benutzer beispielsweise sein Kennwort vergisst, wird die in diesem Feld angegebene E-Mail-Adresse verwendet, um ein temporäres Kennwort und Anweisungen zum Zurücksetzen des Kennworts zu senden.
   * **** Telefonnummer: Geben Sie die Telefonnummer des Benutzers an.
   * **** Ist Admin: Geben Sie an, ob dieser Benutzer [!DNL Audience Manager] Administrator ist. Administratoren können Benutzer verwalten (erstellen, bearbeiten usw.) und Gruppen (erstellen, Berechtigungen zuweisen usw.) Benutzer, die keine Administratoren sind, können nur ihre eigenen Benutzerprofile steuern, beispielsweise die Bearbeitung ihrer E-Mail-Adressen und das Zurücksetzen ihrer eigenen Kennwörter. Weitere Informationen finden Sie unter Kontoeinstellungen [bearbeiten](../../features/administration/edit-account-settings.md).
1. Wählen Sie unter **[!UICONTROL Login]** den gewünschten Status aus:
   * **** Aktiv:  Aktive Benutzer können auf die Gruppenmitgliedschaft zugreifen [!DNL Audience Manager] und die ihnen zugeteilten Berechtigungen erhalten.
   * **** Deaktiviert:  Deaktivierte Benutzer können nicht zugreifen [!DNL Audience Manager] und haben keine Berechtigungen. Wenn Sie Benutzer deaktivieren, bleiben ihre Benutzerinformationen in erhalten [!DNL Audience Manager] und Sie können sie bei Bedarf einfach reaktivieren. Wenn Sie Benutzer entfernen, müssen Sie sie neu erstellen, wenn sie in Zukunft [!DNL Audience Manager] erneut verwendet werden müssen.
   * **** Abgelaufen: Das Kennwort eines Benutzers ist älter als 90 Tage.
   * **** Ausstehend: Der Benutzer hat ein temporäres Kennwort, entweder nach dem Zurücksetzen des Kennworts oder als neues Konto, und er hat noch kein permanentes Kennwort festgelegt.
   * **** Ausgesperrt: 5 Fehlerhafte Anmeldeversuche sperren einen Benutzer.
1. Wählen Sie unter **[!UICONTROL Assigned Groups]**der Dropdownliste die gewünschten Gruppen aus, denen Sie diesen Benutzer zuweisen möchten.
Weitere Informationen zu Gruppen und Berechtigungen finden Sie unter Gruppe [erstellen](../../features/administration/administration-overview.md#create-group).
1. Klicken Sie auf **[!UICONTROL Save]**.

## Eine Gruppe erstellen {#create-group}

Eine *Gruppe* ist eine Sammlung von Benutzern, die Zugriff auf Ziel-, Segment- und Eigenschaftenobjekte haben. Sie können Gruppen auf einzelne Objekte beschränken oder ihnen einen umfassenden Zugriff auf Kombinationen verschiedener Objekte gewähren.

<!-- t_create_groups.xml -->

So erstellen Sie eine Gruppe:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Klicken Sie auf ![](assets/icon_add.png) , um die [!UICONTROL Group Settings] Seite zu öffnen.
1. Mit [!UICONTROL Group Details]:
   * Benennen Sie die Gruppe.
   * Geben Sie eine kurze Gruppenbeschreibung ein.
1. Klicken Sie [!UICONTROL Group Members]**[!UICONTROL Add Users]** in den Optionen auf einen Benutzer, um ihn der Gruppe hinzuzufügen.
1. Wählen Sie [!UICONTROL Group Permissions]in eine [Eigenschaft](../../features/traits/trait-details-page.md), ein [Segment](../../features/segments/segments-purpose.md)oder ein [Ziel](../../features/destinations/destinations.md) aus **[!UICONTROL Add Object]**.
Dadurch wird ein Berechtigungsfenster für das ausgewählte Objekt geöffnet.
1. Aktivieren Sie das Kontrollkästchen für die Berechtigungen, die Gruppenmitglieder haben sollen.
1. *(Optional)* Weisen Sie der Gruppe [Wildcard-Berechtigungen](../../features/administration/administration-overview.md#wild-card-permissions) zu.
1. Klicken Sie auf **[!UICONTROL Save Group]**.

## Grundlegendes zu Wildcard-Berechtigungen {#wild-card-permissions}

Vereinfachung der Verwaltung von Gruppenrechten mit [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] Gewähren Sie den Gruppenmitgliedern automatischen Zugriff auf jede Datenquelle, die einem Segment, einem Ziel oder einer Eigenschaft zugeordnet ist. Im Vergleich dazu können Sie mit regulären Berechtigungen nur bestimmten Datenquellen eines dieser Objekte zuweisen. Und wenn Sie neue Datenquellen hinzufügen, erhalten Gruppenmitglieder keinen Zugriff auf diese neuen Quellen.

Sie müssen die Gruppenberechtigungen öffnen und der Gruppe diese neuen Datenquellen zuweisen. [!UICONTROL Wild Card Permissions] können Sie diesen manuellen Aktualisierungsprozess der Datenquelle vermeiden. Gruppen mit [!UICONTROL Wild Card Permissions] Zugriff auf neue Datenquellen ohne explizite Autorisierung.

![](assets/wild-card.png)

Nachfolgend finden Sie eine Beschreibung der Bedeutung der einzelnen Platzhalterberechtigungen:

**Trait-**

* `MAP_ALL_TRAITS_TO_MODELS` - Benutzer können Eigenschaften als Grundlage für Modelle auswählen.
* `EDIT_ALL_TRAITS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Eigenschaften bearbeiten.
* `VIEW_ALL_TRAITS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Eigenschaften anzeigen.
* `DELETE_ALL_TRAITS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Eigenschaften löschen.
* `CREATE_ALL_ALGO_TRAITS` - Benutzer können algorithmische Eigenschaften erstellen.
* `MAP_ALL_TO_SEGMENTS` - Benutzer können beliebige Eigenschaften ihres Unternehmens zu Segmenten hinzufügen.
* `CREATE_ALL_TRAITS` - Benutzer können Eigenschaften erstellen.

**Berichte**

* `PTRREPORTS` - Diese Berechtigung für Platzhalter bezieht sich auf veraltete Funktionen und wird in Kürze aus der Benutzeroberfläche von Audience Manager entfernt.

**Modelle**

* `VIEW_MODELS` - Benutzer haben die Berechtigung, Modelle ihres Unternehmens anzuzeigen.

**Abgeleitete Signale**

* `VIEW_DERIVED_SIGNALS` - Benutzer können alle abgeleiteten Signale ihres Unternehmens anzeigen.
* `CREATE_DERIVED_SIGNALS` - Benutzer können abgeleitete Signale erstellen.
* `EDIT_DERIVED_SIGNALS` - Benutzer können alle abgeleiteten Signale ihrer Firma bearbeiten.
* `DELETE_DERIVED_SIGNALS` - Benutzer können beliebige der abgeleiteten Signale ihres Unternehmens löschen.

**Ziel**

* `EDIT_ALL_DESTINATIONS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Ziele bearbeiten.
* `CREATE_DESTINATIONS` - Benutzer können Ziele erstellen.
* `VIEW_ALL_DESTINATIONS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Ziele anzeigen.
* `DELETE_ALL_DESTINATIONS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Ziele löschen.

**Tags**

* `VIEW_TAGS` - Benutzer können alles (Anzeigen, Erstellen, Bearbeiten, Löschen) in ihren Tag-Behältern tun.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Benutzer können alles (Anzeigen, Erstellen, Bearbeiten, Löschen) in ihren Audience Lab-Testgruppen tun.

**Segment**

* `CREATE_ALL_SEGMENTS` - Benutzer können Segmente erstellen.
* `DELETE_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente löschen.
* `MAP_ALL_TO_DESTINATIONS` - Benutzer können beliebige Segmente ihres Unternehmens Zielen zuordnen.
* `EDIT_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente bearbeiten.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Benutzer können Segmente als Grundlage für Modelle auswählen.
* `VIEW_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente anzeigen.

**Signale**

* `VIEW_ALL_SIGNALS` - Benutzer können alle in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md)erfassten Signale anzeigen.