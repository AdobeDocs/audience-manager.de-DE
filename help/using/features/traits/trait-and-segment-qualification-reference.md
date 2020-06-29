---
description: Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird im Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird im Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.
seo-title: Eigenschaftsqualifikationsreferenz
solution: Audience Manager
title: Eigenschaftsqualifikationsreferenz
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---


# Referenz zu Eigenschaften und Segmentqualifikationen {#trait-qualification-reference}

Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird im Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Weitere Informationen zur Qualifizierung des [Eigenschaftstyps finden Sie unter Qualifizierung nach](#trait-type) Eigenschaftstyp.

Weitere Informationen zur Segmentqualifizierung finden Sie unter Segmentpopulationen in [Echtzeit und Segmentpopulation](#real-time-segment) insgesamt.



## Eigenschaftsqualifikation nach Eigenschaftstyp {#trait-type}

| Eigenschaftstyp | Qualifikationskriterien |
|---|---|
| Regelbasierte Eigenschaften | Die Qualifizierung von Eigenschaften erfolgt in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren. Ihre Beginn qualifizieren sich ca. 4 Stunden nach der [Erstellung der Eigenschaft](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) in der Benutzeroberfläche für eine regelbasierte Eigenschaft. Regelbasierte Eigenschaften ermöglichen Ihnen die Verwendung von [Neuigkeits- und Häufigkeitssteuerelementen](../segments/recency-and-frequency.md) für die Begrenzung der Anzeigenfrequenz und andere Anwendungsfälle. |
| Integrierte Eigenschaften | Die Qualifizierung von Eigenschaften erfolgt nach der Verarbeitung einer eingehenden Datei, d. h., die eingehende Datei wird in den Audience Manager [](../../faq/faq-inbound-data-ingestion.md) importiert und dann erfolgt die Qualifizierung der Eigenschaften. Sie sollten etwa 4 Stunden nach dem Erstellen einer nicht integrierten Eigenschaft warten, bevor Sie eine eingehende Datei zur Verarbeitung hochladen. Bei nicht an Bord befindlichen Eigenschaften beträgt die maximale Anzahl von Qualifikationen für ein Profil 1. |
| Algorithmische Eigenschaften | Bei algorithmischen Eigenschaften ist die maximale Anzahl von Qualifikationen für ein Profil 1. |
| Ordnereigenschaften | Eine Ordnereigenschaft fasst die Eigenschaftsqualifikationen der darin enthaltenen Eigenschaften zusammen. Eigenschaften von [Read-Ordnern: Info](about-folder-traits.md) für weitere Informationen. |
| Eigenschaften der aktiven Audience und von Datenquelle synchronisierte Eigenschaften | Eine [!UICONTROL Active Audience] Eigenschaft enthält alle Geräte, die in Ihrem Audience Manager-Konto verwaltet werden. [!UICONTROL Data Source Synced Traits] alle mit einer Datenquelle verknüpften Benutzer verfolgen. Lesen Sie mehr über [Aktive Audience-Eigenschaften und Datenquelle-synchronisierte Eigenschaften](client-activity-synced-audience-traits.md). |

## Eindeutige Eigenschaften und Gesamtanzahl der Eigenschaften {#unique-trait-realizations}

![unique-property-realization](assets/trait-graph.png)

Je nach Ergebnistyp, der im Diagramm angezeigt werden soll (gefiltert nach [!UICONTROL Device ID] oder [!UICONTROL Cross-Device ID]), haben die Metriken unterschiedliche Bedeutungen:

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der anonymen Besucher, die die Eigenschaft innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Besucher, die diese Eigenschaft auf ihrem Profil haben.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der authentifizierten Besucher, die das Merkmal innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der authentifizierten Besucher, die diese Eigenschaft auf ihrem Profil haben.

Stellen Sie sich die Zahlen so vor. In der Abbildung oben zeigt die Ansicht [Eigenschaftendetails](../../features/traits/trait-details-page.md) 90.173 die Anzahl der aktiven Geräte, die Ihre Eigenschaften gestern besucht haben. Der Wert [!UICONTROL Total Trait Population] von 55.757 stellt die Anzahl der Benutzer dar, die derzeit für diese Eigenschaft qualifiziert sind. Die [!UICONTROL Total Trait Population] Zahl zeigt die Gesamtanzahl der Benutzer an, die für die Segmentierung/das Targeting verwendet werden könnten. Normalerweise bleiben Benutzer 120 Tage lang Teil einer Eigenschaft.

Da wir zwei verschiedene Rechenaufgaben ausführen, um die zwei Populationen zu berechnen, liegt die [!UICONTROL Total Trait Population] immer um 24 Stunden hinter der [!UICONTROL Unique Trait Realizations] . In der Grafik oben sehen Sie ungefähr 90.400 [!UICONTROL Unique Trait Realizations] und eine [!UICONTROL Total Trait Population] von etwa 90.300 für den 5. Februar. Die 90.400 Profil werden am [!UICONTROL Total Trait Population] darauffolgenden Tag dem hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, wenn man eine Spitze von 10.000 Besuchern im Moment erlebt, würden sie in der Zukunft erscheinen [!UICONTROL Unique Trait Realizations], aber nur 24 Stunden später in der [!UICONTROL Total Trait Population].

Jede Änderung der Eigenschaften spiegelt sich in Segmentpopulationen wider.

## Segmentpopulation in Echtzeit und Segmentpopulation insgesamt {#real-time-segment}

![unique-property-realization](assets/segment-graph.png)

Die [!UICONTROL Real-time Segment Population] Anzahl der Geräte, die sich für das ausgewählte Segment qualifiziert haben und Ihre Eigenschaften innerhalb des ausgewählten Zeitintervalls erreicht haben.

Die [!UICONTROL Total Segment Population] Anzahl der Geräte, die sich innerhalb des ausgewählten Zeitraums für das ausgewählte Segment qualifiziert haben. Der [!UICONTROL 1 Day] Bericht stellt die aktuellste Segmentpopulationszahl dar.

Stellen Sie sich die Zahlen so vor. In oben stehender Abbildung zeigt die Ansicht [Segmentdetails](../../features/segments/segment-summary-view.md) 9.993 die Anzahl der aktiven Geräte, die Ihre Eigenschaften gestern besucht haben und für das Segment qualifiziert sind. Der Wert [!UICONTROL Total Segment Population] von 699.532 stellt die Gesamtzahl der Geräte dar, die derzeit für dieses Segment qualifiziert sind. Die [!UICONTROL Total Segment Population] Abbildung zeigt die Gesamtanzahl der Geräte, die für die Segmentierung/das Targeting verwendet werden können.

Da wir zwei verschiedene Rechenaufgaben ausführen, um die zwei Populationen zu berechnen, liegt die [!UICONTROL Total Segment Population] immer um 24 Stunden hinter der [!UICONTROL Real-time Segment Population] . In dem Diagramm oben sehen Sie einen 8.116 [!UICONTROL Real-time Segment Population] und einen [!UICONTROL Total Segment Population] von 742.000 für den 2. Februar. Die 8.116 Profil werden am folgenden [!UICONTROL Total Segment Population] Tag zum hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, wenn man eine Spitze von 10.000 Besuchern im Moment erlebt, würden sie in der Zukunft erscheinen [!UICONTROL Real-time Segment Population], aber nur 24 Stunden später in der [!UICONTROL Total Segment Population].

## Qualifikationslimit für Eigenschaften {#trait-qualification-limit}

Für jedes Profil gelten maximal 150.000 Eigenschaftsqualifikationen, unabhängig davon, ob es sich um ein authentifiziertes Profil ([DPUUID](../../reference/ids-in-aam.md)) oder eine Geräte-ID ([UUID](../../reference/ids-in-aam.md)) handelt. Beachten Sie, dass die DPUUIDs zwar für eine bestimmte Instanz von eindeutig sind, [!DNL Audience Manager]dass UUIDs jedoch auf der [!DNL Audience Manager] Plattform freigegeben werden. Für [!UICONTROL UUID]uns wird bei der Speicherung von Eigenschaftsqualifikationen eine Fairness-Politik verhängt. Ein Algorithmus stellt sicher, dass für jede Instanz des [!UICONTROL UUID] Profils ein gleich hoher Anteil zur Verfügung steht [!DNL Audience Manager].

