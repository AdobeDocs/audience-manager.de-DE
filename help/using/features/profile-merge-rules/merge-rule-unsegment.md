---
description: Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile disqualifizieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profilzusammenführungsrichtlinie verwendet wird.
seo-description: Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile disqualifizieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profilzusammenführungsrichtlinie verwendet wird.
seo-title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
solution: Audience Manager
title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profilzusammenführung
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung {#profile-merge-rules-and-device-un-segmentation-processes}

Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile disqualifizieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen eines [!UICONTROL Profile Merge Rule] verwendet wird.

## Verfügbare Geräteoptionen {#device-options}

Zur Erinnerung: Die [!UICONTROL Device Options] sind im Abschnitt [!UICONTROL Profile Merge Rules Setup] verfügbar, wenn Sie ein [!UICONTROL Profile Merge Rule] erstellen oder bearbeiten.

## Option &quot;Aktuelles Geräteprofil&quot;und Aufhebung der Gerätesegmentierung {#current-device-profile-options}

**[!UICONTROL Device Profile]** ist die standardmäßige Geräteprofiloption für eine  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] kann ein Geräteprofil aus einem Segment entfernen, wenn Sie die  [!UICONTROL Profile Merge Rule] Option  **[!UICONTROL Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Aufhebung der Segmentierung, wenn:

* Das Geräteprofil ist seit 120 Tagen inaktiv. Bei einer wöchentlichen Datenbereinigung werden inaktive Geräteprofile aus Ihren Segmenten entfernt.
* Das Gerät qualifiziert sich nicht mehr für ein Segment, da es durch Aktualisierungen oder Änderungen am Geräteprofil nicht qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern oder Sie einen [!DNL AND NOT] -Operator auf eine Segmentregel anwenden oder [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md)-Bedingungen angeben, die die Einstellungen &quot;kleiner als/gleich&quot;verwenden. Anwendungsbeispiele werden in der Dokumentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) beschrieben.

![device-only](assets/device-only.png)

## Keine Geräteoption und Aufhebung der Gerätesegmentierung {#no-device-option}

[!DNL Audience Manager] kann eine geräteübergreifende ID aus einem Segment entfernen, wenn Sie die  [!UICONTROL Profile Merge Rule] Option  **[!UICONTROL Current Authenticated Profiles]** +  **[!UICONTROL No Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Aufhebung der Segmentierung, wenn die geräteübergreifende ID nicht mehr für ein Segment qualifiziert ist, da sie durch Aktualisierungen oder Änderungen am geräteübergreifenden Profil nicht qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern oder Sie einen [!UICONTROL AND NOT] -Operator auf eine Segmentregel anwenden oder [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md)-Bedingungen angeben, die die Einstellungen &quot;kleiner als/gleich&quot;verwenden. Anwendungsbeispiele werden in der Dokumentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) beschrieben.

![](assets/current-no-device.png)

## Gerätediagrammoptionen und Aufhebung der Gerätesegmentierung {#device-graph-options-unsegmentation}

[!DNL Audience Manager] kann mehrere Geräteprofile aus einem Segment entfernen, wenn Sie eine Gerätediagrammoption  [!UICONTROL Profile Merge Rule] verwenden. Die Segmentierung wird aufgehoben, wenn das zusammengeführte Profil des Geräts aus dem Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Aktualisierungen oder Änderungen an diesem zusammengeführten Profil es aus dem Segment disqualifizieren. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern oder Sie einen [!UICONTROL AND NOT] -Operator auf eine Segmentregel anwenden oder [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md)-Bedingungen angeben, die die Einstellungen &quot;kleiner als/gleich&quot;verwenden. Anwendungsbeispiele werden in der Dokumentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) beschrieben.

>[!NOTE]
>
>**100 Gerätegrenzwerte für die Segmentbewertung und den Ausschluss** von der Qualifikation.
>Audience Manager führt bis zu 100 Geräte zusammen, wenn Segmente mit einer Profilzusammenführungsrichtlinie ausgewertet werden, die ein Gerätediagramm verwendet. Audience Manager bewertet das aktuelle Gerät und bis zu 99 Geräte, die mit dem aktuellen Gerät verknüpft sind, anhand eines [authentifizierten Profils](../../reference/visitor-authentication-states.md) (geräteübergreifende ID). Wenn das Signal zur Aufhebung der Segmentierung ausgegeben wird, werden das aktuelle Gerät und zusätzliche Geräte aus dem Segment im Ziel entfernt.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
* [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md)

