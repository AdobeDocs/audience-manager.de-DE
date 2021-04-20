---
description: Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird im Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Eigenschaftsqualifikation.
keywords: Eigenschaftsqualifikation, Realisierung von Eigenschaften, Eindeutige Eigenschaften, UTR, Gesamtanzahl der Eigenschaften, TTP
seo-description: Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird im Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Eigenschaftsqualifikation.
seo-title: Eigenschaftsqualifikationsreferenz
solution: Audience Manager
title: Eigenschaftsqualifikationsreferenz
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,223f5fc6-c939-4bc6-94a3-5d953abc601a
translation-type: tm+mt
source-git-commit: e13f81df9b0d59cd958f4c2a615c31df00ce2cc5
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# Referenz: Eigenschafts- und Segmentqualifikationen {#trait-qualification-reference}

Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird im Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Weitere Informationen zur Qualifizierung des Eigenschaftstyps finden Sie unter [Eigenschaftsqualifikation nach Eigenschaftstyp](#trait-type).

Weitere Informationen zur Segmentqualifizierung finden Sie unter [Segmentpopulation in Echtzeit und Segmentpopulation insgesamt](#real-time-segment).



## Eigenschaftsqualifikation nach Eigenschaftstyp {#trait-type}

| Eigenschaftstyp | Qualifikationskriterien |
|---|---|
| Regelbasierte Eigenschaften | Die Qualifizierung von Eigenschaften erfolgt in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren. Ihre Beginn qualifizieren sich ca. 4 Stunden nach dem Erstellen der Eigenschaft [in der Benutzeroberfläche für eine regelbasierte Eigenschaft. ](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Regelbasierte Eigenschaften ermöglichen Ihnen die Verwendung der Steuerelemente [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) für die Anzeigenfrequenzzuordnung und andere Anwendungsfälle. |
| Integrierte Eigenschaften | Die Qualifizierung der Eigenschaften erfolgt, nachdem eine eingehende Datei verarbeitet wurde, d. h. die eingehende Datei wird [in Audience Manager](../../faq/faq-inbound-data-ingestion.md) importiert, und zwar dann, wenn die Eigenschaftsqualifikation erfolgt. Sie sollten etwa 4 Stunden nach dem Erstellen einer nicht integrierten Eigenschaft warten, bevor Sie eine eingehende Datei zur Verarbeitung hochladen. Bei nicht an Bord befindlichen Eigenschaften beträgt die maximale Anzahl von Qualifikationen für ein Profil 1. |
| Algorithmische Eigenschaften | Bei algorithmischen Eigenschaften ist die maximale Anzahl von Qualifikationen für ein Profil 1. |
| Ordnereigenschaften | Eine Ordnereigenschaft fasst die Eigenschaftsqualifikationen der darin enthaltenen Eigenschaften zusammen. Lesen Sie [Ordnereigenschaften: Info](about-folder-traits.md) für weitere Informationen. |
| Eigenschaften aktiver Zielgruppen und mit Datenquellen synchronisierte Eigenschaften | Eine [!UICONTROL Active Audience]-Eigenschaft enthält alle in Ihrem Audience Manager-Konto verwalteten Geräte. [!UICONTROL Data Source Synced Traits] alle mit einer Datenquelle verknüpften Benutzer verfolgen. Lesen Sie mehr über [Eigenschaften für aktive Audiencen und Datenquellen-synchronisierte Eigenschaften](client-activity-synced-audience-traits.md). |

## Eindeutige Eigenschaften und Gesamtanzahl der Eigenschaften {#unique-trait-realizations}

![unique-property-realization](assets/trait-graph.png)

Je nach dem Ergebnistyp, den das Diagramm anzeigen soll (gefiltert nach [!UICONTROL Device ID] oder [!UICONTROL Cross-Device ID]), haben die Metriken eine unterschiedliche Bedeutung:

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der anonymen Besucher, die die Eigenschaft innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Besucher, die diese Eigenschaft auf ihrem Profil haben.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der authentifizierten Besucher, die das Merkmal innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der authentifizierten Besucher, die diese Eigenschaft auf ihrem Profil haben.

Stellen Sie sich die Zahlen so vor. In der Abbildung oben zeigt die Ansicht [Eigenschaftendetails](../../features/traits/trait-details-page.md) 90.173 die Anzahl der aktiven Geräte, die Ihre Eigenschaften gestern besucht haben. Der Wert [!UICONTROL Total Trait Population] von 55.757 stellt die Anzahl der Benutzer dar, die derzeit für diese Eigenschaft qualifiziert sind. Die [!UICONTROL Total Trait Population]-Zahl zeigt die Gesamtanzahl der Benutzer an, die für die Segmentierung/das Targeting verwendet werden könnten. Normalerweise bleiben Benutzer 120 Tage lang Teil einer Eigenschaft.

Da wir zwei verschiedene Rechenaufträge ausführen, um die beiden Populationen zu berechnen, liegt das [!UICONTROL Total Trait Population] immer um 24 Stunden hinter dem [!UICONTROL Unique Trait Realizations] zurück. Im Diagramm oben sehen Sie ungefähr 90.400 [!UICONTROL Unique Trait Realizations] und einen [!UICONTROL Total Trait Population] von etwa 90.300 für den 5. Februar. Die 90.400 Profil werden am folgenden Tag dem [!UICONTROL Total Trait Population] hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, würden Sie, wenn Sie eine Spitze von 10.000 Besuchern im Moment erleben würden, diese im [!UICONTROL Unique Trait Realizations] von morgen erscheinen, aber erst 24 Stunden später im [!UICONTROL Total Trait Population].

Jede Änderung der Eigenschaften spiegelt sich in Segmentpopulationen wider.

## Segmentpopulation in Echtzeit und Segmentpopulation insgesamt {#real-time-segment}

![unique-property-realization](assets/segment-graph.png)

Das [!UICONTROL Real-time Segment Population] zählt die Anzahl der Geräte, die sich innerhalb des ausgewählten Zeitintervalls für das ausgewählte Segment qualifiziert haben und Ihre Eigenschaften erreicht haben.

Das [!UICONTROL Total Segment Population] zählt die Anzahl der Geräte, die sich innerhalb des ausgewählten Zeitraums für das ausgewählte Segment qualifiziert haben. Der [!UICONTROL 1 Day]-Bericht stellt die aktuellste Segmentpopulationszahl dar.

Stellen Sie sich die Zahlen so vor. In der obigen Abbildung steht in der Ansicht [Segmentdetails](../../features/segments/segment-summary-view.md) 9.993 die Anzahl der aktiven Geräte, die Ihre Eigenschaften gestern besucht haben und für das Segment qualifiziert sind. Die Zahl [!UICONTROL Total Segment Population] von 699.532 stellt die Gesamtzahl der Geräte dar, die derzeit für dieses Segment qualifiziert sind. Die Zahl [!UICONTROL Total Segment Population] zeigt die Gesamtanzahl der Geräte an, die für die Segmentierung/das Targeting verwendet werden könnten.

Da wir zwei verschiedene Rechenaufträge ausführen, um die beiden Populationen zu berechnen, liegt das [!UICONTROL Total Segment Population] immer um 24 Stunden hinter dem [!UICONTROL Real-time Segment Population] zurück. Im Diagramm oben sehen Sie einen Wert von 8,116 [!UICONTROL Real-time Segment Population] und einen von [!UICONTROL Total Segment Population] von 742.000 für den 2. Februar. Die 8.116 Profil werden am folgenden Tag zum [!UICONTROL Total Segment Population] hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, würden Sie, wenn Sie eine Spitze von 10.000 Besuchern im Moment erleben würden, diese im [!UICONTROL Real-time Segment Population] von morgen erscheinen, aber erst 24 Stunden später im [!UICONTROL Total Segment Population].

## Qualifikationslimit für Eigenschaften {#trait-qualification-limit}

Für jedes Profil gelten maximal 150.000 Eigenschaftsqualifikationen, unabhängig davon, ob es sich um ein authentifiziertes Profil ([DPUUID](../../reference/ids-in-aam.md)) oder um eine Geräte-ID ([UUID](../../reference/ids-in-aam.md)) handelt. Beachten Sie, dass die DPUUIDs zwar für eine bestimmte Instanz von [!DNL Audience Manager] eindeutig sind, UUIDs jedoch für die [!DNL Audience Manager]-Plattform freigegeben werden. Für [!UICONTROL UUID]s verhängen wir beim Speichern von Eigenschaftsqualifikationen eine Fairness-Richtlinie. Ein Algorithmus stellt sicher, dass für jede Instanz von [!DNL Audience Manager] ein gleich hoher Anteil des [!UICONTROL UUID]-Profils verfügbar ist.
