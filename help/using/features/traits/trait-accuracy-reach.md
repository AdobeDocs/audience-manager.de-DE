---
description: Beschreibt die Beziehung zwischen Genauigkeit und Reichweite in algorithmischen Eigenschaften.
seo-description: Beschreibt die Beziehung zwischen Genauigkeit und Reichweite in algorithmischen Eigenschaften.
seo-title: Genauigkeit und Reichweite
solution: Audience Manager
title: Genauigkeit und Reichweite
uuid: d121e099-6642-4003-ad4f-507d21e478d8
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Genauigkeit und Reichweite {#accuracy-and-reach}

Beschreibt die Beziehung zwischen Genauigkeit und Reichweite in algorithmischen Eigenschaften.

<!-- c_accuracy_reach.xml -->

## Genauigkeit vs. Reichweite: Info

Es ist wichtig, die Beziehung zwischen Genauigkeit und Reichweite bei der Arbeit mit algorithmischen Eigenschaften zu verstehen. Die Genauigkeit wird durch einen bewerteten Wert dargestellt, der angibt, wie ähnlich die Benutzer Ihrer Grundlinie sind. Die Genauigkeitsskala reicht von 0 (am wenigsten genau) bis 1 (am genauesten). Reichweite ist einfach ein Wert, der die Anzahl der Unique Users darstellt, die Sie in eine Eigenschaft einbeziehen möchten. Reichweite und Genauigkeit sind umgekehrt. Genauere Eigenschaften erreichen weniger Benutzer und Eigenschaften mit größerer Reichweite sind weniger genau. Die folgende Abbildung zeigt dieses Konzept.

![](assets/Reach_v_Accuracy.png)

## Genauigkeit und Reichweite beeinflussen die Zielgruppengröße

Ihre Geschäftsziele sollten Ihnen dabei helfen, bei der Arbeit mit algorithmischen Eigenschaften die richtigen Entscheidungen über Genauigkeit und Reichweite zu treffen. Wenn die Genauigkeit Ihr Ziel ist, beachten Sie, dass die Population eines Merkmals während der Ausführung eines Modells erhöht oder verringert werden kann. Bevölkerungsänderungen sind die Ergebnisse des Algorithmus, der während jedes Bewertungszeitraums Entscheidungen trifft. Manchmal findet der Algorithmus qualifiziertere Benutzer während eines Verarbeitungszyklus, während andere weniger Benutzer finden. Die Ergebnisse werden durch die Ausgangsdaten bestimmt, die zur Erstellung des Modells und der neuen Besucher sowie der Eigenschaftsqualifikationen verwendet werden, die seit der letzten Modellausführung aufgetreten sind. Bei der Arbeit mit Reichweite bleibt die Benutzeranzahl dagegen konstant. Wenn Sie z. B. 10.000 Benutzer erreichen möchten, stellt der Algorithmus sicher, dass er für jede Modellausführung immer diese Zahl erreicht.

## Allgemeine Anwendungsfälle für Genauigkeit oder Reichweite

Der Fokus auf Genauigkeit oder Reichweite hängt davon ab, was Sie mit einem bestimmten Segment erreichen möchten. Die folgende Tabelle kann Ihnen helfen, beim Erstellen einer Eigenschaft die Genauigkeit oder Reichweite zu bewerten.

| Favoriten für Eigenschaftsentscheidung | Hilft bei der Suche |
|---|---|
| **Genauigkeit** | Benutzer ähnlich wie Kunden mit Basisstatus in Ihrem Modell. Nützlich für zielgerichtete Kampagnen, wenn Sie eine bestimmte Zielgruppe erreichen möchten. |
| **Reichweite** | Eine bestimmte Anzahl von Benutzern für jede Datenausführung. Nützlich für Markenkampagnen, wenn Sie daran interessiert sind, eine bestimmte Zielgruppe zu erreichen. |