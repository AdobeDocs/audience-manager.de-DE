---
description: Recommendations und Anwendungsfälle für das Segment-Retargeting und die personalisierte Segmentqualifikation mit dem Gerätediagramm „Profillink“.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Anwendungsfälle für Profilverknüpfungsgerätediagramme
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Anwendungsfälle für Profilverknüpfungsgerätediagramme {#profile-link-device-graph-use-cases}

Recommendations und Anwendungsfälle für das Segment-Retargeting und die personalisierte Segmentqualifikation mit dem [!UICONTROL Profile Link Device Graph].

## Empfehlungen {#recommendations}

Betrachten Sie das [!UICONTROL Profile Link] Gerätediagramm für Kampagnen, die:

* Verfügen über ein hohes Maß an Authentifizierung für ihre digitalen Eigenschaften. Verwenden Sie eine [Diagrammoption für externe Geräte](merge-rule-definitions.md#device-options) wenn nur wenige authentifizierte Benutzer vorhanden sind.
* Genaue Zielgruppenbestimmung bekannter Zielgruppen verlangen. Die [!UICONTROL Profile Link Device Graph] wird mit authentifizierten First-Party-Daten erstellt.
* Bekannte Zielgruppen in ihrem authentifizierten und nicht authentifizierten Status in Echtzeit ansprechen.

![](assets/merge-rule-triangle2.png)

## Geräteübergreifendes Targeting {#cross-device-personalization}

Angenommen, John besitzt drei Geräte, mit denen er regelmäßig nach Pauschalangeboten sucht: seinen Laptop ([!DNL Device 1]), sein Smartphone ([!DNL Device 2]) und sein Tablet ([!DNL Device 3]). John verwendet jedoch seine Geräte, um nach verschiedenen Elementen der Paketangebote zu suchen:

* Er benutzt seinen Laptop, um nach Flügen zu suchen;
* Er nutzt sein Smartphone, um Hotels zu suchen;
* Er nutzt sein Tablet, um Führungen zu suchen.

Selbst wenn John nicht auf allen drei der oben genannten Geräte authentifiziert wird, kann ein Anbieter von Ferienpaketen diese Geräte mithilfe der **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**-Regel mit Johns authentifiziertem Profil verknüpfen, unter der Annahme, dass er die letzte Person war, die sich auf allen drei Geräten authentifiziert hat.

![last-device-graph](assets/last-device-graph.png)

Da Audience Manager jedes Geräteprofil qualifiziert, das an der Profilzusammenführung für ein Segment teilgenommen hat, werden alle drei Geräteprofile segmentiert. Der [!UICONTROL Profile Link Device Graph] ermöglicht es Audience Managern, das Verhalten auf allen drei Geräten zu überprüfen und jedes Gerät für ein Segment zu qualifizieren, für das kein einzelnes Geräteprofil allein qualifiziert ist.

Diese [!UICONTROL Profile Merge Rule] ermöglicht es Marketing-Experten, allen Geräten, die einer Person gehören, ein konsistentes Erlebnis bereitzustellen, basierend auf der Benutzeraktivität und nicht auf der individuellen Geräteaktivität.

![Geräteübergreifende Personalisierung](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md)
>* [Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien](merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)
