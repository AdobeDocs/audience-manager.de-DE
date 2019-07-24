---
description: In diesem Artikel werden zwei Funktionen beschrieben, die eine erweiterte Funktion für die Audience Lab Duplicate Allocation Template und Segment Holdout bereitstellen.
seo-description: In diesem Artikel werden zwei Funktionen beschrieben, die eine erweiterte Funktion für die Audience Lab Duplicate Allocation Template und Segment Holdout bereitstellen.
seo-title: Audience Lab Advanced Feature
solution: Audience Manager
title: Audience Lab Advanced Feature
uuid: 0 f 57 d 634-Caa 0-40 da -81 a 2-c 23 fbd 299 bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Erweiterte Funktionen {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* Verteilung von Geräten zwischen Testsegmenten;
* Zuordnung von Testsegmenten zu Zielen;
* Die Konversionseigenschaften, die Sie für eine Testgruppe verwenden;
* Der Datumsbereich, in dem die Testgruppe zu Ihren ausgewählten Zielen veröffentlicht wird.

Durch Duplizierung einer Zuordnungsvorlage können Sie dieselbe Verteilung von Testsegmenten und Zielen für ein anderes Basissegment in einer neuen Testgruppe wiederverwenden. Nachfolgend sehen Sie ein Beispiel für eine Zuordnungsvorlage. The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Verwenden der doppelten Zuordnungsvorlage

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. Sie können diese Funktion zum Beispiel verwenden, wenn Sie einen Test ausführen, in dem Sie die Effektivität mehrerer Ziele für mehrere Segmente ermitteln möchten.

1. Suchen Sie in der Hauptansicht "Audience Lab" nach der Testgruppe, deren Zuordnungsvorlage Sie in einer neuen Testgruppe reproduzieren möchten. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In the [!UICONTROL Create Test Group] wizard, you can specify a base segment and rename your test segments, if you wish.
3. You *cannot* modify:

   * Verteilung von Geräten zwischen Testsegmenten;
   * Die Konversionseigenschaften;
   * Zuordnung von Testsegmenten zu Zielen. Sie können den Zuordnungsschlüssel nur für die Ziele ausfüllen, die eine erfordern.
   * Der Datumsbereich, in dem Ihre Testgruppe auf Ihren ausgewählten Zielen veröffentlicht wird.

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] ist eine erweiterte Funktion, die bei der Kundenanforderung aktiviert ist. Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

Verwenden Sie diese Funktion, um einen Teil der Zielgruppe nicht in den Test aufzunehmen. Der ausgewählte Prozentsatz wird aus dem Test entfernt. Auf diese Weise können Sie die Anzahl der Konversionen von Zielgruppen (aktiviert auf Ziele) und Zielgruppen ohne Zielgruppe ("Holdout-Gruppe" ) messen und vergleichen.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Verwenden von Testsegment Holdout

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. In the **[!UICONTROL Allocate Test Segment]** step, you can select a part of the audience to be withheld from testing.

   ![Listenelement](assets/test-segment-holdout.png)

1. Verwenden Sie den Schieberegler, um anzupassen, wie viele Geräte aus dem Test ausgeschlossen werden sollen. Beachten Sie, dass das Test Segment 1 und das Testsegment 2 jetzt nur 70% aller Geräte ausmachen.

   ![](assets/test-segment-holdout-selected.png)

1. Go through the rest of the steps in the **[!UICONTROL Create Test Group]** workflow and select **[!UICONTROL Finalize Group]** when you're satisfied with your selection. Sie haben jetzt eine Testgruppe mit einem Teil der Zielgruppe, der vom Test abhält.
