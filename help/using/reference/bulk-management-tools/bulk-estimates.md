---
description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Anfrage zu einer Massenschätzung durchzuführen.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Massenschätzungen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Massenschätzungen{#bulk-estimates}

Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Befolgen Sie diese Anweisungen, um eine Anfrage zu einer Massenschätzung durchzuführen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche von [!DNL Audience Manager] zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

Um Massenaktualisierungen vorzunehmen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeile [!UICONTROL Estimate Segment Size].
2. Klicken Sie auf die Registerkarte **[!UICONTROL Estimate]** .
3. Fügen Sie die Überschrift für die Schätzung in die erste Zeile des Arbeitsblatts für die Schätzung ein.
4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen , die dem zu aktualisierenden Element entspricht.
Durch diese Aktion wird das Dialogfeld [!UICONTROL Account Information] geöffnet.
6. Geben Sie die erforderlichen [Anmeldedaten ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) an und klicken Sie auf **[!UICONTROL Submit]**.

Dadurch wird eine [!UICONTROL Response] -Spalte im Arbeitsblatt erstellt, die Daten zur geschätzten Segmentgröße enthält. Vor der Eingabe von Daten sollte Ihr Bulk-Schätzarbeitsblatt in etwa wie folgt aussehen:

![](assets/estimate.png)
Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).
