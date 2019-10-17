---
description: Die Segmentierung beschreibt Prozesse, die Geräteprofile deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Regel zur Profilzusammenführung verwendet wird.
seo-description: Die Segmentierung beschreibt Prozesse, die Geräteprofile deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, die zum Erstellen einer Regel zur Profilzusammenführung verwendet wird.
seo-title: Regeln zur Profilzusammenführung und Prozesse zur Aufhebung der Segmentierung des Geräts
solution: Audience Manager
title: Regeln zur Profilzusammenführung und Prozesse zur Aufhebung der Segmentierung des Geräts
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: 54ae5956a34c193d42d4ff9a231249d56cce87aa

---


# Regeln zur Profilzusammenführung und Prozesse zur Aufhebung der Segmentierung des Geräts {#profile-merge-rules-and-device-un-segmentation-processes}

Die Segmentierung beschreibt Prozesse, die Geräteprofile deaktivieren und aus Segmenten entfernen. Ihre Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, mit der ein [!UICONTROL Profile Merge Rule]Gerät erstellt wurde.

## Verfügbare Geräteoptionen {#device-options}

Zur Erinnerung: Die [!UICONTROL Device Options] sind im Abschnitt verfügbar, wenn Sie eine [!UICONTROL Profile Merge Rules Setup] Datei erstellen oder bearbeiten [!UICONTROL Profile Merge Rule].

## Option "Aktuelles Geräteprofil"und "Geräteaufschlüsselung" {#current-device-profile-options}

**[!UICONTROL Device Profile]** ist die standardmäßige Geräteprofiloption für ein [!UICONTROL Profile Merge Rule]Gerät. [!DNL Audience Manager] Sie können ein Geräteprofil aus einem Segment entfernen, wenn Sie die [!UICONTROL Profile Merge Rule]**[!UICONTROL Device Profile]Option** verwenden. Unter diesen Bedingungen erfolgt die Segmentierung, wenn:

* Das Geräteprofil ist seit 120 Tagen inaktiv. Bei einer wöchentlichen Datenbereinigung werden inaktive Geräteprofile aus Ihren Segmenten entfernt.
* Das Gerät qualifiziert sich nicht mehr für ein Segment, da es durch Aktualisierungen oder Änderungen am Geräteprofil nicht qualifiziert wird. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern oder Sie einen [!DNL AND NOT] Operator auf eine Segmentregel anwenden oder [Neuigkeits- und Häufigkeitsbedingungen](../segments/recency-and-frequency.md) angeben, die die Einstellungen "kleiner als/gleich"verwenden. Anwendungsfälle werden in der Dokumentation zur [sofortigen geräteübergreifenden Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![device-only](assets/device-only.png)

## Keine Geräteoption und keine Geräteunterteilung {#no-device-option}

[!DNL Audience Manager] Sie können eine geräteübergreifende ID aus einem Segment entfernen, wenn Sie die [!UICONTROL Profile Merge Rule] Option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** verwenden. Unter diesen Bedingungen erfolgt die Aufhebung der Segmentierung, wenn die geräteübergreifende ID nicht mehr für ein Segment qualifiziert ist, da Updates oder Änderungen am geräteübergreifenden Profil das Segment nicht mehr qualifizieren. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern oder Sie einen [!UICONTROL AND NOT] Operator auf eine Segmentregel anwenden oder [Neuigkeits- und Häufigkeitsbedingungen](../segments/recency-and-frequency.md) angeben, die die Einstellungen "kleiner als/gleich"verwenden. Anwendungsfälle werden in der Dokumentation zur [sofortigen geräteübergreifenden Unterdrückung](instant-cross-device-suppression.md) beschrieben.

![](assets/current-no-device.png)

## Gerätediagrammoptionen und Gerätesegmentierung {#device-graph-options-unsegmentation}

[!DNL Audience Manager] können mehrere Geräteprofile aus einem Segment entfernen, wenn Sie eine Gerätediagrammoption [!UICONTROL Profile Merge Rule] verwenden. Die Segmentierung wird aufgehoben, wenn das zusammengeführte Profil des Geräts aus dem Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Updates oder Änderungen an diesem zusammengeführten Profil es aus dem Segment ausschließen. Dies geschieht, wenn sich die Segmentqualifizierungskriterien ändern oder Sie einen [!UICONTROL AND NOT] Operator auf eine Segmentregel anwenden oder [Neuigkeits- und Häufigkeitsbedingungen](../segments/recency-and-frequency.md) angeben, die die Einstellungen "kleiner als/gleich"verwenden. Anwendungsfälle werden in der Dokumentation zur [sofortigen geräteübergreifenden Unterdrückung](instant-cross-device-suppression.md) beschrieben.

>[!NOTE]
>
>**100 Gerätebeschränkung für Segmentbewertung und -disqualifizierung**.
>Audience Manager führt bis zu 100 Geräte zusammen, wenn Segmente mit einer Profilzusammenführungsregel ausgewertet werden, die ein Gerätediagramm verwendet. Audience Manager bewertet das aktuelle Gerät und bis zu 99 Geräte, die mit dem aktuellen Gerät über ein [authentifiziertes Profil](../../reference/visitor-authentication-states.md) (geräteübergreifende ID) verknüpft sind. Wenn das Segmentsignal ausgegeben wird, werden das aktuelle Gerät und weitere Geräte aus dem Segment im Ziel entfernt.

![](assets/last-device-graph.png)

>[!MORE_LIKE_THIS]
>
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung und zu Gerätediagrammen](../../faq/faq-profile-merge.md)
>* [Sofortige geräteübergreifende Unterdrückung](instant-cross-device-suppression.md)

