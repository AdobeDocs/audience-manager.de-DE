---
description: Aufstockung von Eigenschaftseigenschaften, um historische Zielgruppen zu erfassen und Verlust relevanter Daten vor dem Erstellungsdatum von Eigenschaften zu vermeiden.
seo-description: Aufstockung von Eigenschaftseigenschaften, um historische Zielgruppen zu erfassen und Verlust relevanter Daten vor dem Erstellungsdatum von Eigenschaften zu vermeiden.
seo-title: Aufstockung Trait Realizations
title: Aufstockung Trait Realizations
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

Aufstockung von Eigenschaftseigenschaften, um historische Zielgruppen zu erfassen und Verlust relevanter Daten vor dem Erstellungsdatum von Eigenschaften zu vermeiden.

[!UICONTROL Data Explorer Trait Backfill] ist eine Premium-Funktion, die das Erlebnis für Audience Manager verbessert, indem zusätzliche Anwendungsfälle entsperrt werden. Die Aufstockung erfordert zusätzliche Verarbeitungsleistung und steht allen Audience Manager-Kunden zu inkrementellen Kosten zur Verfügung. Weitere Einzelheiten erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

Wenn Sie Eigenschaften aus nicht verwendeten Signalen erstellen, können Sie die Eigenschaftsrealizationen über einen bestimmten Zeitraum aufstocken. [!DNL Audience Manager] erfasst die Verlaufsdaten zu Zielgruppen, die für die neue Eigenschaft qualifiziert sind, und speichert sie im entsprechenden Profil. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Sie können Eigenschaften von Eigenschaften für regelbasierte und onboardierte Eigenschaften aufstocken.

Hier erfahren Sie, wie Sie Eigenschaften von Eigenschaften aufstocken:

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. Erstellen Sie eine neue Eigenschaft basierend auf den gewünschten Signalen.
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. Vordefinierte Aufstockungsintervalle umfassen 1, 7, 14 und 30 Tage. Sie können auch einen benutzerdefinierten Datumsbereich von bis zu 30 Tagen auswählen.
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >Trait-Aufstockung und Schätzung sind nicht für Eigenschaften mit Ausdrücken verfügbar, die die folgenden Operatoren verwenden:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Erstellen Sie die Eigenschaft.

Nachdem Sie die Erstellung abgeschlossen haben, werden die rückdatierten Realizationen in den Neuberechnungsstatistiken angezeigt.

## Trait Backfilling Latency {#trait-backfilling-latency}

Neu erstellte Eigenschaften erfassen Zielgruppen zwei bis drei Stunden nach der Erstellung. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] Damit können Sie bis zu 50 Eigenschaften pro Monat aufstocken, wobei der Aufstockungszähler am 1. Tag jedes Monats zurückgesetzt wird.

>[!NOTE]
>
>Trait backfill quota does not carry from previous months. Wenn Sie z. B. 30 Eigenschaften in diesem Monat aufstocken, wird das Kontingent für die Aufstockung des nächsten Monats auf 50, nicht auf 70 zurückgesetzt.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.