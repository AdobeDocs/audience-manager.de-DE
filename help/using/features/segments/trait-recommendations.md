---
description: Wenn Sie in Trait Recommendations in Segment Builder ein Segment erstellen oder bearbeiten, erhalten Sie Empfehlungen zu zusätzlichen Merkmalen, die Sie einschließen können. Diese sind vergleichbar mit den Merkmalen in der Segmentregel. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.
seo-description: Beim Erstellen Ihrer Segmente erhalten Sie Empfehlungen zu Eigenschaften im Live-Format.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Trait Recommendations

Beim Erstellen Ihrer Segmente erhalten Sie Empfehlungen zu Eigenschaften im Live-Format.

## Videodemonstration

Beginnen Sie damit, sich das Video "Empfehlungen für Eigenschaften"anzusehen, und lesen Sie dann weitere Informationen.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=ger)

## Überblick

[!UICONTROL Trait Recommendations], powered by [!DNL Adobe Sensei], bringt Datenwissenschaften in Ihre täglichen Arbeitsabläufe von Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.

![Übersicht über Traffic-Empfehlungen](assets/trait-recommendations-overview.png)

**Kurz gesagt:**

* Audience Manager zeigt Eigenschaften von Erstanbietern und Eigenschaften von Drittanbietern aus Ihren derzeit abonnierten Datenfeeds als empfohlene Eigenschaften an.
* Audience Manager zeigt maximal fünfzig Eigenschaften an, die denen in der Segmentregel ähneln.
* Sie können die Datenquellen herausfiltern, aus denen keine Empfehlungen angezeigt werden sollen.
* Bei der Berechnung von Ähnlichkeiten berücksichtigt Audience Manager [UUIDs](../../reference/ids-in-aam.md) , die in den letzten 30 Tagen für die Eigenschaft qualifiziert waren.
* Wenn Sie die Fehlermeldung "Keine ähnlichen Eigenschaften gefunden. Eigenschaften sind möglicherweise zu neu.", bedeutet dies, dass entweder in den letzten 30 Tagen keine Aktivität für diese Eigenschaft stattgefunden hat oder dass Audience Manager die Empfehlungen für diese Eigenschaft noch nicht aktualisiert hat. Bitte versuchen Sie es in 24 Stunden erneut.

## Nutzungsszenarios

Mit [!UICONTROL Trait Recommendations]dieser Funktion können Sie Ihre Arbeitsabläufe je nach Verwendung von Audience Manager verbessern:

* Als Marketingspezialist können Sie mithilfe ähnlicher Eigenschaften schnell Zielgruppen finden, die an ergänzenden Produkten interessiert sind, sodass Sie Ihre Reichweite erhöhen können.
* Wenn Sie Audience Manager als Herausgeber verwenden, [!UICONTROL Trait Recommendations]können Sie das Verhalten der Zielgruppe verstehen und bessere Segmente für den Anzeigenverkauf oder die Benutzerakquise erstellen.

## Unterschiede zwischen Eigenschaftsempfehlungen und Algorithmusmodellen

### Algorithmische Modelle

[!UICONTROL Algorithmic Models] Findet nicht nur die einflussreichsten Eigenschaften, sondern bewertet auch die Benutzer anhand dieser Eigenschaften und weist jedem Benutzer eine individuelle Bewertung zu. Anschließend erstellen Sie algorithmische Eigenschaften, die auf Ihre Benutzer zugeschnitten sind. Mit den Steuerelementen für Genauigkeit und Reichweite im [!UICONTROL Trait Builder]können Sie festlegen, welche Benutzer zu den einflussreichen Eigenschaften gehören, die Sie als Ziel auswählen möchten.

[!UICONTROL Algorithmic Models] ermöglicht Ihnen, Benutzer mit unterschiedlichen Genauigkeitsstufen auszuwählen und zu testen, in [!UICONTROL Audience Lab] welcher Benutzergruppe sie besser konvertiert. Siehe den ausführlichen Verwendungsfall unter [Modelle vergleichen im Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models]diesem Fall wird das Modell alle 8 Tage ausgeführt und aktualisiert die für algorithmische Eigenschaften qualifizierten Benutzer.

