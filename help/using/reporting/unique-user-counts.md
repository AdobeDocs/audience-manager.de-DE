---
description: Beschreibt die Variation der Gesamtwerte für Unique User zwischen Berichten für dasselbe Merkmal und denselben Zeitraum.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Zählen von eindeutigen Benutzern in Überschneidungs- und allgemeinen Berichten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
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
