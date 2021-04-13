---
description: Die Segmentierung beschreibt Prozesse, die Geräte-Profil deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Profil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profil Merge Rule verwendet wird.
seo-description: Die Segmentierung beschreibt Prozesse, die Geräte-Profil deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Profil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profil Merge Rule verwendet wird.
seo-title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
solution: Audience Manager
title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profil-Zusammenführung
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung {#profile-merge-rules-and-device-un-segmentation-processes}

Die Segmentierung beschreibt Prozesse, die Geräte-Profil deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Profil aus einem Segment zu entfernen, hängt von der Geräteoption ab, mit der ein [!UICONTROL Profile Merge Rule] erstellt wird.

## Verfügbare Geräteoptionen {#device-options}

Zur Erinnerung: Die [!UICONTROL Device Options] sind im Abschnitt [!UICONTROL Profile Merge Rules Setup] verfügbar, wenn Sie ein [!UICONTROL Profile Merge Rule] erstellen oder bearbeiten.

## Option für aktuelles Profil und Gerätegesegmentierung {#current-device-profile-options}

**[!UICONTROL Device Profile]** ist die Standardoption für das Profil des Geräts für eine  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] Sie können ein Profil aus einem Segment entfernen, wenn Sie die  [!UICONTROL Profile Merge Rule] Option  **[!UICONTROL Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Segmentierung, wenn:

* Das Profil des Geräts ist seit 120 Tagen inaktiv. Bei einer wöchentlichen Datenbereinigung werden inaktive Profil aus Ihren Segmenten entfernt.
* Das Gerät kann nicht mehr für ein Segment zugelassen werden, da es durch Updates oder Änderungen am Profil des Geräts nicht mehr qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern, oder Sie wenden einen [!DNL AND NOT]-Operator auf eine Segmentregel an oder geben [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md)-Bedingungen an, die die Einstellungen kleiner als/gleich verwenden. Anwendungsfälle werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![device-only](assets/device-only.png)

## Keine Geräteoption und keine Gerätesegmentierung {#no-device-option}

[!DNL Audience Manager] Sie können eine geräteübergreifende ID aus einem Segment entfernen, wenn Sie die  [!UICONTROL Profile Merge Rule] +- **[!UICONTROL Current Authenticated Profiles]** Option  **[!UICONTROL No Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Segmentierung, wenn die geräteübergreifende ID nicht mehr für ein Segment qualifiziert ist, da Updates oder Änderungen am geräteübergreifenden Profil es nicht mehr qualifizieren. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern, oder Sie wenden einen [!UICONTROL AND NOT]-Operator auf eine Segmentregel an oder geben [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md)-Bedingungen an, die die Einstellungen kleiner als/gleich verwenden. Anwendungsfälle werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![](assets/current-no-device.png)

## Gerätediagrammoptionen und Gerätesegmentierung {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Sie können mehrere Gerätegruppen aus einem Profil entfernen, wenn Sie eine Gerätediagrammoption  [!UICONTROL Profile Merge Rule] verwenden. Die Segmentierung wird aufgehoben, wenn das zusammengeführte Profil des Geräts aus dem Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Updates oder Änderungen an diesem zusammengeführten Profil es aus dem Segment ausschließen. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern, oder Sie wenden einen [!UICONTROL AND NOT]-Operator auf eine Segmentregel an oder geben [Neuigkeit und Häufigkeit](../segments/recency-and-frequency.md)-Bedingungen an, die die Einstellungen kleiner als/gleich verwenden. Anwendungsfälle werden in der Dokumentation [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md) beschrieben.

>[!NOTE]
>
>**100 Gerätebeschränkung für Segmentbewertung und -disqualifizierung**.
>Audience Manager führt bei der Segmentauswertung bis zu 100 Geräte mit einer Profil Merge Rule zusammen, die ein Gerätediagramm verwendet. Audience Manager bewertet das aktuelle Gerät und bis zu 99 Geräte, die mit dem aktuellen Gerät durch ein [authentifiziertes Profil](../../reference/visitor-authentication-states.md) (geräteübergreifende ID) verbunden sind. Wenn das Segmentsignal ausgegeben wird, werden das aktuelle Gerät und weitere Geräte aus dem Segment im Ziel entfernt.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md)

