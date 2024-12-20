---
description: Audience Lab ermöglicht mehrere Anwendungsfälle, indem Sie Baseline-Segmente zur Erstellung von Testgruppen verwenden. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese verschiedenen Zielen zuordnen und dann bestimmen, welche der Segmente am effektivsten zur Steigerung der Konversionen sind.
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

[!UICONTROL Audience Lab] ermöglicht mehrere Anwendungsfälle, indem Sie Baseline-Segmente zur Erstellung von Testgruppen verwenden können. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese verschiedenen Zielen zuordnen und dann bestimmen, welche der Segmente am effektivsten zur Steigerung der Konversionen sind.

## Vergleichen von Modellen in Audience Lab {#compare-models}

Sie können in [!DNL Audience Manager] verschiedene Modelltypen und -quellen verwenden. [!UICONTROL Audience Lab] bietet eine einfache Möglichkeit, die Konversionsraten Ihrer Kunden für alle aktiven Modelle zu vergleichen.

<!-- audience-lab-compare-models.xml -->

In diesem Anwendungsbeispiel vergleichen Sie verschiedene Modelle. Sie können entweder Modelle verwenden, die über ein hausinternes Data Warehouse erstellt wurden, und sie in [!DNL Audience Manager] als [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) importieren oder Sie können die Funktion [Algorithmische Modelle](../../features/algorithmic-models/understanding-models.md) in [!DNL Audience Manager] verwenden.

1. Erstellen Sie zwei Modelle entweder im [Model Builder](../../features/algorithmic-models/create-model.md) oder über eine externe Plattform.
1. Erstellen Sie [algorithmische Eigenschaften](../../features/traits/create-algorithmic-traits.md) aus dem algorithmischen Modell oder importieren Sie Ihre eigenen Modelle als integrierte Eigenschaften.
1. Erstellen Sie sich gegenseitig ausschließende Segmente, damit sich Benutzende in beiden Modellen nicht überschneiden:

   * Erstellen Sie ein *Segment 1* und ein *Segment 2*.
   * Weisen Sie die Segmentregel für *Segment 1* als Eigenschaft Modell 1 [!DNL AND NOT] Eigenschaft Modell 2 und umgekehrt für Segment *Segment 2*.

1. [Erstellen Sie zwei Segmenttestgruppen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], eine mit *Segment 1* als Baseline und die andere mit *Segment 2* als Baseline.

   * Halten Sie die Variablen für beide Testgruppen gleich: gleiche Ziele, kreative Eigenschaften, Konversionseigenschaften.
   * Stellen Sie sicher, dass die Testsegmente eine ähnliche Anzahl von Benutzern haben (z. B. 1,6 Millionen und 1,8 Millionen in Ordnung, 1,6 Millionen und 16 Millionen nicht).
   * Reservieren Sie ein Kontrollsegment in jeder Testsegment-Testgruppe. Auf diese Weise können Sie einen kleinen Teil jedes Segments beiseite legen und sie im Test nicht explizit ansprechen.

1. Überprüfen Sie die Ergebnisse:

   * Die [Berichtsansicht des Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) zeigt die Anzahl der Konversionen an, die jedes Modell steuert. Bei konversionsbasierten Kampagnen gibt das Testsegment mit den meisten Konversionen das Modell an, das die beste Leistung erzielt.
   * Da Sie über Steuerungssegmente verfügen, können Sie auch bewerten, wie sich das Modell im Vergleich zum „Standard-Targeting“ entwickelt hat. Sie testen nicht nur ein Modell gegen das andere, sondern auch die Frage: „Hat dieses Modell besser abgeschnitten als normale Methoden?“

## Testen von Kreativen in verschiedenen Zielen {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Verwenden Sie [!UICONTROL Audience Lab], um die Anzahl der Konversionen zu messen, die ein Kreativ über verschiedene Ziele hinweg treibt. In diesem Anwendungsbeispiel können Sie auch die Konversionen des Kreativen an natürlich vorkommenden Konversionen messen.

1. [Erstellen Sie eine Segmenttestgruppe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), indem Sie das Segment auswählen, mit dem Sie das Kreativ-Tool testen möchten, und es als Baseline-Segment auswählen.
1. Teilen Sie das Basissegment in Testsegmente und Kontrollsegmente auf.
1. Ordnen Sie die Testsegmente den verschiedenen Zielen zu, die Sie testen möchten.
1. Das Kontrollsegment kann zurückgehalten und keinem Ziel zugeordnet werden. Das Kontrollsegment sollte nicht vom Kreativtest angesprochen werden, um eine Baseline für die Ergebnisse natürlich vorkommender Konversionen festzulegen.
1. Geben Sie ein Start- und ein Enddatum für den Test an.
1. Richten Sie das Segment und das Kreativteam in den Zielen ein.
1. Die [Berichtsansicht im Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) zeigt die Anzahl der Konversionen an, die der Kreative durch die Ziele treibt.
1. Da Sie ein Kontrollsegment erstellt haben, können Sie auch bewerten, wie sich das Kreativ-Tool mit natürlich auftretenden Konversionen verhalten hat. Sie testen die Frage: „Hat dieses kreative Tool eine höhere Konversionsrate generiert als normale Verfahren?“
