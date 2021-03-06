---
description: Beschreibt die Schwankungen der Summen Unique Users zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum.
seo-description: Beschreibt die Schwankungen der Summen Unique Users zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum in Adobe Audience Manager
seo-title: Zählen von Unique Users in Überlagerungen und allgemeinen Berichten in AAM
solution: Audience Manager
title: Zählen von Unique Users in Überlagerungen und allgemeinen Berichten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Berichtsreferenz
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Zählen von Unique Users in Überlagerungen und allgemeinen Berichten{#counting-unique-users-in-overlap-and-general-reports}

Auf dieser Seite wird beschrieben, wie sich die Summen der Unique Users zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum unterscheiden.

<!-- 

c_unique_user_counts.xml

 -->

## Überlagerungsbericht: Unique User Count

Die Überschneidungsberichte zählen Benutzer als eindeutig, wenn sie sich für eine Eigenschaft qualifizieren:

* Während des ausgewählten Zeitintervalls für den Bericht.
* Der Wert [Time-to-Live](../features/traits/segment-ttl-explained.md) ist länger als das ausgewählte Zeitintervall für den Bericht.
* Wenn sie in unserem System als aktiv angesehen werden (d. h. für eine andere Eigenschaft qualifiziert, eine ID-Synchronisierung aufweist usw.) innerhalb der letzten 60 Tage.

## Allgemeiner Bericht: Unique User Count

Der Bericht &quot;Allgemein&quot;zählt Sitebesucher als eindeutig, wenn sie sich im ausgewählten Zeitraum für die Eigenschaft qualifiziert haben.

>[!MORELIKETHIS]
>
>* [Interaktive Berichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
* [Allgemeine Berichte](../reporting/general-reports.md#general-reports-overview)

