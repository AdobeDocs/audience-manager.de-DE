---
description: Beschreibt die Variation der Gesamtwerte für Unique User zwischen Berichten für dasselbe Merkmal und denselben Zeitraum.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Zählen von eindeutigen Benutzern in Überschneidungs- und allgemeinen Berichten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# Zählen von eindeutigen Benutzern in Überschneidungs- und allgemeinen Berichten{#counting-unique-users-in-overlap-and-general-reports}

Auf dieser Seite werden die Unterschiede in den Summen der Unique User zwischen Berichten für dasselbe Merkmal und denselben Zeitraum beschrieben.

<!-- 

c_unique_user_counts.xml

 -->

## Überschneidungsbericht: Anzahl der eindeutigen Benutzer

Die Überschneidungsberichte zählen Benutzer als eindeutig, wenn sie für eine Eigenschaft qualifiziert sind:

* Während des für den Bericht ausgewählten Zeitintervalls.
* Der Wert [Time-to-Live](../features/traits/segment-ttl-explained.md) ist länger als das ausgewählte Zeitintervall für den Bericht.
* Wenn sie in den letzten 60 Tagen in unserem System als aktiv angesehen wurden (d. h. für eine andere Eigenschaft qualifiziert waren, eine ID-Synchronisierung hatten usw.).

## Allgemeiner Bericht: Anzahl der eindeutigen Benutzer

Der allgemeine Bericht zählt Besuchende der Site als eindeutig, wenn sie sich im ausgewählten Zeitraum für das Merkmal qualifiziert haben.

>[!MORELIKETHIS]
>
>* [Interaktive Berichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Allgemeine Berichte](../reporting/general-reports.md#general-reports-overview)
