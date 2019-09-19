---
description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Sammelanfrage durchzuführen.
seo-description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Sammelanfrage durchzuführen.
seo-title: Massenschätzungen
solution: Audience Manager
title: Massenschätzungen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Massenschätzungen{#bulk-estimates}

Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Sammelanfrage durchzuführen.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden *nicht* von unterstützt [!DNL Audience Manager]. Dieses Tool wird nur aus praktischen Gründen und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../../api/rest-api-main/aam-api-getting-started.md) arbeiten. [In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

Um Massenaktualisierungen vorzunehmen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie die [!UICONTROL Estimate Segment Size] Kopfzeile.
1. Click the **[!UICONTROL Estimate]** tab.
1. Fügen Sie die Überschrift für die Schätzung in die erste Zeile des Arbeitsblatts für die Schätzung ein.
1. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen, die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet das [!UICONTROL Account Information] Dialogfeld.

1. Geben Sie die erforderlichen [Anmeldedaten](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

Dadurch wird eine [!UICONTROL Response] Spalte im Arbeitsblatt erstellt, die Daten zur geschätzten Segmentgröße enthält. Bevor Sie Daten eingeben, sollte Ihr Arbeitsblatt für die Massenschätzung in etwa wie folgt aussehen:

![](assets/estimate.png)Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).

