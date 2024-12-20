---
description: In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für die Vorlage für die Zuordnung von Audience Lab-Duplikaten und den Segment-Holdout bieten.
seo-description: This article describes two features which provide advanced functionality for Audience Lab  Duplicate Allocation Template and Segment Holdout.
seo-title: Audience Lab Advanced Functionality
solution: Audience Manager
title: Erweiterte Funktionen von Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# Erweiterte Funktionen [!DNL Audience Lab] {#audience-lab-advanced-functionality}

In diesem Artikel werden zwei Funktionen beschrieben, die erweiterte Funktionen für [!DNL Audience Lab] bereitstellen: [!DNL Duplicate Allocation Template] und [!DNL Segment Holdout].

## Zuordnungsvorlage duplizieren {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

[!DNL Audience Lab] stellt die [!DNL Allocation Template] die verschiedenen Auswahlen dar, die Sie beim Erstellen einer Testgruppe treffen:

* die Verteilung der Produkte auf die Testsegmente;
* die Zuordnung von Testsegmenten zu Zielen;
* Die Konversionseigenschaften, die Sie für eine Testgruppe verwenden.
* Der Datumsbereich, in dem die Testgruppe in Ihren ausgewählten Zielen veröffentlicht.

Durch das Duplizieren einer Zuordnungsvorlage können Sie dieselbe Verteilung von Testsegmenten und Zielen für ein anderes Basissegment in einer neuen Testgruppe wiederverwenden. Ein Beispiel für eine Zuordnungsvorlage wird unten dargestellt. Das Bild wird aus dem [!UICONTROL Summary & Finalize] Schritt im Workflow **Testgruppe erstellen** übernommen.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Verwenden doppelter Zuordnungsvorlagen

Erstellen Sie eine erste Testgruppe und wählen Sie dann **[!UICONTROL Duplicate Allocation Template]** aus, um dieselben Einstellungen in mehreren Testgruppen wiederzuverwenden. Sie können diese Funktion beispielsweise verwenden, wenn Sie einen Test ausführen, bei dem Sie die Wirksamkeit mehrerer Ziele für mehrere Segmente ermitteln möchten.

1. Suchen Sie in der Hauptansicht von Audience Lab nach der Testgruppe, deren Zuordnungsvorlage Sie in einer neuen Testgruppe reproduzieren möchten. Wählen Sie in der Dropdown-Liste **[!UICONTROL Duplicate Allocation Template]** aus.

   ![](assets/duplicate-allocation-template.png)

2. Im [!UICONTROL Create Test Group]-Assistenten können Sie ein Basissegment angeben und Ihre Testsegmente bei Bedarf umbenennen.
3. Sie *Folgendes*:

   * die Verteilung der Produkte auf die Testsegmente;
   * die Konversionseigenschaft(en);
   * Die Zuordnung von Testsegmenten zu Zielen. Sie können nur den Zuordnungsschlüssel für die Ziele ausfüllen, für die ein Schlüssel erforderlich ist.
   * Der Datumsbereich, in dem Ihre Testgruppe an Ihren ausgewählten Zielen veröffentlichen wird.

4. Überprüfen Sie die in den vorherigen Schritten hinzugefügten Informationen und wählen Sie **[!UICONTROL Finalize Group]** aus.

## Testsegment-Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] ist eine erweiterte Funktion, die auf Kundenwunsch aktiviert wird. Bitte kontaktieren Sie [!DNL Customer Care] oder [!DNL Adobe Consulting], um diese Funktion zu aktivieren.

Verwenden Sie diese Funktion, um zu verhindern, dass ein Teil der Zielgruppe in den Test einbezogen wird. Der ausgewählte Prozentsatz wird beim Test nicht berücksichtigt. Auf diese Weise können Sie die Anzahl der Konversionen aus ausgewählten (für Ziele aktiviert) und nicht ausgewählten (Holdout-Gruppe) Zielgruppen messen und vergleichen.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Verwenden des Testsegment-Holdouts

1. Erstellen Sie mithilfe des [!UICONTROL Create Test Group]-Assistenten eine neue Testgruppe.
1. Im **[!UICONTROL Allocate Test Segment]** Schritt können Sie einen Teil der Audience auswählen, der nicht getestet werden soll.

   ![Listenelement](assets/test-segment-holdout.png)

1. Stellen Sie mit dem Schieberegler ein, wie viele Geräte Sie vor Tests zurückhalten möchten. Beachten Sie, dass Testsegment 1 und Testsegment 2 jetzt nur noch 70 % der gesamten Geräte ausmachen.

   ![](assets/test-segment-holdout-selected.png)

1. Führen Sie die restlichen Schritte im **[!UICONTROL Create Test Group]**-Workflow aus und wählen Sie **[!UICONTROL Finalize Group]** aus, wenn Sie mit Ihrer Auswahl zufrieden sind. Jetzt verfügen Sie über eine Testgruppe, bei der ein Teil der Zielgruppe vom Testen ausgeschlossen ist.
