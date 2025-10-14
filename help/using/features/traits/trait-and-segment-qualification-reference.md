---
description: Die Eigenschaftsqualifizierung oder Eigenschaftsrealisierung wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Detaillierte Informationen zur Qualifizierung von Eigenschaften finden Sie in der folgenden Tabelle.
keywords: Eigenschaftenqualifizierung, Eigenschaftenrealisierung, Realisierung eindeutiger Eigenschaften, UTR, Gesamtpopulation von Eigenschaften, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Referenz zur Eigenschaftenqualifizierung
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Referenz zur Trait- und Segmentqualifikation {#trait-qualification-reference}

Die Eigenschaftsqualifizierung oder Eigenschaftsrealisierung wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Siehe [Eigenschaftsqualifizierung nach &#x200B;](#trait-type)) für Details zur Eigenschaftstypqualifizierung.

Weitere Informationen zur Segmentqualifikation finden [&#x200B; unter „Echtzeit](#real-time-segment)Segmentpopulation und Gesamtsegmentpopulation“.



## Eigenschaftenqualifizierung nach Eigenschaftstyp {#trait-type}

| Eigenschaftstyp | Qualifikationskriterien |
|---|---|
| Regelbasierte Eigenschaften | Die Eigenschaftsqualifizierung erfolgt in Echtzeit, da Benutzende in ihrem Browser für eine Eigenschaft qualifiziert sind. Ihre Benutzerinnen und Benutzer qualifizieren sich etwa 4 Stunden, nachdem Sie in der Benutzeroberfläche die Eigenschaft [Erstellen](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) für eine regelbasierte Eigenschaft. Regelbasierte Eigenschaften ermöglichen die Verwendung von Steuerelementen [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) für die Begrenzung der Anzeigenfrequenz und andere Anwendungsfälle. |
| Integrierte Eigenschaften | Die Eigenschaftsqualifizierung erfolgt, nachdem eine eingehende Datei verarbeitet wurde, d. h. die eingehende Datei [in Audience Manager importiert](../../faq/faq-inbound-data-ingestion.md) und zwar dann, wenn die Eigenschaftsqualifizierung erfolgt. Nach der Erstellung einer integrierten Eigenschaft sollten Sie etwa 4 Stunden warten, bevor Sie eine eingehende Datei zur Verarbeitung hochladen. Für integrierte Eigenschaften beträgt die maximale Anzahl von Qualifikationen für ein Benutzerprofil 1. |
| Algorithmische Eigenschaften | Bei algorithmischen Eigenschaften ist die maximale Anzahl von Qualifikationen für ein Benutzerprofil 1. |
| Ordnereigenschaften | Eine Ordnereigenschaft fasst die Eigenschaftsqualifikationen der enthaltenen Eigenschaften zusammen. Weitere [&#x200B; finden Sie unter &#x200B;](about-folder-traits.md): Ordnereigenschaften. |
| Aktive Zielgruppeneigenschaften und synchronisierte Source-Dateneigenschaften | Eine [!UICONTROL Active Audience] Eigenschaft enthält alle Geräte, die in Ihrem Audience Manager-Konto verwaltet werden. [!UICONTROL Data Source Synced Traits] verfolgen alle Benutzer, die einer Datenquelle zugeordnet sind. Lesen Sie mehr über [Aktive Zielgruppeneigenschaften und Daten-Source-synchronisierte Eigenschaften](client-activity-synced-audience-traits.md). |

## Realisierungen einzigartiger Eigenschaften und gesamte Population von Eigenschaften {#unique-trait-realizations}

![unique-trait-realization](assets/trait-graph.png)

Je nach Typ der Ergebnisse, die das Diagramm anzeigen soll (gefiltert nach [!UICONTROL Device ID] oder [!UICONTROL Cross-Device ID]), haben die Metriken unterschiedliche Bedeutungen:

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der Besucherinnen und Besucher Ihres anonymen Geräts, die die Eigenschaft innerhalb verschiedener Zeitbereiche zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Gerätebesucher, die diese Eigenschaft in ihrem Profil haben.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der authentifizierten Besucherinnen und Besucher, die das Merkmal innerhalb verschiedener Zeitbereiche zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der authentifizierten Besucher, die diese Eigenschaft in ihrem Profil haben.

Stellen Sie sich die Zahlen so vor. In der obigen Abbildung [&#x200B; 90.173 aus der Ansicht &#x200B;](../../features/traits/trait-details-page.md)Trait-Details“ die Anzahl der aktiven Geräte, die Ihre Eigenschaften gestern besucht haben. Die [!UICONTROL Total Trait Population] von 55.757 stellt die Anzahl der Benutzenden dar, die derzeit für diese Eigenschaft qualifiziert sind. Die [!UICONTROL Total Trait Population] Abbildung zeigt die Gesamtanzahl der Benutzer, die für die Segmentierung/Zielgruppenbestimmung verwendet werden könnten. In der Regel bleiben Benutzende 120 Tage lang Teil eines Merkmals.

Da wir zur Berechnung der beiden Populationen zwei verschiedene Rechenvorgänge ausführen, hinkt der [!UICONTROL Total Trait Population] dem [!UICONTROL Unique Trait Realizations] immer um 24 Stunden hinterher. Im obigen Diagramm sehen Sie etwa 90.400 [!UICONTROL Unique Trait Realizations] und eine [!UICONTROL Total Trait Population] von etwa 90.300 für den 5. Februar. Die 90.400 Profile werden der [!UICONTROL Total Trait Population] am folgenden Tag hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, wenn Sie eine Spitze von 10.000 Besuchern gerade erlebt haben, würden sie morgen im [!UICONTROL Unique Trait Realizations] angezeigt werden, aber erst 24 Stunden später im [!UICONTROL Total Trait Population].

Jede Änderung bei den Realisierungen von Eigenschaften spiegelt sich in den Segmentpopulationen wider.

## Echtzeit-Segmentpopulation und Gesamt-Segmentpopulation {#real-time-segment}

![unique-trait-realization](assets/segment-graph.png)

Die [!UICONTROL Real-time Segment Population] zählt die Anzahl der Geräte, die sich für das ausgewählte Segment qualifiziert haben und innerhalb des ausgewählten Zeitintervalls Ihre Eigenschaften erreicht haben.

Die [!UICONTROL Total Segment Population] zählt die Anzahl der Geräte, die sich innerhalb des ausgewählten Zeitraums für das ausgewählte Segment qualifiziert haben. Der [!UICONTROL 1 Day] Bericht stellt die aktuellste Segmentpopulation dar.

Stellen Sie sich die Zahlen so vor. In der obigen Abbildung stellt [Segmentdetails](../../features/segments/segment-summary-view.md) die Anzahl der aktiven Geräte dar, die gestern Ihre Eigenschaften besucht und sich für das Segment qualifiziert haben. Die [!UICONTROL Total Segment Population] von 699.532 stellt die Gesamtzahl der Geräte dar, die derzeit für dieses Segment qualifiziert sind. Die [!UICONTROL Total Segment Population] Abbildung zeigt die Gesamtzahl der Geräte an, die für die Segmentierung/Zielgruppenbestimmung verwendet werden können.

Da wir zur Berechnung der beiden Populationen zwei verschiedene Rechenvorgänge ausführen, hinkt der [!UICONTROL Total Segment Population] dem [!UICONTROL Real-time Segment Population] immer um 24 Stunden hinterher. Im obigen Diagramm sehen Sie eine [!UICONTROL Real-time Segment Population] von 8.116 und eine [!UICONTROL Total Segment Population] von 742.000 für den 2. Februar. Die 8.116 Profile werden der [!UICONTROL Total Segment Population] am folgenden Tag hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, wenn Sie eine Spitze von 10.000 Besuchern gerade erlebt haben, würden sie morgen im [!UICONTROL Real-time Segment Population] angezeigt werden, aber erst 24 Stunden später im [!UICONTROL Total Segment Population].

## Qualifikationsgrenze der Eigenschaft {#trait-qualification-limit}

Wir erzwingen ein Limit von 150.000 Eigenschaftsqualifikationen für jedes Benutzerprofil, unabhängig davon, ob es sich um ein authentifiziertes Profil ([DPUUID](../../reference/ids-in-aam.md)) oder eine Geräte-ID ([UUID](../../reference/ids-in-aam.md)) handelt. Beachten Sie, dass die DPUUIDs zwar für eine bestimmte Instanz von [!DNL Audience Manager] eindeutig sind, UUIDs jedoch für die gesamte [!DNL Audience Manager]-Plattform freigegeben werden. Für [!UICONTROL UUID] schreiben wir eine Fairness-Politik bei der Speicherung von Eigenschaftsqualifikationen vor. Ein Algorithmus stellt sicher, dass für jede Instanz von [!UICONTROL UUID] ein gleicher Anteil des [!DNL Audience Manager] bereitgestellt wird.
