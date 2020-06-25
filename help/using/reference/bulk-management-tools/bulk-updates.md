---
description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Eigenschaftenordnerelemente in einem einzigen Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.
keywords: baaam
seo-description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Eigenschaftenordnerelemente in einem einzigen Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.
seo-title: Massenaktualisierungen
solution: Audience Manager
title: Massenaktualisierungen
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# Massenaktualisierungen{#bulk-updates}

Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Eigenschaftenordnerelemente in einem einzigen Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

Um Massenaktualisierungen vorzunehmen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie die Aktualisierungskopfzeilen für das Element, das Sie bearbeiten möchten.
2. Click the **[!UICONTROL Update]** tab.
3. Fügen Sie die Aktualisierungskopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein. Beachten Sie Folgendes:

   * Beim Aktualisieren eines Ordners sind alle Header erforderlich.
   * Beim Aktualisieren von Segmenten oder Eigenschaften benötigen Sie nur die Segment-ID (SID) und das Header-Element, das geändert werden muss. Nicht verwendete Kopfzeilen löschen.

4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf eine Aktualisierungsschaltfläche, die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet das [!UICONTROL Account Information] Dialogfeld.

6. Geben Sie die erforderlichen [Anmeldedaten](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results] Spalte. Die [!UICONTROL Results] Spalte gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie in den [REST-APIs](../../api/rest-api-main/rest-api-main.md) . Bevor Sie Daten eingeben, sollte Ihr Bulk Update-Arbeitsblatt wie folgt aussehen:

![](assets/update.png)

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
