---
description: Beschreibt die Variation in eindeutigen Benutzersummen zwischen Berichten für dieselben Eigenschaften und Zeiträume.
seo-description: Beschreibt die Variation in eindeutigen Benutzersummen zwischen Berichten für dieselben Eigenschaften und Zeiträume in Adobe Audience Manager
seo-title: Zählung individueller Benutzer in Überlappung und allgemeine Berichte in AAM
solution: Audience Manager
title: Zählung individueller Benutzer in Überlappung und allgemeine Berichte
uuid: 450 f 6 a 8 c-f 363-43 de-b 2 d 8-0 a 156 f 14 ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

Diese Seite beschreibt die Variation in eindeutigen Benutzersummen zwischen Berichten für dieselben Eigenschaften und Zeiträume.

<!-- 

c_unique_user_counts.xml

 -->

## Überlappungsbericht: Unique User Count

Die Überlappungsberichte zählen Benutzer als individuell, wenn sie für eine Eigenschaft qualifiziert sind:

* Während des ausgewählten Zeitintervalls für den Bericht.
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* Wenn sie in unserem System als aktiv angesehen werden (d. h. qualifiziert für jede andere Eigenschaft, hatten eine ID-Synchronisierung usw.) innerhalb der vergangenen 60 Tage.

## Allgemeiner Bericht: Unique User Count

Der allgemeine Bericht zählt Site-Besucher als eindeutig, wenn sie im ausgewählten Zeitraum für die Eigenschaft qualifiziert sind.

>[!MORE_ LIKE_ THIS]
>
>* [Interaktive Berichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Allgemeine Berichte](../reporting/general-reports.md#general-reports-overview)

