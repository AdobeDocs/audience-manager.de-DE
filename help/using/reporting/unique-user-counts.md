---
description: Beschreibt die Schwankungen der Summen individueller Benutzer zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum.
seo-description: Beschreibt die Schwankungen der Summen individueller Benutzer zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum in Adobe Audience Manager
seo-title: Zählung individueller Benutzer in Überschneidungen und allgemeinen Berichten in AAM
solution: Audience Manager
title: Zählen von Unique Users in Überlagerungen und allgemeinen Berichten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 10%

---


# Zählen von Unique Users in Überlagerungen und allgemeinen Berichten{#counting-unique-users-in-overlap-and-general-reports}

Diese Seite beschreibt die Schwankungen der Summen individueller Benutzer zwischen Berichten für dieselbe Eigenschaft und denselben Zeitraum.

<!-- 

c_unique_user_counts.xml

 -->

## Überschneidungsbericht: Individuelle Benutzeranzahl

Die Überschneidungsberichte zählen Benutzer als eindeutig, wenn sie sich für eine Eigenschaft qualifizieren:

* Im ausgewählten Zeitintervall für den Bericht.
* Dieser Wert ist länger als das ausgewählte Zeitintervall für den Bericht.[](../features/traits/segment-ttl-explained.md)
* Wenn sie in unserem System als aktiv angesehen werden (d.h. für eine andere Eigenschaft qualifiziert, über eine ID-Synchronisierung usw.) innerhalb der letzten 60 Tage.

## Allgemeiner Bericht: Individuelle Benutzeranzahl

Der Bericht &quot;Allgemein&quot;zählt Site-Besucher als eindeutig, wenn sie sich im ausgewählten Zeitraum für die Eigenschaft qualifiziert haben.

>[!MORELIKETHIS]
>
>* [Interaktive Berichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Allgemeine Berichte](../reporting/general-reports.md#general-reports-overview)

