---
description: Mit Profilzusammenführungsrichtlinien erhalten Sie Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Person auf mehreren Geräten präzise ansprechen.
seo-description: Mit Profilzusammenführungsrichtlinien erhalten Sie Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Person auf mehreren Geräten präzise ansprechen.
seo-title: Profilzusammenführungsrichtlinien – Überblick
solution: Audience Manager
title: Profilzusammenführungsrichtlinien – Überblick
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profilzusammenführung
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] Überblick {#profile-merge-rules-overview}

Mit [!UICONTROL Profile Merge Rules] können Sie steuern, welche Datensätze für die Segmentierung verwendet werden, und Benutzer auf mehreren Geräten präzise ansprechen.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Datenerfassung und Zielgruppenbestimmung mit anonymen und authentifizierten Profilen {#data-collection-targeting}

Normalerweise beruht die Zielgruppensegmentierung und das Targeting auf Daten, die von allen Benutzern auf einem Gerät erfasst wurden. Die Datenerfassung und das Targeting auf der Grundlage von Daten auf Geräteebene hat einige Nachteile. Sie können beispielsweise nicht zwischen mehreren Benutzern unterscheiden, die ein Gerät gemeinsam nutzen oder Benutzer auf mehreren Geräten präzise ansprechen. Die gerätezentrierte Datenerfassung reicht nicht mehr für digitale Marketingkampagnen oder geräteübergreifendes Targeting aus.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] grundlegend ändert die Art und Weise, wie Daten und Segmente für das Targeting von Benutzern  [!DNL Audience Manager] erfasst werden. Damit können Sie mit zwei verschiedenen Profiltypen arbeiten: einem Geräteprofil und einem [authentifizierten Profil](../../reference/visitor-authentication-states.md).

| Profiltyp | Beschreibung |
|---|---|
| [!UICONTROL Device Profile] | Ein [!UICONTROL device profile] ist an eine ID für ein bestimmtes Gerät wie eine [!UICONTROL cookie]-ID oder eine Mobilgeräte-ID gebunden.<br><br> Zu diesem Dienst gehören:<ul><li>[!UICONTROL Rule-based traits] realisiert, wenn ein Benutzer nicht authentifiziert ist.</li><li>[!UICONTROL Onboarded traits] an eine Geräte-ID gebunden sind, z. B.  [!UICONTROL cookie-based], Drittanbieterdaten.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile] ist an eine Benutzer-ID gebunden, die übergeben wird, wenn sich eine Person bei Ihrer Site anmeldet.<br><br>Zu diesem Dienst gehören:<ul><li>[!UICONTROL Rule-based traits] über Geräte hinweg erfasst werden, wenn ein Benutzer authentifiziert wird.</li><li>[!UICONTROL Onboarded traits] in einer Offline-Datei, die mit derselben Benutzer-ID verknüpft ist.</li></ul> |

Diese unterschiedlichen Profile steuern die Daten, die Sie für die Segmentierung verwenden können. Mit einem [authentifizierten Profil](../../reference/visitor-authentication-states.md) können Sie beispielsweise für einen einzelnen Benutzer genaue [!UICONTROL segments] basierend auf Daten von mehreren Geräten erstellen. So können Sie Kunden auf mehreren Geräten ein konsistentes Markenerlebnis bieten. [!DNL Audience Manager] Dies wird erreicht, indem die Zuordnung der verschiedenen Geräte, die eine Person für ihre Online-Aktivitäten verwendet, zu ihrem  [authentifizierten Profil](../../reference/visitor-authentication-states.md) gespeichert wird. Diese Zuordnungen werden als [!UICONTROL Profile Link Device Graph] bezeichnet.

![](assets/authenticated2.png)

## Vorteile {#advantages}

Mit [!UICONTROL Profile Merge Rules] können Sie:

* Nutzer der Zielgruppe auf der Basis von [authentifiziertem Profil](../../reference/visitor-authentication-states.md), anonymen Profilen oder Kombinationen aus beiden Profilen auswählen.
* Targeting eines bestimmten Kunden auf allen seinen Geräten.
* Erstellen Sie ein Gerätediagramm basierend auf deterministischen Daten.
* Optimieren Sie die Daten in Ihrem [!UICONTROL segments] basierend auf verschiedenen Profilen.
* Hier erhalten Sie weitere Einblicke in Ihre Zielgruppe.
