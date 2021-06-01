---
description: Aufstockung von Eigenschaftsrealisierungen, um historische Zielgruppen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-description: Aufstockung von Eigenschaftsrealisierungen, um historische Zielgruppen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-title: Aufstocken von Eigenschaftsrealisierungen
title: Aufstocken von Eigenschaftsrealisierungen
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: 'Data Explorer '
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# Aufstocken von Eigenschaftsrealisierungen {#backfill-trait-realizations}

Aufstockung von Eigenschaftsrealisierungen, um historische Zielgruppen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] ist eine Premium-Funktion, die das Benutzererlebnis verbessert, indem zusätzliche Anwendungsfälle freigeschaltet werden. Die Aufstockung erfordert zusätzliche Verarbeitungsleistung und steht allen Audience Manager zu inkrementellen Kosten zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

Wenn Sie Eigenschaften aus nicht verwendeten Signalen erstellen, können Sie festlegen, die Eigenschaftsrealisierungen über einen bestimmten Zeitraum aufzustocken. [!DNL Audience Manager] erfasst die historischen Daten zu Zielgruppen, die für die neue Eigenschaft qualifiziert sind, und speichert sie im entsprechenden Profil. Sie können **[!UICONTROL Backfill Options]** im Abschnitt [!UICONTROL Trait Expression] des **[Trait Builder](../../features/traits/about-trait-builder.md)** sehen.

>[!NOTE]
>
>Sie können Eigenschaftsrealisierungen für regelbasierte und integrierte Eigenschaften aufstocken.

So stocken Sie Eigenschaftsrealisierungen auf:

1. Wechseln Sie zu [!UICONTROL Audience Data > Signals > Search] und führen Sie eine Signalsuche aus oder verwenden Sie das [Signale-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md), um die in der neuen Eigenschaft zu verwendenden Signale zu identifizieren.
1. Erstellen Sie eine neue Eigenschaft basierend auf den gewünschten Signalen.
1. Verwenden Sie **[!UICONTROL Backfill Options]** im Abschnitt **[!UICONTROL Trait Expression]** , um das Zeitintervall auszuwählen, für das Sie Eigenschaftsrealisierungen aufstocken möchten. Vordefinierte Aufstockungsintervalle umfassen 1, 7, 14 und 30 Tage. Sie können auch einen benutzerdefinierten Datumsbereich von bis zu 30 Tagen auswählen.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optional) Klicken Sie im Abschnitt **[!UICONTROL Estimated Trait Realizations]** auf **[!UICONTROL Estimate Realizations]** , um die geschätzten [!UICONTROL Unique Trait Realizations]- und [!UICONTROL Total Trait Population]-Werte für die aufgestockten Eigenschaften der letzten 7 Tage anzuzeigen.

   ![estimated-trait-realizations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Die Aufstockung und Schätzung von Eigenschaften ist nicht für Eigenschaften mit Ausdrücken verfügbar, die die folgenden Operatoren verwenden:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Erstellen Sie die Eigenschaft.

Sobald Sie die Erstellung der Eigenschaft abgeschlossen haben, werden die rückständigen Realisierungen in den Realisierungsstatistiken angezeigt.

Sehen Sie sich das Video unten an, um eine Videoeinführung dazu zu erhalten, wie Sie Eigenschaften aufstocken können.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Aufstockung der Eigenschaften {#trait-backfilling-latency}

Neu erstellte Eigenschaften beginnen zwei bis drei Stunden nach der Erstellung mit der Erfassung von Zielgruppen. Aufgrund des großen Datenvolumens, das [!DNL Audience Manager] täglich ausführt, wird die aufgestockte Population jedoch nicht sofort in den Diagrammen [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] angezeigt.

Audience Manager aktualisiert das [!UICONTROL Trait Graph]-Objekt mit der aufgestockten Population innerhalb von 48 Stunden nach der Erstellung von Eigenschaften.

## Eigenschaftsaufstockungsgrenze {#trait-backfilling-limit}

[!UICONTROL Data Explorer] ermöglicht es Ihnen, bis zu 50 Eigenschaften pro Monat aufzustocken, wobei der Aufstockungszähler am 1. Tag jedes Monats zurückgesetzt wird.

>[!NOTE]
>
>Das Aufstockungskontingent für Eigenschaften wird nicht von früheren Monaten übernommen. Wenn Sie z. B. diesen Monat 30 Eigenschaften aufstocken, wird das Aufstockungskontingent für Eigenschaften für den nächsten Monat auf 50, nicht auf 70 zurückgesetzt.

## Auswirkungen auf die Berichterstellung {#reporting-impact}

Aufstockte Realisierungen von Eigenschaften werden in den Metriken [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] angezeigt, da [!DNL Audience Manager] historische Signale in Realisierungen von Eigenschaften umwandelt.

Die [!UICONTROL Trait Graph], [!UICONTROL General Reports] und [!UICONTROL Trend Reports] werden jedoch nicht nachträglich mit historischen Metriken aktualisiert, die vor dem Erstellungsdatum der Eigenschaft aufgestockt wurden.
