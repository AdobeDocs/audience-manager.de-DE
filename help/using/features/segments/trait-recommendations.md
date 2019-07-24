---
description: Wenn Sie in Trait Recommendations in Segment Builder ein Segment erstellen oder bearbeiten, erhalten Sie Empfehlungen zu zusätzlichen Merkmalen, die Sie einschließen können. Diese sind vergleichbar mit den Merkmalen in der Segmentregel. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.
seo-description: Empfehlungen für Live-Eigenschaften erhalten Sie beim Erstellen Ihrer Segmente.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# Trait Recommendations

Empfehlungen für Live-Eigenschaften erhalten Sie beim Erstellen Ihrer Segmente.

## Überblick

[!UICONTROL Trait Recommendations], powered by [!DNL Adobe Sensei], bringt die Datenwissenschaft in Ihre Day-to-Day-Workflows von Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.

![Übersicht über Recommendations-Empfehlungen](assets/trait-recommendations-overview.png)

**In einer Nutshell:**

* Audience Manager zeigt Eigenschaften von Erstanbietern und Drittanbietereigenschaften aus Ihren derzeit abonnierten Datenfeeds als Eigenschaften an.
* Audience Manager zeigt maximal fünfzig Eigenschaften an, die dem in der Segmentregel ähneln.
* Sie können die Datenquellen herausfiltern, aus denen keine Empfehlungen erscheinen sollen.
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* Wenn die Fehlermeldung "Keine ähnlichen Eigenschaften gefunden" angezeigt wird. Eigenschaften sind möglicherweise zu neu. " Dies bedeutet, dass entweder in den letzten 30 Tagen keine Aktivitäten für diese Eigenschaft vorhanden waren oder Audience Manager die Empfehlungen für diese Eigenschaft noch nicht aktualisiert hat. Bitte erneut in 24 Stunden versuchen.

## Nutzungsszenarios

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* Als Marketingexperten können Sie Zielgruppen mit ähnlichen Eigenschaften schnell finden, um sich ergänzende Produkte mithilfe ähnlicher Eigenschaften anzusehen.
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## Unterschiede zwischen Eigenschaftenempfehlungen und algorithmischen Modellen

### Algorithmische Modelle

[!UICONTROL Algorithmic Models] nicht nur die einflussreichsten Eigenschaften findet, sondern auch Benutzer anhand dieser Eigenschaften auswertet und jedem Benutzer ein einzelnes Ergebnis zuweist. Anschließend erstellen Sie algorithmische Eigenschaften zur Ausrichtung Ihrer Benutzer. With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] ermöglicht es Ihnen, Benutzer auf unterschiedlichen Genauigkeitsstufen auszuwählen und zu testen, welche [!UICONTROL Audience Lab] Benutzergruppe besser konvertiert werden soll. See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### Trait Recommendations

[!UICONTROL Trait Recommendations] bietet eine schnelle Möglichkeit, Einblicke zu anderen Eigenschaften zu erhalten, die den in einem Segment verwendeten Ähneln.

You should use [!UICONTROL Trait Recommendations] when:

* Sie benötigen beim Erstellen eines Segments schnelle Einblicke;
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Zielgruppe schnell unterdrücken möchten, die konvertiert.
* Sie versuchen, die Reichweite zu maximieren.

## Arbeitsablauf

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. Der Segmentaufbau-Workflow ist für neue und vorhandene Segmente sehr ähnlich:

### Neue Segmente

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. Sie können nun empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die Sie der Segmentregel hinzugefügt haben. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Die ausgeschlossenen Datenquellen werden direkt oberhalb der Liste empfohlener Eigenschaften angezeigt. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### Vorhandene Segmente

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. Sie können empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die bereits in der Segmentregel enthalten sind. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Die ausgeschlossenen Datenquellen werden direkt oberhalb der Liste empfohlener Eigenschaften angezeigt. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

Wenn Sie ein Segment erstellen oder bearbeiten und der Segmentregel eine Eigenschaft hinzufügen, werden Ihnen maximal fünfzig empfohlene Eigenschaften angezeigt, ähnlich wie der, den Sie hinzugefügt haben. Wenn die Segmentregel mehr als eine Eigenschaft enthält, verwendet Audience Manager eine runde Robin-Methode, um die beste Übereinstimmung für jede Eigenschaft anzuzeigen, dann die zweitbeste Übereinstimmung für jede Eigenschaft usw., für die größten fünfzig Eigenschaften nach Population in der Segmentregel.

![Drei Basiseigenschaften](assets/three-base-traits.png)

Wenn die Segmentregel z. B. drei Eigenschaften enthält, lauten die empfohlenen Eigenschaften wie folgt:

1. Beste Übereinstimmung für Merkmal 3 (die Eigenschaft mit der größten Population);
2. Beste Übereinstimmung für Merkmal 1;
3. Beste Übereinstimmung für Merkmal 2;
4. Zweitbeste Übereinstimmung für Merkmal 3;
5. Zweitbeste Übereinstimmung für Trait 1 usw. Bis zu 50 Eigenschaften.

Um Empfehlungen für eine bestimmte Eigenschaft zu erhalten, können Sie auf die Eigenschaften in der Segmentregel (1) oder in der empfohlenen Eigenschaftenansicht (2) klicken.

![](assets/three-base-traits-numbered.png)

Durch Klicken auf eine Eigenschaft wird ein Popup-Fenster geöffnet, wie im Bild unten dargestellt. If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>Die ausgeschlossenen Datenquellen auf der Hauptseite werden bei der Erstellung von Empfehlungen innerhalb des Popupfensters für die Eigenschafteninformationen berücksichtigt. Wenn Sie Datenquellen in dieser Ansicht ausschließen, gelten die Ausnahmen für die Hauptseite.

> [!NOTE]
>
> Empfohlene Eigenschaften können Ihre Erstanbieter- oder Drittanbietereigenschaften aus Feeds sein, die Sie abonniert haben.

## Funktionsweise

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager zeigt dann bis zu fünfzig Eigenschaften mit der höchsten Ähnlichkeit an.

## Eigenschaften-Ähnlichkeitsbewertung

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. Für zwei Eigenschaften A und B sieht die Berechnung wie folgt aus:

![](assets/jaccard_similarity.png)

Siehe auch die beiden unten stehenden Beispiele.

### Beispiel 1 - Ähnlichkeitsbewertung Niedrige Eigenschaften

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### Beispiel 2 - Eigenschaftsähnlichkeitsbewertung

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### Interpretieren der Eigenschaften-Ähnlichkeitsbewertung

Verwenden Sie die unten stehende Tabelle als grobes Handbuch zur Ähnlichkeit von Ähnlichkeit. Dieses Handbuch basiert auf den Ähnlichkeitswerten, die über die meisten Eigenschaften hinweg beobachtet werden.

| [!UICONTROL Trait Similarity Score] | Bedeutung |
---------|----------|
| 0.1 und höher | Hohe Ähnlichkeit zwischen Eigenschaften |
| 0.03 - 0.1 | Mittlere Ähnlichkeit zwischen Eigenschaften |
| 0.01 - 0.03 | Geringe Ähnlichkeit zwischen Eigenschaften |
| 0 - 0.01 | Sehr niedrige Ähnlichkeit zwischen Eigenschaften |

## Rollenbasierte Zugriffssteuerung (RBAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## Einschränkungen

* Derzeit zeigt Audience Manager keine Ordnereigenschaften als empfohlene Eigenschaften an. Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.