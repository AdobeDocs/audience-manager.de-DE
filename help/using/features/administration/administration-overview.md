---
description: Mit den Optionen im Menü "Administration" können Sie Audience Manager-Benutzer erstellen und Gruppen zuweisen. Sie können auch Beschränkungen (Eigenschaften, Segmente, Ziele und Modelle) anzeigen.
keywords: rbac; RBAC; role based; rollenbasiert; rollenbasierte Zugriffssteuerungselemente
seo-description: Mit den Optionen im Menü "Administration" können Sie Audience Manager-Benutzer erstellen und Gruppen zuweisen. Sie können auch Beschränkungen (Eigenschaften, Segmente, Ziele und Modelle) anzeigen.
seo-title: Administrations-
solution: Audience Manager
title: Administrations-
topic: DIL-API
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Administration (RBAC-Steuerelemente) {#administration}

![](assets/rbac-controls.png)

Mit den Optionen im [!UICONTROL Administration] Menü können Sie Audience Manager-Benutzer erstellen und Gruppen zuweisen. Sie können auch Beschränkungen (Eigenschaften, Segmente, Ziele und Modelle) anzeigen.

Enterprise-Kunden [!DNL Audience Manager] benötigen eine Datenverwaltungsplattform für all ihre Daten, müssen jedoch die Sichtbarkeit der verschiedenen Datenelemente auf bestimmte Geschäftseinheiten kontrollieren können. Dies können Sie mithilfe von Gruppenberechtigungen erreichen, auch als [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]) bezeichnet.

[!DNL Audience Manager] verwendet Gruppen, um Berechtigungen zuzuweisen. Berechtigungen werden nicht auf Benutzerebene zugewiesen. Gruppenberechtigungen sind an Objekte (Eigenschaften, Segmente usw.) gebunden. und Aktionen, die Sie für diese Objekte ausführen können (bearbeiten, anzeigen usw.). Diese Steuerelemente sind auch über die REST-apis von Audience Manager verfügbar. Siehe API-Methoden [für Benutzerverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gruppenverwaltung](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)und [Zugriffsberechtigungen](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) .

## Create Users {#create-users}

<!-- t_create_users.xml -->

Erstellen Sie Benutzer in [!DNL Audience Manager] und geben Sie Benutzerdetails, Anmeldestatus und Benutzer an Gruppen an.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Klicken ![](assets/icon_add.png) Sie auf, um die [!UICONTROL Create New User] Seite anzuzeigen.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Benutzername:** Geben Sie einen eindeutigen Benutzernamen für Audience Manager an.
   * **Vorname:** Geben Sie den Vornamen des Benutzers an.
   * **Nachname:** Geben Sie den Nachnamen des Benutzers an.
   * **E-Mail-Adresse:** Geben Sie die E-Mail-Adresse des Benutzers an. [!DNL Audience Manager] keine regelmäßigen Benachrichtigungen an Benutzer sendet. [!DNL Audience Manager] Administratoren haben Zugriff auf die E-Email-Adressen der Benutzer und können Benutzer bei Bedarf manuell e-email senden. Wenn ein Benutzer beispielsweise sein Kennwort vergisst, wird die in diesem Feld angegebene E-Mail-Adresse zum Senden eines temporären Kennworts und Anweisungen zum Zurücksetzen des Kennworts verwendet.
   * **Telefonnummer:** Geben Sie die Telefonnummer des Benutzers an.
   * **Lautet Admin:** Geben Sie an, ob dieser Benutzer Administrator [!DNL Audience Manager] ist. Administratoren können Benutzer verwalten (erstellen, bearbeiten usw.) und Gruppen (erstellen, Zuweisen Berechtigungen usw.). Benutzer ohne Administratorrechte können nur eigene Benutzerprofile steuern, einschließlich Bearbeiten ihrer E-Mail-Adressen und Zurücksetzen eigener Passwörter. Weitere Informationen finden Sie unter [Kontoeinstellungen bearbeiten](../../features/administration/edit-account-settings.md).
