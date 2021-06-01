---
description: Recommendations und Anwendungsfälle für Segment-Retargeting und die Qualifizierung personalisierter Segmente mit dem Gerätediagramm für Profillink.
seo-description: Recommendations und Anwendungsfälle für Segment-Retargeting und die Qualifizierung personalisierter Segmente mit dem Gerätediagramm für Profillink.
seo-title: Anwendungsfälle für das Profil-Link-Gerätediagramm
solution: Audience Manager
title: Anwendungsfälle für das Profil-Link-Gerätediagramm
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profilzusammenführung
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# Anwendungsfälle für das Profil-Link-Gerätediagramm {#profile-link-device-graph-use-cases}

Recommendations und Anwendungsfälle für Segment-Retargeting und die Qualifizierung personalisierter Segmente mit dem [!UICONTROL Profile Link Device Graph].

## Empfehlungen {#recommendations}

Beachten Sie das Gerätediagramm [!UICONTROL Profile Link] für Kampagnen, die:

* Sie haben eine allgemeine Authentifizierung für alle digitalen Eigenschaften. Verwenden Sie eine [externe Gerätediagrammoption](merge-rule-definitions.md#device-options), wenn Sie eine geringe Anzahl authentifizierter Benutzer haben.
* Sorgfältiges Targeting bekannter Zielgruppen erforderlich. [!UICONTROL Profile Link Device Graph] wird mithilfe authentifizierter Erstanbieter-Daten erstellt.
* Richten Sie bekannte Zielgruppen in Echtzeit auf ihre authentifizierten und nicht authentifizierten Status aus.

![](assets/merge-rule-triangle2.png)

## Geräteübergreifendes Targeting {#cross-device-personalization}

Angenommen, John besitzt drei Geräte, die er regelmäßig verwendet, um nach Weihnachtspaketangeboten zu suchen: sein Laptop ([!DNL Device 1]), sein Smartphone ([!DNL Device 2]) und sein Tablet ([!DNL Device 3]). John verwendet jedoch seine Geräte, um nach verschiedenen Elementen der Paketangebote zu suchen:

* Er benutzt seinen Laptop, um nach Flügen zu suchen.
* Er benutzt sein Smartphone, um nach Hotels zu suchen.
* Er benutzt sein Tablet, um nach Führungen zu suchen.

Selbst wenn John nicht auf allen drei oben genannten Geräten authentifiziert ist, kann ein Urlaubspaketanbieter diese Geräte mithilfe der Regel **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** mit dem authentifizierten Profil von John verknüpfen, sofern er der Letzte war, der sich auf allen drei Geräten authentifiziert hat.

![last-device-graph](assets/last-device-graph.png)

Da Audience Manager jedes Geräteprofil qualifiziert, das an der Profilzusammenführung für ein Segment teilgenommen hat, werden alle drei Geräteprofile segmentiert. Der [!UICONTROL Profile Link Device Graph] ermöglicht es dem Audience Manager, das Verhalten auf allen drei Geräten zu untersuchen und jedes Gerät für ein Segment zu qualifizieren, für das kein Geräteprofil allein qualifiziert ist.

Diese [!UICONTROL Profile Merge Rule] ermöglicht es Marketing-Experten, allen Geräten einer Person ein konsistentes Erlebnis bereitzustellen, basierend auf der Benutzeraktivität anstelle der einzelnen Geräteaktivität.

![geräteübergreifende Personalisierung](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md)
* [Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien](merge-rule-targeting-options.md)
* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)

