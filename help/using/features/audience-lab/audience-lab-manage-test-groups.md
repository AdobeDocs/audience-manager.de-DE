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


# Testgruppen verwalten {#manage-test-groups}

Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe erforderlich sind [!UICONTROL Audience Lab].

## Segmenttestgruppen erstellen {#create-test-groups}

### Voraussetzungen

<!-- create-test-group.xml -->

* Sie müssen mindestens eine **Konversion-Eigenschaft** einrichten. Sie können Konversionseigenschaften im [Eigenschaftenaufbau](../../features/traits/create-onboarded-rule-based-traits.md)einrichten, indem Sie **die Konversion** als Ereignistyp auswählen. Für weitere Informationen zu Konversionseigenschaften und deren Einrichtung haben wir ein [Video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) vorbereitet.

   >[!IMPORTANT]
   >
   >[Folder traits](../../features/traits/about-folder-traits.md) are **not supported** by [!UICONTROL Audience Lab]. Wenn Sie den [Ereignistyp](../../features/traits/create-onboarded-rule-based-traits.md) einer Ordnereigenschaft auf **die Konversion** einstellen, werden keine Daten für [!UICONTROL Audience Lab] diese spezielle Ordnereigenschaft generiert.

* Für Unternehmen, die [rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md)verwenden: Weisen Sie dem [!UICONTROL Audience Lab][Platzhalterzugriff](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** Zugriff zu. Mit dieser Berechtigung kann der Benutzer die Ergebnisse eines Tests erstellen und anzeigen. Ein Benutzer kann nur Segmente aus einer Datenquelle verwenden, **die sie lesen** und **die Zielgruppenberechtigungen** zuordnen. Der Benutzer kann nur Konversionseigenschaften aus einer Datenquelle verwenden, für die **sie** die Berechtigung &quot;Lesen&quot; haben. Ein Benutzer kann nur Ziele sehen, auf die er Zugriff hat. Bevor Sie also den [!DNL Audience Lab] Platzhalterzugriff einer Gruppe hinzufügen, stellen Sie sicher, dass die Gruppe:
   * Zugriff auf relevante Konversionseigenschaften;
   * Zugriff auf relevante Segmente für Tests;
   * Zugriff auf relevante Ziele.

So erstellen Sie eine neue [!UICONTROL Segment Test Group]:

1. Wählen **[!UICONTROL Create New Test Group]** Sie im [!UICONTROL Audience Lab] Dashboard den Assistenten aus.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Füllen Sie a **[!UICONTROL Test Group Name]** und **[!UICONTROL Description]** a aus.
   * Wählen Sie entweder **[!UICONTROL Base Segment]** durch Navigieren im Dateibrowser oder durch Eingabe in der Suchleiste. **[!UICONTROL Choose Segment.]**
   * Sie können die Testgruppe als Entwurf speichern und später fortsetzen.
   * Ein Warnhinweis wird angezeigt, wenn das ausgewählte Basissegment bereits in anderen Testgruppen verwendet wird. Die doppelte Verwendung des Basissegments kann die Umrechnungsergebnisse beider Tests verfälschen.

1. **[!UICONTROL Allocate Test Segments]**

   * Sie können **bis zu 15 Testsegmente erstellen** und den Prozentsatz der Geräte wie gewünscht unterteilen.
   * Sie können den Namen der Testsegmente bearbeiten, indem Sie darauf klicken.
   * Die Prozentsätze werden automatisch gleichmäßig auf 100% aufgeteilt, wenn neue Testsegmente zugeordnet werden. Sie können die Prozentsätze dann manuell bearbeiten. Klicken Sie auf das Kontrollkästchen, nachdem Sie die Prozentsätze bearbeitet haben, und stellen Sie sicher, dass sie bis zu 100% hinzufügen. Andernfalls können Sie nicht mit dem nächsten Schritt fortfahren.

1. **[!UICONTROL Set a Control Segment]**

   * Wählen Sie ein Kontrollsegment aus, wenn Sie einen bestimmten Teil des Segments festlegen möchten, der als Kontrollgruppe verwendet werden soll. Mit Steuerungsgruppen können Sie die Auswirkungen der Testsegmente erkennen, die Sie im Vergleich zu einem Vergleich erstellt haben.
   * Sie können ein Testsegment als Steuerungssegment in der Dropdown-Liste auswählen oder **[!UICONTROL None]** für kein Steuerelement wählen.
   * Klicken Sie auf, **[!UICONTROL Next]** wenn Sie fertig sind.

1. **[!UICONTROL Select Conversion Traits]**

   * Fügen Sie Konversionseigenschaften hinzu, indem Sie in das Fenster Konversionseigenschaften eingeben. Dies ist ein **obligatorischer** Schritt, und Sie können nicht zum nächsten Schritt gehen, es sei denn, Sie fügen mindestens eine Konversionseigenschaft hinzu.
   * Falls gewünscht, können Sie bis zu 5 Konversionseigenschaften hinzufügen.
   * Es wird ein Warnhinweis angezeigt, wenn Sie eine Konversionseigenschaft auswählen, die bereits für andere Testgruppen verwendet wird.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Geben Sie in das Suchfeld die gewünschten Ziele ein oder verwenden Sie den Dropdownpfeil. [!UICONTROL Audience Lab] Testsegmente können an URL, Cookie oder Server-zu-Server-Ziele gesendet werden.
   * Ziehen Sie Segmente per Drag &amp; Drop in Ziele.
   * Wenn Sie ein Segment an einem Ziel abgelegt haben, füllen Sie die **[!UICONTROL Destination Mapping Value]** Blindheit aus.
   * Sie können dasselbe Testsegment an mehrere Ziele senden und einem einzelnen Ziel mehrere Testsegmente hinzufügen.
   * Ziele werden ausgegraut, wenn sie auf Grundlage [von Datenexportsteuerelementen für ein bestimmtes Testsegment nicht verfügbar](../../features/data-export-controls.md)sind.
   * Benutzer sehen nur die Ziele, auf die sie Zugriff haben, auf Grundlage der [RBAC-Benutzergruppe](../../features/administration/administration-overview.md) , zu der sie gehören.
   * Schließlich müssen Sie ein Startdatum für Ihre Testgruppe auswählen. Dieses Datum markiert den Zeitraum, in dem Ihre Testgruppe in Ziele veröffentlicht wird. Wählen **Sie Kein Enddatum** für einen unbegrenzten Vergleich der Testsegmente aus.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] mit einem authentifizierten Profil werden nur in Echtzeit-Zielen unterstützt. Wenn ein Testsegment mit einer Profilzusammenführungsregel dieser Konfiguration an ein dateibasiertes Server-to-Server-Ziel gesendet wird, werden die Zielgruppen möglicherweise nicht gefüllt.

   Klicken **[!UICONTROL Next]** Sie auf, um Ihre Testgruppe zu überprüfen und zu beenden.

