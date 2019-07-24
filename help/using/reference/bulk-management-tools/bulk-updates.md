---
description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften und Segmente oder Eigenschaftenordner in einem einzelnen Vorgang bearbeiten. Führen Sie die folgenden Schritte aus, um Massenaktualisierungen vorzunehmen.
keywords: baaam
seo-description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften und Segmente oder Eigenschaftenordner in einem einzelnen Vorgang bearbeiten. Führen Sie die folgenden Schritte aus, um Massenaktualisierungen vorzunehmen.
seo-title: Massenaktualisierungen
solution: Audience Manager
title: Massenaktualisierungen
uuid: 22 f 1 badd-a 274-4 d 3 e -9957-a 24 bf 8 c 1 d 0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften und Segmente oder Eigenschaftenordner in einem einzelnen Vorgang bearbeiten. Führen Sie die folgenden Schritte aus, um Massenaktualisierungen vorzunehmen.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Fügen Sie die Updatepakete in die erste Zeile des Aktualisierungsarbeitsblatts ein. Beachten Sie Folgendes:

   * Beim Aktualisieren eines Ordners sind alle Header erforderlich.
   * Beim Aktualisieren von Segmenten oder Eigenschaften benötigen Sie lediglich die Segment-ID (SID) und das Header-Element, das geändert werden muss. Löschen Sie nicht verwendete Header.

1. Fügen Sie die Daten, die Sie ändern möchten, in eine entsprechende Spalte ein, basierend auf der Kopfzeilenbeschriftung.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf eine Aktualisierungsschaltfläche, die dem Element entspricht, das Sie aktualisieren.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Vor der Eingabe der Daten sollte Ihr Massen-Updatesheet wie folgt aussehen:

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
