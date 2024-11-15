---
description: Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in Audience Lab erforderlich sind
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Verwalten von Testgruppen
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Verwalten von Testgruppen {#manage-test-groups}

Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in [!UICONTROL Audience Lab] erforderlich sind.

## Erstellen von Segmenttestgruppen {#create-test-groups}

### Voraussetzungen

<!-- create-test-group.xml -->

* Sie müssen mindestens eine **Konversionseigenschaft** einrichten. Sie können Konversionseigenschaften im [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md) einrichten, indem Sie **Konversion** als Ereignistyp auswählen. Weitere Informationen dazu, welche Konversionseigenschaften vorhanden sind und wie sie eingerichtet werden, erhalten Sie von uns, wenn Sie ein [Video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) für Sie vorbereitet haben.

  >[!IMPORTANT]
  >
  >[Ordnereigenschaften](../../features/traits/about-folder-traits.md) werden **nicht von** von [!UICONTROL Audience Lab] unterstützt. Wenn Sie den [Ereignistyp](../../features/traits/create-onboarded-rule-based-traits.md) einer Ordnereigenschaft auf **Konversion** setzen, werden in [!UICONTROL Audience Lab] keine Daten für diese bestimmte Ordnereigenschaft generiert.

* Für Unternehmen, die die [rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md) verwenden: Weisen Sie die [!UICONTROL Audience Lab] [Platzhalterberechtigung](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** zu, um Zugriff bereitzustellen. Mit dieser Berechtigung kann der Benutzer die Ergebnisse eines Tests erstellen und anzeigen. Ein Benutzer kann nur Segmente aus einer Datenquelle verwenden, für die er über die Berechtigungen **read** und **map to destination** verfügt. Der Benutzer kann Konversionseigenschaften nur aus einer Datenquelle verwenden, für die er über **&quot;read&quot;** -Berechtigungen verfügt. Ein Benutzer kann nur Ziele anzeigen, auf die er ebenfalls Zugriff hat. Stellen Sie also vor dem Hinzufügen der Platzhalterberechtigung [!DNL Audience Lab] zu einer Gruppe sicher, dass die Gruppe über Folgendes verfügt:
   * Zugriff auf das Lesen relevanter Konversionseigenschaften;
   * Zugang zu Lese- und Zuordnungssegmenten für Tests;
   * Zugang zu relevanten Zielen.

So erstellen Sie eine neue [!UICONTROL Segment Test Group]:

1. Wählen Sie **[!UICONTROL Create New Test Group]** im Dashboard [!UICONTROL Audience Lab] aus, um den Assistenten zu starten.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Füllen Sie eine **[!UICONTROL Test Group Name]** und eine **[!UICONTROL Description]** aus.
   * Wählen Sie die **[!UICONTROL Base Segment]** aus, indem Sie entweder im Dateibrowser navigieren oder in die Suchleiste eingeben und durch Drücken von **[!UICONTROL Choose Segment.]** bestätigen.
   * Sie können die Testgruppe als Entwurf speichern und die Arbeit daran später fortsetzen.
   * Es wird ein Warnhinweis angezeigt, falls das von Ihnen ausgewählte Basissegment bereits in anderen Testgruppen verwendet wird. Die doppelte Verwendung des Basissegments kann die Konversionsergebnisse für beide Tests verzerren.

1. **[!UICONTROL Allocate Test Segments]**

   * Sie können **bis zu 15 Testsegmente** erstellen und den Prozentsatz der Geräte nach Wunsch teilen.
   * Sie können den Namen der Testsegmente bearbeiten, indem Sie darauf klicken.
   * Die Prozentsätze teilen sich bei der Zuweisung neuer Testsegmente automatisch gleichmäßig auf 100 %. Anschließend können Sie die Prozentsätze manuell bearbeiten. Aktivieren Sie das Kontrollkästchen, nachdem Sie die Prozentsätze bearbeitet haben, und stellen Sie sicher, dass sie bis zu 100 % ergeben. Andernfalls können Sie nicht mit dem nächsten Schritt fortfahren.

1. **[!UICONTROL Set a Control Segment]**

   * Wählen Sie ein Kontrollsegment aus, wenn Sie einen bestimmten Teil des Segments zur Verwendung als Kontrollgruppe beilegen möchten. Kontrollgruppen ermöglichen es Ihnen, die Auswirkungen der von Ihnen erstellten Testsegmente im Vergleich zu einem Benchmark zu sehen.
   * Sie können ein Testsegment als Kontrollsegment in der Dropdown-Liste auswählen oder Sie können &quot;**[!UICONTROL None]**&quot;für kein Steuerelement auswählen.
   * Klicken Sie auf **[!UICONTROL Next]** , wenn Sie fertig sind.

1. **[!UICONTROL Select Conversion Traits]**

   * Fügen Sie Konversionseigenschaften hinzu, indem Sie im Fenster &quot;Konversionseigenschaften&quot;eingeben. Dies ist ein Schritt **mandatory** und Sie können nicht mit dem nächsten Schritt fortfahren, es sei denn, Sie fügen mindestens eine Konversionseigenschaft hinzu.
   * Sie können bei Bedarf bis zu 5 Konversionseigenschaften hinzufügen.
   * Es wird ein Warnhinweis angezeigt, wenn Sie eine Konversionseigenschaft auswählen, die bereits für andere Testgruppen verwendet wurde.
   * Beachten Sie, dass Audience Manager die Verwendung von [Ordnereigenschaften](/help/using/features/traits/about-folder-traits.md) als Konversionseigenschaften nicht unterstützt. Wenn Sie eine Ordnereigenschaft als Konversionseigenschaft auswählen, werden im Test 0 Aggregat- und Trendberichte angezeigt.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Geben Sie die gewünschten Ziele in das Suchfeld ein oder verwenden Sie den Dropdown-Pfeil. [!UICONTROL Audience Lab] -Testsegmente können an URL-, Cookie- oder Server-zu-Server-Ziele gesendet werden.
   * Ziehen Sie Segmente per Drag-and-Drop in Ziele.
   * Geben Sie nach dem Ablegen eines Segments in einem Ziel die **[!UICONTROL Destination Mapping Value]** im Blind ein.
   * Sie können dasselbe Testsegment an mehrere Ziele senden und mehrere Testsegmente zu einem einzelnen Ziel hinzufügen.
   * Ziele werden grau dargestellt, wenn sie für ein bestimmtes Testsegment basierend auf [Datenexportkontrollen](../../features/data-export-controls.md) nicht verfügbar sind.
   * Benutzer sehen nur die Ziele, auf die sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](../../features/administration/administration-overview.md), der sie angehören.
   * Schließlich müssen Sie ein Startdatum für Ihre Testgruppe auswählen. Dieses Datum markiert den Beginn des Zeitraums, in dem Ihre Testgruppe in Zielen veröffentlicht wird. Wählen Sie **Kein Enddatum** für einen unbegrenzten Vergleich der Testsegmente.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] mit einem authentifizierten Profil wird nur in Echtzeit-Zielen unterstützt. Wenn ein Testsegment mit einer Profilzusammenführungsregel dieser Konfiguration an ein dateibasiertes Server-zu-Server-Ziel gesendet wird, werden die Zielgruppen möglicherweise nicht aufgefüllt.

   Klicken Sie auf **[!UICONTROL Next]** , um Ihre Testgruppe zu überprüfen und abzuschließen.

