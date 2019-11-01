---
description: Wenn Sie in Trait Recommendations in Segment Builder ein Segment erstellen oder bearbeiten, erhalten Sie Empfehlungen zu zusätzlichen Merkmalen, die Sie einschließen können. Diese sind vergleichbar mit den Merkmalen in der Segmentregel. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.
seo-description: Beim Erstellen Ihrer Segmente erhalten Sie Empfehlungen zu Eigenschaften im Live-Format.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# Trait Recommendations

Erhalten Sie beim Erstellen Ihrer Segmente Live-Eigenschaftenempfehlungen aus Ihren eigenen Erstanbieter-Eigenschaften und [!UICONTROL Audience Marketplace] -Datenfeeds.

## Videodemonstration

Beginnen Sie damit, sich das unten stehende [!UICONTROL Trait Recommendations] Video anzusehen, und lesen Sie es für weitere Informationen. Die Videodemonstration zeigt Ihnen, wie Sie mit Empfehlungen aus Ihren eigenen Erstanbieter-Eigenschaften sowie mit Eigenschaftsempfehlungen aus [!UICONTROL Audience Marketplace] Datenfeeds arbeiten können, die *Sie bereits abonniert* haben.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=ger)

Das nächste Video skizziert den Arbeitsablauf für [!UICONTROL Marketplace Recommendations]und zeigt Ihnen, wie Sie Ihren Segmenten Eigenschaften hinzufügen, basierend auf Empfehlungen aus Data Feeds in [!UICONTROL Audience Marketplace]. Diese Empfehlungen basieren auf Datenfeeds, die *Sie nicht abonniert* haben.

