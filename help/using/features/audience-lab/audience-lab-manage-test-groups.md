---
description: Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in Audience Lab erforderlich sind
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Testgruppen verwalten
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Testgruppen verwalten {#manage-test-groups}

Dieses Verfahren führt Sie durch die Schritte, die zum Erstellen, Bearbeiten oder Löschen einer Testgruppe in [!UICONTROL Audience Lab] erforderlich sind.

## Erstellen von Segmenttestgruppen {#create-test-groups}

### Voraussetzungen

<!-- create-test-group.xml -->

* Es muss mindestens ein „Konversionseigenschaft **eingerichtet**. Sie können Konversionseigenschaften im [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md) einrichten, indem Sie als Ereignistyp **Konversion** auswählen. Für weitere Informationen zu Konversionseigenschaften und deren Einrichtung haben wir ein [Video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) für Sie vorbereitet.

  >[!IMPORTANT]
  >
  >[Ordnereigenschaften](../../features/traits/about-folder-traits.md) werden **nicht unterstützt** von [!UICONTROL Audience Lab]. Wenn Sie [Ereignistyp](../../features/traits/create-onboarded-rule-based-traits.md) einer Ordnereigenschaft auf **Konversion** setzen, werden in [!UICONTROL Audience Lab] keine Daten für diese bestimmte Ordnereigenschaft generiert.

* Für Unternehmen, die [Rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md) verwenden: Weisen Sie die [!UICONTROL Audience Lab] [Platzhalterberechtigung](../../features/administration/administration-overview.md#wild-card-permissions) zu, um Zugriff **[!UICONTROL User Groups]**. Mit dieser Berechtigung kann der Benutzer die Ergebnisse eines Tests erstellen und anzeigen. Ein Benutzer kann nur Segmente aus einer Datenquelle verwenden, für die er über Berechtigungen **Lesen** und **Zuordnen** Ziel“ verfügt. Benutzende können Konversionseigenschaften nur aus einer Datenquelle verwenden, für die sie über **Leseberechtigungen**. Benutzende können nur Ziele sehen, auf die sie auch Zugriff haben. Bevor Sie also einer Gruppe die Berechtigung [!DNL Audience Lab] Platzhalter hinzufügen, stellen Sie sicher, dass die Gruppe über Folgendes verfügt:
   * Zugriff auf das Lesen relevanter Konversionsmerkmale;
   * Zugriff auf das Lesen und Zuordnen relevanter Segmente für Tests;
   * Zugriff auf relevante Ziele.

So erstellen Sie eine neue [!UICONTROL Segment Test Group]:

1. Wählen Sie **[!UICONTROL Create New Test Group]** im [!UICONTROL Audience Lab] Dashboard aus, um den Assistenten zu starten.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Füllen Sie ein **[!UICONTROL Test Group Name]** und ein **[!UICONTROL Description]** aus.
   * Wählen Sie die **[!UICONTROL Base Segment]** aus, indem Sie entweder im Datei-Browser navigieren oder in die Suchleiste eingeben. Bestätigen Sie Ihre Auswahl, indem Sie **[!UICONTROL Choose Segment.]**
   * Sie können die Testgruppe als Entwurf speichern und die Bearbeitung später fortsetzen.
   * Ein Warnhinweis wird angezeigt, wenn das ausgewählte Basissegment bereits in anderen Testgruppen verwendet wird. Die zweimalige Verwendung des Basissegments kann die Konversionsergebnisse für beide Tests verfälschen.

1. **[!UICONTROL Allocate Test Segments]**

   * Sie können **bis zu 15 Testsegmente“ erstellen** den Prozentsatz der Geräte nach Bedarf teilen.
   * Sie können den Namen der Testsegmente bearbeiten, indem Sie darauf klicken.
   * Die Prozentsätze teilen sich automatisch gleichmäßig auf 100 % auf, wenn neue Testsegmente zugewiesen werden. Anschließend können Sie die Prozentsätze manuell bearbeiten. Aktivieren Sie das Kontrollkästchen nach der Bearbeitung der Prozentsätze und stellen Sie sicher, dass sie bis zu 100 % addieren, da Sie sonst nicht mit dem nächsten Schritt fortfahren können.

1. **[!UICONTROL Set a Control Segment]**

   * Wählen Sie ein Kontrollsegment aus, wenn Sie einen bestimmten Teil des Segments zur Verwendung als Kontrollgruppe zurückstellen möchten. Mit Kontrollgruppen können Sie die Wirkung der von Ihnen erstellten Testsegmente im Vergleich zu einem Benchmark sehen.
   * Sie können ein Testsegment als Kontrollsegment in der Dropdown-Liste auswählen oder &quot;**[!UICONTROL None]** für kein Steuerelement“ auswählen.
   * Wenn Sie fertig sind, klicken Sie auf **[!UICONTROL Next]** .

1. **[!UICONTROL Select Conversion Traits]**

   * Fügen Sie Konversionseigenschaften hinzu, indem Sie im Fenster „Konversionseigenschaft“ eingeben. Dies ist ein **obligatorischer** Schritt, und Sie können nicht mit dem nächsten Schritt fortfahren, es sei denn, Sie fügen mindestens ein Konversionsmerkmal hinzu.
   * Sie können bei Bedarf bis zu 5 Konversionseigenschaften hinzufügen.
   * Ein Warnhinweis wird angezeigt, wenn Sie ein Konversionsmerkmal auswählen, das bereits für andere Testgruppen verwendet wird.
   * Beachten Sie, dass Audience Manager die Verwendung von [Ordnereigenschaften](/help/using/features/traits/about-folder-traits.md) als Konversionseigenschaften nicht unterstützt. Wenn Sie eine Ordnereigenschaft als Konversionseigenschaft auswählen, werden im Test Aggregat- und Trendberichte von 0 angezeigt.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Geben Sie die gewünschten Ziele in das Suchfeld ein oder verwenden Sie den Dropdown-Pfeil. [!UICONTROL Audience Lab] Testsegmente können an URL-, Cookie- oder Server-zu-Server-Ziele gesendet werden.
   * Ziehen Sie Segmente per Drag-and-Drop an Ziele.
   * Nachdem Sie ein Segment in einem Ziel abgelegt haben, füllen Sie die **[!UICONTROL Destination Mapping Value]** im Blind aus.
   * Sie können dasselbe Testsegment an mehrere Ziele senden und mehrere Testsegmente zu einem einzelnen Ziel hinzufügen.
   * Ziele werden ausgegraut, wenn sie für ein bestimmtes Testsegment nicht verfügbar sind, das auf [Datenexportsteuerelementen“ ](../../features/data-export-controls.md).
   * Benutzerinnen und Benutzer sehen nur die Ziele, auf die sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](../../features/administration/administration-overview.md) zu der sie gehören.
   * Schließlich müssen Sie ein Startdatum für Ihre Testgruppe auswählen. Dieses Datum markiert den Beginn des Zeitraums, in dem Ihre Testgruppe für Ziele veröffentlicht wird. Wählen Sie **Kein Enddatum** für einen unbegrenzten Vergleich der Testsegmente aus.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] mit einem authentifizierten Profil werden nur in Echtzeit-Zielen unterstützt. Wenn ein Testsegment mit einer Profilzusammenführungsregel dieser Konfiguration an ein dateibasiertes Server-zu-Server-Ziel gesendet wird, werden die Zielgruppen möglicherweise nicht befüllt.

   Klicken Sie auf **[!UICONTROL Next]** , um Ihre Testgruppe zu überprüfen und abzuschließen.

