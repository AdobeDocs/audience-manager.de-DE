---
description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Führen Sie die folgenden Schritte aus, um eine Massenerstellungsanforderung durchzuführen.
seo-description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Führen Sie die folgenden Schritte aus, um eine Massenerstellungsanforderung durchzuführen.
seo-title: Massenerstellung
solution: Audience Manager
title: Massenerstellung
uuid: 1 e 09 bcfa -783 e -4 e 9 b -9 ead -147 f 8 d 1381 c 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Führen Sie die folgenden Schritte aus, um eine Massenerstellungsanforderung durchzuführen.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

>[!CAUTION]
>
>Kombinieren Sie Objekttypen nicht in einer Massenerstellungsanforderung. Die Header für jedes Objekt sind eindeutig und können nicht kombiniert werden. Löschen Sie das Arbeitsblatt und machen Sie eine separate Anforderung für verschiedene Elemente.

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. Fügen Sie die Kopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
1. Fügen Sie die Daten, die Sie ändern möchten, in eine entsprechende Spalte ein, basierend auf der Kopfzeilenbeschriftung.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen, die mit dem Element übereinstimmt, das Sie aktualisieren.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Bevor Sie Daten eingeben, sollte Ihr Arbeitsblatt zur Massenerstellung dem folgenden Beispiel ähnlich aussehen. Beachten Sie, dass hier nicht alle verschiedenen Erstellungsoptionen angezeigt werden. Dies ist enthalten, damit Sie erkennen können, wie ein ausgefülltes Arbeitsblatt aussehen könnte.

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
