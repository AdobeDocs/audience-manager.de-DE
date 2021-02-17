---
description: Wenn Sie in Trait Recommendations in Segment Builder ein Segment erstellen oder bearbeiten, erhalten Sie Empfehlungen zu zusätzlichen Merkmalen, die Sie einschließen können. Diese sind vergleichbar mit den Merkmalen in der Segmentregel. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.
seo-description: Beim Erstellen Ihrer Segmente erhalten Sie Empfehlungen zu Eigenschaften im Live-Format.
seo-title: Eigenschaftenempfehlungen
solution: Audience Manager
title: Eigenschaftenempfehlungen
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# Eigenschaftenempfehlungen

Erhalten Sie beim Erstellen Ihrer Segmente Live-Eigenschaftenempfehlungen aus Ihren eigenen Erstanbietereigenschaften und [!UICONTROL Audience Marketplace]-Datenfeeds.

## Videodemonstration

Beginn, indem Sie sich das [!UICONTROL Trait Recommendations] Video unten ansehen, und lesen Sie dann für weitere Informationen. Die Videodemonstration zeigt Ihnen, wie Sie mit Empfehlungen aus Ihren eigenen Erstanbieter-Eigenschaften sowie mit Eigenschaftsempfehlungen von [!UICONTROL Audience Marketplace]-Datenfeeds arbeiten können, die *bereits von* abonniert wurden.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

Das nächste Video skizziert den Arbeitsablauf für [!UICONTROL Marketplace Recommendations] und zeigt Ihnen, wie Sie Ihren Segmenten Eigenschaften hinzufügen, basierend auf Empfehlungen aus Datenfeeds in [!UICONTROL Audience Marketplace]. Diese Empfehlungen basieren auf Datenfeeds, die *Sie nicht abonniert haben.*

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Überblick

[!UICONTROL Trait Recommendations], powered by  [!DNL Adobe Sensei], bringt Datenwissenschaft in Ihre tägliche Workflows.
Wenn Sie mit [!UICONTROL Trait Recommendations] ein Segment in [Segmentaufbau](segment-builder.md) erstellen oder bearbeiten, erhalten Sie Empfehlungen zu zusätzlichen Eigenschaften, die Sie einbeziehen können, die den Eigenschaften in der Segmentregel ähnlich sind.

Audience Manager zeigt Ihnen Eigenschaftsempfehlungen sowohl aus Ihren Erstanbietereigenschaften im Abschnitt **[!UICONTROL Recommendations]** als auch aus **[!UICONTROL Audience Marketplace]** im Abschnitt **[!UICONTROL Recommendations from Marketplace]** an.

Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.

![Recommendations-Übersicht](assets/trait-recommendations-overview-full.png)

**Kurz gesagt:**

* Audience Manager zeigt Erstanbieter-Eigenschaften im Abschnitt [!UICONTROL Recommendations] an. Empfehlungen von Marktplätzen aus öffentlichen und privaten Feeds, die Sie nicht abonniert haben, sind im Abschnitt [!UICONTROL Recommendations from Marketplace] sichtbar. Klicken Sie auf den Feed-Namen, um [!UICONTROL Audience Marketplace] aufzurufen und zu abonnieren.
* Audience Manager zeigt maximal fünfzig Eigenschaften an, die denen in der Segmentregel ähneln.
* Sie können die Datenquellen herausfiltern, aus denen keine Empfehlungen angezeigt werden sollen.
* Bei der Berechnung von Ähnlichkeiten betrachtet Audience Manager [UUIDs](../../reference/ids-in-aam.md), die sich in den letzten 30 Tagen für die Eigenschaft qualifizieren.
* Wenn Sie die Fehlermeldung &quot;Keine ähnlichen Eigenschaften gefunden. Eigenschaften sind möglicherweise zu neu.&quot;, bedeutet dies, dass entweder in den letzten 30 Tagen keine Aktivität für diese Eigenschaft stattgefunden hat oder Audience Manager die Empfehlungen für diese Eigenschaft noch nicht aktualisiert hat. Bitte versuchen Sie es in 24 Stunden erneut.

## Nutzungsszenarios

