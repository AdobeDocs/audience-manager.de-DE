---
description: Audience Lab ermöglicht mehrere Anwendungsfälle, indem Sie Ausgangssegmente zum Erstellen von Testgruppen verwenden können. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese verschiedenen Zielen zuordnen und dann bestimmen, welche der Segmente bei der Förderung von Konversionen am effektivsten sind.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Anwendungsfälle für Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Anwendungsfälle für Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] ermöglicht mehrere Anwendungsfälle, indem Sie Ausgangssegmente zum Erstellen von Testgruppen verwenden können. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese verschiedenen Zielen zuordnen und dann bestimmen, welche der Segmente bei der Förderung von Konversionen am effektivsten sind.

## Modelle in Audience Lab vergleichen {#compare-models}

Sie können mehrere verschiedene Typen und Quellen von Modellen in [!DNL Audience Manager] verwenden. [!UICONTROL Audience Lab] bietet eine einfache Möglichkeit, die Konversionsraten Ihrer Kunden über Ihre aktiven Modelle hinweg zu vergleichen.

<!-- audience-lab-compare-models.xml -->

In diesem Anwendungsfall vergleichen Sie verschiedene Modelle. Sie können Modelle, die über ein internes Data Warehouse erstellt wurden, entweder in [!DNL Audience Manager] als [integrierte Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) importieren oder die Funktion [Algorithmische Modelle](../../features/algorithmic-models/understanding-models.md) in [!DNL Audience Manager] verwenden.

1. Erstellen Sie zwei Modelle entweder im [Modell-Builder](../../features/algorithmic-models/create-model.md) oder über eine externe Plattform.
1. Erstellen Sie [algorithmische Eigenschaften](../../features/traits/create-algorithmic-traits.md) aus dem algorithmischen Modell oder importieren Sie Ihre eigenen Modelle als integrierte Eigenschaften.
1. Erstellen Sie Segmente, die sich gegenseitig ausschließen, damit sich Benutzer in beiden Modellen nicht überschneiden:

   * Erstellen Sie ein *Modell 1-Segment* und ein *Modell 2-Segment*.
   * Die Segmentregel für *Modell 1 Segment* muss die Eigenschaft Modell 1 Eigenschaft [!DNL AND NOT] Modell 2 und umgekehrt für das Segment *Modell 2 Segment* sein.

1. [Erstellen Sie zwei Segmenttestgruppen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab]: eine mit *Modell 1 Segment* als Grundlinie, die andere mit *Modell 2 Segment* als Grundlinie.

   * Behalten Sie die Variablen für beide Testgruppen bei: dieselben Ziele, kreativen Eigenschaften und Konversionseigenschaften.
   * Stellen Sie sicher, dass die Testsegmente eine ähnliche Anzahl von Benutzern haben (z. B. 1,6 Mio. und 1,8 Mio. ist in Ordnung, 1,6 Mio. und 16 Mio. nicht).
   * Reservieren Sie ein Kontrollsegment in jeder Testgruppe eines Testsegments. Auf diese Weise können Sie einen kleinen Teil jedes Segments beiseite legen und sie nicht explizit im Test ansprechen.

1. Untersuchen Sie die Ergebnisse:

   * Die Berichterstellungsansicht [Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) zeigt die Anzahl der Konversionen an, die die einzelnen Modelle erzielen. Bei konversionsbasierten Kampagnen zeigt das Testsegment, das die meisten Konversionen steuert, das Modell an, das die beste Leistung erzielt.
   * Da Sie über Kontrollsegmente verfügen, können Sie auch bewerten, wie das Modell mit &quot;Standard-Targeting&quot;funktioniert hat. Sie testen nicht nur ein Modell im Vergleich zum anderen, sondern testen auch die Frage: &quot;Hat dieses Modell bessere Ergebnisse erzielt als normale Praktiken?&quot;

## Testen von kreativen Elementen über Ziele hinweg {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Verwenden Sie [!UICONTROL Audience Lab] , um die Anzahl der Konversionen zu messen, die ein kreatives Element über verschiedene Ziele hinweg erzielt. In diesem Anwendungsfall können Sie auch die Konversionen des Kreativelements gegenüber natürlich vorkommenden Konversionen messen.

1. [Erstellen Sie eine Segmenttestgruppe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), indem Sie das Segment auswählen, mit dem Sie das Kreativelement als Grundliniensegment testen möchten.
1. Teilen Sie das Grundliniensegment in Testsegmente und Kontrollsegmente auf.
1. Ordnen Sie die Testsegmente den verschiedenen Zielen zu, die Sie testen möchten.
1. Das Kontrollsegment kann zurückgehalten und keinem Ziel zugeordnet werden. Das Kontrollsegment sollte nicht vom Testkreativ angesprochen werden, um eine Ergebnisgrundlinie für natürlich vorkommende Konversionen festzulegen.
1. Geben Sie ein Start- und ein Enddatum für den Test an.
1. Richten Sie das Segment und das Kreativ in den Zielen ein.
1. Die Berichterstellungsansicht [Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) zeigt die Anzahl der Konversionen, die der Kreativschaffende über die Ziele hinweg durchführt.
1. Da Sie ein Kontrollsegment erstellt haben, können Sie auch bewerten, wie das Kreativelement mit natürlich vorkommenden Konversionen abgeschnitten hat. Sie testen die Frage: &quot;Hat dieses Kreativ eine höhere Konversionsrate generiert als normale Praktiken?&quot;
