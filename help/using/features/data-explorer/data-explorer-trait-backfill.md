---
description: Aufstockung von Eigenschaftenrealisierungen, um historische Zielgruppen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-description: Aufstockung von Eigenschaftenrealisierungen, um historische Zielgruppen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-title: Eigenschaften-Realisierungen für Aufstockungen
title: Eigenschaften-Realisierungen für Aufstockungen
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Eigenschaften-Realisierungen für Aufstockungen {#backfill-trait-realizations}

Aufstockung von Eigenschaftenrealisierungen, um historische Zielgruppen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.

[!UICONTROL Data Explorer Trait Backfill] ist eine Premium-Funktion, die das Audience Manager-Erlebnis verbessert, indem zusätzliche Anwendungsfälle freigeschaltet werden. Die Aufstockung erfordert zusätzliche Verarbeitungsleistung und steht allen Audience Manager-Kunden zu inkrementellen Kosten zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

Wenn Sie Eigenschaften aus nicht verwendeten Signalen erstellen, können Sie die Eigenschaften über einen bestimmten Zeitraum aufstocken. [!DNL Audience Manager] erfasst die historischen Daten zu Zielgruppen, die für die neue Eigenschaft infrage kommen, und speichert sie im entsprechenden Profil. Sie können den **[!UICONTROL Backfill Options]** Abschnitt [!UICONTROL Trait Expression] im **[Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md)** sehen.

>[!NOTE]
>
>Sie können Eigenschaftenrealisierungen für regelbasierte und Onboarded-Eigenschaften aufstocken.

So stocken Sie Eigenschaftenrealisierungen auf:

1. Gehen Sie zu [!UICONTROL Audience Data > Signals > Search] und führen Sie eine Signalsuche aus oder verwenden Sie das [Signal-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) , um die Signale zu identifizieren, die in der neuen Eigenschaft verwendet werden sollen.
1. Erstellen Sie eine neue Eigenschaft basierend auf den gewünschten Signalen.
1. Verwenden Sie die **[!UICONTROL Backfill Options]** im **[!UICONTROL Trait Expression]** Abschnitt, um das Zeitintervall auszuwählen, in dem Sie Eigenschaftenrealisierungen aufstocken möchten. Vordefinierte Aufstockungsintervalle umfassen 1, 7, 14 und 30 Tage. Sie können auch einen benutzerdefinierten Datumsbereich von bis zu 30 Tagen auswählen.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optional) Klicken Sie **[!UICONTROL Estimate Realizations]** in den **[!UICONTROL Estimated Trait Realizations]** Abschnitt, um die geschätzten [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] Werte für die hinterfüllte Eigenschaft der letzten 7 Tage anzuzeigen.

   ![Schätzung-Eigenschaften-Realisierungen](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Für Eigenschaften mit Ausdrücken, die die folgenden Operatoren verwenden, stehen keine Rückfüllung und Schätzung der Eigenschaften zur Verfügung:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Erstellen Sie die Eigenschaft.

Nachdem Sie die Eigenschaft erstellt haben, sehen Sie, wie die in der Realisierungsstatistik enthaltenen rückständigen Realisierungen aussehen.

## Latenz zum Aufstocken von Eigenschaften {#trait-backfilling-latency}

Neu erstellte Eigenschaften beginnen zwei bis drei Stunden nach der Erstellung mit der Erfassung von Zielgruppen. Aufgrund der großen Datenmenge, die täglich [!DNL Audience Manager] arbeitet, wird die aufgestockte Population jedoch nicht sofort in den Diagrammen [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] Diagrammen wiedergegeben.

Audience Manager aktualisiert die [!UICONTROL Trait Graph] mit der aufgestockten Population innerhalb von 48 Stunden nach Erstellung der Eigenschaften.

## Maximale Nachfüllung der Eigenschaften {#trait-backfilling-limit}

[!UICONTROL Data Explorer] ermöglicht es Ihnen, bis zu 50 Eigenschaften pro Monat aufzustocken, wobei der Zähler für die Aufstockung am 1. Tag jedes Monats zurückgesetzt wird.

>[!NOTE]
>
>Die Quote für die Rückfüllung der Eigenschaften wird nicht von den Vormonaten übernommen. Wenn Sie z. B. diesen Monat 30 Eigenschaften aufstocken, wird das Eigenschafts-Aufstockungskontingent für den nächsten Monat auf 50, nicht auf 70 zurückgesetzt.

## Auswirkungen auf die Berichterstattung {#reporting-impact}

Rückgefüllte Eigenschaften werden in der [!UICONTROL Unique Trait Realizations] und in den [!UICONTROL Total Trait Population] Metriken angezeigt, wenn historische Signale in Eigenschaften umgesetzt [!DNL Audience Manager] werden.

Die [!UICONTROL Trait Graph], [!UICONTROL General Reports]und [!UICONTROL Trend Reports] werden jedoch nicht rückwirkend aktualisiert, wenn historische Metriken vor dem Erstellungsdatum der Eigenschaft aufgestockt werden.