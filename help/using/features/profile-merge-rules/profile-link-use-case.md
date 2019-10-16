---
description: Empfehlungen und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem Profillink-Gerätediagramm.
seo-description: Empfehlungen und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem Profillink-Gerätediagramm.
seo-title: Anwendungsfälle des Profillink-Gerätediagramms
solution: Audience Manager
title: Anwendungsfälle des Profillink-Gerätediagramms
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Anwendungsfälle des Profillink-Gerätediagramms {#profile-link-device-graph-use-cases}

Empfehlungen und Anwendungsfälle für Segment-Retargeting und personalisierte Segmentqualifizierung mit der [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Betrachten Sie das [!UICONTROL Profile Link] Gerätediagramm für Kampagnen, die:

* Sie haben eine hochwertige Authentifizierung über ihre digitalen Eigenschaften hinweg. Verwenden Sie eine [externe Gerätediagrammoption](merge-rule-definitions.md#device-options) , wenn Sie nur über eine geringe Anzahl authentifizierter Benutzer verfügen.
* Genaues Targeting bekannter Zielgruppen erforderlich. Die [!UICONTROL Profile Link Device Graph] Daten werden mit authentifizierten Erstanbieterdaten erstellt.
* Targeting bekannter Zielgruppen über ihren authentifizierten und nicht authentifizierten Status in Echtzeit.

![](assets/merge-rule-triangle2.png)

## Geräteübergreifendes Targeting {#cross-device-personalization}

Nehmen wir an, John besitzt drei Geräte, die er regelmäßig benutzt, um nach Pauschalangeboten zu suchen: sein Laptop ([!DNL Device 1]), sein Smartphone ([!DNL Device 2]) und sein Tablet ([!DNL Device 3]). John verwendet seine Geräte jedoch, um nach verschiedenen Artikeln der Paketangebote zu suchen:

* Er benutzt seinen Laptop, um nach Flügen zu suchen.
* Er verwendet sein Smartphone, um nach Hotels zu suchen.
* Er benutzt sein Tablet, um Führungen zu suchen.

Selbst wenn John nicht auf allen drei oben genannten Geräten authentifiziert ist, kann ein Anbieter von Pauschalreisen mithilfe der **[!UICONTROL Last Authenticated Profiles]** +- **[!UICONTROL Profile Link Device Graph]** Regel diese Geräte mit John's authentifiziertem Profil verknüpfen, vorausgesetzt, er war der Letzte, der sich auf allen drei Geräten authentifiziert hat.

![last-device-graph](assets/last-device-graph.png)

Da Audience Manager jedes Geräteprofil qualifiziert, das an der Profilzusammenführung für ein Segment teilgenommen hat, werden alle drei Geräteprofile segmentiert. Mit [!UICONTROL Profile Link Device Graph] dieser Funktion kann Audience Manager das Verhalten auf allen drei Geräten prüfen und jedes Gerät für ein Segment qualifizieren, für das kein Geräteprofil allein geeignet ist.

Auf diese Weise [!UICONTROL Profile Merge Rule] können Marketingexperten allen Geräten, die einer Person gehören, ein einheitliches Erlebnis bieten, das auf der Benutzeraktivität und nicht auf der individuellen Geräteaktivität basiert.

![geräteübergreifende Personalisierung](assets/cross-device-personalization.png)

>[!MORE_LIKE_THIS]
>
>* [Anwendungsbeispiele für Diagramme externer Geräte](external-graph-use-cases.md)
>* [Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung](merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)