>[!VIDEO](https://video.tv.adobe.com/v/29363/?captions=ger)

## Überblick

[!UICONTROL Trait Recommendations], powered by [!DNL Adobe Sensei], bringt Datenwissenschaften in Ihre täglichen Arbeitsabläufe von Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule.

Audience Manager zeigt Ihnen Eigenschaftsempfehlungen sowohl aus Ihren Erstanbietereigenschaften, im **[!UICONTROL Recommendations]** Abschnitt als auch aus **[!UICONTROL Audience Marketplace]** dem **[!UICONTROL Recommendations from Marketplace]** Abschnitt an.

Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.

![Übersicht über Traffic-Empfehlungen](assets/trait-recommendations-overview-full.png)

**Kurz gesagt:**

* Audience Manager zeigt Eigenschaften von Erstanbietern im [!UICONTROL Recommendations] Abschnitt an. Empfehlungen von Marktplätzen aus öffentlichen und privaten Feeds, die Sie nicht abonniert haben, sind im [!UICONTROL Recommendations from Marketplace] Abschnitt sichtbar. Klicken Sie auf den Feed-Namen, um ihn aufzurufen [!UICONTROL Audience Marketplace] und abonnieren.
* Audience Manager zeigt maximal fünfzig Eigenschaften an, die denen in der Segmentregel ähneln.
* Sie können die Datenquellen herausfiltern, aus denen keine Empfehlungen angezeigt werden sollen.
* Bei der Berechnung von Ähnlichkeiten berücksichtigt Audience Manager [UUIDs](../../reference/ids-in-aam.md) , die in den letzten 30 Tagen für die Eigenschaft qualifiziert waren.
* Wenn Sie die Fehlermeldung "Keine ähnlichen Eigenschaften gefunden. Eigenschaften sind möglicherweise zu neu.", bedeutet dies, dass entweder in den letzten 30 Tagen keine Aktivität für diese Eigenschaft stattgefunden hat oder dass Audience Manager die Empfehlungen für diese Eigenschaft noch nicht aktualisiert hat. Bitte versuchen Sie es in 24 Stunden erneut.

## Nutzungsszenarios

Mit [!UICONTROL Trait Recommendations]dieser Funktion können Sie Ihre Arbeitsabläufe je nach Verwendung von Audience Manager verbessern:

* Als Marketingspezialist können Sie mithilfe ähnlicher Eigenschaften schnell Zielgruppen finden, die an ergänzenden Produkten interessiert sind, sodass Sie Ihre Reichweite erhöhen können.
* Wenn Sie Audience Manager als Herausgeber verwenden, [!UICONTROL Trait Recommendations]können Sie das Verhalten der Zielgruppe verstehen und bessere Segmente für den Anzeigenverkauf oder die Benutzerakquise erstellen.
* Als [!UICONTROL Audience Marketplace] Datenkäufer möchte ich relevante Drittanbieterdaten ermitteln, ohne eine große Anzahl von Feeds durchsuchen zu müssen.
* Als [!UICONTROL Audience Marketplace] Datenanbieter möchte ich den Käufern relevante Daten empfehlen, damit ich von optimalen und relevanten Abonnements profitieren kann.

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

Beim Erstellen oder Bearbeiten eines Segments im [Segmentaufbau](segment-builder.md)können Sie Eigenschaften, die den Eigenschaften in der Segmentregel ähneln, untersuchen. Der Arbeitsablauf [Segmentaufbau](segment-builder.md) ist für neue und vorhandene Segmente sehr ähnlich:

### Neue Segmente

1. Gehen Sie zu **Zielgruppendaten &gt; Segmente** und klicken Sie auf Neu **hinzufügen**.
2. Fügen Sie der Segmentregel im Dropdownfeld **Eigenschaften** mindestens eine Eigenschaft hinzu.
3. Sie können empfohlene Eigenschaften und [!UICONTROL Audience Marketplace] Eigenschaftsempfehlungen von Erstanbietern aus Feeds, die Sie abonniert haben, im **[!UICONTROL Recommendations]** Abschnitt anzeigen. Der **[!UICONTROL Recommendations from Marketplace]** Abschnitt zeigt Empfehlungen zu Eigenschaften von Feeds an, die Sie nicht abonniert haben. Alle diese Empfehlungen ähneln den Eigenschaften, die Sie der Segmentregel hinzugefügt haben. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
4. (Optional) Um empfohlene Erstanbieter-Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das **X** -Symbol für die Datenquellen, die Sie ausschließen möchten.
   > [!NOTE]
   >
   > Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Klicken Sie im grauen Feld auf **X** , um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
5. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+** .

> [!IMPORTANT]
> Beim Hinzufügen von [!UICONTROL Marketplace] Eigenschaften zu einem Segment werden die Eigenschaften nur zur Segmentschätzung verwendet, bis Sie den entsprechenden Datenfeed abonnieren. Eigenschaften, die aus nicht abonnierten Datenfeeds stammen, werden in der Eigenschaftenliste mit einem Warenkorbsymbol gekennzeichnet. Klicken Sie auf den Eigenschaftsnamen, um zur Data Feed-Seite zu wechseln und sie zu abonnieren.
> ![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
> Sie können ein Segment mit Eigenschaften von Drittanbietern erst speichern, nachdem Sie sich bei den entsprechenden Datenfeeds angemeldet haben.

### Vorhandene Segmente

1. Gehen Sie zu **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, wählen Sie das Segment aus, das Sie bearbeiten möchten, und klicken Sie auf ![Bearbeiten](assets/edit-button.png).
1. Blättern Sie nach unten zum [!UICONTROL Traits] Dropdown-Feld.
1. Sie können empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die bereits in der Segmentregel enthalten sind. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das **X** -Symbol für die Datenquellen, die Sie ausschließen möchten.
   > [!NOTE]
   >
   > Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Klicken Sie im grauen Feld auf **X** , um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
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

![base-properties-Beispiel](assets/three-base-traits-numbered.png)

Wenn Sie auf eine Eigenschaft eines Erstanbieters klicken, wird ein Popup-Fenster geöffnet, wie in der Abbildung unten dargestellt. Wenn die empfohlenen Eigenschaften nicht Teil des Segments sind, können Sie sie mit **+** zum Segment hinzufügen.

![add-to-segment](assets/add_to_segments.png)

> [!TIP]
>
>Die ausgeschlossenen Datenquellen der Hauptseite werden bei der Erstellung von Empfehlungen im Popup-Fenster "Eigenschafteninformationen"berücksichtigt. Wenn Sie Datenquellen in dieser Ansicht ausschließen, gelten die Ausschlüsse auch für die Hauptseite.

> [!NOTE]
>
> Empfohlene Eigenschaften können Ihre Eigenschaften von Erstanbietern oder Eigenschaften von Drittanbietern aus Datenfeeds sein, die Sie abonniert haben [!UICONTROL Audience Marketplace].

## Funktionsweise

Um Eigenschaftsempfehlungen zu erstellen, berechnet Audience Manager die [Jaccard-Ähnlichkeit](https://en.wikipedia.org/wiki/Jaccard_index) zwischen der Zieleigenschaft und allen anderen Eigenschaften, auf die Ihr Konto Zugriff hat, einschließlich Drittanbieterdaten. Audience Manager zeigt dann bis zu fünfzig Eigenschaften mit der höchsten Ähnlichkeit an.

## Ähnlichkeitsbewertung {#trait-similarity-score}

Audience Manager berechnet die [!UICONTROL Trait Similarity Score] Werte zwischen zwei Eigenschaften, indem Schnittmenge und Vereinigung im Hinblick auf die Anzahl der [!UICONTROL UUID]s berechnet und dann die beiden dividiert werden. Für zwei Eigenschaften A und B sieht die Berechnung wie folgt aus:

![jaccard-Ähnlichkeit](assets/jaccard_similarity.png)

Siehe auch die beiden folgenden Beispiele.

### Beispiel 1: Low-Trait-Ähnlichkeitsbewertung

Angesichts der beiden Eigenschaften A und B haben alle Eigenschaften eine Bevölkerung von 1.000.000 [!UICONTROL UUID]s, von denen 25.000 [!UICONTROL UUID]s für beide Eigenschaften qualifiziert sind.
Wenn Sie die obige Formel verwenden, führt dies zu Folgendem: 25.000 / 1.975.000 = 0,012. Das ist ein niedriger Wert [!UICONTROL Trait Similarity Score], die beiden Eigenschaften sind sehr unähnlich.

![Merkmal-Recommendations-low-überlappend](assets/Trait-Recommendations-Low-overlap.png)

### Beispiel 2 - Bewertung der Ähnlichkeit von Eigenschaften

Wenn dieselben Eigenschaften A und B 400.000 [!UICONTROL UUID]s hatten, die für beide Eigenschaften infrage kommen, ist der Wert [!UICONTROL Trait Similarity Score] viel höher:
400.000 / 1.600.000 = 0,25

![Eigenschaften-Empfehlungen-hohe Überschneidung](assets/Trait-Recommendations-High-overlap.png)

### So interpretieren Sie die Eigenschafts-Ähnlichkeitsbewertung

Verwenden Sie die unten stehende Tabelle als grobe Hilfslinie, um Ähnlichkeiten zu erkennen. Dieser Leitfaden basiert auf den Ähnlichkeitswerten, die bei den meisten Eigenschaften beobachtet wurden.

| [!UICONTROL Trait Similarity Score] | Bedeutung |
---------|----------|
| 0.1 und höher | Hohe Ähnlichkeit zwischen Eigenschaften |
| 0.03 - 0.1 | Mittlere Ähnlichkeit zwischen Eigenschaften |
| 0.01 - 0.03 | Geringe Ähnlichkeit zwischen Eigenschaften |
| 0 - 0.01 | Sehr niedrige Ähnlichkeit zwischen Eigenschaften |

## Rollenbasierte Zugriffssteuerung (RBAC)

Für Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, benötigen Sie die Berechtigung zum Erstellen und Bearbeiten von Segmenten, um empfohlene Eigenschaften anzuzeigen. Die angezeigten Eigenschaftenempfehlungen sind nur diejenigen aus Datenquellen, auf die Sie über [!UICONTROL RBAC]Zugriff haben.

> [!IMPORTANT]
>
> Um einem Segment [!UICONTROL Marketplace Recommendations] hinzuzufügen, müssen Benutzer zunächst die entsprechenden Datenfeeds abonnieren. Nur Benutzer mit Administratorrechten können [!UICONTROL Audience Marketplace] Datenfeeds abonnieren.

Lesen Sie mehr über [!UICONTROL RBAC] Steuerelemente [hier](../administration/administration-overview.md).

## Einschränkungen

* Derzeit zeigt Audience Manager keine Ordnereigenschaften als empfohlene Eigenschaften an. Mehr über Ordnereigenschaften [hier](../traits/manage-folder-traits.md).
* Bei der Anzeige von Eigenschaftsempfehlungen berücksichtigt Audience Manager keine [!DNL Boolean] Operatoren ([!DNL AND], [!DNL OR], [!DNL NOT]) in Segmentregeln.
