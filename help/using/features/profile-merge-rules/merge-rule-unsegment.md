---
description: Die Segmentierung beschreibt Prozesse, die Geräte-Profil deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Profil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profil Merge Rule verwendet wird.
seo-description: Die Segmentierung beschreibt Prozesse, die Geräte-Profil deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Profil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Profil Merge Rule verwendet wird.
seo-title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
solution: Audience Manager
title: Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 6%

---


# Profilzusammenführungsrichtlinien und Prozesses zur Aufhebung der Gerätesegmentierung {#profile-merge-rules-and-device-un-segmentation-processes}

Die Segmentierung beschreibt Prozesse, die Geräte-Profil deaktivieren und aus Segmenten entfernen. Die Fähigkeit, ein Profil aus einem Segment zu entfernen, hängt von der Geräteoption ab, mit der ein Segment erstellt wurde [!UICONTROL Profile Merge Rule].

## Verfügbare Geräteoptionen {#device-options}

Zur Erinnerung: Die [!UICONTROL Device Options] sind im Abschnitt verfügbar, wenn Sie eine [!UICONTROL Profile Merge Rules Setup] Datei erstellen oder bearbeiten [!UICONTROL Profile Merge Rule].

## Option zum aktuellen Profil und Gerätesegmentierung {#current-device-profile-options}

**[!UICONTROL Device Profile]** ist die Standardoption für das Profil des Geräts für eine [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] Sie können ein Profil aus einem Segment entfernen, wenn Sie die [!UICONTROL Profile Merge Rule] Option **[!UICONTROL Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Segmentierung, wenn:

* Das Profil des Geräts ist seit 120 Tagen inaktiv. Bei einer wöchentlichen Datenbereinigung werden inaktive Profil aus Ihren Segmenten entfernt.
* Das Gerät kann nicht mehr für ein Segment zugelassen werden, da es durch Updates oder Änderungen am Profil des Geräts nicht mehr qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern oder Sie einen [!DNL AND NOT] Operator auf eine Segmentregel anwenden oder [Neuigkeits- und Häufigkeitsbedingungen](../segments/recency-and-frequency.md) angeben, die die Einstellungen &quot;kleiner als/gleich&quot;verwenden. Anwendungsfälle werden in der Dokumentation zur [sofortigen geräteübergreifenden Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![device-only](assets/device-only.png)

## Keine Geräteoption und keine Geräteunterteilung {#no-device-option}

[!DNL Audience Manager] Sie können eine geräteübergreifende ID aus einem Segment entfernen, wenn Sie die [!UICONTROL Profile Merge Rule] Option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Segmentierung, wenn die geräteübergreifende ID nicht mehr für ein Segment qualifiziert ist, da Updates oder Änderungen am geräteübergreifenden Profil es nicht mehr qualifizieren. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern oder Sie einen [!UICONTROL AND NOT] Operator auf eine Segmentregel anwenden oder [Neuigkeits- und Häufigkeitsbedingungen](../segments/recency-and-frequency.md) angeben, die die Einstellungen &quot;kleiner als/gleich&quot;verwenden. Anwendungsfälle werden in der Dokumentation zur [sofortigen geräteübergreifenden Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![](assets/current-no-device.png)

## Gerätediagrammoptionen und Gerätesegmentierung {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Sie können mehrere Gerätegruppen aus einem Profil entfernen, wenn Sie eine Gerätediagrammoption [!UICONTROL Profile Merge Rule] verwenden. Die Segmentierung wird aufgehoben, wenn das zusammengeführte Profil des Geräts aus dem Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Updates oder Änderungen an diesem zusammengeführten Profil es aus dem Segment ausschließen. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern oder Sie einen [!UICONTROL AND NOT] Operator auf eine Segmentregel anwenden oder [Neuigkeits- und Häufigkeitsbedingungen](../segments/recency-and-frequency.md) angeben, die die Einstellungen &quot;kleiner als/gleich&quot;verwenden. Anwendungsfälle werden in der Dokumentation zur [sofortigen geräteübergreifenden Unterdrückung](instant-cross-device-suppression.md) beschrieben.

>[!NOTE]
>
>**100 Gerätebeschränkung für Segmentbewertung und -disqualifizierung**.
>Audience Manager führt bei der Segmentauswertung bis zu 100 Geräte mit einer Profil Merge Rule zusammen, die ein Gerätediagramm verwendet. Audience Manager bewertet das aktuelle Gerät und bis zu 99 Geräte, die mit einem [authentifizierten Profil](../../reference/visitor-authentication-states.md) (geräteübergreifende ID) mit dem aktuellen Gerät verbunden sind. Wenn das Segmentsignal ausgegeben wird, werden das aktuelle Gerät und weitere Geräte aus dem Segment im Ziel entfernt.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md)

