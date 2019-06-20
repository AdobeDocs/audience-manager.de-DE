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
Wenn [!UICONTROL Trait Recommendations]Sie ein Segment im [Segmentaufbau](segment-builder.md)erstellen oder bearbeiten, erhalten Sie Empfehlungen zu weiteren Eigenschaften, die Sie einbeziehen können, die den Eigenschaften in der Segmentregel ähneln. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.

![Übersicht über Recommendations-Empfehlungen](assets/trait-recommendations-overview.png)

**In einer Nutshell:**

* Audience Manager zeigt Eigenschaften von Erstanbietern und Drittanbietereigenschaften aus Ihren derzeit abonnierten Datenfeeds als Eigenschaften an.
* Audience Manager zeigt maximal fünfzig Eigenschaften an, die dem in der Segmentregel ähneln.
* Sie können die Datenquellen herausfiltern, aus denen keine Empfehlungen erscheinen sollen.
* Bei der Berechnung von Ähnlichkeiten berücksichtigt Audience Manager [uuids](../../reference/ids-in-aam.md) , die für die Eigenschaft in den letzten 30 Tagen qualifiziert waren.
* Wenn die Fehlermeldung &quot;Keine ähnlichen Eigenschaften gefunden&quot; angezeigt wird. Eigenschaften sind möglicherweise zu neu. &quot; Dies bedeutet, dass entweder in den letzten 30 Tagen keine Aktivitäten für diese Eigenschaft vorhanden waren oder Audience Manager die Empfehlungen für diese Eigenschaft noch nicht aktualisiert hat. Bitte erneut in 24 Stunden versuchen.

## Nutzungsszenarios

Mit [!UICONTROL Trait Recommendations]können Sie Ihre Workflows je nach Verwendung von Audience Manager verbessern:

* Als Marketingexperten können Sie Zielgruppen mit ähnlichen Eigenschaften schnell finden, um sich ergänzende Produkte mithilfe ähnlicher Eigenschaften anzusehen.
* Wenn Sie Audience Manager als Herausgeber verwenden, können [!UICONTROL Trait Recommendations]Sie das Zielgruppenverhalten verstehen und bessere Segmente für Anzeigenverkäufe oder Benutzerakquise erstellen.

## Unterschiede zwischen Eigenschaftenempfehlungen und algorithmischen Modellen

### Algorithmische Modelle

[!UICONTROL Algorithmic Models] nicht nur die einflussreichsten Eigenschaften findet, sondern auch Benutzer anhand dieser Eigenschaften auswertet und jedem Benutzer ein einzelnes Ergebnis zuweist. Anschließend erstellen Sie algorithmische Eigenschaften zur Ausrichtung Ihrer Benutzer. Mit Präzision und Reichweitesteuerung in können [!UICONTROL Trait Builder]Sie angeben, welche Benutzer alle Benutzer mit einflussreichen Eigenschaften als Ziel haben.

[!UICONTROL Algorithmic Models] ermöglicht es Ihnen, Benutzer auf unterschiedlichen Genauigkeitsstufen auszuwählen und zu testen, welche [!UICONTROL Audience Lab] Benutzergruppe besser konvertiert werden soll. Weitere Informationen finden Sie im detaillierten Verwendungsfall unter Modelle [vergleichen in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models]läuft das Modell alle 8 Tage ab und aktualisiert die Benutzer, die für algorithmische Eigenschaften qualifiziert sind.

### Trait Recommendations

[!UICONTROL Trait Recommendations] bietet eine schnelle Möglichkeit, Einblicke zu anderen Eigenschaften zu erhalten, die den in einem Segment verwendeten Ähneln.

Sie sollten Folgendes verwenden [!UICONTROL Trait Recommendations] :

* Sie benötigen beim Erstellen eines Segments schnelle Einblicke;
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Zielgruppe schnell unterdrücken möchten, die konvertiert.
* Sie versuchen, die Reichweite zu maximieren.

## Arbeitsablauf

Beim Erstellen oder Bearbeiten eines Segments im [Segmentaufbau](segment-builder.md)können Sie Eigenschaften ähnlich den Eigenschaften in der Segmentregel untersuchen. Der Segmentaufbau-Workflow ist für neue und vorhandene Segmente sehr ähnlich:

### Neue Segmente

1. Wählen Sie in **Zielgruppendaten &gt; Segmente** Neu **hinzufügen**.
1. Fügen Sie in der **Dropdown-Liste Eigenschaften** mindestens eine Eigenschaft zur Segmentregel hinzu.
1. Sie können nun empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die Sie der Segmentregel hinzugefügt haben. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das **X** -Symbol für die Datenquellen, die Sie ausschließen möchten.
   > [!NOTE]
   > 
   >Die ausgeschlossenen Datenquellen werden direkt oberhalb der Liste empfohlener Eigenschaften angezeigt. Drücken Sie im grauen Feld auf **X** , um die Ausnahmen zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut zu sehen.
