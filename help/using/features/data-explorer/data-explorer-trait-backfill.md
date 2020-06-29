---
description: Aufstockung von Eigenschaftenrealisierungen, um historische Audiencen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-description: Aufstockung von Eigenschaftenrealisierungen, um historische Audiencen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-title: Eigenschaften-Realisierungen für Aufstockungen
title: Eigenschaften-Realisierungen für Aufstockungen
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---


# Eigenschaften-Realisierungen für Aufstockungen {#backfill-trait-realizations}

Aufstockung von Eigenschaftenrealisierungen, um historische Audiencen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] ist eine Premium-Funktion, die den Audience Manager durch die Erschließung zusätzlicher Nutzungsszenarien verbessert. Die Aufstockung erfordert zusätzliche Verarbeitungsleistung und steht allen Audience Manager zu inkrementellen Kosten zur Verfügung. Weitere Informationen erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

Wenn Sie Eigenschaften aus nicht verwendeten Signalen erstellen, können Sie die Eigenschaften über einen bestimmten Zeitraum aufstocken. [!DNL Audience Manager] erfasst die Verlaufsdaten zu Audiencen, die für die neue Eigenschaft infrage kommen, und speichert sie im entsprechenden Profil. Sie können den **[!UICONTROL Backfill Options]** Abschnitt [!UICONTROL Trait Expression] im **[Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md)**sehen.

>[!NOTE]
>
>Sie können Eigenschaftenrealisierungen für regelbasierte und Onboarded-Eigenschaften aufstocken.

So stocken Sie Eigenschaftenrealisierungen auf:

1. Gehen Sie zu [!UICONTROL Audience Data > Signals > Search] und führen Sie eine Signalsuche aus oder verwenden Sie das [Signal-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) , um die in der neuen Eigenschaft zu verwendenden Signale zu identifizieren.
1. Erstellen Sie eine neue Eigenschaft basierend auf den gewünschten Signalen.
1. Verwenden Sie die **[!UICONTROL Backfill Options]** im **[!UICONTROL Trait Expression]** Abschnitt, um das Zeitintervall auszuwählen, in dem Sie Eigenschaftenrealisierungen aufstocken möchten. Vordefinierte Aufstockungsintervalle umfassen 1, 7, 14 und 30 Tage. Sie können auch einen benutzerdefinierten Datumsbereich von bis zu 30 Tagen auswählen.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optional) Klicken Sie **[!UICONTROL Estimate Realizations]** in den **[!UICONTROL Estimated Trait Realizations]** Abschnitt, um die geschätzten [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] Werte für die hinterfüllte Eigenschaft der letzten 7 Tage anzuzeigen.

   ![Schätzung-Eigenschaften-Realisierungen](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Für Eigenschaften mit Ausdrücken, die die folgenden Operatoren verwenden, stehen keine Trait-Aufstockung und -Schätzung zur Verfügung:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Erstellen Sie die Eigenschaft.

Nachdem Sie die Eigenschaft erstellt haben, sehen Sie, wie die in der Realisierungsstatistik enthaltenen rückständigen Realisierungen aussehen.

Sehen Sie sich das unten stehende Video an, um sich einen Video mit einer Anleitung zum Aufstocken von Eigenschaften anzusehen.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latenz zum Aufstocken von Eigenschaften {#trait-backfilling-latency}

Neu erstellter Beginn Eigenschaften, der Audiencen zwei bis drei Stunden nach der Erstellung erfasst. Aufgrund der großen Datenmenge, die täglich [!DNL Audience Manager] arbeitet, wird die aufgestockte Population jedoch nicht sofort in den Diagrammen [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] Diagrammen wiedergegeben.

Audience Manager aktualisiert die [!UICONTROL Trait Graph] Variable innerhalb von 48 Stunden nach Erstellung der Eigenschaften mit der aufgestockten Population.

## Maximale Nachfüllung der Eigenschaften {#trait-backfilling-limit}

[!UICONTROL Data Explorer] ermöglicht es Ihnen, bis zu 50 Eigenschaften pro Monat aufzustocken, wobei der Zähler für die Aufstockung am 1. Tag jedes Monats zurückgesetzt wird.

>[!NOTE]
>
>Die Quote für die Rückfüllung der Eigenschaften wird nicht von den Vormonaten übernommen. Wenn Sie z. B. diesen Monat 30 Eigenschaften aufstocken, wird das Eigenschafts-Aufstockungskontingent für den nächsten Monat auf 50, nicht auf 70 zurückgesetzt.

## Auswirkungen auf den Berichte {#reporting-impact}

Rückgefüllte Eigenschaften werden in der [!UICONTROL Unique Trait Realizations] und in den [!UICONTROL Total Trait Population] Metriken angezeigt, wenn historische Signale in Eigenschaften umgesetzt [!DNL Audience Manager] werden.

Die [!UICONTROL Trait Graph], [!UICONTROL General Reports]und [!UICONTROL Trend Reports] werden jedoch nicht rückwirkend aktualisiert, wenn historische Metriken vor dem Erstellungsdatum der Eigenschaft aufgestockt werden.