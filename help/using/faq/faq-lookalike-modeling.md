---
description: Die Look-alike-Modellierung hilft Ihnen, durch automatisierte Datenanalyse neue, einzigartige Zielgruppen zu entdecken. Dieser Artikel enthält Antworten auf die am häufigsten gestellten Fragen.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zur Look-alike-Modellierung
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Häufig gestellte Fragen zur Look-alike-Modellierung

## Überblick {#overview}

Dieser Artikel enthält Antworten auf die am häufigsten gestellten Fragen zu [!UICONTROL Look-Alike Modeling].

## Fragen {#questions}

**Warum erhalte ich ein flaches [!UICONTROL Accuracy & Reach] Diagramm?**

Ein flaches [!UICONTROL Accuracy & Reach] Diagramm bedeutet, dass fast jeder Benutzer vom Modell denselben Wert erhalten hat. Dies kann vorkommen, wenn Sie die Site-Besuchereigenschaft in die Datenquellen einbeziehen, in denen Sie das Modell ausgeführt haben. Um dies zu vermeiden, entfernen Sie die generische Eigenschaft während des Modellerstellungsschritts mithilfe des Felds [!UICONTROL Exclusions] aus der Modelleingabe.

 

**Warum haben einige meiner einflussreichsten Eigenschaften sehr kleine Zielgruppen?**

Der Algorithmus wählt Eigenschaften aus, die in hohem Maße mit der Grundlinieneigenschaft korreliert sind. Wenn sich beispielsweise eine bestimmte Eigenschaft zu 100 % mit der Grundlinieneigenschaft überschneidet, hat sie eine sehr hohe Gewichtung, selbst wenn die Anzahl der Benutzer in dieser Eigenschaft gering ist.

 

**Warum wird mein Modell nicht ausgeführt/erneut ausgeführt?**

Modelle, die Ergebnisse generiert haben, werden nur dann weiterhin ausgeführt, wenn Sie mindestens eine aktive algorithmische Eigenschaft erstellt und sie einem aktiven Segment und einem Ziel zugeordnet haben.

 

**Warum hat mein Modell keine Ergebnisse generiert?**

Dies wird normalerweise dadurch verursacht, dass es keine signifikanten Eigenschaftenüberschneidungen zwischen der Grundgesamtheit und der Population in den ausgewählten Datenquellen gibt.

 

**Gibt es Empfehlungen für die Grundlinie der Eigenschaft oder Segmentgröße?**

Einige tausend Benutzer sollten ausreichend sein, um das Modell auszuführen, da es erhebliche Eigenschaftenüberschneidungen zwischen der Grundlinien-Population und der Population in den ausgewählten Datenquellen gibt. [!UICONTROL Look-Alike Modeling] liefert genauere Ergebnisse, je größer die Grundlinie ist.

 

**Welche Datenquellen von Drittanbietern sollte ich für mein Modell wählen?**

Verwenden Sie Datenquellen, die sich zumindest teilweise mit Ihrer Grundlinie überschneiden, aber gleichzeitig zusätzliche Benutzer bringen. Sie sollten auch die mit den einzelnen Daten-Feeds verbundenen Kosten berücksichtigen. Die Kosten- und Preismodelle variieren je nach Datenanbieter in [!UICONTROL Audience Marketplace].

 

**Kostet es die Verwendung von Drittanbieterdaten für die Modellierung?**

Dies hängt vom Preismodell des ausgewählten Daten-Feeds ab. Einige Feeds ermöglichen eine kostenlose Modellierung, während andere Ihnen eine Gebühr berechnen. Weitere Informationen finden Sie unter [Abrechnung für Daten-Feed-Käufer](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) .

 

**Wie viele Modelle/Eigenschaften darf ich erstellen?**

Derzeit können Sie bis zu 20 algorithmische Modelle und 50 algorithmische Eigenschaften erstellen.

 

**Wie oft dauert die Aktualisierung der Modellschulung und der algorithmischen Eigenschaftspopulation?**

Das Modell trainiert alle 8 Tage neu, zusammen mit der Aktualisierung der algorithmischen Eigenschaftspopulation.