1. Um die empfohlene Eigenschaft der Segmentregel hinzuzufügen, klicken Sie auf das **Symbol +** .

### Vorhandene Segmente

1. Wechseln **[!UICONTROL Audience Data]Sie zu &gt;[!UICONTROL Segments]**, wählen Sie das Segment aus, das Sie bearbeiten möchten, und klicken Sie auf ![Bearbeiten](assets/edit-button.png).
1. Blättern Sie nach unten zum [!UICONTROL Traits] Dropdown-Feld.
1. Sie können empfohlene Eigenschaften sehen, die den Eigenschaften ähnlich sind, die bereits in der Segmentregel enthalten sind. Blättern Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das **X** -Symbol für die Datenquellen, die Sie ausschließen möchten.
   > [!NOTE]
   > 
   >Die ausgeschlossenen Datenquellen werden direkt oberhalb der Liste empfohlener Eigenschaften angezeigt. Drücken Sie im grauen Feld auf **X** , um die Ausnahmen zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut zu sehen.
1. Um die empfohlene Eigenschaft der Segmentregel hinzuzufügen, klicken Sie auf das **Symbol +** .

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

Durch Klicken auf eine Eigenschaft wird ein Popup-Fenster geöffnet, wie im Bild unten dargestellt. Wenn die empfohlenen Eigenschaften nicht Teil des Segments sind, können Sie sie dem Segment durch Drücken von **+** hinzufügen.

![](assets/add_to_segments.png)

> [!TIP]
>
>Die ausgeschlossenen Datenquellen auf der Hauptseite werden bei der Erstellung von Empfehlungen innerhalb des Popupfensters für die Eigenschafteninformationen berücksichtigt. Wenn Sie Datenquellen in dieser Ansicht ausschließen, gelten die Ausnahmen für die Hauptseite.

> [!NOTE]
>
> Empfohlene Eigenschaften können Ihre Erstanbieter- oder Drittanbietereigenschaften aus Feeds sein, die Sie abonniert haben.

## Funktionsweise

Um Eigenschaften zu erzeugen, berechnet Audience Manager die [Jaccard-Ähnlichkeit](https://en.wikipedia.org/wiki/Jaccard_index) zwischen der Zieleigenschaft und allen anderen Eigenschaften, auf die Ihr Konto Zugriff hat, einschließlich Daten von Drittanbietern. Audience Manager zeigt dann bis zu fünfzig Eigenschaften mit der höchsten Ähnlichkeit an.

## Eigenschaften-Ähnlichkeitsbewertung

Audience Manager berechnet den Abstand [!UICONTROL Trait Similarity Score] zwischen zwei Eigenschaften, indem er die Schnittmenge und Vereinigung in Bezug auf die Anzahl [!UICONTROL UUID]der s berechnet und diese dann dividiert. Für zwei Eigenschaften A und B sieht die Berechnung wie folgt aus:

![](assets/jaccard_similarity.png)

Siehe auch die beiden unten stehenden Beispiele.

### Beispiel 1 - Ähnlichkeitsbewertung Niedrige Eigenschaften

Angenommen, die beiden Eigenschaften A und B besitzen eine Population von 1.000.000 [!UICONTROL UUID]s, 25.000 [!UICONTROL UUID]s, von denen beide Eigenschaften besitzen.
Mit der obigen Formel ergibt sich Folgendes Ergebnis: 25.000/1.975.000 = 0.012. Dies ist ein niedriger [!UICONTROL Trait Similarity Score], die beiden Eigenschaften sind sehr unterschiedlich.

![](assets/Trait-Recommendations-Low-overlap.png)

### Beispiel 2 - Eigenschaftsähnlichkeitsbewertung

Wenn dieselben Eigenschaften A und B 400.000 [!UICONTRL uuids]enthielten, die beide Eigenschaften erfüllen, ist der [!UICONTROL Trait Similarity Score] weitaus höhere Wert:
400.000/1.600.000 = 0.25

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

Für Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, müssen Sie berechtigt sein, Segmente zu erstellen und zu bearbeiten, um empfohlene Eigenschaften anzuzeigen. Und die empfohlenen Eigenschaften sind nur diejenigen aus Datenquellen, auf die Sie Zugriff [!UICONTROL RBAC]haben. Hier finden Sie weitere Informationen [!UICONTROL RBAC] zu den Steuerelementen [](../administration/administration-overview.md).

## Einschränkungen

* Derzeit zeigt Audience Manager keine Ordnereigenschaften als empfohlene Eigenschaften an. Weitere Informationen zu Ordnereigenschaften [](../traits/manage-folder-traits.md)finden Sie hier.
* Bei der Anzeige von Eigenschaften-Empfehlungen berücksichtigt Audience Manager [!DNL Boolean] keine Operatoren ([!DNL AND][!DNL OR], [!DNL NOT]) in Segmentregeln.