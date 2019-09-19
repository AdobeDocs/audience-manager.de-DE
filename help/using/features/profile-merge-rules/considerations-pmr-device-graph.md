---
description: Vermeiden Sie die Verwendung von Profilzusammenführungsregeln mit einem Gerätediagramm für Segmente, die wenig bis gar keine Segmentpopulation in Echtzeit aufweisen.
seo-description: Vermeiden Sie die Verwendung von Profilzusammenführungsregeln mit einem Gerätediagramm für Segmente, die wenig bis gar keine Segmentpopulation in Echtzeit aufweisen.
seo-title: Wichtige Überlegungen für Regeln zum Profilzusammenführen mit Gerätediagrammen
title: Wichtige Überlegungen für Regeln zum Profilzusammenführen mit Gerätediagrammen
uuid: 93cd8861-210d-4c52-9cb7-6f2dd7dc018a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Wichtige Überlegungen für Regeln zum Profilzusammenführen mit Gerätediagrammen {#important-considerations-for-profile-merge-rules-with-device-graphs}

Vermeiden Sie die Verwendung [!UICONTROL Profile Merge Rules] mit einer [!UICONTROL Device Graph] für Segmente, die wenig bis gar keine Segmentpopulation in Echtzeit aufweisen.

>[!IMPORTANT]
>
>Wenn die [!UICONTROL Profile Merge Rule] Konfiguration fehlerhaft ist, kann die in Batch-Ziele exportierte Segmentpopulation deutlich niedriger als erwartet sein.

Segmente, die eine [Profilzusammenführungsregel mit einem Gerätediagramm](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) verwenden, werden nur mit Geräten ausgewertet, die in Echtzeit auf den Edge-Servern[ von ](../../reference/system-components/components-edge.md)Audience Manager angezeigt werden, nachdem das Segment erstellt wurde.

Denken Sie daran, dass eine [!UICONTROL Profile Merge Rule] mit [!UICONTROL Device Graph] einer der folgenden Geräteoptionen ausgewählt ist, wie unten dargestellt.

![](assets/pmr-considerations-1.png)

Geräte, die sich für ein Segment in Echtzeit qualifizieren, werden anhand der Echtzeit-Bevölkerung des [Segments](../../features/segments/segment-builder-data.md#segment-populations)gemessen.

![](assets/pmr-considerations-2.png)

Eine geringe Segmentpopulation in Echtzeit bedeutet, dass nur sehr wenige Geräte, die für das Segment qualifiziert sind, in Echtzeit gesehen werden. Für eine optimale Leistung sollten Segmente mit wenig bis gar keiner Echtzeit-Population einen [!UICONTROL Profile Merge Rule] Satz verwenden, um den Wert zu bewerten, wie in der Abbildung unten dargestellt *[!UICONTROL Current Device]*.

![](assets/pmr-considerations-3.png)

Wenn Sie die Einstellung [!UICONTROL Profile Merge Rule] zum Auswerten des Segments festlegen, *[!UICONTROL Current Device]* wird sichergestellt, dass alle Geräte (nicht nur die in Echtzeit angezeigten) für das Segment ausgewertet werden. Alle Geräte, die für das Segment qualifiziert sind, werden durch die gesamte Segmentpopulation definiert, wie unten dargestellt.

![](assets/pmr-considerations-4.png)