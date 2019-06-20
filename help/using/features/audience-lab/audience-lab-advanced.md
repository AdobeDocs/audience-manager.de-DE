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

In diesem Artikel werden zwei Funktionen beschrieben, [!DNL Audience Lab]die eine erweiterte Funktionalität bieten: [!DNL Duplicate Allocation Template] und [!DNL Segment Holdout].

## Doppelte Zuordnungsvorlage {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab]stehen die [!DNL Allocation Template] verschiedenen Auswahlmöglichkeiten für die Erstellung einer Testgruppe zur Verfügung:

* Verteilung von Geräten zwischen Testsegmenten;
* Zuordnung von Testsegmenten zu Zielen;
* Die Konversionseigenschaften, die Sie für eine Testgruppe verwenden;
* Der Datumsbereich, in dem die Testgruppe zu Ihren ausgewählten Zielen veröffentlicht wird.

Durch Duplizierung einer Zuordnungsvorlage können Sie dieselbe Verteilung von Testsegmenten und Zielen für ein anderes Basissegment in einer neuen Testgruppe wiederverwenden. Nachfolgend sehen Sie ein Beispiel für eine Zuordnungsvorlage. Das Bild wird aus dem [!UICONTROL Summary & Finalize] Schritt im Arbeitsablauf &quot;Testgruppe **erstellen** &quot; übernommen.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Verwenden der doppelten Zuordnungsvorlage

Erstellen Sie eine anfängliche Testgruppe und wählen **[!UICONTROL Duplicate Allocation Template]** Sie dann die gleichen Einstellungen für mehrere Testgruppen aus. Sie können diese Funktion zum Beispiel verwenden, wenn Sie einen Test ausführen, in dem Sie die Effektivität mehrerer Ziele für mehrere Segmente ermitteln möchten.

1. Suchen Sie in der Hauptansicht &quot;Audience Lab&quot; nach der Testgruppe, deren Zuordnungsvorlage Sie in einer neuen Testgruppe reproduzieren möchten. Wählen **[!UICONTROL Duplicate Allocation Template]** Sie in der Dropdown-Liste den Eintrag.

   ![](assets/duplicate-allocation-template.png)

2. Im [!UICONTROL Create Test Group] Assistenten können Sie ein Basissegment angeben und Ihre Testsegmente umbenennen, falls gewünscht.
3. Sie können Folgendes *nicht* ändern:

   * Verteilung von Geräten zwischen Testsegmenten;
   * Die Konversionseigenschaften;
   * Zuordnung von Testsegmenten zu Zielen. Sie können den Zuordnungsschlüssel nur für die Ziele ausfüllen, die eine erfordern.
   * Der Datumsbereich, in dem Ihre Testgruppe auf Ihren ausgewählten Zielen veröffentlicht wird.

4. Überprüfen Sie die Informationen, die Sie in den vorherigen Schritten hinzugefügt haben, und wählen **[!UICONTROL Finalize Group]** Sie diese aus.

## Testsegment testen {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] ist eine erweiterte Funktion, die bei der Kundenanforderung aktiviert ist. Bitte wenden [!DNL Customer Care][!DNL Adobe Consulting] Sie sich an oder aktivieren Sie diese Funktion.

Verwenden Sie diese Funktion, um einen Teil der Zielgruppe nicht in den Test aufzunehmen. Der ausgewählte Prozentsatz wird aus dem Test entfernt. Auf diese Weise können Sie die Anzahl der Konversionen von Zielgruppen (aktiviert auf Ziele) und Zielgruppen ohne Zielgruppe (&quot;Holdout-Gruppe&quot; ) messen und vergleichen.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Verwenden von Testsegment Holdout

1. Erstellen Sie mit dem [!UICONTROL Create Test Group] Assistenten eine neue Testgruppe.
1. Im **[!UICONTROL Allocate Test Segment]** Schritt können Sie einen Teil der Zielgruppe auswählen, der vom Test beibehalten werden soll.

   ![Listenelement](assets/test-segment-holdout.png)

1. Verwenden Sie den Schieberegler, um anzupassen, wie viele Geräte aus dem Test ausgeschlossen werden sollen. Beachten Sie, dass das Test Segment 1 und das Testsegment 2 jetzt nur 70% aller Geräte ausmachen.

   ![](assets/test-segment-holdout-selected.png)

1. Gehen Sie durch den Rest der Schritte im **[!UICONTROL Create Test Group]** Arbeitsablauf und wählen **[!UICONTROL Finalize Group]** Sie dann aus, wenn Sie mit Ihrer Auswahl zufrieden sind. Sie haben jetzt eine Testgruppe mit einem Teil der Zielgruppe, der vom Test abhält.
