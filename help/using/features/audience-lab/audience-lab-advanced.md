---
description: In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für die Audience Lab-Duplikat-Zuordnungsvorlage und den Segmentausfall bereitstellen.
seo-description: In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für die Audience Lab-Duplikat-Zuordnungsvorlage und den Segmentausfall bereitstellen.
seo-title: Erweiterte Funktionen von Audience Lab
solution: Audience Manager
title: Erweiterte Funktionen von Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 1%

---


# [!DNL Audience Lab] Erweiterte Funktionen  {#audience-lab-advanced-functionality}

In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für [!DNL Audience Lab] bieten: [!DNL Duplicate Allocation Template] und [!DNL Segment Holdout].

## Duplikat-Zuordnungsvorlage {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab] stellt [!DNL Allocation Template] die verschiedenen Auswahlen dar, die Sie beim Erstellen einer Testgruppe treffen:

* die Verteilung der Geräte zwischen Testsegmenten;
* Zuordnung von Testsegmenten zu Zielen;
* die Konversionseigenschaften, die Sie für eine Testgruppe verwenden;
* Der Datumsbereich, in dem die Testgruppe für Ihre ausgewählten Ziele veröffentlicht wird.

Durch Duplizieren einer Zuordnungsvorlage können Sie dieselbe Verteilung von Testsegmenten und Zielen für ein anderes Basissegment in einer neuen Testgruppe wiederverwenden. Ein Beispiel für eine Zuordnungsvorlage ist unten dargestellt. Das Bild wird aus dem Schritt [!UICONTROL Summary & Finalize] im Arbeitsablauf **Testgruppe erstellen** entnommen.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Verwenden der Vorlage für die Duplikat-Zuordnung

Erstellen Sie eine erste Testgruppe und wählen Sie **[!UICONTROL Duplicate Allocation Template]** aus, um dieselben Einstellungen für mehrere Testgruppen wiederzuverwenden. Sie können diese Funktion beispielsweise verwenden, wenn Sie einen Test durchführen, bei dem Sie die Wirksamkeit mehrerer Ziele für mehrere Segmente ermitteln möchten.

1. Suchen Sie in der Hauptgruppe &quot;Audience Lab&quot;nach der Testgruppe, deren Zuordnungsvorlage Sie in einer neuen Testgruppe reproduzieren möchten. Wählen Sie im Dropdown-Feld **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. Im Assistenten [!UICONTROL Create Test Group] können Sie bei Bedarf ein Basissegment angeben und Ihre Testsegmente umbenennen.
3. Sie können *nicht* ändern:

   * die Verteilung der Geräte zwischen Testsegmenten;
   * die Konversionseigenschaft(en);
   * Die Zuordnung von Testsegmenten zu Zielen. Sie können nur den Zuordnungsschlüssel für die Ziele ausfüllen, für die ein Zuordnungsschlüssel erforderlich ist.
   * Der Datumsbereich, in dem Ihre Testgruppe an den ausgewählten Zielen veröffentlicht wird.

4. Überprüfen Sie die Informationen, die Sie in den vorherigen Schritten hinzugefügt haben, und wählen Sie **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] ist eine erweiterte Funktion, die auf Kundenanforderung aktiviert wird. Bitte wenden Sie sich an [!DNL Customer Care] oder [!DNL Adobe Consulting], um diese Funktion zu aktivieren.

Verwenden Sie diese Funktion, um zu verhindern, dass ein Teil der Audience in den Test einbezogen wird. Der ausgewählte Prozentsatz wird aus dem Test ausgeschlossen. Auf diese Weise können Sie die Anzahl der Konversionen von zielgerichteten (auf Zielen aktivierten) und nicht zielgerichteten (ausgeschlossenen) Audiencen messen und vergleichen.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Testsegment-Holdout

1. Erstellen Sie mithilfe des Assistenten [!UICONTROL Create Test Group] eine neue Testgruppe.
1. Im Schritt **[!UICONTROL Allocate Test Segment]** können Sie einen Teil der Audience auswählen, der nicht getestet werden soll.

   ![Liste](assets/test-segment-holdout.png)

1. Mit dem Schieberegler können Sie einstellen, wie viele Geräte Sie aus dem Test heraushalten möchten. Beachten Sie, dass Test Segment 1 und Test Segment 2 jetzt nur noch 70 % der Geräte ausmachen.

   ![](assets/test-segment-holdout-selected.png)

1. Gehen Sie durch die restlichen Schritte im **[!UICONTROL Create Test Group]**-Workflow und wählen Sie **[!UICONTROL Finalize Group]**, wenn Sie mit Ihrer Auswahl zufrieden sind. Sie haben jetzt eine Testgruppe, bei der ein Teil der Audience nicht getestet werden kann.
