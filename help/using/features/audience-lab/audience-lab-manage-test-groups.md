---
description: Dieser Vorgang führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in Audience Lab erforderlich sind
seo-description: Dieser Vorgang führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in Audience Lab erforderlich sind
seo-title: Verwalten von Testgruppen
solution: Audience Manager
title: Verwalten von Testgruppen
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: 96b353d4b35a72ea087f7c82910e9272bc457bdc

---


# Verwalten von Testgruppen {#manage-test-groups}

Dieser Vorgang führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in [!UICONTROL Audience Lab]erforderlich sind.

## Erstellen von Segmenttestgruppen {#create-test-groups}

### Voraussetzungen

<!-- create-test-group.xml -->

* Sie müssen mindestens eine **Konversionseigenschaft** einrichten. Sie können Konversionseigenschaften im [Eigenschaften-Aufbau](../../features/traits/create-onboarded-rule-based-traits.md)einrichten, indem Sie als Ereignistyp " **Konversion** "auswählen. Für weitere Informationen darüber, welche Konversionseigenschaften vorhanden sind und wie sie eingerichtet werden, haben wir ein [Video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) für Sie vorbereitet.

   >[!IMPORTANT]
   >
   >[Ordnereigenschaften](../../features/traits/about-folder-traits.md) werden **nicht unterstützt** [!UICONTROL Audience Lab]. Wenn Sie den [Ereignistyp](../../features/traits/create-onboarded-rule-based-traits.md) eines Ordnermerkmals auf **Konversion** einstellen, werden keine Daten in [!UICONTROL Audience Lab] diesem spezifischen Ordnermerkmal generiert.

* Für Unternehmen, die [rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md)verwenden: Weisen Sie die [!UICONTROL Audience Lab] Platzhalterberechtigung[ zu, um Zugriff ](../../features/administration/administration-overview.md#wild-card-permissions)**[!UICONTROL User Groups]** zu gewähren. Mit dieser Berechtigung kann der Benutzer die Ergebnisse eines Tests erstellen und anzeigen. Benutzer können nur Segmente aus einer Datenquelle verwenden, für die sie **Lese** - und **Zuordnung zu Zielberechtigungen** haben. Der Benutzer kann nur Konversionseigenschaften aus einer Datenquelle verwenden, für die er **"Lesen"** -Berechtigungen besitzt. Ein Benutzer kann nur Ziele anzeigen, auf die er ebenfalls Zugriff hat. Bevor Sie einer Gruppe die [!DNL Audience Lab] Platzhalterberechtigung hinzufügen, stellen Sie daher sicher, dass die Gruppe über Folgendes verfügt:
   * Zugang zum Lesen relevanter Konversionseigenschaften;
   * Zugang zu Lese- und Zuordnungssegmenten für Tests;
   * Zugang zu den betreffenden Zielen.

So erstellen Sie eine neue [!UICONTROL Segment Test Group]:

1. Wählen Sie **[!UICONTROL Create New Test Group]** im [!UICONTROL Audience Lab] Dashboard aus, um den Assistenten zu starten.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Füllen Sie ein **[!UICONTROL Test Group Name]** und ein **[!UICONTROL Description]**.
   * Wählen Sie die **[!UICONTROL Base Segment]** entweder durch Navigieren im Dateibrowser oder durch Eingabe in die Suchleiste, bestätigen Sie durch Drücken der Taste **[!UICONTROL Choose Segment.]**
   * Sie können die Testgruppe als Entwurf speichern und die Arbeit daran später fortsetzen.
   * Es wird eine Warnung angezeigt, wenn das von Ihnen ausgewählte Basissegment bereits in anderen Testgruppen verwendet wird. Die doppelte Verwendung des Basissegments kann die Konversionsergebnisse beider Tests verzerren.

1. **[!UICONTROL Allocate Test Segments]**

   * Sie können **bis zu 15 Testsegmente** erstellen und den Prozentsatz der Geräte nach Wunsch teilen.
   * Sie können den Namen der Testsegmente bearbeiten, indem Sie darauf klicken.
   * Die Prozentsätze werden bei der Zuweisung neuer Testsegmente automatisch gleichmäßig auf 100 % aufgeteilt. Anschließend können Sie die Prozentsätze manuell bearbeiten. Aktivieren Sie das Kontrollkästchen, nachdem Sie die Prozentsätze bearbeitet haben, und stellen Sie sicher, dass sie bis zu 100 % ergeben. Andernfalls können Sie nicht mit dem nächsten Schritt fortfahren.

1. **[!UICONTROL Set a Control Segment]**

   * Wählen Sie ein Kontrollsegment aus, wenn Sie einen bestimmten Teil des Segments als Kontrollgruppe festlegen möchten. Mit Steuerungsgruppen können Sie die Auswirkungen der von Ihnen erstellten Testsegmente im Vergleich zu einer Benchmark sehen.
   * Sie können ein Testsegment als Steuerungssegment in der Dropdown-Liste auswählen oder **[!UICONTROL None]** für kein Steuerelement wählen.
   * Klicken Sie auf **[!UICONTROL Next]** , wenn Sie fertig sind.

1. **[!UICONTROL Select Conversion Traits]**

   * Fügen Sie Konversionseigenschaften hinzu, indem Sie im Fenster "Konversionseigenschaften"eingeben. Dies ist ein **obligatorischer** Schritt, und Sie können nicht mit dem nächsten Schritt fortfahren, es sei denn, Sie fügen mindestens eine Konversionseigenschaft hinzu.
   * Sie können auf Wunsch bis zu 5 Konversionseigenschaften hinzufügen.
   * Es wird eine Warnung angezeigt, wenn Sie eine Konversionseigenschaft auswählen, die bereits für andere Testgruppen verwendet wurde.
   * Beachten Sie, dass Audience Manager die Verwendung von [Ordnereigenschaften](/help/using/features/traits/about-folder-traits.md) als Konversionseigenschaften nicht unterstützt. Wenn Sie eine Ordnereigenschaft als Konversionseigenschaft auswählen, werden im Test 0 Summenberichte und Trendberichte angezeigt.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Geben Sie die gewünschten Ziele in das Suchfeld ein oder verwenden Sie den Dropdownpfeil. [!UICONTROL Audience Lab] Testsegmente können an URL-, Cookie- oder Server-zu-Server-Ziele gesendet werden.
   * Ziehen Sie Segmente per Drag &amp; Drop in Ziele.
   * Nachdem Sie ein Segment an einem Ziel abgelegt haben, füllen Sie das **[!UICONTROL Destination Mapping Value]** Blind aus.
   * Sie können dasselbe Testsegment an mehrere Ziele senden und mehrere Testsegmente zu einem einzigen Ziel hinzufügen.
   * Ziele werden ausgegraut, wenn sie für ein bestimmtes Testsegment basierend auf [Datenexportkontrollen](../../features/data-export-controls.md)nicht verfügbar sind.
   * Benutzer sehen nur die Ziele, auf die sie Zugriff haben, je nach der [RBAC-Benutzergruppe](../../features/administration/administration-overview.md) , zu der sie gehören.
   * Schließlich müssen Sie ein Startdatum für Ihre Testgruppe auswählen. Dieses Datum markiert den Beginn des Zeitraums, in dem Ihre Testgruppe an Zielen veröffentlicht wird. Wählen Sie **Kein Enddatum** für einen unbegrenzten Vergleich der Testsegmente.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] mit einem authentifizierten Profil werden nur in Echtzeit-Zielen unterstützt. Wenn ein Testsegment mit einer Profilzusammenführungsregel dieser Konfiguration an ein dateibasiertes Server-zu-Server-Ziel gesendet wird, werden die Zielgruppen möglicherweise nicht aufgefüllt.

   Klicken Sie auf **[!UICONTROL Next]** , um Ihre Testgruppe zu überprüfen und abzuschließen.

