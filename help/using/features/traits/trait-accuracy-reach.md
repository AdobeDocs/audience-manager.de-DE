---
description: Beschreibt die Beziehung zwischen Genauigkeit und Reichweite in algorithmischen Eigenschaften.
seo-description: Describes the relationship between accuracy and reach in algorithmic traits.
seo-title: Accuracy and Reach
solution: Audience Manager
title: Genauigkeit und Reichweite
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
TQID: https://experienceleague.adobe.com/EBd69CXQbzvMDT-VjZqeZ1Y30LtP4QdkWlmTcCmWax8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 0%

---

# Genauigkeit und Reichweite {#accuracy-and-reach}

Beschreibt die Beziehung zwischen Genauigkeit und Reichweite in algorithmischen Eigenschaften.

<!-- c_accuracy_reach.xml -->

## Genauigkeit vs. Reichweite: Über

Bei der Arbeit mit algorithmischen Eigenschaften ist es wichtig, die Beziehung zwischen Genauigkeit und Reichweite zu verstehen. Die Genauigkeit wird durch einen bewerteten Wert dargestellt, der widerspiegelt, wie ähnlich die Benutzerinnen und Benutzer Ihrer Grundlinie sind. Die Genauigkeitsskala reicht von 0 (am wenigsten genau) bis 1 (am genauesten). Reichweite ist einfach ein Wert, der die Anzahl der eindeutigen Benutzer angibt, die Sie in eine Eigenschaft aufnehmen möchten. Reichweite und Genauigkeit stehen in umgekehrter Beziehung zueinander. Präzise Eigenschaften erreichen weniger Benutzer und Eigenschaften mit größerer Reichweite sind weniger genau. Die folgende Abbildung veranschaulicht dieses Konzept.

![](assets/Reach_v_Accuracy.png)

## Genauigkeit und Reichweite beeinflussen die Zielgruppengröße

Ihre Geschäftsziele sollten Ihnen dabei helfen, bei der Arbeit mit algorithmischen Eigenschaften die richtigen Entscheidungen über Genauigkeit und Reichweite zu treffen. Wenn Genauigkeit Ihr Ziel ist, beachten Sie, dass die Population eines Merkmals über Modellausführungen hinweg zunehmen oder abnehmen kann. Populationsänderungen sind das Ergebnis des Algorithmus, der während jedes Auswertungszeitraums Entscheidungen trifft. Manchmal findet der Algorithmus während eines Verarbeitungszyklus mehr qualifizierte Benutzende, und in anderen Fällen weniger. Die Ergebnisse werden anhand der zum Erstellen des Modells verwendeten Basisdaten sowie der neuen Besucher und Eigenschaftsqualifikationen bestimmt, die seit der vorherigen Modellausführung verfügbar waren. Bei der Arbeit mit REACH dagegen bleibt die Anzahl der Benutzenden konstant. Wenn Sie beispielsweise 10.000 Benutzer erreichen möchten, stellt der Algorithmus sicher, dass er bei jeder Modellausführung immer diese Zahl erreicht.

## Allgemeine Anwendungsfälle für Genauigkeit vs. Reichweite

Der Fokus auf Genauigkeit oder Reichweite hängt davon ab, was Sie mit einem bestimmten Segment erreichen möchten. Die folgende Tabelle kann Ihnen dabei helfen, die Genauigkeit im Vergleich zur Reichweite beim Erstellen einer Eigenschaft zu bewerten.

| Merkmal-Entscheidung begünstigt | Hilft bei der Suche |
|---|---|
| **Genauigkeit** | Benutzende, die den Basiskunden in Ihrem Modell ähnlich sind. Nützlich für zielgerichtete Kampagnen, wenn Sie eine bestimmte Zielgruppe erreichen möchten. |
| **REACH** | Eine bestimmte Anzahl von Benutzern für jede Datenausführung. Nützlich für Markenkampagnen, wenn Sie eine Zielgruppe einer bestimmten Größe erreichen möchten. |