Mit [!UICONTROL Trait Recommendations] können Sie Ihre Workflows je nach Verwendung von Audience Manager verbessern:

* Als Vermarkter können Sie mithilfe ähnlicher Eigenschaften schnell Audiencen finden, die an ergänzenden Produkten interessiert sind, sodass Sie Ihre Reichweite vergrößern können.
* Wenn Sie Audience Manager als Herausgeber verwenden und [!UICONTROL Trait Recommendations] verwenden, können Sie das Verhalten der Audience verstehen und bessere Segmente für den Anzeigenverkauf oder die Benutzerakquise erstellen.
* Als [!UICONTROL Audience Marketplace]-Datenkäufer möchte ich relevante Drittanbieterdaten ermitteln, ohne eine große Anzahl von Feeds durchsuchen zu müssen.
* Als [!UICONTROL Audience Marketplace] Datenanbieter möchte ich den Käufern relevante Daten empfehlen, damit ich von optimalen und relevanten Abonnements profitieren kann.

## Unterschiede zwischen Eigenschaften-Recommendations und Algorithmusmodellen

### Algorithmische Modelle

[!UICONTROL Algorithmic Models] Findet nicht nur die einflussreichsten Eigenschaften, sondern bewertet auch die Benutzer anhand dieser Eigenschaften und weist jedem Benutzer ein individuelles Ergebnis zu. Anschließend erstellen Sie algorithmische Eigenschaften, um Ihre Benutzer anzusprechen. Mit den Genauigkeits- und Reichweitensteuerelementen im [!UICONTROL Trait Builder] können Sie angeben, welche Benutzer zu den einflussreichen Eigenschaften gehören, die Sie Zielgruppen vornehmen möchten.

[!UICONTROL Algorithmic Models] ermöglicht Ihnen, Benutzer mit unterschiedlichen Genauigkeitsstufen auszuwählen und zu testen, in  [!UICONTROL Audience Lab] welcher Benutzergruppe die Konvertierung besser ist. Weitere Informationen finden Sie im detaillierten Anwendungsfall unter [Vergleichen von Modellen in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models] wird das Modell alle 8 Tage ausgeführt und aktualisiert die für algorithmische Eigenschaften qualifizierten Benutzer.

### Eigenschaftenempfehlungen

[!UICONTROL Trait Recommendations] ist eine schnelle Möglichkeit, Einblicke in andere Eigenschaften zu erhalten, die den Eigenschaften in einem Segment ähnlich sind.

Verwenden Sie [!UICONTROL Trait Recommendations], wenn:

* Sie benötigen schnelle Einblicke beim Erstellen eines Segments.
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie schnell konvertierende Zielgruppen unterdrücken möchten.
* Sie versuchen, die Reichweite zu maximieren.

## Arbeitsablauf

Beim Erstellen oder Bearbeiten eines Segments in [Segmentaufbau](segment-builder.md) können Sie Eigenschaften, die den Eigenschaften in der Segmentregel ähneln, untersuchen. Der Arbeitsablauf [Segmentaufbau](segment-builder.md) ist für neue und vorhandene Segmente sehr ähnlich:

### Neue Segmente

1. Wechseln Sie zu **Audience Data > Segments** und klicken Sie auf **Hinzufügen New**.
1. Fügen Sie der Segmentregel im Dropdownfeld **Eigenschaften** mindestens eine Eigenschaft hinzu.
1. Sie können die von Erstanbietern empfohlenen Eigenschaften und die [!UICONTROL Audience Marketplace]-Eigenschaftsempfehlungen von Feeds sehen, die Sie abonniert haben, im Abschnitt **[!UICONTROL Recommendations]**. Der Abschnitt **[!UICONTROL Recommendations from Marketplace]** zeigt Empfehlungen zu Eigenschaften aus Feeds an, die Sie nicht abonniert haben. Alle diese Empfehlungen ähneln den Eigenschaften, die Sie der Segmentregel hinzugefügt haben. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Erstanbieter-Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das Symbol **X** für die Datenquellen, die Sie ausschließen möchten.

   >[!NOTE]
   >
   >Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Klicken Sie im grauen Feld auf **X**, um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
1. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+**.

>[!IMPORTANT]
>
>Wenn Sie einem Segment [!UICONTROL Marketplace]-Eigenschaften hinzufügen, werden die Eigenschaften nur für die Segmentschätzung verwendet, bis Sie den entsprechenden Datenfeed abonnieren. Eigenschaften, die aus nicht abonnierten Datenfeeds stammen, werden in der Liste &quot;Eigenschaften&quot;mit einem Warenkorbsymbol gekennzeichnet. Klicken Sie auf den Eigenschaftsnamen, um zur Data Feed-Seite zu wechseln und sie zu abonnieren.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Sie können ein Segment mit Eigenschaften von Drittanbietern erst speichern, nachdem Sie sich bei den entsprechenden Datenfeeds angemeldet haben.

### Vorhandene Segmente

1. Gehen Sie zu **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, wählen Sie das Segment, das Sie bearbeiten möchten, und klicken Sie auf ![Bearbeiten](assets/edit-button.png).
1. Blättern Sie nach unten zum Dropdown-Feld [!UICONTROL Traits].
1. Sie können empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die bereits in der Segmentregel enthalten sind. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das Symbol **X** für die Datenquellen, die Sie ausschließen möchten.

   >[!NOTE]
   >
   >Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Klicken Sie im grauen Feld auf **X**, um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
1. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+**.

Wenn Sie ein Segment erstellen oder bearbeiten und der Segmentregel eine Eigenschaft hinzufügen, sehen Sie maximal 50 empfohlene Eigenschaften, ähnlich denen, die Sie hinzugefügt haben. Wenn die Segmentregel mehr als eine Eigenschaft enthält, verwendet Audience Manager eine Round-Robin-Methode, um die beste Übereinstimmung für jede Eigenschaft anzuzeigen, dann die zweitbeste Übereinstimmung für jede Eigenschaft usw. für die größten fünfzig Eigenschaften nach Population in der Segmentregel.

![Drei Basiseigenschaften](assets/three-base-traits.png)

Wenn die Segmentregel z. B. drei Eigenschaften enthält, wie unten dargestellt, werden folgende Eigenschaften empfohlen:

1. Optimale Übereinstimmung für Eigenschaft 3 (die Eigenschaft mit der größten Population);
1. Optimale Übereinstimmung für Eigenschaft 1;
1. Optimale Übereinstimmung für Eigenschaft 2;
1. Zweitbeste Übereinstimmung für Eigenschaft 3;
1. Zweitbeste Übereinstimmung für Eigenschaft 1 usw., bis Sie zu fünfzig Eigenschaften gelangen.

Um Empfehlungen für eine bestimmte Eigenschaft abzurufen, können Sie auf die Eigenschaften in der Segmentregel (1) oder in der Ansicht der empfohlenen Eigenschaften (2) klicken.

![base-properties-Beispiel](assets/three-base-traits-numbered.png)

Wenn Sie auf eine Eigenschaft eines Erstanbieters klicken, wird ein Popup-Fenster geöffnet, wie in der Abbildung unten dargestellt. Wenn die empfohlenen Eigenschaften nicht Teil des Segments sind, können Sie sie dem Segment hinzufügen, indem Sie **+** drücken.

![add-to-segment](assets/add_to_segments.png)

>[!TIP]
>
>Die ausgeschlossenen Datenquellen der Hauptseite werden bei der Erstellung von Empfehlungen im Popup-Fenster &quot;Eigenschafteninformationen&quot;berücksichtigt. Wenn Sie Datenquellen in dieser Ansicht ausschließen, gelten die Ausschlüsse auch für die Hauptseite.

>[!NOTE]
>
>Empfohlene Eigenschaften können Ihre Eigenschaften von Erstanbietern oder Eigenschaften von Drittanbietern aus Datenfeeds sein, die Sie in [!UICONTROL Audience Marketplace] abonniert haben.

## Funktionsweise

