---
description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Führen Sie die folgenden Schritte aus, um eine Massenschätzung anzufordern.
seo-description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Führen Sie die folgenden Schritte aus, um eine Massenschätzung anzufordern.
seo-title: Massenschätzungen
solution: Audience Manager
title: Massenschätzungen
uuid: 63 b 2 f 06 a -8 ba 0-47 a 2-bd 0 b -8039 b 2 d 4 c 95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Führen Sie die folgenden Schritte aus, um eine Massenschätzung anzufordern.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. Fügen Sie die Schätzung in die erste Zeile des Schätzarbeitsblatts ein.
1. Fügen Sie die Daten, die Sie ändern möchten, in eine entsprechende Spalte ein, basierend auf der Kopfzeilenbeschriftung.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen, die mit dem Element übereinstimmt, das Sie aktualisieren.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. Bevor Sie Daten eingeben, sollte Ihr Arbeitsblatt zur Massenschätzung wie folgt aussehen:

![](assets/estimate.png)Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden [Sie weitere Informationen unter Fehlerbehebung für Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-troubleshooting.md).

