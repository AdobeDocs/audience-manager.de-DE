---
description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Sammelanfrage durchzuführen.
seo-description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Sammelanfrage durchzuführen.
seo-title: Massenschätzungen
solution: Audience Manager
title: Massenschätzungen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Massenschätzungen{#bulk-estimates}

Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Sammelanfrage durchzuführen.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene  [!DNL Audience Manager] RBAC-Gruppenberechtigungen werden berücksichtigt  [!UICONTROL Bulk Management Tools].

Um Massenaktualisierungen vorzunehmen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeile [!UICONTROL Estimate Segment Size].
2. Klicken Sie auf die Registerkarte **[!UICONTROL Estimate]**.
3. Fügen Sie die Überschrift für die Schätzung in die erste Zeile des Arbeitsblatts für die Schätzung ein.
4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen, die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet das Dialogfeld [!UICONTROL Account Information].
6. Geben Sie die erforderlichen [Anmeldeangaben](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

Dadurch wird eine Spalte [!UICONTROL Response] im Arbeitsblatt erstellt, die Daten zur geschätzten Segmentgröße enthält. Bevor Sie Daten eingeben, sollte Ihr Arbeitsblatt für die Massenschätzung wie folgt aussehen:

![](assets/estimate.png)
Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter  [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
