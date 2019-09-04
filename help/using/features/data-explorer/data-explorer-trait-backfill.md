---
description: Aufstockung von Eigenschaftseigenschaften, um historische Zielgruppen zu erfassen und Verlust relevanter Daten vor dem Erstellungsdatum von Eigenschaften zu vermeiden.
seo-description: Aufstockung von Eigenschaftseigenschaften, um historische Zielgruppen zu erfassen und Verlust relevanter Daten vor dem Erstellungsdatum von Eigenschaften zu vermeiden.
seo-title: Aufstockung Trait Realizations
title: Aufstockung Trait Realizations
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Aufstockung Trait Realizations {#backfill-trait-realizations}

Aufstockung von Eigenschaftseigenschaften, um historische Zielgruppen zu erfassen und Verlust relevanter Daten vor dem Erstellungsdatum von Eigenschaften zu vermeiden.

[!UICONTROL Data Explorer Trait Backfill] ist eine Premium-Funktion, die das Erlebnis für Audience Manager verbessert, indem zusätzliche Anwendungsfälle entsperrt werden. Die Aufstockung erfordert zusätzliche Verarbeitungsleistung und steht allen Audience Manager-Kunden zu inkrementellen Kosten zur Verfügung. Weitere Einzelheiten erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

Wenn Sie Eigenschaften aus nicht verwendeten Signalen erstellen, können Sie die Eigenschaftsrealizationen über einen bestimmten Zeitraum aufstocken. [!DNL Audience Manager] erfasst die Verlaufsdaten zu Zielgruppen, die für die neue Eigenschaft qualifiziert sind, und speichert sie im entsprechenden Profil. Sie können den Abschnitt **[!UICONTROL Backfill Options]** im [!UICONTROL Trait Expression] Abschnitt **[Eigenschaften erstellen](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Sie können Eigenschaften von Eigenschaften für regelbasierte und onboardierte Eigenschaften aufstocken.

Hier erfahren Sie, wie Sie Eigenschaften von Eigenschaften aufstocken:

1. Navigieren Sie [!UICONTROL Audience Data > Signals > Search] zum amd-Ausführen einer Signatursuche oder verwenden Sie das [Signal-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) , um die Signale zu identifizieren, die in der neuen Eigenschaft verwendet werden sollen.
1. Erstellen Sie eine neue Eigenschaft basierend auf den gewünschten Signalen.
1. Verwenden Sie den **[!UICONTROL Backfill Options]****[!UICONTROL Trait Expression]** Abschnitt, um das Zeitintervall auszuwählen, in dem Sie Eigenschaften für Eigenschaften aufstocken möchten. Vordefinierte Aufstockungsintervalle umfassen 1, 7, 14 und 30 Tage. Sie können auch einen benutzerdefinierten Datumsbereich von bis zu 30 Tagen auswählen.

   ![trait-aufstockung](assets/signals-trait-backfill.png)

1. (Optional) Klicken **[!UICONTROL Estimate Realizations]** Sie in den **[!UICONTROL Estimated Trait Realizations]** Abschnitt, um die Schätzung [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] die Werte für die Aufstockung in den letzten 7 Tagen anzuzeigen.

   ![estimate-trait-realizations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Trait-Aufstockung und Schätzung sind nicht für Eigenschaften mit Ausdrücken verfügbar, die die folgenden Operatoren verwenden:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Erstellen Sie die Eigenschaft.

Nachdem Sie die Erstellung abgeschlossen haben, werden die rückdatierten Realizationen in den Neuberechnungsstatistiken angezeigt.

## Trait Backfill Latency {#trait-backfilling-latency}

Neu erstellte Eigenschaften erfassen Zielgruppen zwei bis drei Stunden nach der Erstellung. Aufgrund des umfangreichen Datenvolumens, der [!DNL Audience Manager] täglich ausgeführt wird, wird die Aufstockung jedoch nicht sofort im Diagramm [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] dargestellt.

Audience Manager aktualisiert die wiederherzugefüllte [!UICONTROL Trait Graph] Population innerhalb von 48 Stunden nach der Erstellung von Eigenschaften.

## Trait-Aufstockung {#trait-backfilling-limit}

[!UICONTROL Data Explorer] Damit können Sie bis zu 50 Eigenschaften pro Monat aufstocken, wobei der Aufstockungszähler am 1. Tag jedes Monats zurückgesetzt wird.

>[!NOTE]
>
>Trait backfill quota does not carry from previous months. Wenn Sie z. B. 30 Eigenschaften in diesem Monat aufstocken, wird das Kontingent für die Aufstockung des nächsten Monats auf 50, nicht auf 70 zurückgesetzt.

## Auswirkungen auf die Berichterstellung {#reporting-impact}

Zurückgestellte Eigenschaftenrealizationen werden in den [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] Metriken dargestellt, da [!DNL Audience Manager] historische Signale in Eigenschaftsrealizationen umgewandelt werden.

Die Variable [!UICONTROL Trait Graph], [!UICONTROL General Reports]und [!UICONTROL Trend Reports] wird nicht rückwirkend mit historischen Metriken aktualisiert, die vor dem Erstellungsdatum der Eigenschaft zurückgesetzt wurden.