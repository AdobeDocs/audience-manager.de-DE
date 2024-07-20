---
description: Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile disqualifizieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profilzusammenführungsrichtlinie verwendet wird.
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung {#profile-merge-rules-and-device-un-segmentation-processes}

Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile disqualifizieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen eines [!UICONTROL Profile Merge Rule] verwendet wird.

## Verfügbare Geräteoptionen {#device-options}

Zur Erinnerung: Die [!UICONTROL Device Options] sind im Abschnitt [!UICONTROL Profile Merge Rules Setup] verfügbar, wenn Sie eine [!UICONTROL Profile Merge Rule] erstellen oder bearbeiten.

## Option &quot;Aktuelles Geräteprofil&quot;und Aufhebung der Gerätesegmentierung {#current-device-profile-options}

**[!UICONTROL Device Profile]** ist die standardmäßige Geräteprofiloption für einen [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] kann ein Geräteprofil aus einem Segment entfernen, wenn Ihr [!UICONTROL Profile Merge Rule] die Option **[!UICONTROL Device Profile]** verwendet. Unter diesen Bedingungen erfolgt die Aufhebung der Segmentierung, wenn:

* Das Geräteprofil ist seit 120 Tagen inaktiv. Bei einer wöchentlichen Datenbereinigung werden inaktive Geräteprofile aus Ihren Segmenten entfernt.
* Das Gerät qualifiziert sich nicht mehr für ein Segment, da es durch Aktualisierungen oder Änderungen am Geräteprofil nicht qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern, oder Sie wenden einen [!DNL AND NOT] -Operator auf eine Segmentregel an oder geben [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) Bedingungen an, die die Einstellungen kleiner als/gleich verwenden. Anwendungsbeispiele werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![nur Gerät](assets/device-only.png)

## Keine Geräteoption und Aufhebung der Gerätesegmentierung {#no-device-option}

[!DNL Audience Manager] kann eine geräteübergreifende ID aus einem Segment entfernen, wenn Ihr [!UICONTROL Profile Merge Rule] die Option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** verwendet. Unter diesen Bedingungen erfolgt die Aufhebung der Segmentierung, wenn die geräteübergreifende ID nicht mehr für ein Segment qualifiziert ist, da sie durch Aktualisierungen oder Änderungen am geräteübergreifenden Profil nicht qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern, oder Sie wenden einen [!UICONTROL AND NOT] -Operator auf eine Segmentregel an oder geben [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) Bedingungen an, die die Einstellungen kleiner als/gleich verwenden. Anwendungsbeispiele werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![](assets/current-no-device.png)

## Gerätediagrammoptionen und Aufhebung der Gerätesegmentierung {#device-graph-options-unsegmentation}

[!DNL Audience Manager] kann mehrere Geräteprofile aus einem Segment entfernen, wenn Ihr [!UICONTROL Profile Merge Rule] eine Gerätediagrammoption verwendet. Die Segmentierung wird aufgehoben, wenn das zusammengeführte Profil des Geräts aus dem Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Aktualisierungen oder Änderungen an diesem zusammengeführten Profil es aus dem Segment disqualifizieren. Dies geschieht, wenn sich die Segmentqualifikationskriterien ändern, oder Sie wenden einen [!UICONTROL AND NOT] -Operator auf eine Segmentregel an oder geben [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md) Bedingungen an, die die Einstellungen kleiner als/gleich verwenden. Anwendungsbeispiele werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

>[!NOTE]
>
>**100 Gerätebegrenzung für die Segmentbewertung und -disqualifizierung**.
>Audience Manager führt bis zu 100 Geräte zusammen, wenn Segmente mit einer Profilzusammenführungsrichtlinie ausgewertet werden, die ein Gerätediagramm verwendet. Audience Manager wertet das aktuelle Gerät und bis zu 99 mit dem aktuellen Gerät verknüpfte Geräte anhand eines [authentifizierten Profils](../../reference/visitor-authentication-states.md) (geräteübergreifende ID) aus. Wenn das Signal zur Aufhebung der Segmentierung ausgegeben wird, werden das aktuelle Gerät und zusätzliche Geräte aus dem Segment im Ziel entfernt.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md)
