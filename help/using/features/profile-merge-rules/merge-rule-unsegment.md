---
description: Die Aufhebung der Segmentierung beschreibt Prozesse, durch die Geräteprofile disqualifiziert und aus Segmenten entfernt werden. Welche Möglichkeit Sie haben, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profilzusammenführungsregel verwendet wird.
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: Regeln für die Profilzusammenführung und Prozesse zur Aufhebung der Segmentierung von Geräten
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Regeln für die Profilzusammenführung und Prozesse zur Aufhebung der Segmentierung von Geräten {#profile-merge-rules-and-device-un-segmentation-processes}

Die Aufhebung der Segmentierung beschreibt Prozesse, durch die Geräteprofile disqualifiziert und aus Segmenten entfernt werden. Ihre Möglichkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen eines [!UICONTROL Profile Merge Rule] verwendet wird.

## Verfügbare Geräteoptionen {#device-options}

Zur Erinnerung: Die [!UICONTROL Device Options] stehen beim Erstellen oder Bearbeiten eines [!UICONTROL Profile Merge Rules Setup] im Abschnitt [!UICONTROL Profile Merge Rule] zur Verfügung.

## Option „Aktuelles Geräteprofil“ und „Geräte-Segmentierung aufheben“ {#current-device-profile-options}

**[!UICONTROL Device Profile]** ist die standardmäßige Geräteprofiloption für ein [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] können ein Geräteprofil aus einem Segment entfernen, wenn Ihr [!UICONTROL Profile Merge Rule] die Option **[!UICONTROL Device Profile]** verwendet. Unter diesen Bedingungen erfolgt eine Nicht-Segmentierung, wenn:

* Das Geräteprofil ist seit 120 Tagen inaktiv. Ein wöchentlicher Datenbereinigungsprozess entfernt inaktive Geräteprofile aus Ihren Segmenten.
* Das Gerät ist nicht mehr für ein Segment qualifiziert, da es durch Aktualisierungen oder Änderungen am Geräteprofil nicht qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern, Sie einen [!DNL AND NOT] auf eine Segmentregel anwenden oder Bedingungen für [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) angeben, die die Einstellungen „kleiner als/gleich“ verwenden. Anwendungsfälle werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![nur für Geräte](assets/device-only.png)

## Keine Geräteoption und Geräte-Segmentierung {#no-device-option}

[!DNL Audience Manager] können eine geräteübergreifende ID aus einem Segment entfernen, wenn Ihr [!UICONTROL Profile Merge Rule] die Option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** verwendet. Unter diesen Bedingungen erfolgt eine Nicht-Segmentierung, wenn die geräteübergreifende ID sich nicht mehr für ein Segment qualifiziert, da Aktualisierungen oder Änderungen am geräteübergreifenden Profil es disqualifizieren. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern, Sie einen [!UICONTROL AND NOT] auf eine Segmentregel anwenden oder Bedingungen für [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) angeben, die die Einstellungen „kleiner als/gleich“ verwenden. Anwendungsfälle werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![](assets/current-no-device.png)

## Diagrammoptionen für Geräte und Unsegmentierung von Geräten {#device-graph-options-unsegmentation}

[!DNL Audience Manager] können mehrere Geräteprofile aus einem Segment entfernen, wenn Ihr [!UICONTROL Profile Merge Rule] eine Gerätediagramm-Option verwendet. Die Nicht-Segmentierung erfolgt, wenn das zusammengeführte Profil des Geräts aus dem Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Aktualisierungen oder Änderungen an diesem zusammengeführten Profil es nicht für das Segment qualifizieren. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern, Sie einen [!UICONTROL AND NOT] auf eine Segmentregel anwenden oder Bedingungen für [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) angeben, die die Einstellungen „kleiner als/gleich“ verwenden. Anwendungsfälle werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

>[!NOTE]
>
>**100 Geräte-Limit für Segmentauswertung und Disqualifizierung**.
>>Audience Manager führt beim Auswerten von Segmenten mit einer Profilzusammenführungsregel, die ein Gerätediagramm verwendet, bis zu 100 Geräte zusammen. Audience Manager bewertet das aktuelle Gerät und bis zu 99 Geräte, die mit dem aktuellen Gerät durch ein [authentifiziertes Profil“ ](../../reference/visitor-authentication-states.md) sind (geräteübergreifende ID). Wenn das Signal zum Aufheben der Segmentierung ausgegeben wird, werden das aktuelle Gerät und zusätzliche Geräte aus dem Segment im Ziel entfernt.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md)
