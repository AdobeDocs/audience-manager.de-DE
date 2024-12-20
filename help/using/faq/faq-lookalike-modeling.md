---
description: Die Look-Alike-Modellierung hilft Ihnen durch automatisierte Datenanalyse, neue, einzigartige Zielgruppen zu entdecken. Dieser Artikel enthält Antworten auf die am häufigsten gestellten Fragen.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zur Look-Alike-Modellierung
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Häufig gestellte Fragen zur Look-Alike-Modellierung

## Überblick {#overview}

Dieser Artikel enthält Antworten auf die am häufigsten gestellten Fragen zu [!UICONTROL Look-Alike Modeling].

## Questions {#questions}

**Warum erhalte ich eine flache [!UICONTROL Accuracy & Reach]?**

Ein flaches [!UICONTROL Accuracy & Reach] bedeutet, dass fast alle Benutzenden vom Modell die gleiche Bewertung erhalten haben. Dies kann vorkommen, wenn Sie die Site-Besuchereigenschaft in die Datenquellen einbeziehen, auf denen Sie das Modell ausgeführt haben. Um dies zu vermeiden, entfernen Sie das generische Merkmal während des Schritts der Modellerstellung aus der Modelleingabe, indem Sie das Feld [!UICONTROL Exclusions] verwenden.

 

**Warum haben einige meiner einflussreichsten Eigenschaften ein sehr kleines Publikum?**

Der Algorithmus wählt Eigenschaften aus, die stark mit der Grundeigenschaft korreliert sind. Wenn eine bestimmte Eigenschaft beispielsweise 100 % mit der Grundlinie-Eigenschaft überschneidet, hat sie eine sehr hohe Gewichtung, auch wenn die Anzahl der Benutzerinnen und Benutzer in dieser Eigenschaft klein ist.

 

**Warum wurde mein Modell nicht ausgeführt/erneut ausgeführt?**

Modelle, die Ergebnisse erzeugt haben, werden nur dann weiter ausgeführt, wenn Sie mindestens ein aktives algorithmisches Merkmal erstellt und einem aktiven Segment und einem Ziel zugeordnet haben.

 

**Warum hat mein Modell keine Ergebnisse hervorgebracht?**

Dies ist in der Regel darauf zurückzuführen, dass es keine signifikanten Eigenschaftsüberschneidungen zwischen der Grundlinienpopulation und der Population in den ausgewählten Datenquellen gibt.

 

**Gibt es eine Empfehlung zur grundlegenden Eigenschaft oder Segmentgröße?**

Einige Tausend Benutzer sollten ausreichend sein, um das Modell unter auszuführen, da es eine erhebliche Eigenschaftsüberschneidung zwischen der Grundlinienpopulation und der Population in den ausgewählten Datenquellen gibt. [!UICONTROL Look-Alike Modeling] genauere Ergebnisse liefert, ist die Grundlinie umso größer.

 

**Welche Datenquellen von Drittanbietern sollte ich für mein Modell auswählen?**

Verwenden Sie Datenquellen, die sich mindestens teilweise mit Ihrer grundlegenden Eigenschaft/Ihrem Segment überschneiden, aber gleichzeitig zusätzliche Benutzer bzw. Benutzerinnen einbringen. Sie sollten auch die mit jedem Daten-Feed verbundenen Kosten berücksichtigen. Kosten- und Preismodelle variieren je nach Datenanbieter in [!UICONTROL Audience Marketplace].

 

**Kostet die Verwendung von Drittanbieterdaten für die Modellierung?**

Dies hängt vom Preismodell des ausgewählten Daten-Feeds ab. Einige Feeds ermöglichen die Modellierung ohne Kosten, während andere eine Gebühr berechnen. Weitere [ finden Sie unter „Abrechnung für Daten](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)Feed-Käufer“.

 

**Wie viele Modelle/Eigenschaften darf ich erstellen?**

Derzeit können Sie bis zu 20 algorithmische Modelle und 50 algorithmische Eigenschaften erstellen.

 

**Wie häufig werden die Modelle trainiert und die algorithmische Eigenschaftenpopulation aktualisiert?**

Das Modell trainiert einmal alle 8 Tage neu und aktualisiert dabei die algorithmische Eigenschaftspopulation.