### Trait Recommendations

[!UICONTROL Trait Recommendations] ist eine schnelle Möglichkeit, Einblicke in andere Eigenschaften zu erhalten, die den Eigenschaften in einem Segment ähnlich sind.

Sie sollten [!UICONTROL Trait Recommendations] Folgendes verwenden:

* Beim Erstellen eines Segments benötigen Sie schnelle Einblicke.
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Konvertierung der Zielgruppe schnell unterdrücken möchten.
* Sie versuchen, die Reichweite zu maximieren.

## Arbeitsablauf

Beim Erstellen oder Bearbeiten eines Segments im [Segmentaufbau](segment-builder.md)können Sie Eigenschaften, die den Eigenschaften in der Segmentregel ähneln, untersuchen. Der Segment Builder-Arbeitsablauf ist für neue und vorhandene Segmente sehr ähnlich:

### Neue Segmente

1. Wählen Sie unter **Zielgruppendaten &gt; Segmente** die Option Neu **hinzufügen**.
2. Fügen Sie der Segmentregel im Dropdownfeld **Eigenschaften** mindestens eine Eigenschaft hinzu.
3. Sie können jetzt empfohlene Eigenschaften sehen, die den Eigenschaften ähneln, die Sie der Segmentregel hinzugefügt haben. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
4. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das **X** -Symbol für die Datenquellen, die Sie ausschließen möchten.
   > [!NOTE]
   > 
   >Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Drücken Sie **X** im grauen Feld, um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
5. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+** .

### Vorhandene Segmente

1. Gehen Sie zu **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, wählen Sie das Segment aus, das Sie bearbeiten möchten, und drücken Sie die ![Taste Bearbeiten](assets/edit-button.png).
1. Blättern Sie nach unten zum [!UICONTROL Traits] Dropdown-Feld.
1. Sie können empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die bereits in der Segmentregel enthalten sind. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das **X** -Symbol für die Datenquellen, die Sie ausschließen möchten.
   > [!NOTE]
   > 
   >Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Drücken Sie **X** im grauen Feld, um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
1. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+** .

Wenn Sie ein Segment erstellen oder bearbeiten und der Segmentregel eine Eigenschaft hinzufügen, sehen Sie maximal 50 empfohlene Eigenschaften, ähnlich denen, die Sie hinzugefügt haben. Wenn die Segmentregel mehr als eine Eigenschaft enthält, verwendet Audience Manager eine Round-Robin-Methode, um die beste Übereinstimmung für jede Eigenschaft anzuzeigen, dann die zweitbeste Übereinstimmung für jede Eigenschaft usw. für die größten fünfzig Eigenschaften nach Population in der Segmentregel.

![Drei Basiseigenschaften](assets/three-base-traits.png)

Wenn die Segmentregel z. B. drei Eigenschaften enthält, wie unten dargestellt, werden folgende Eigenschaften empfohlen:

1. beste Übereinstimmung für Eigenschaft 3 (die Eigenschaft mit der größten Population);
2. Optimale Übereinstimmung für Eigenschaft 1;
3. Optimale Übereinstimmung für Eigenschaft 2;
4. Zweitbeste Übereinstimmung für Eigenschaft 3;
5. Zweitbeste Übereinstimmung für Eigenschaft 1 usw., bis Sie zu fünfzig Eigenschaften gelangen.

Um Empfehlungen für eine bestimmte Eigenschaft abzurufen, können Sie auf die Eigenschaften in der Segmentregel (1) oder in der Ansicht "Empfohlene Eigenschaften"(2) klicken.

![](assets/three-base-traits-numbered.png)

Wenn Sie auf eine Eigenschaft klicken, wird ein Popup-Fenster geöffnet, wie in der Abbildung unten dargestellt. Wenn die empfohlenen Eigenschaften nicht Teil des Segments sind, können Sie sie mit **+** zum Segment hinzufügen.

![](assets/add_to_segments.png)

> [!TIP]
>
>Die ausgeschlossenen Datenquellen der Hauptseite werden bei der Erstellung von Empfehlungen im Popup-Fenster "Eigenschafteninformationen"berücksichtigt. Wenn Sie Datenquellen in dieser Ansicht ausschließen, gelten die Ausschlüsse auch für die Hauptseite.

