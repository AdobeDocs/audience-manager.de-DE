---
description: Vermeiden Sie die Verwendung von Profilzusammenführungsregeln mit einem Gerätediagramm für Segmente, die wenig zu keiner Echtzeit-Segmentpopulation führen.
seo-description: Vermeiden Sie die Verwendung von Profilzusammenführungsregeln mit einem Gerätediagramm für Segmente, die wenig zu keiner Echtzeit-Segmentpopulation führen.
seo-title: Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen
title: Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen
uuid: 93 cd 8861-210 d -4 c 52-9 cb 7-6 f 2 dd 7 dc 018 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen {#important-considerations-for-profile-merge-rules-with-device-graphs}

Vermeiden Sie es, [!UICONTROL Profile Merge Rules] für [!UICONTROL Device Graph] Segmente zu verwenden, die wenig zu keiner Echtzeit-Segmentpopulation haben.

>[!IMPORTANT]
>
>Wenn sie [!UICONTROL Profile Merge Rule] falsch konfiguriert ist, kann die Segmentpopulation, die zu Stapelzielen führte, deutlich niedriger ausfallen als erwartet.

Segmente, die eine Regel [zum Profilzusammenführen mit einem Gerätediagramm](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) verwenden, werden nur für Geräte ausgewertet, die in Echtzeit auf [den Edge-Servern](../../reference/system-components/components-edge.md) von Audience Manager angezeigt werden, nachdem das Segment erstellt wurde.

Denken Sie daran, dass eine [!UICONTROL Profile Merge Rule][!UICONTROL Device Graph] der folgenden Geräteoptionen ausgewählt ist, wie unten dargestellt.

![](assets/pmr-considerations-1.png)

Geräte, die sich in Echtzeit für ein Segment qualifizieren, werden durch die Echtzeitpopulation [des Segments gemessen](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

Eine geringe Echtzeit-Segmentpopulation bedeutet, dass nur sehr wenige der für das Segment qualifizierenden Geräte in Echtzeit angesehen werden. Für eine optimale Leistung sollten Segmente mit wenig zu keiner Echtzeit-Population einen [!UICONTROL Profile Merge Rule] Satz verwenden, um *[!UICONTROL Current Device]*wie im unten stehenden Bild zu bewerten.

![](assets/pmr-considerations-3.png)

Durch Festlegen des [!UICONTROL Profile Merge Rule] Werts wird *[!UICONTROL Current Device]* sichergestellt, dass alle Geräte (nicht nur die in Echtzeit angezeigten) für das Segment ausgewertet werden. Alle für das Segment qualifizierenden Geräte werden durch die gesamte Segmentpopulation definiert, wie unten dargestellt.

![](assets/pmr-considerations-4.png)