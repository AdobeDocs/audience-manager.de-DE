---
description: Mit Profilzusammenführungsregeln erhalten Sie die Kontrolle über die Datensätze, die für die Segmentierung verwendet werden, und können eine Person genau auf mehreren Geräten ansprechen.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Übersicht über Profilzusammenführungsregeln
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules] {#profile-merge-rules-overview}

Mit [!UICONTROL Profile Merge Rules] können Sie steuern, welche Datensätze für die Segmentierung verwendet werden, und Benutzer auf mehreren Geräten genau ansprechen.

>[!VIDEO](https://video.tv.adobe.com/v/32162?captions=ger)

## Datenerfassung und Zielgruppenbestimmung mit anonymen und authentifizierten Profilen {#data-collection-targeting}

In der Regel beruht die Segmentierung und Zielgruppenbestimmung von Audiences auf Daten, die von allen Benutzenden auf einem Gerät erfasst werden. Die Datenerfassung und Zielgruppenbestimmung auf der Grundlage von Daten auf Geräteebene hat einige Nachteile. Sie können beispielsweise nicht zwischen mehreren Benutzenden unterscheiden, die ein Gerät gemeinsam nutzen oder Benutzende auf mehreren Geräten präzise ansprechen. Die gerätezentrierte Datenerfassung ist für digitale Marketing-Kampagnen oder geräteübergreifendes Targeting nicht mehr ausreichend.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] ändert die Art und Weise, wie [!DNL Audience Manager] Daten und Segmente für Benutzende für die Zielgruppenbestimmung erfasst, grundlegend. Damit können Sie mit zwei verschiedenen Profiltypen arbeiten: einem Geräteprofil und einem [authentifizierten Profil](../../reference/visitor-authentication-states.md).

| Profiltyp | Beschreibung |
|---|---|
| [!UICONTROL Device Profile] | Eine [!UICONTROL device profile] ist an eine ID für ein bestimmtes Gerät gebunden, z. B. eine [!UICONTROL cookie]-ID oder eine ID für ein Mobilgerät.<br><br> Sie umfasst:<ul><li>[!UICONTROL Rule-based traits] erkannt, wenn ein Benutzer nicht authentifiziert ist.</li><li>[!UICONTROL Onboarded traits] mit einer Geräte-ID verknüpft, z. B. [!UICONTROL cookie-based], Daten von Drittanbietern.</li></ul> |
| [!UICONTROL Authenticated Profile] | Die [!UICONTROL authenticated profile] ist an eine Benutzer-ID gebunden, die übergeben wird, wenn sich eine Person bei Ihrer Site anmeldet.<br><br>Dazu gehören:<ul><li>[!UICONTROL Rule-based traits], die bei der Authentifizierung eines Benutzers auf allen Geräten erfasst werden.</li><li>[!UICONTROL Onboarded traits] in einer mit derselben Benutzer-ID verknüpften Offline-Datei.</li></ul> |

Diese verschiedenen Profile steuern die Daten, die Sie für die Segmentierung verwenden können. Mit einem [authentifizierten Profil](../../reference/visitor-authentication-states.md) können Sie beispielsweise für einen einzelnen Benutzer genaue [!UICONTROL segments] auf der Grundlage von Daten von mehreren Geräten erstellen. Dies bedeutet, dass Sie Kunden auf mehreren Geräten ein konsistentes Markenerlebnis bieten können. [!DNL Audience Manager] wird dies erreicht, indem die Zuordnung der verschiedenen Geräte, die eine Person für ihre Online-Aktivitäten verwendet, zu ihrem [authentifizierten Profil“ ](../../reference/visitor-authentication-states.md). Diese Zuordnungen werden als [!UICONTROL Profile Link Device Graph] bezeichnet.

![](assets/authenticated2.png)

## Vorteile {#advantages}

Mit [!UICONTROL Profile Merge Rules] können Sie:

* Targeting von Benutzern basierend [authentifiziertes Profil](../../reference/visitor-authentication-states.md) anonymen Profilen oder Kombinationen aus beiden.
* Targeting eines bestimmten Kunden auf seinen Geräten
* Erstellen Sie ein Gerätediagramm basierend auf deterministischen Daten.
* Passen Sie die Daten in Ihren [!UICONTROL segments] basierend auf verschiedenen Profilen an.
* Gewinnen Sie zusätzliche Einblicke in Ihre Audience.
