---
description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften sowie Segment- oder Eigenschaftenordnerelemente in einem Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.
keywords: baaam
seo-description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften sowie Segment- oder Eigenschaftenordnerelemente in einem Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.
seo-title: Massenaktualisierungen
solution: Audience Manager
title: Massenaktualisierungen
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Massenaktualisierungen{#bulk-updates}

Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften sowie Segment- oder Eigenschaftenordnerelemente in einem Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden *nicht* von unterstützt [!DNL Audience Manager]. Dieses Tool wird nur aus praktischen Gründen und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../../api/rest-api-main/aam-api-getting-started.md) arbeiten. [In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

Um Massenaktualisierungen vorzunehmen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie die Aktualisierungskopfzeilen für das Element, das Sie bearbeiten möchten.
1. Click the **[!UICONTROL Update]** tab.
1. Fügen Sie die Aktualisierungskopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein. Beachten Sie Folgendes:

   * Beim Aktualisieren eines Ordners sind alle Header erforderlich.
   * Beim Aktualisieren von Segmenten oder Eigenschaften benötigen Sie nur die Segment-ID (SID) und das Header-Element, das geändert werden muss. Nicht verwendete Kopfzeilen löschen.

1. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf eine Aktualisierungsschaltfläche, die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet das [!UICONTROL Account Information] Dialogfeld.

1. Geben Sie die erforderlichen [Anmeldedaten](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results] Spalte. Die [!UICONTROL Results] Spalte gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie in den [REST-APIs](../../api/rest-api-main/rest-api-main.md) . Bevor Sie Daten eingeben, sollte Ihr Bulk Update-Arbeitsblatt wie folgt aussehen:

![](assets/update.png)

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
