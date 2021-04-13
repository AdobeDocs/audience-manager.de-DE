---
description: Recommendations und Anwendungsfälle für Segmentneuerung und personalisierte Segmentqualifizierung mit dem Profil Link-Gerätediagramm.
seo-description: Recommendations und Anwendungsfälle für Segmentneuerung und personalisierte Segmentqualifizierung mit dem Profil Link-Gerätediagramm.
seo-title: Anwendungsfälle für das Profil-Link-Gerätediagramm
solution: Audience Manager
title: Anwendungsfälle für das Profil-Link-Gerätediagramm
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profil-Zusammenführung
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# Anwendungsfälle für das Profil-Link-Gerätediagramm {#profile-link-device-graph-use-cases}

Recommendations und Anwendungsfälle für Segment-Remotings und personalisierte Segmentqualifizierung mit dem [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Betrachten Sie das Gerätediagramm [!UICONTROL Profile Link] für Kampagnen, die:

* Sie haben eine hochwertige Authentifizierung über ihre digitalen Eigenschaften hinweg. Verwenden Sie eine [externe Gerätediagrammoption](merge-rule-definitions.md#device-options), wenn Sie eine geringe Anzahl authentifizierter Benutzer haben.
* Genaues Targeting bekannter Audiencen erforderlich. Das [!UICONTROL Profile Link Device Graph] wird mit authentifizierten Erstanbieterdaten erstellt.
* Zielgruppe bekannter Audiencen über ihren authentifizierten und nicht authentifizierten Status in Echtzeit.

![](assets/merge-rule-triangle2.png)

## Geräteübergreifendes Targeting {#cross-device-personalization}

Nehmen wir an, John besitzt drei Geräte, die er regelmäßig benutzt, um nach Pauschalangeboten zu suchen: sein Laptop ([!DNL Device 1]), sein Smartphone ([!DNL Device 2]) und sein Tablet ([!DNL Device 3]). John verwendet seine Geräte jedoch, um nach verschiedenen Artikeln der Paketangebote zu suchen:

* Er nutzt seinen Laptop, um nach Flügen zu suchen.
* Er verwendet sein Smartphone, um nach Hotels zu suchen.
* Er benutzt sein Tablet, um Führungen zu suchen.

Auch wenn John nicht auf allen drei oben genannten Geräten authentifiziert ist, kann ein Anbieter von Pauschalreisen diese Geräte mit John&#39;s authentifiziertem Profil verknüpfen, vorausgesetzt, er war der Letzte, der sich auf allen drei Geräten authentifiziert hat.**[!UICONTROL Last Authenticated Profiles]****[!UICONTROL Profile Link Device Graph]**

![last-device-graph](assets/last-device-graph.png)

Da Audience Manager jedes Profil qualifiziert, das an der Segmentzusammenführung teilgenommen hat, werden alle drei Profil segmentiert. Das [!UICONTROL Profile Link Device Graph] ermöglicht es Audience Managern, das Verhalten auf allen drei Geräten zu überprüfen und jedes Gerät für ein Segment zu qualifizieren, für das kein einzelnes Profil allein qualifiziert ist.

Mit diesem [!UICONTROL Profile Merge Rule] können Marketingexperten ein konsistentes Erlebnis für alle Geräte bereitstellen, die einer Person gehören, basierend auf der Aktivität des Benutzers und nicht auf der Aktivität des jeweiligen Geräts.

![geräteübergreifende Personalisierung](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md)
>* [Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien](merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Profil-Zusammenführungsregeln](../../faq/faq-profile-merge.md)