Zur Erstellung von Eigenschaftsempfehlungen berechnet Audience Manager die [Jaccard-Ähnlichkeit](https://en.wikipedia.org/wiki/Jaccard_index) zwischen der Eigenschaft &quot;Zielgruppe&quot;und allen anderen Eigenschaften, auf die Ihr Konto zugreifen kann, einschließlich Drittanbieterdaten. Audience Manager zeigt dann bis zu fünfzig Eigenschaften mit der höchsten Ähnlichkeit an.

## Ähnlichkeitsbewertung der Eigenschaften {#trait-similarity-score}

Audience Manager berechnen die &lt; a0/> zwischen zwei Eigenschaften, indem sie die Schnittmenge und Vereinigung in Bezug auf die Anzahl der [!UICONTROL UUID]s berechnen und dann die beiden teilen. [!UICONTROL Trait Similarity Score] Für die beiden Eigenschaften A und B sieht die Berechnung wie folgt aus:

![jaccard-Ähnlichkeit](assets/jaccard_similarity.png)

Siehe auch die beiden folgenden Beispiele.

### Beispiel 1: Low-Trait-Ähnlichkeitsbewertung

Bei den beiden Eigenschaften A und B haben alle Eigenschaften eine Bevölkerung von 1.000.000 [!UICONTROL UUID]s, von denen 25.000 [!UICONTROL UUID]s für beide Eigenschaften qualifiziert sind.
Wenn Sie die obige Formel verwenden, führt dies zu Folgendem: 25.000 / 1.975.000 = 0,012. Dies ist ein niedriger [!UICONTROL Trait Similarity Score], die beiden Eigenschaften sind sehr unterschiedlich.

![Merkmal-Recommendations-low-überlappend](assets/Trait-Recommendations-Low-overlap.png)

### Beispiel 2 - Bewertung der Ähnlichkeit von Eigenschaften

Wenn dieselben Eigenschaften A und B 400.000 [!UICONTROL UUID]s hatten, die für beide Eigenschaften infrage kommen, ist das [!UICONTROL Trait Similarity Score] viel höher:
400.000 / 1.600.000 = 0,25

![Eigenschaften-Empfehlungen-hohe Überschneidung](assets/Trait-Recommendations-High-overlap.png)

### So interpretieren Sie die Eigenschafts-Ähnlichkeitsbewertung

Verwenden Sie die unten stehende Tabelle als grobe Hilfslinie, um Ähnlichkeiten zu erkennen. Dieser Leitfaden basiert auf den Ähnlichkeitswerten, die bei den meisten Eigenschaften beobachtet wurden.

| [!UICONTROL Trait Similarity Score] | Bedeutung |
---------|----------|
| 0.1 und höher | Hohe Ähnlichkeit zwischen Eigenschaften |
| 0.03 - 0.1 | Mittlere Ähnlichkeit zwischen Eigenschaften |
| 0.01 - 0.03 | Geringe Ähnlichkeit zwischen Eigenschaften |
| 0 - 0,01 | Sehr niedrige Ähnlichkeit zwischen Eigenschaften |

## Rollenbasierte Zugriffskontrolle (RBAC)

Für Firmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, benötigen Sie die Berechtigung zum Erstellen und Bearbeiten von Segmenten, um empfohlene Eigenschaften anzuzeigen. Die angezeigten Eigenschaftenempfehlungen sind nur diejenigen aus Datenquellen, auf die Sie über [!UICONTROL RBAC] zugreifen können.

>[!IMPORTANT]
>
>Um einem Segment [!UICONTROL Marketplace Recommendations] hinzuzufügen, müssen Benutzer zunächst die entsprechenden Datenfeeds abonnieren. Nur Benutzer mit Administratorrechten können [!UICONTROL Audience Marketplace]-Datenfeeds abonnieren.

Lesen Sie mehr über [!UICONTROL RBAC] Steuerelemente [hier](../administration/administration-overview.md).

## Einschränkungen

* Derzeit zeigt Audience Manager keine Ordnereigenschaften als empfohlene Eigenschaften an. Lesen Sie mehr über die Ordnereigenschaften [hier](../traits/manage-folder-traits.md).
* Bei der Anzeige von Trait Recommendations berücksichtigt Audience Manager die Operatoren [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) in Segmentregeln nicht.
