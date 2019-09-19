---
description: Beschreibt die Schwankungen der Summen individueller Benutzer zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum.
seo-description: Beschreibt die Schwankungen der Summen individueller Benutzer zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum in Adobe Audience Manager
seo-title: Zählung individueller Benutzer in Überschneidungen und allgemeinen Berichten in AAM
solution: Audience Manager
title: Zählung individueller Benutzer in Überschneidungen und allgemeinen Berichten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Zählung individueller Benutzer in Überschneidungen und allgemeinen Berichten{#counting-unique-users-in-overlap-and-general-reports}

Diese Seite beschreibt die Schwankungen der Summen individueller Benutzer zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum.

<!-- 

c_unique_user_counts.xml

 -->

## Überschneidungsbericht: Individuelle Benutzeranzahl

Die Überschneidungsberichte zählen Benutzer als eindeutig, wenn sie sich für eine Eigenschaft qualifizieren:

* Im ausgewählten Zeitintervall für den Bericht.
* Dieser Wert hat einen [Time-to-Live](../features/traits/segment-ttl-explained.md) -Wert, der länger ist als das ausgewählte Zeitintervall für den Bericht.
* Wenn sie in unserem System als aktiv angesehen werden (d.h. für eine andere Eigenschaft qualifiziert, über eine ID-Synchronisierung usw.) innerhalb der letzten 60 Tage.

## Allgemeiner Bericht: Individuelle Benutzeranzahl

Der Bericht "Allgemein"zählt Sitebesucher als eindeutig, wenn sie sich im ausgewählten Zeitraum für die Eigenschaft qualifiziert haben.

>[!MORE_LIKE_THIS]
>
>* [Interaktive Berichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Allgemeine Berichte](../reporting/general-reports.md#general-reports-overview)

