---
description: Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in Audience Lab erforderlich sind.
seo-description: Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in Audience Lab erforderlich sind.
seo-title: Testgruppen verwalten
solution: Audience Manager
title: Testgruppen verwalten
uuid: 2 fadddeb -5574-4853-8 c 52-c 58456582 c 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### Voraussetzungen

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[Ordnereigenschaften](../../features/traits/about-folder-traits.md) werden **** nicht unterstützt. [!UICONTROL Audience Lab] Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. Mit dieser Berechtigung kann der Benutzer die Ergebnisse eines Tests erstellen und anzeigen. A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. Ein Benutzer kann nur Ziele sehen, auf die er Zugriff hat. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * Zugriff auf relevante Konversionseigenschaften;
   * Zugriff auf relevante Segmente für Tests;
   * Zugriff auf relevante Ziele.

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * Sie können die Testgruppe als Entwurf speichern und später fortsetzen.
   * Ein Warnhinweis wird angezeigt, wenn das ausgewählte Basissegment bereits in anderen Testgruppen verwendet wird. Die doppelte Verwendung des Basissegments kann die Umrechnungsergebnisse beider Tests verfälschen.

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * Sie können den Namen der Testsegmente bearbeiten, indem Sie darauf klicken.
   * Die Prozentsätze werden automatisch gleichmäßig auf 100% aufgeteilt, wenn neue Testsegmente zugeordnet werden. Sie können die Prozentsätze dann manuell bearbeiten. Klicken Sie auf das Kontrollkästchen, nachdem Sie die Prozentsätze bearbeitet haben, und stellen Sie sicher, dass sie bis zu 100% hinzufügen. Andernfalls können Sie nicht mit dem nächsten Schritt fortfahren.

1. **[!UICONTROL Set a Control Segment]**

   * Wählen Sie ein Kontrollsegment aus, wenn Sie einen bestimmten Teil des Segments festlegen möchten, der als Kontrollgruppe verwendet werden soll. Mit Steuerungsgruppen können Sie die Auswirkungen der Testsegmente erkennen, die Sie im Vergleich zu einem Vergleich erstellt haben.
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you're done.

1. **[!UICONTROL Select Conversion Traits]**

   * Fügen Sie Konversionseigenschaften hinzu, indem Sie in das Fenster Konversionseigenschaften eingeben. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * Falls gewünscht, können Sie bis zu 5 Konversionseigenschaften hinzufügen.
   * Es wird ein Warnhinweis angezeigt, wenn Sie eine Konversionseigenschaft auswählen, die bereits für andere Testgruppen verwendet wird.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Geben Sie in das Suchfeld die gewünschten Ziele ein oder verwenden Sie den Dropdownpfeil. [!UICONTROL Audience Lab] Testsegmente können an URL, Cookie oder Server-zu-Server-Ziele gesendet werden.
   * Ziehen Sie Segmente per Drag &amp; Drop in Ziele.
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * Sie können dasselbe Testsegment an mehrere Ziele senden und einem einzelnen Ziel mehrere Testsegmente hinzufügen.
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * Schließlich müssen Sie ein Startdatum für Ihre Testgruppe auswählen. Dieses Datum markiert den Zeitraum, in dem Ihre Testgruppe in Ziele veröffentlicht wird. Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] mit einem authentifizierten Profil werden nur in Echtzeit-Zielen unterstützt. Wenn ein Testsegment mit einer Profilzusammenführungsregel dieser Konfiguration an ein dateibasiertes Server-to-Server-Ziel gesendet wird, werden die Zielgruppen möglicherweise nicht gefüllt.

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * Beachten Sie, dass Sie nach Abschluss einer Testgruppe dupliziert oder gelöscht werden können, aber nicht bearbeitet werden können.
   >[!NOTE]
   >* Sie können die Testgruppen jederzeit im Erstellungsvorgang speichern und zu einem späteren Zeitpunkt zum Assistenten zurückkehren. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. In the [!UICONTROL Create Segment Test Group] wizard, you can save your test group as a draft and resume working on it later.

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Suchen Sie die Testgruppe, die Sie löschen möchten. Sie können das Bild entweder:

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