1. Wählen Sie den **[!UICONTROL Login]** gewünschten Status aus:
   * **Aktiv:** Aktive Benutzer können Zugriff [!DNL Audience Manager] auf die Berechtigungen haben und über die von der Gruppenmitgliedschaft gewährten Berechtigungen verfügen.
   * **Deaktiviert:** Deaktivierte Benutzer können keinen Zugriff [!DNL Audience Manager] haben und haben keine Berechtigungen. Wenn Sie Benutzer deaktivieren, bleiben ihre Benutzerinformationen erhalten [!DNL Audience Manager] und Sie können sie bei Bedarf reaktivieren. Wenn Sie Benutzer entfernen, müssen sie sie erneut erstellen, wenn sie in Zukunft [!DNL Audience Manager] erneut verwendet werden müssen.
   * **Abgelaufen:** Das Kennwort eines Benutzers ist älter als 90 Tage.
   * **Ausstehend:** Der Benutzer hat ein temporäres Kennwort, entweder nach einem Zurücksetzen des Kennworts oder als brandneues Konto, und sie haben noch kein permanentes Kennwort festgelegt.
   * **Gesperrt:** 5 falsche Anmeldeversuche sperren einen Benutzer.
1. Wählen Sie unter **[!UICONTROL Assigned Groups]**der Dropdownliste die gewünschten Gruppen aus, denen Sie diesen Benutzer zuweisen möchten.
Weitere Informationen zu Gruppen und Berechtigungen finden Sie unter [Erstellen einer Gruppe](../../features/administration/administration-overview.md#create-group).
1. Klicken Sie auf **[!UICONTROL Save]**.

## Eine Gruppe erstellen {#create-group}

Eine *Gruppe* ist eine Sammlung von Benutzern, die Zugriffsrechte für Ziel, Segment und Eigenschaften freigeben. Sie können Gruppen nur auf einzelne Objekte beschränken oder ihnen breiten Zugriff auf Kombinationen verschiedener Objekte erteilen.

<!-- t_create_groups.xml -->

So erstellen Sie eine Gruppe:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Klicken ![](assets/icon_add.png) Sie auf, um die [!UICONTROL Group Settings] Seite zu öffnen.
1. Mit [!UICONTROL Group Details]:
   * Benennen Sie die Gruppe.
   * Geben Sie eine kurze Gruppenbeschreibung ein.
1. Klicken Sie in [!UICONTROL Group Members]auf einen Benutzer aus **[!UICONTROL Add Users]** Optionen, um ihn der Gruppe hinzuzufügen.
1. Wählen Sie in ein [!UICONTROL Group Permissions][Merkmal](../../features/traits/trait-details-page.md), [Segment](../../features/segments/segments-purpose.md)oder [Ziel](../../features/destinations/destinations.md) **[!UICONTROL Add Object]**aus.
Dadurch wird ein Berechtigungsfenster für das ausgewählte Objekt geöffnet.
1. Aktivieren Sie das Kontrollkästchen der Berechtigungen, die Gruppenmitglieder haben sollen.
1. *(Optional)* Weisen [Sie der Gruppe Wildcard-Berechtigungen](../../features/administration/administration-overview.md#wild-card-permissions) zu.
1. Klicken Sie auf **[!UICONTROL Save Group]**.

## Wildcard-Berechtigungen {#wild-card-permissions}

Vereinfachen Sie die Gruppenrechteverwaltung mit [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] Geben Sie den Gruppenmitgliedern automatisch Zugriff auf alle mit einem Segment, Ziel oder einer Eigenschaft verknüpften Datenquellen. Im Gegensatz dazu können Sie mit regulären Berechtigungen dem eines dieser Objekte nur bestimmte Datenquellen zuweisen. Und wenn Sie neue Datenquellen hinzufügen, erhalten Gruppenmitglieder keinen Zugriff auf diese neuen Quellen.

Sie müssen die Gruppenberechtigungen öffnen und diese neuen Datenquellen der Gruppe zuweisen. [!UICONTROL Wild Card Permissions] Vermeiden Sie es, diesen manuellen Datenquellenaktualisierungsprozess zu vermeiden. Gruppen mit [!UICONTROL Wild Card Permissions] Zugriff auf neue Datenquellen ohne explizite Autorisierung.

![](assets/wild-card.png)

Lesen Sie unten, was die einzelnen Platzhalterberechtigungen bedeuten:

**Trait-**

* `MAP_ALL_TRAITS_TO_MODELS` - Benutzer können Eigenschaften als Grundlinie für Modelle auswählen.
* `EDIT_ALL_TRAITS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Eigenschaften bearbeiten.
* `VIEW_ALL_TRAITS` - Benutzer können alle Eigenschaften anzeigen, die innerhalb ihres Unternehmenskontos eingerichtet wurden.
* `DELETE_ALL_TRAITS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Eigenschaften löschen.
* `CREATE_ALL_ALGO_TRAITS` - Benutzer können algorithmische Eigenschaften erstellen.
* `MAP_ALL_TO_SEGMENTS` - Benutzer können alle Eigenschaften, die zu ihrem Unternehmen gehören, Segmente hinzufügen.
* `CREATE_ALL_TRAITS` - Benutzer können Eigenschaften erstellen.

**Berichte**

* `PTRREPORTS` - Diese Berechtigung bezieht sich auf veraltete Funktionen und wird in Kürze aus der Benutzeroberfläche von Audience Manager entfernt.

**Modelle**

* `VIEW_MODELS` - Benutzer haben die Berechtigung, Modelle anzuzeigen, die zu ihrem Unternehmen gehören.

**Abgeleitete Signale**

* `VIEW_DERIVED_SIGNALS` - Benutzer können alle abgeleiteten Signale anzeigen, die zu ihrem Unternehmen gehören.
* `CREATE_DERIVED_SIGNALS` - Benutzer können abgeleitete Signale erstellen.
* `EDIT_DERIVED_SIGNALS` - Benutzer können alle abgeleiteten Signale bearbeiten, die zu ihrem Unternehmen gehören.
* `DELETE_DERIVED_SIGNALS` - Benutzer können alle abgeleiteten Signale löschen, die zu ihrem Unternehmen gehören.

**Ziel**

* `EDIT_ALL_DESTINATIONS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Ziele bearbeiten.
* `CREATE_DESTINATIONS` - Benutzer können Ziele erstellen.
* `VIEW_ALL_DESTINATIONS` - Benutzer können alle Ziele anzeigen, die innerhalb ihres Unternehmenskontos eingerichtet wurden.
* `DELETE_ALL_DESTINATIONS` - Benutzer können alle Ziele löschen, die innerhalb ihres Unternehmenskontos eingerichtet wurden.

**Tags**

* `VIEW_TAGS` - Benutzer können auf ihren Tag-Containern alles (anzeigen, erstellen, bearbeiten, löschen) ausführen.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Benutzer können in ihren Audience Lab-Testgruppen alles (anzeigen, erstellen, bearbeiten, löschen) durchführen.

**Segment**

* `CREATE_ALL_SEGMENTS` - Benutzer können Segmente erstellen.
* `DELETE_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente löschen.
* `MAP_ALL_TO_DESTINATIONS` - Benutzer können beliebigen Segmenten, die zu ihrem Unternehmen gehören, Ziele zuordnen.
* `EDIT_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente bearbeiten.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Benutzer können Segmente als Grundlinie für Modelle auswählen.
* `VIEW_ALL_SEGMENTS` - Benutzer können alle in ihrem Unternehmenskonto eingerichteten Segmente anzeigen.

**Signale**

* `VIEW_ALL_SIGNALS` - Benutzer können alle in [Data Explorer erfassten Signale anzeigen](/help/using/features/data-explorer/data-explorer-overview.md).