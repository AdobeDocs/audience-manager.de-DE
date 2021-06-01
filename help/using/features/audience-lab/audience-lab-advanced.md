---
description: In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für die doppelte Zuordnungsvorlage für Audience Lab und die Segmentspeicherung bieten.
seo-description: In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für die doppelte Zuordnungsvorlage für Audience Lab und die Segmentspeicherung bieten.
seo-title: Erweiterte Funktionen von Audience Lab
solution: Audience Manager
title: Erweiterte Funktionen von Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: 'Audience Lab '
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# [!DNL Audience Lab] Erweiterte Funktionen  {#audience-lab-advanced-functionality}

In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für [!DNL Audience Lab] bieten: [!DNL Duplicate Allocation Template] und [!DNL Segment Holdout].

## Vorlage für doppelte Zuordnung {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab] stellt [!DNL Allocation Template] die verschiedenen Auswahlen dar, die Sie beim Erstellen einer Testgruppe treffen:

* die Verteilung der Geräte zwischen Testsegmenten;
* Zuordnung von Testsegmenten zu Zielen;
* Die Konversionseigenschaften, die Sie für eine Testgruppe verwenden;
* Der Datumsbereich, in dem die Testgruppe in Ihren ausgewählten Zielen veröffentlicht wird.

Durch Duplizieren einer Zuordnungsvorlage können Sie dieselbe Verteilung von Testsegmenten und Zielen für ein anderes Basissegment in einer neuen Testgruppe wiederverwenden. Ein Beispiel für eine Zuordnungsvorlage ist unten dargestellt. Das Bild wird aus dem Schritt [!UICONTROL Summary & Finalize] im Workflow **Erstellen einer Testgruppe** übernommen.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Verwenden der Vorlage &quot;Zuordnung duplizieren&quot;

Erstellen Sie eine erste Testgruppe und wählen Sie **[!UICONTROL Duplicate Allocation Template]** aus, um dieselben Einstellungen für mehrere Testgruppen wiederzuverwenden. Sie können diese Funktion beispielsweise verwenden, wenn Sie einen Test durchführen, bei dem Sie die Wirksamkeit mehrerer Ziele für mehrere Segmente ermitteln möchten.

1. Suchen Sie in der Hauptansicht von Audience Lab nach der Testgruppe, deren Zuordnungsvorlage Sie in einer neuen Testgruppe reproduzieren möchten. Wählen Sie im Dropdown-Feld **[!UICONTROL Duplicate Allocation Template]** aus.

   ![](assets/duplicate-allocation-template.png)

2. Im Assistenten [!UICONTROL Create Test Group] können Sie bei Bedarf ein Basissegment angeben und Ihre Testsegmente umbenennen.
3. Sie *können* nicht ändern:

   * die Verteilung der Geräte zwischen Testsegmenten;
   * die Konversionseigenschaften;
   * Die Zuordnung von Testsegmenten zu Zielen. Sie können nur den Zuordnungsschlüssel für die Ziele ausfüllen, die eines erfordern.
   * Der Datumsbereich, in dem Ihre Testgruppe in Ihren ausgewählten Zielen veröffentlicht.

4. Überprüfen Sie die Informationen, die Sie in den vorherigen Schritten hinzugefügt haben, und wählen Sie **[!UICONTROL Finalize Group]** aus.

## Testsegment mit {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] ist eine erweiterte Funktion, die auf Kundenanfrage aktiviert wird. Wenden Sie sich an [!DNL Customer Care] oder [!DNL Adobe Consulting], um diese Funktion zu aktivieren.

Verwenden Sie diese Funktion, um zu verhindern, dass ein Teil der Zielgruppe in den Test einbezogen wird. Der ausgewählte Prozentsatz wird aus dem Test ausgeschlossen. Auf diese Weise können Sie die Anzahl der Konversionen aus Zielgruppen (aktiviert für Ziele) und Zielgruppen ohne Targeting (Ausschluss-Gruppe) messen und vergleichen.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Verwenden des Testsegments Holdout

1. Erstellen Sie mit dem Assistenten [!UICONTROL Create Test Group] eine neue Testgruppe.
1. Im Schritt **[!UICONTROL Allocate Test Segment]** können Sie einen Teil der Audience auswählen, der nicht getestet werden soll.

   ![Listenelement](assets/test-segment-holdout.png)

1. Mit dem Schieberegler können Sie einstellen, wie viele Geräte Sie aus dem Test ausschließen möchten. Beachten Sie, dass Test Segment 1 und Test Segment 2 jetzt nur noch 70 % der Geräte insgesamt ausmachen.

   ![](assets/test-segment-holdout-selected.png)

1. Führen Sie die restlichen Schritte im Workflow **[!UICONTROL Create Test Group]** aus und wählen Sie **[!UICONTROL Finalize Group]** aus, wenn Sie mit Ihrer Auswahl zufrieden sind. Sie haben jetzt eine Testgruppe mit einem Teil der Zielgruppe, die nicht getestet werden konnte.
