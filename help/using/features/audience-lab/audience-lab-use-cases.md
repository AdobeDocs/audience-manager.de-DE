---
description: Audience Lab ermöglicht mehrere Anwendungsfälle, indem Sie Ausgangssegmente zum Erstellen von Testgruppen verwenden können. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese unterschiedlichen Zielen zuordnen und dann feststellen, welche der Segmente am effektivsten zur Förderung von Konversionen beitragen.
seo-description: Audience Lab ermöglicht mehrere Anwendungsfälle, indem Sie Ausgangssegmente zum Erstellen von Testgruppen verwenden können. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese unterschiedlichen Zielen zuordnen und dann feststellen, welche der Segmente am effektivsten zur Förderung von Konversionen beitragen.
seo-title: 'Anwendungsfälle: Audience Lab'
solution: Audience Manager
title: 'Anwendungsfälle: Audience Lab'
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---


# Anwendungsfälle: Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] ermöglicht mehrere Anwendungsfälle, indem Sie Ausgangssegmente zum Erstellen von Testgruppen verwenden können. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese unterschiedlichen Zielen zuordnen und dann feststellen, welche der Segmente am effektivsten zur Förderung von Konversionen beitragen.

## Modelle in Audience Lab vergleichen {#compare-models}

Sie können verschiedene Typen und Quellen von Modellen in verwenden [!DNL Audience Manager]. [!UICONTROL Audience Lab] Angebot bieten eine einfache Möglichkeit, die Konversionsraten Ihrer Kunden in allen aktiven Modellen zu vergleichen.

<!-- audience-lab-compare-models.xml -->

In diesem Anwendungsfall vergleichen Sie verschiedene Modelle. Sie können entweder Modelle verwenden, die über eine interne data warehouse erstellt wurden, und sie [!DNL Audience Manager] als [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) importieren, oder Sie können die Funktion [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) in [!DNL Audience Manager]verwenden.

1. Erstellen Sie zwei Modelle entweder im [Modellaufbau](../../features/algorithmic-models/create-model.md)oder über eine externe Plattform.
1. Erstellen Sie [algorithmische Eigenschaften](../../features/traits/create-algorithmic-traits.md) aus dem algorithmischen Modell oder importieren Sie Ihre eigenen Modelle als integrierte Eigenschaften.
1. Erstellen Sie Segmente, die sich gegenseitig ausschließen, damit sich die Benutzer beider Modelle nicht überschneiden:

   * Erstellen Sie ein Segment ** Modell 1 und ein Segment *Modell 2*.
   * Die Segmentregel für *Modell-1-Segment* muss die Eigenschaft [!DNL AND NOT] des Modells 1 und umgekehrt für Segment ** Modell 2 aufweisen.

1. [Erstellen Sie zwei Segmenttestgruppen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], eine mit *Modell 1 Segment* als Grundlinie, die andere mit *Modell 2 Segment* als Grundlinie.

   * Halten Sie die Variablen für beide Testgruppen gleich: dieselben Ziele, kreative Elemente, Konversionseigenschaften.
   * Stellen Sie sicher, dass die Testsegmente eine ähnliche Anzahl von Benutzern haben (z. B. 1,6 Mio. und 1,8 Mio. sind in Ordnung, 1,6 Mio. und 16 Mio. nicht).
   * Reservieren Sie ein Kontrollsegment in jeder Testgruppe des Testsegments. Auf diese Weise können Sie einen kleinen Teil jedes Segments beilegen und nicht explizit im Test Zielgruppen vornehmen.

1. Überprüfen Sie die Ergebnisse:

   * Die Ansicht [des](../../features/audience-lab/audience-lab-reporting-view.md) Audience Lab-Berichte zeigt die Anzahl der Konvertierungen an, die die einzelnen Modelle ausführen. Bei konversionsbasierten Kampagnen bezeichnet das Testsegment, das die meisten Konversionen auslöst, das leistungsstärkste Modell.
   * Da Sie Steuerungssegmente haben, können Sie auch die Leistung des Modells im Vergleich zum Standard-Targeting bewerten. Sie testen nicht nur ein Modell im Vergleich zum anderen, sondern testen auch die Frage, &quot;ob dieses Modell besser abgeschnitten hat als normale Praktiken?&quot;

## Testen von kreativen Elementen über Ziele hinweg {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Verwenden Sie diese Option [!UICONTROL Audience Lab] zum Messen der Anzahl der Konversionen, die ein kreatives Element über verschiedene Ziele hinweg bringt. Mit diesem Verwendungsfall können Sie auch die Konversionen des kreativen Elements gegen natürlich auftretende Konversionen messen.

1. [Erstellen Sie eine Segment-Testgruppe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), und wählen Sie das Segment aus, mit dem Sie das Kreativelement als Grundliniensegment testen möchten.
1. Teilt das Grundliniensegment in Test- und Kontrollsegmente.
1. Ordnen Sie die Testsegmente den verschiedenen Zielen zu, die Sie testen möchten.
1. Das Kontrollsegment kann zurückgehalten und keinem Ziel zugeordnet werden. Das Kontrollsegment sollte nicht durch das Testkreativelement zielgerichtet sein, um eine Ergebnisgrundlinie für natürlich vorkommende Konversionen festzulegen.
1. Geben Sie ein Beginn- und ein Enddatum für den Test an.
1. Richten Sie das Segment und das kreative Element in den Zielen ein.
1. Die Ansicht [zum](../../features/audience-lab/audience-lab-reporting-view.md) Audience Lab Berichte zeigt die Anzahl der Konvertierungen, die das kreative Element über die Ziele hinweg durchführt.
1. Da Sie ein Kontrollsegment erstellt haben, können Sie auch bewerten, wie das Kreativelement mit natürlich vorkommenden Konversionen umgegangen ist. Sie testen die Frage: &quot;Hat dieses Kreativelement zu einem höheren Konversionsrate geführt als normale Praktiken?&quot;
