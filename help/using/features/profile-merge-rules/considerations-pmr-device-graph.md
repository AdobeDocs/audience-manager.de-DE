---
description: Vermeiden Sie die Verwendung von Profilzusammenführungsregeln mit einem Gerätediagramm für Segmente, die wenig zu keiner Echtzeit-Segmentpopulation führen.
seo-description: Vermeiden Sie die Verwendung von Profilzusammenführungsregeln mit einem Gerätediagramm für Segmente, die wenig zu keiner Echtzeit-Segmentpopulation führen.
seo-title: Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen
title: Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen
uuid: 93 cd 8861-210 d -4 c 52-9 cb 7-6 f 2 dd 7 dc 018 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Important Considerations for Profile Merge Rules with Device Graphs {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>If the [!UICONTROL Profile Merge Rule] is configured incorrectly, the segment population exported to batch destinations may be significantly lower than expected.

Segments using a [Profile Merge Rule with a Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) are only evaluated against devices seen in real-time on [Audience Manager’s Edge Servers](../../reference/system-components/components-edge.md) after the segment has been created.

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

Devices that qualify for a segment in real-time are measured by the [segment’s real-time population](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

Eine geringe Echtzeit-Segmentpopulation bedeutet, dass nur sehr wenige der für das Segment qualifizierenden Geräte in Echtzeit angesehen werden. For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. Alle für das Segment qualifizierenden Geräte werden durch die gesamte Segmentpopulation definiert, wie unten dargestellt.

![](assets/pmr-considerations-4.png)