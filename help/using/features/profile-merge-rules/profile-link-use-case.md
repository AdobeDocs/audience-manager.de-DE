---
description: Empfehlungen und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem Profil Link-Gerätediagramm.
seo-description: Empfehlungen und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem Profil Link-Gerätediagramm.
seo-title: Anwendungsfälle für Profil Link Device Graph
solution: Audience Manager
title: Anwendungsfälle für Profil Link Device Graph
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---


# Anwendungsfälle für Profil Link Device Graph {#profile-link-device-graph-use-cases}

Empfehlungen und Anwendungsfälle für Segment-Retargeting und personalisierte Segmentqualifizierung mit der [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Betrachten Sie das [!UICONTROL Profile Link] Gerätediagramm für Kampagnen, die:

* Sie haben eine hochwertige Authentifizierung über ihre digitalen Eigenschaften hinweg. Verwenden Sie eine [externe Gerätediagrammoption](merge-rule-definitions.md#device-options) , wenn Sie nur über eine geringe Anzahl authentifizierter Benutzer verfügen.
* Genaues Targeting bekannter Audiencen erforderlich. Die [!UICONTROL Profile Link Device Graph] Daten werden mit authentifizierten Erstanbieterdaten erstellt.
* Target bekannte Audiencen über ihren authentifizierten und nicht authentifizierten Status in Echtzeit.

![](assets/merge-rule-triangle2.png)

## Geräteübergreifendes Targeting {#cross-device-personalization}

Nehmen wir an, John besitzt drei Geräte, die er regelmäßig benutzt, um nach Pauschalangeboten zu suchen: sein Laptop ([!DNL Device 1]), sein Smartphone ([!DNL Device 2]) und sein Tablet ([!DNL Device 3]). John verwendet seine Geräte jedoch, um nach verschiedenen Artikeln der Paketangebote zu suchen:

* Er nutzt seinen Laptop, um nach Flügen zu suchen.
* Er verwendet sein Smartphone, um nach Hotels zu suchen.
* Er benutzt sein Tablet, um Führungen zu suchen.

Selbst wenn John nicht auf allen drei oben genannten Geräten authentifiziert ist, kann ein Anbieter von Pauschalreisen diese Geräte mit dem authentifizierten Profil von John verknüpfen, wobei er davon ausgeht, dass er der letzte war, der sich auf allen drei Geräten authentifiziert hat. Dies geschieht mit der Regel **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** .

![last-device-graph](assets/last-device-graph.png)

Da Audience Manager jedes Profil qualifiziert, das an der Segmentzusammenführung teilgenommen hat, werden alle drei Profil segmentiert. Mit dem [!UICONTROL Profile Link Device Graph] können Audience Manager das Verhalten auf allen drei Geräten überprüfen und jedes Gerät für ein Segment qualifizieren, für das kein einzelnes Profil qualifiziert ist.

Dadurch [!UICONTROL Profile Merge Rule] können Marketingexperten allen Geräten, die einer Person gehören, ein einheitliches Erlebnis bieten, basierend auf der Aktivität des Benutzers und nicht auf der Aktivität des jeweiligen Geräts.

![geräteübergreifende Personalisierung](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Anwendungsbeispiele für Diagramme externer Geräte](external-graph-use-cases.md)
>* [Allgemeine Anwendungsfälle für Profil-Zusammenführungsregeln](merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Profil-Zusammenführungsregeln](../../faq/faq-profile-merge.md)