1. **[!UICONTROL Summary & Finalize]**

   * Überprüfen Sie die in den vorherigen Schritten hinzugefügten Informationen und wählen Sie **[!UICONTROL Finalize Group]** aus.
   * Denken Sie daran, dass eine Testgruppe, sobald sie abgeschlossen ist, dupliziert oder gelöscht, aber nicht bearbeitet werden kann.

   >[!NOTE]
   >* Sie können die Testgruppen zu einem beliebigen Zeitpunkt im Erstellungsprozess speichern und zu einem späteren Zeitpunkt zum Assistenten zurückkehren. Der Testgruppenstatus wird **[!UICONTROL Draft]** und die Testgruppe sendet erst dann Daten an Ziele, wenn Sie die Segment-Testgruppe abgeschlossen haben.
   >* Für Entwurfstests können Sie zurückgehen und die Testgruppen bearbeiten, indem Sie in der Hauptansicht der **[!UICONTROL Edit]** auf der Karte Testgruppe auf [!UICONTROL Audience Lab] klicken.

## Segmenttestgruppen bearbeiten {#edit-test-groups}

In [!UICONTROL Audience Lab] können Sie nur Testgruppen für Entwürfe bearbeiten. Im [!UICONTROL Create Segment Test Group] können Sie Ihre Testgruppe als Entwurf speichern und die Bearbeitung später fortsetzen.

1. Navigieren Sie zur [!UICONTROL Audience Lab] Hauptansicht.
1. Suchen Sie nach Ihren Testgruppenentwürfen und wählen Sie das **[!UICONTROL Edit]** auf der Karte Testgruppe aus.
1. Setzen Sie den [ „Segmenttestgruppe erstellen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) fort und wählen Sie **[!UICONTROL Finalize Group]** aus, wenn Sie fertig sind.

## Segmenttestgruppen löschen {#delete-test-groups}

1. Navigieren Sie zur [!UICONTROL Audience Lab] Hauptansicht.
1. Suchen Sie die Testgruppe, die Sie löschen möchten. Sie haben folgende Möglichkeiten:

   * Drücken Sie die **[!UICONTROL Delete]** in der Testgruppenkarte oder
   * Klicken Sie auf den Titel der Testgruppe auf der Karte Testgruppe , um zur Ansicht [Testgruppeninformationen](../../features/audience-lab/audience-lab-information-view.md) zu wechseln, und drücken Sie das **[!UICONTROL Delete]** in der Titelleiste.

1. Bei [abgeschlossenen Testsegmenten](../../features/audience-lab/audience-lab.md#status) werden Sie durch einen Warnhinweis aufgefordert, die CSV-Datei herunterzuladen, um die Berichte bei Bedarf zu speichern.