1. **[!UICONTROL Summary & Finalize]**

   * Überprüfen Sie die Informationen, die Sie in den vorherigen Schritten hinzugefügt haben, und wählen Sie **[!UICONTROL Finalize Group]**.
   * Denken Sie daran, dass eine Testgruppe, sobald Sie sie fertig gestellt haben, dupliziert oder gelöscht, jedoch nicht bearbeitet werden kann.
   >[!NOTE]
   >* Sie können die Testgruppen jederzeit im Erstellungsprozess speichern und zu einem späteren Zeitpunkt zum Assistenten zurückkehren. Der Status der Testgruppe wird angezeigt **[!UICONTROL Draft]** und die Testgruppe sendet erst dann Daten an Ziele, wenn Sie die Segmenttestgruppe fertigstellen.
   >* Bei Testentwürfen können Sie die Testgruppen durch Klicken **[!UICONTROL Edit]** in der [!UICONTROL Audience Lab] Hauptansicht auf die Testgruppenkarte bearbeiten.


## Segmenttestgruppen bearbeiten {#edit-test-groups}

Sie können [!UICONTROL Audience Lab]außerdem nur Entwurfstestgruppen bearbeiten. Im [!UICONTROL Create Segment Test Group] Assistenten können Sie Ihre Testgruppe als Entwurf speichern und die Arbeit daran später fortsetzen.

1. Navigieren Sie zur [!UICONTROL Audience Lab] Hauptansicht.
1. Suchen Sie nach Ihren Entwurfs-Testgruppen und wählen Sie das **[!UICONTROL Edit]** Steuerelement in der Testgruppenkarte aus.
1. Setzen Sie den Assistenten zum [Erstellen von Segmenttestgruppen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) fort und wählen Sie **[!UICONTROL Finalize Group]** , wenn Sie fertig sind.

## Segmenttestgruppen löschen {#delete-test-groups}

1. Navigieren Sie zur [!UICONTROL Audience Lab] Hauptansicht.
1. Suchen Sie die zu löschende Testgruppe. Sie können das Bild entweder:

   * drücken Sie die **[!UICONTROL Delete]** Steuerung auf der Prüfgruppenkarte oder
   * Drücken Sie auf den Testgruppentitel in der Testgruppenkarte, um zur Ansicht " [Testgruppeninformationen](../../features/audience-lab/audience-lab-information-view.md) "zu wechseln, und drücken Sie das **[!UICONTROL Delete]** Steuerelement in der Titelleiste.

1. Bei [abgeschlossenen Testsegmenten](../../features/audience-lab/audience-lab.md#status)werden Sie in einer Warnmeldung aufgefordert, die CSV-Datei herunterzuladen, um die Berichterstellung zu speichern, wenn Sie möchten.
