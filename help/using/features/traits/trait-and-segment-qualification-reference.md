---
description: Die Eigenschaftsqualifizierung oder die Realisierung von Eigenschaften wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Detaillierte Informationen zur Eigenschaftsqualifikation finden Sie in der nachfolgenden Tabelle.
keywords: Eigenschaftsqualifikation, Eigenschaftsrealisierung, Einzelmerkmal-Realisierungen, UTR, Gesamtzahl der Eigenschaftspopulationen, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Eigenschaftsqualifikationsreferenz
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Referenz zu Eigenschafts- und Segmentqualifikationen {#trait-qualification-reference}

Die Eigenschaftsqualifizierung oder die Realisierung von Eigenschaften wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Weitere Informationen zur Qualifizierung des Eigenschaftstyps finden Sie unter [Eigenschaftsqualifikation nach Eigenschaftstyp](#trait-type) .

Weitere Informationen zur Segmentqualifizierung finden Sie unter [Segmentpopulation in Echtzeit und Segmentpopulation insgesamt](#real-time-segment) .



## Eigenschaftsqualifikation nach Eigenschaftstyp {#trait-type}

| Eigenschaftstyp | Qualifikationskriterien |
|---|---|
| Regelbasierte Eigenschaften | Die Eigenschaftsqualifizierung erfolgt in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren. Ihre Benutzer qualifizieren sich ca. 4 Stunden nach der Erstellung der Eigenschaft [1} in der Benutzeroberfläche für eine regelbasierte Eigenschaft. ](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Regelbasierte Eigenschaften ermöglichen die Verwendung von [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) -Steuerelementen für die Begrenzung der Anzeigenfrequenz und andere Anwendungsfälle. |
| Integrierte Eigenschaften | Die Eigenschaftsqualifizierung erfolgt nach der Verarbeitung einer eingehenden Datei, d. h. die eingehende Datei wird [in Audience Manager](../../faq/faq-inbound-data-ingestion.md) importiert und die Eigenschaftsqualifizierung erfolgt. Sie sollten etwa 4 Stunden nach der Erstellung einer integrierten Eigenschaft warten, bevor Sie eine eingehende Datei zur Verarbeitung hochladen. Bei integrierten Eigenschaften beträgt die maximale Anzahl der Qualifikationen für ein Benutzerprofil 1. |
| Algorithmische Eigenschaften | Für algorithmische Eigenschaften beträgt die maximale Anzahl der Qualifikationen für ein Benutzerprofil 1. |
| Ordnereigenschaften | Eine Ordnereigenschaft fasst die Eigenschaftsqualifikationen der darin enthaltenen Eigenschaften zusammen. Weitere Informationen finden Sie unter [Ordnereigenschaften: Info](about-folder-traits.md) . |
| Eigenschaften aktiver Zielgruppen und von Source synchronisierte Daten | Eine [!UICONTROL Active Audience] -Eigenschaft enthält alle Geräte, die in Ihrem Audience Manager-Konto verwaltet werden. [!UICONTROL Data Source Synced Traits] verfolgt alle mit einer Datenquelle verknüpften Benutzer. Erfahren Sie mehr über [Eigenschaften aktiver Zielgruppen und mit Source synchronisierte Daten-Eigenschaften](client-activity-synced-audience-traits.md). |

## Eindeutige Eigenschaftsrealisierungen und Gesamtzahl der Eigenschaftspopulationen {#unique-trait-realizations}

![unique-trait-realization](assets/trait-graph.png)

Je nach Ergebnistyp, den das Diagramm anzeigen soll (gefiltert nach [!UICONTROL Device ID] oder [!UICONTROL Cross-Device ID]), haben die Metriken unterschiedliche Bedeutungen:

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der Besucher Ihres anonymen Geräts, die die Eigenschaft innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Gerätebesucher, deren Profil diese Eigenschaft aufweist.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl Ihrer authentifizierten Besucher, die ihrem Profil die Eigenschaft innerhalb verschiedener Zeiträume hinzugefügt haben.
* [!UICONTROL Total Trait Population] ist die Anzahl Ihrer authentifizierten Besucher, die diese Eigenschaft in ihrem Profil haben.

Stellen Sie sich die Zahlen so vor. In der obigen Abbildung stellt die Ansicht [Eigenschaftendetails](../../features/traits/trait-details-page.md) 90.173 die Anzahl der aktiven Geräte dar, die Ihre Eigenschaften gestern besucht haben. Der [!UICONTROL Total Trait Population] -Wert von 55.757 stellt die Anzahl der Benutzer dar, die derzeit für diese Eigenschaft qualifiziert sind. Die [!UICONTROL Total Trait Population] -Zahl soll die Gesamtanzahl der Benutzer anzeigen, die für die Segmentierung/das Targeting verwendet werden können. In der Regel bleiben Benutzer 120 Tage lang Teil einer Eigenschaft.

Da wir zwei verschiedene Rechenvorgänge ausführen, um die beiden Populationen zu berechnen, liegt die [!UICONTROL Total Trait Population] immer um 24 Stunden hinter der [!UICONTROL Unique Trait Realizations]. In der obigen Grafik sehen Sie ungefähr 90.400 [!UICONTROL Unique Trait Realizations] und eine [!UICONTROL Total Trait Population] von etwa 90.300 für den 5. Februar. Die 90.400 Profile werden am darauf folgenden Tag zum [!UICONTROL Total Trait Population] hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, würden Sie, wenn Sie im Moment eine Spitze von 10.000 Besuchern erlebten, in der [!UICONTROL Unique Trait Realizations] von morgen erscheinen, aber erst 24 Stunden später in der [!UICONTROL Total Trait Population] erscheinen.

Jede Änderung der Eigenschaftsrealisierungen spiegelt sich in den Segmentpopulationen wider.

## Segmentpopulation in Echtzeit und Segmentpopulation insgesamt {#real-time-segment}

![unique-trait-realization](assets/segment-graph.png)

Der [!UICONTROL Real-time Segment Population] zählt die Anzahl der Geräte, die sich für das ausgewählte Segment qualifiziert haben und Ihre Eigenschaften innerhalb des ausgewählten Zeitintervalls erreicht haben.

Der [!UICONTROL Total Segment Population] zählt die Anzahl der Geräte, die sich für das ausgewählte Segment innerhalb des ausgewählten Zeitraums qualifiziert haben. Der [!UICONTROL 1 Day] -Bericht stellt die aktuellste Segmentpopulationszahl dar.

Stellen Sie sich die Zahlen so vor. In der obigen Abbildung stellt in der Ansicht [Segmentdetails](../../features/segments/segment-summary-view.md) 9.993 die Anzahl der aktiven Geräte dar, die Ihre Eigenschaften gestern besucht und sich für das Segment qualifiziert haben. Der [!UICONTROL Total Segment Population] -Wert von 699.532 stellt die Gesamtzahl der Geräte dar, die derzeit für dieses Segment qualifiziert sind. Die [!UICONTROL Total Segment Population] -Zahl soll die Gesamtanzahl der Geräte anzeigen, die für die Segmentierung/das Targeting verwendet werden können.

Da wir zwei verschiedene Rechenvorgänge ausführen, um die beiden Populationen zu berechnen, liegt die [!UICONTROL Total Segment Population] immer um 24 Stunden hinter der [!UICONTROL Real-time Segment Population]. Im obigen Diagramm sehen Sie einen 8.116 [!UICONTROL Real-time Segment Population] und einen 1 von 742.000 für den 2. Februar. [!UICONTROL Total Segment Population] Die 8.116 Profile werden am folgenden Tag zum [!UICONTROL Total Segment Population] hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, würden Sie, wenn Sie im Moment eine Spitze von 10.000 Besuchern erlebten, in der [!UICONTROL Real-time Segment Population] von morgen erscheinen, aber erst 24 Stunden später in der [!UICONTROL Total Segment Population] erscheinen.

## Eigenschaftsqualifikationslimit {#trait-qualification-limit}

Für jedes Benutzerprofil wird eine Beschränkung von 150.000 Eigenschaftsqualifikationen erzwungen, unabhängig davon, ob es sich um ein authentifiziertes Profil ([DPUUID](../../reference/ids-in-aam.md)) oder eine Geräte-ID ([UID](../../reference/ids-in-aam.md)) handelt. Beachten Sie, dass die DPUUIDs zwar für eine bestimmte Instanz von [!DNL Audience Manager] eindeutig sind, die UUIDs jedoch auf der gesamten [!DNL Audience Manager]-Plattform freigegeben werden. Für [!UICONTROL UUID]s legen wir beim Speichern von Eigenschaftsqualifikationen eine Fairness-Richtlinie fest. Ein Algorithmus stellt sicher, dass für jede Instanz von [!DNL Audience Manager] ein gleich hoher Anteil des [!UICONTROL UUID] Profils verfügbar ist.
