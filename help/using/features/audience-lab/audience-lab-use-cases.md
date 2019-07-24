---
description: Audience Lab aktiviert mehrere Anwendungsfälle, indem Sie Basissegmente zum Erstellen von Testgruppen verwenden. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese unterschiedlichen Ziele zuordnen und dann bestimmen, welche der Segmente bei der Förderung von Konversionen am effektivsten sind.
seo-description: Audience Lab aktiviert mehrere Anwendungsfälle, indem Sie Basissegmente zum Erstellen von Testgruppen verwenden. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese unterschiedlichen Ziele zuordnen und dann bestimmen, welche der Segmente bei der Förderung von Konversionen am effektivsten sind.
seo-title: Anwendungsfälle für Zielgruppen
solution: Audience Manager
title: Anwendungsfälle für Zielgruppen
topic: DIL-API
uuid: 727 bec 8 a-df 9 a -40 cc-b 8 a 7-e 1980 d 146 a 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] aktiviert mehrere Anwendungsfälle, indem Sie Basissegmente zum Erstellen von Testgruppen verwenden. Sie können Testgruppen in mehrere sich gegenseitig ausschließende Testsegmente unterteilen, diese unterschiedlichen Ziele zuordnen und dann bestimmen, welche der Segmente bei der Förderung von Konversionen am effektivsten sind.

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] bietet eine einfache Möglichkeit, die Konversionsraten Ihrer Kunden über Ihre aktiven Modelle hinweg zu vergleichen.

<!-- audience-lab-compare-models.xml -->

In diesem Anwendungsfall vergleichen Sie verschiedene Modelle. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. Erstellen Sie gegenseitige Segmente, sodass sich Benutzer in beiden Modellen nicht überschneiden:

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [Erstellen Sie zwei Segmenttestgruppen](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], eine mit *Model 1 Segment* als Grundlinie, die andere mit *Model 2-Segment* als Grundlinie.

   * Halten Sie die Variablen für beide Testgruppen gleich: gleiche Ziele, kreative Elemente, Konversionseigenschaften.
   * Stellen Sie sicher, dass die Testsegmente ähnliche Anzahl von Benutzern haben (z. B. 1,6 Mio. und 1,8 Mio. liegt in der Mitte, 1,6 Mio. und 16 Mio. nicht).
   * Reservieren Sie ein Kontrollsegment in jeder Testgruppe des Testsegments. Auf diese Weise können Sie einen kleinen Teil jedes Segments festlegen und nicht explizit im Test als Ziel auswählen.

1. Überprüfen Sie die Ergebnisse:

   * The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions each model is driving. Bei konversionsbasierten Kampagnen zeigt das Testsegment, das die meisten Konversionen ansteuert, das Modell an, das am besten funktioniert.
   * Da Sie über Kontrollsegmente verfügen, können Sie auch bewerten, wie das Modell das standardmäßige Targeting hat. Sie testen nicht nur ein Modell im Vergleich zum anderen, sondern testen die Frage "Hat dieses Modell besser funktioniert als normale Praktiken? «

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. Mit diesem Verwendungsfall können Sie außerdem die Konversionen der kreativen Elemente gegenüber automatisch auftretenden Konversionen messen.

1. [Erstellen Sie eine Segmenttestgruppe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)und wählen Sie das Segment aus, das Sie als Grundliniensegment testen möchten.
1. Teilen Sie das Grundliniensegment in Testsegmente und steuern Sie Segmente.
1. Ordnen Sie die Testsegmente den verschiedenen Zielen zu, die Sie testen möchten.
1. Das Steuerungssegment kann beibehalten und keinem Ziel zugeordnet werden. Das Kontrollsegment sollte nicht durch das kreative Testelement ausgerichtet werden, um eine Ausgangslinie für natürlicherweise auftretende Konvertierungen festzulegen.
1. Geben Sie ein Startdatum und ein Enddatum für den Test an.
1. Richten Sie das Segment und die kreativen Elemente in den Zielen ein.
1. The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions the creative is driving across the destinations.
1. Da Sie ein Steuerelement erstellt haben, können Sie auch auswerten, wie die kreativen Elemente für natürlich auftretende Konversionen vorgenommen wurden. Sie testen die Frage: " Hat dieses kreative Element eine höhere Konversionsrate generiert als normale Praktiken? «