1. **[!UICONTROL Summary & Finalize]**

   * Überprüfen Sie die Informationen, die Sie in den vorherigen Schritten hinzugefügt haben, und wählen **[!UICONTROL Finalize Group]** Sie diese aus.
   * Beachten Sie, dass Sie nach Abschluss einer Testgruppe dupliziert oder gelöscht werden können, aber nicht bearbeitet werden können.
   >[!NOTE]
   >* Sie können die Testgruppen jederzeit im Erstellungsvorgang speichern und zu einem späteren Zeitpunkt zum Assistenten zurückkehren. Der Status der Testgruppe wird **[!UICONTROL Draft]** und die Testgruppe sendet keine Daten an Ziele, bis Sie die Segmenttestgruppe fertigstellen.
   >* Bei Entwurfstests können Sie die Testgruppen zurücksetzen und bearbeiten, indem Sie in der Hauptansicht auf **[!UICONTROL Edit]** die Karte der Testgruppe [!UICONTROL Audience Lab] klicken.


## Segmenttestgruppen bearbeiten {#edit-test-groups}

In [!UICONTROL Audience Lab]können Sie nur Entwurfstestgruppen bearbeiten. Im [!UICONTROL Create Segment Test Group] Assistenten können Sie Ihre Testgruppe als Entwurf speichern und später fortsetzen.

1. Navigieren Sie zur [!UICONTROL Audience Lab] Hauptansicht.
1. Suchen Sie nach Ihren Entwurfsgruppen und wählen Sie die **[!UICONTROL Edit]** Steuerung in der Karte der Testgruppe aus.
1. Nehmen Sie den [Assistenten &quot;Segmenttestgruppe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) erstellen&quot; wieder auf und wählen Sie **[!UICONTROL Finalize Group]** dann aus, wann Sie fertig sind.

## Segmenttestgruppen löschen {#delete-test-groups}

1. Navigieren Sie zur [!UICONTROL Audience Lab] Hauptansicht.
1. Suchen Sie die Testgruppe, die Sie löschen möchten. Sie können das Bild entweder:

   * drücken Sie die **[!UICONTROL Delete]** Steuerung auf der Karte der Testgruppe oder
   * Drücken Sie in der Testgruppenkarte den Titel der Testgruppe, um zur Ansicht [&quot;Test Group Information](../../features/audience-lab/audience-lab-information-view.md) &quot; zu wechseln, und drücken Sie in **[!UICONTROL Delete]** der Titelleiste die Steuerung.

1. Bei [abgeschlossenen Testsegmenten](../../features/audience-lab/audience-lab.md#status)werden Sie aufgefordert, die CSV-Datei herunterzuladen, um die Berichterstellung zu speichern, falls gewünscht.