1. **[!UICONTROL Summary & Finalize]**

   * Überprüfen Sie die Informationen, die Sie in den vorherigen Schritten hinzugefügt haben, und wählen Sie **[!UICONTROL Finalize Group]** aus.
   * Denken Sie daran, dass eine Testgruppe nach ihrer Fertigstellung dupliziert oder gelöscht, aber nicht bearbeitet werden kann.

   >[!NOTE]
   >* Sie können die Testgruppen jederzeit im Erstellungsprozess speichern und zu einem späteren Zeitpunkt zum Assistenten zurückkehren. Der Testgruppenstatus ist **[!UICONTROL Draft]** und die Testgruppe sendet erst dann Daten an Ziele, wenn Sie die Segmenttestgruppe fertigstellen.
   >* Für Testentwürfe können Sie die Testgruppen wiederherstellen und bearbeiten, indem Sie in der Hauptansicht von [!UICONTROL Audience Lab] auf der Testgruppenkarte auf **[!UICONTROL Edit]** klicken.

## Bearbeiten von Segmenttestgruppen {#edit-test-groups}

In [!UICONTROL Audience Lab] können Sie nur Entwürfe von Testgruppen bearbeiten. Im Assistenten [!UICONTROL Create Segment Test Group] können Sie Ihre Testgruppe als Entwurf speichern und die Arbeit daran später fortsetzen.

1. Navigieren Sie zur Hauptansicht &quot;[!UICONTROL Audience Lab]&quot;.
1. Suchen Sie nach Ihren Testgruppenentwürfen und wählen Sie das Steuerelement **[!UICONTROL Edit]** in der Testgruppenkarte aus.
1. Setzen Sie den Assistenten [Segmenttestgruppe erstellen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) fort und wählen Sie danach **[!UICONTROL Finalize Group]** aus.

## Segmenttestgruppen löschen {#delete-test-groups}

1. Navigieren Sie zur Hauptansicht &quot;[!UICONTROL Audience Lab]&quot;.
1. Suchen Sie die Testgruppe, die Sie löschen möchten. Sie haben folgende Möglichkeiten:

   * Drücken Sie die **[!UICONTROL Delete]** -Steuerung auf der Testgruppenkarte oder
   * Drücken Sie den Testgruppentitel auf der Testgruppenkarte, um zur Ansicht [Testgruppeninformationen](../../features/audience-lab/audience-lab-information-view.md) zu wechseln, und drücken Sie das Steuerelement **[!UICONTROL Delete]** in der Titelleiste.

1. Für [abgeschlossene Testsegmente](../../features/audience-lab/audience-lab.md#status) werden Sie in einem Warnhinweis aufgefordert, die CSV-Datei herunterzuladen, um die Berichterstellung zu speichern.