> [!NOTE]
>
> Empfohlene Eigenschaften können Ihre Eigenschaften von Erstanbietern oder Eigenschaften von Drittanbietern aus Feeds sein, die Sie abonniert haben.

## Funktionsweise

Um Eigenschaftsempfehlungen zu erstellen, berechnet Audience Manager die [Jaccard-Ähnlichkeit](https://en.wikipedia.org/wiki/Jaccard_index) zwischen der Zieleigenschaft und allen anderen Eigenschaften, auf die Ihr Konto Zugriff hat, einschließlich Drittanbieterdaten. Audience Manager zeigt dann bis zu fünfzig Eigenschaften mit der höchsten Ähnlichkeit an.

## Ähnlichkeitsbewertung

Audience Manager berechnet die [!UICONTROL Trait Similarity Score] Werte zwischen zwei Eigenschaften, indem Schnittmenge und Vereinigung im Hinblick auf die Anzahl der [!UICONTROL UUID]s berechnet und dann die beiden dividiert werden. Für zwei Eigenschaften A und B sieht die Berechnung wie folgt aus:

![](assets/jaccard_similarity.png)

Siehe auch die beiden folgenden Beispiele.

### Beispiel 1: Low-Trait-Ähnlichkeitsbewertung

Angesichts der beiden Eigenschaften A und B haben alle Eigenschaften eine Bevölkerung von 1.000.000 [!UICONTROL UUID]s, von denen 25.000 [!UICONTROL UUID]s für beide Eigenschaften qualifiziert sind.
Wenn Sie die obige Formel verwenden, führt dies zu Folgendem: 25.000 / 1.975.000 = 0,012. Das ist ein niedriger Wert [!UICONTROL Trait Similarity Score], die beiden Eigenschaften sind sehr unähnlich.

![](assets/Trait-Recommendations-Low-overlap.png)

### Beispiel 2 - Bewertung der Ähnlichkeit von Eigenschaften

Wenn dieselben Eigenschaften A und B 400.000 [!UICONTRL ]UUIDs enthielten, die für beide Eigenschaften infrage kommen, [!UICONTROL Trait Similarity Score] ist der Wert viel höher:
400.000 / 1.600.000 = 0,25

![](assets/Trait-Recommendations-High-overlap.png)

### So interpretieren Sie die Eigenschafts-Ähnlichkeitsbewertung

Verwenden Sie die unten stehende Tabelle als grobe Hilfslinie, um Ähnlichkeiten zu erkennen. Dieser Leitfaden basiert auf den Ähnlichkeitswerten, die bei den meisten Eigenschaften beobachtet wurden.

| [!UICONTROL Trait Similarity Score] | Bedeutung |
---------|----------|
| 0.1 und höher | Hohe Ähnlichkeit zwischen Eigenschaften |
| 0.03 - 0.1 | Mittlere Ähnlichkeit zwischen Eigenschaften |
| 0.01 - 0.03 | Geringe Ähnlichkeit zwischen Eigenschaften |
| 0 - 0.01 | Sehr niedrige Ähnlichkeit zwischen Eigenschaften |

## Rollenbasierte Zugriffssteuerung (RBAC)

Für Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, benötigen Sie die Berechtigung zum Erstellen und Bearbeiten von Segmenten, um empfohlene Eigenschaften anzuzeigen. Die empfohlenen Eigenschaften, die Sie sehen, sind nur diejenigen aus Datenquellen, auf die Sie über [!UICONTROL RBAC]Zugriff haben. Lesen Sie mehr über [!UICONTROL RBAC] Steuerelemente [hier](../administration/administration-overview.md).

## Einschränkungen

* Derzeit zeigt Audience Manager keine Ordnereigenschaften als empfohlene Eigenschaften an. Mehr über Ordnereigenschaften [hier](../traits/manage-folder-traits.md).
* Bei der Anzeige von Eigenschaftsempfehlungen berücksichtigt Audience Manager keine [!DNL Boolean] Operatoren ([!DNL AND], [!DNL OR], [!DNL NOT]) in Segmentregeln.