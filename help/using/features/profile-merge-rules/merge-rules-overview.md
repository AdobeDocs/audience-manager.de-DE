---
description: Mit Profil Merge Rules erhalten Sie die Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Zielgruppe auf mehreren Geräten durchführen.
seo-description: Mit Profil Merge Rules erhalten Sie die Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Zielgruppe auf mehreren Geräten durchführen.
seo-title: Profilzusammenführungsrichtlinien – Überblick
solution: Audience Manager
title: Profilzusammenführungsrichtlinien – Überblick
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profil-Zusammenführung
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] Überblick {#profile-merge-rules-overview}

Mit [!UICONTROL Profile Merge Rules] können Sie steuern, welche Datensätze für die Segmentierung verwendet werden, und Benutzer auf mehreren Geräten genau Zielgruppe werden.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Datenerfassung und Targeting mit anonymen und authentifizierten Profilen {#data-collection-targeting}

Normalerweise basieren die Segmentierung und das Targeting von Audiencen auf Daten, die von allen Benutzern auf einem Gerät erfasst werden. Die Datenerfassung und das Targeting auf der Grundlage von Daten auf Geräteebene haben einige Nachteile. Beispielsweise können Sie nicht zwischen mehreren Benutzern unterscheiden, die ein Gerät gemeinsam verwenden, oder Benutzer, die auf mehreren Geräten genau Zielgruppe haben. Die gerätezentrierte Datenerfassung reicht nicht mehr für Kampagnen des digitalen Marketings oder geräteübergreifendes Targeting aus.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] Die Art und Weise, wie Daten und Segmente für Benutzer zum Targeting  [!DNL Audience Manager] erfasst werden, wird grundlegend geändert. Damit können Sie mit zwei verschiedenen Typen von Profilen arbeiten: einem Gerätemodell und einem [authentifizierten Profil](../../reference/visitor-authentication-states.md).

| Profil | Beschreibung |
|---|---|
| [!UICONTROL Device Profile] | Ein [!UICONTROL device profile] ist an eine ID für ein bestimmtes Gerät wie eine [!UICONTROL cookie]-ID oder eine Mobilgerät-ID gebunden.<br><br> Zu diesem Dienst gehören:<ul><li>[!UICONTROL Rule-based traits] realisiert, wenn ein Benutzer nicht authentifiziert ist.</li><li>[!UICONTROL Onboarded traits] an eine Geräte-ID gebunden, z. B.  [!UICONTROL cookie-based]an Daten von Drittanbietern.</li></ul> |
| [!UICONTROL Authenticated Profile] | Das [!UICONTROL authenticated profile] ist an eine Benutzer-ID gebunden, die weitergegeben wird, wenn sich eine Person bei Ihrer Site anmeldet.<br><br>Zu diesem Dienst gehören:<ul><li>[!UICONTROL Rule-based traits] über Geräte hinweg erfasst werden, wenn ein Benutzer authentifiziert wird.</li><li>[!UICONTROL Onboarded traits] in einer Offlinedatei, die mit derselben Benutzer-ID verknüpft ist.</li></ul> |

Diese verschiedenen Profil steuern die Daten, die Sie für die Segmentierung verwenden können. Beispielsweise können Sie mit einem [authentifizierten Profil](../../reference/visitor-authentication-states.md) genaue [!UICONTROL segments]-Daten aus mehreren Geräten für einen einzelnen Benutzer erstellen. Dies bedeutet, dass Sie Kunden auf mehreren Geräten eine einheitliche Markendarstellung bieten können. [!DNL Audience Manager] Dies wird erreicht, indem die Zuordnung der verschiedenen Geräte, die eine Person für ihre Online-Aktivitäten verwendet, zu ihrem  [authentifizierten Profil](../../reference/visitor-authentication-states.md) gespeichert wird. Diese Zuordnungen werden als [!UICONTROL Profile Link Device Graph] bezeichnet.

![](assets/authenticated2.png)

## Vorteile {#advantages}

Mit [!UICONTROL Profile Merge Rules] können Sie:

* Zielgruppen-Benutzer, die auf [authentifiziertem Profil](../../reference/visitor-authentication-states.md), anonymen Profilen oder Kombinationen aus beiden basieren.
* Zielgruppe eines bestimmten Kunden auf allen Geräten.
* Erstellen Sie ein Gerätediagramm basierend auf deterministischen Daten.
* Feinabstimmung der Daten in Ihrem [!UICONTROL segments] auf Grundlage verschiedener Profil.
* Erhalten Sie weitere Einblicke in Ihre Audience.
