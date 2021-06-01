---
description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Anfrage zu einer Massenschätzung durchzuführen.
seo-description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Anfrage zu einer Massenschätzung durchzuführen.
seo-title: Massenschätzungen
solution: Audience Manager
title: Massenschätzungen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Massenschätzungen{#bulk-estimates}

Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Anfrage zu einer Massenschätzung durchzuführen.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen werden in der berücksichtigt  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools].

Um Massenaktualisierungen vorzunehmen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeile [!UICONTROL Estimate Segment Size] .
2. Klicken Sie auf die Registerkarte **[!UICONTROL Estimate]** .
3. Fügen Sie die Überschrift für die Schätzung in die erste Zeile des Arbeitsblatts für die Schätzung ein.
4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen , die dem zu aktualisierenden Element entspricht.
Durch diese Aktion wird das Dialogfeld [!UICONTROL Account Information] geöffnet.
6. Geben Sie die erforderlichen [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

Dadurch wird eine [!UICONTROL Response] -Spalte im Arbeitsblatt erstellt, die Daten zur geschätzten Segmentgröße enthält. Vor der Eingabe von Daten sollte Ihr Bulk-Schätzarbeitsblatt in etwa wie folgt aussehen:

![](assets/estimate.png)
Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter  [Fehlerbehebung für Tools zur Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).
