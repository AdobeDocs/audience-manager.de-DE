---
description: Wenn Sie in Trait Recommendations in Segment Builder ein Segment erstellen oder bearbeiten, erhalten Sie Empfehlungen zu zusätzlichen Merkmalen, die Sie einschließen können. Diese sind vergleichbar mit den Merkmalen in der Segmentregel. Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.
seo-description: Erhalten Sie beim Erstellen Ihrer Segmente Empfehlungen zu Live-Eigenschaften.
seo-title: Eigenschaftenempfehlungen
solution: Audience Manager
title: Eigenschaftenempfehlungen
feature: 'Segmente '
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# Eigenschaftenempfehlungen

Erhalten Sie Live-Eigenschaftenempfehlungen beim Erstellen Ihrer Segmente, ausgehend von Ihren eigenen Erstanbietereigenschaften und [!UICONTROL Audience Marketplace]-Daten-Feeds.

## Videodemonstration

Sehen Sie sich zunächst das Video [!UICONTROL Trait Recommendations] unten an und lesen Sie dann weitere Informationen. Die Videodemonstration zeigt Ihnen, wie Sie mit Empfehlungen aus Ihren eigenen Erstanbietereigenschaften sowie mit Eigenschaftsempfehlungen aus [!UICONTROL Audience Marketplace] -Daten-Feeds arbeiten können, die *Sie bereits für* abonniert haben.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

Im nächsten Video wird der Arbeitsablauf für [!UICONTROL Marketplace Recommendations] beschrieben, in dem Sie anhand von Empfehlungen aus Daten-Feeds in [!UICONTROL Audience Marketplace] zeigen, wie Sie Ihren Segmenten Eigenschaften hinzufügen können. Diese Empfehlungen basieren auf Daten-Feeds, die *Sie nicht für* abonniert haben.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Überblick

[!UICONTROL Trait Recommendations], gestützt auf  [!DNL Adobe Sensei], bringt die Datenwissenschaft in Ihre alltäglichen Audience Manager-Workflows.
Bei [!UICONTROL Trait Recommendations] erhalten Sie beim Erstellen oder Bearbeiten eines Segments in [Segment Builder](segment-builder.md) Empfehlungen zu zusätzlichen Eigenschaften, die Sie einbeziehen können, die den Eigenschaften in der Segmentregel ähnlich sind.

In Audience Manager werden Eigenschaftsempfehlungen sowohl aus Ihren Erstanbietereigenschaften im Abschnitt **[!UICONTROL Recommendations]** als auch aus **[!UICONTROL Audience Marketplace]** im Abschnitt **[!UICONTROL Recommendations from Marketplace]** angezeigt.

Fügen Sie die empfohlenen Merkmale zu Ihrem Segment hinzu, um Ihre Zielgruppe zu erweitern.

![Übersicht über Trait Recommendations](assets/trait-recommendations-overview-full.png)

**Kurz gesagt:**

* Audience Manager zeigt Erstanbietereigenschaften im Abschnitt [!UICONTROL Recommendations] an. Empfehlungen von Marketplace aus öffentlichen und privaten Feeds, die Sie nicht abonniert haben, sind im Abschnitt [!UICONTROL Recommendations from Marketplace] sichtbar. Klicken Sie auf den Feed-Namen, um zu [!UICONTROL Audience Marketplace] zu wechseln und zu abonnieren.
* Audience Manager zeigt maximal fünfzig Eigenschaften an, die denen in der Segmentregel ähneln.
* Sie können die Datenquellen herausfiltern, aus denen keine Empfehlungen angezeigt werden sollen.
* Beim Berechnen der Ähnlichkeiten berücksichtigt der Audience Manager [UUIDs](../../reference/ids-in-aam.md) , die sich in den letzten 30 Tagen für die Eigenschaft qualifiziert haben.
* Wenn Sie die Fehlermeldung &quot;Keine ähnlichen Eigenschaften gefunden. Eigenschaften können zu neu sein.&quot; bedeutet dies, dass es in den letzten 30 Tagen entweder keine Aktivität für diese Eigenschaft gab oder Audience Manager die Empfehlungen für diese Eigenschaft noch nicht aktualisiert hat. Bitte versuchen Sie es in 24 Stunden erneut.

## Nutzungsszenarios

Mit [!UICONTROL Trait Recommendations] können Sie Ihre Workflows je nach Verwendung von Audience Manager verbessern:

* Marketingexperten können mithilfe ähnlicher Eigenschaften schnell Zielgruppen finden, die sich für komplementäre Produkte interessieren, sodass Sie Ihre Reichweite erhöhen können.
* Wenn Sie Audience Manager als Publisher mit [!UICONTROL Trait Recommendations] verwenden, können Sie das Zielgruppenverhalten verstehen und bessere Segmente für Anzeigenverkäufe oder Benutzerakquise erstellen.
* Als [!UICONTROL Audience Marketplace] Datenkäufer möchte ich relevante Drittanbieterdaten ermitteln, ohne eine große Anzahl von Feeds durchsuchen zu müssen.
* Als [!UICONTROL Audience Marketplace] Datenanbieter möchte ich Käufern relevante Daten empfehlen, damit ich von optimalen und relevanten Abonnements profitieren kann.

## Unterschiede zwischen Trait Recommendations und algorithmischen Modellen

### Algorithmische Modelle

[!UICONTROL Algorithmic Models] findet nicht nur die einflussreichsten Eigenschaften, sondern bewertet auch Benutzer anhand dieser Eigenschaften und weist jedem Benutzer ein individuelles Ergebnis zu. Anschließend erstellen Sie algorithmische Eigenschaften, um Ihre Benutzer anzusprechen. Mit den Genauigkeits- und Reichweitenkontrollen im [!UICONTROL Trait Builder] können Sie festlegen, welche Benutzer unter all jenen mit den einflussreichen Eigenschaften Sie als Ziel auswählen möchten.

[!UICONTROL Algorithmic Models] ermöglicht es Ihnen, Benutzer mit unterschiedlichen Genauigkeitsstufen auszuwählen und zu testen, in  [!UICONTROL Audience Lab] welcher Benutzergruppe die Konvertierung besser ist. Weitere Informationen finden Sie im detaillierten Anwendungsfall unter [Vergleichen von Modellen in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models] wird das Modell alle 8 Tage ausgeführt und aktualisiert die für algorithmische Eigenschaften qualifizierten Benutzer.

### Eigenschaftenempfehlungen

[!UICONTROL Trait Recommendations] ist eine schnelle Möglichkeit, Einblicke in andere Eigenschaften zu erhalten, die den Eigenschaften ähneln, die Sie in einem Segment verwenden.

Sie sollten [!UICONTROL Trait Recommendations] verwenden, wenn:

* Sie benötigen schnelle Einblicke beim Erstellen eines Segments.
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie schnell konvertierende Zielgruppen unterdrücken möchten.
* Sie versuchen, die Reichweite zu maximieren.

## Arbeitsablauf

Beim Erstellen oder Bearbeiten eines Segments in [Segment Builder](segment-builder.md) können Sie Eigenschaften analysieren, die den Eigenschaften in der Segmentregel ähneln. Der Workflow [Segment Builder](segment-builder.md) ähnelt sehr dem für neue und vorhandene Segmente:

### Neue Segmente

1. Gehen Sie zu **Zielgruppendaten > Segmente** und klicken Sie auf **Neu hinzufügen**.
1. Fügen Sie der Segmentregel im Dropdown-Feld **Eigenschaften** mindestens eine Eigenschaft hinzu.
1. Sie können die von Erstanbietern empfohlenen Eigenschaften und die [!UICONTROL Audience Marketplace]-Eigenschaftenempfehlungen aus Feeds sehen, die Sie abonniert haben, im Abschnitt **[!UICONTROL Recommendations]** . Im Abschnitt **[!UICONTROL Recommendations from Marketplace]** werden Eigenschaftsempfehlungen aus Feeds angezeigt, die Sie nicht abonniert haben. Alle diese Empfehlungen ähneln den Eigenschaften, die Sie der Segmentregel hinzugefügt haben. Scrollen Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Erstanbietereigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das Symbol **X** für die Datenquellen, die Sie ausschließen möchten.

   >[!NOTE]
   >
   >Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Klicken Sie im grauen Feld auf **X**, um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
1. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+**.

>[!IMPORTANT]
>
>Beim Hinzufügen von [!UICONTROL Marketplace]-Eigenschaften zu einem Segment werden die Eigenschaften nur für die Segmentschätzung verwendet, bis Sie den entsprechenden Daten-Feed abonnieren. Eigenschaften, die aus Daten-Feeds stammen, die Sie nicht abonniert haben, werden in der Eigenschaftsliste mit einem Warenkorbsymbol markiert. Klicken Sie auf den Eigenschaftsnamen, um zur Daten-Feed-Seite zu gelangen und sie zu abonnieren.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Sie können ein Segment mit Eigenschaften von Drittanbietern erst speichern, nachdem Sie sich bei den entsprechenden Daten-Feeds angemeldet haben.

### Vorhandene Segmente

1. Gehen Sie zu **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, wählen Sie das Segment aus, das Sie bearbeiten möchten, und klicken Sie auf ![Bearbeiten](assets/edit-button.png).
1. Scrollen Sie nach unten zum Dropdown-Feld [!UICONTROL Traits].
1. Sie können empfohlene Eigenschaften sehen, die den Eigenschaften ähneln, die bereits in der Segmentregel enthalten sind. Scrollen Sie nach unten, um alle empfohlenen Eigenschaften anzuzeigen.
1. (Optional) Um empfohlene Eigenschaften aus bestimmten Datenquellen auszuschließen, klicken Sie auf das Symbol **X** für die Datenquellen, die Sie ausschließen möchten.

   >[!NOTE]
   >
   >Die ausgeschlossenen Datenquellen werden direkt über der Liste der empfohlenen Eigenschaften angezeigt. Klicken Sie im grauen Feld auf **X**, um die Ausschlüsse zu entfernen und die Ergebnisse aus den entsprechenden Datenquellen erneut anzuzeigen.
1. Um der Segmentregel empfohlene Eigenschaften hinzuzufügen, klicken Sie auf das Symbol **+**.

Wenn Sie ein Segment erstellen oder bearbeiten und der Segmentregel eine Eigenschaft hinzufügen, werden Ihnen maximal fünfzig empfohlene Eigenschaften angezeigt, die der von Ihnen hinzugefügten ähneln. Wenn die Segmentregel mehr als eine Eigenschaft enthält, verwendet Audience Manager eine Round-Robin-Methode, um die beste Übereinstimmung für jede Eigenschaft anzuzeigen, dann die zweitbeste Übereinstimmung für jede Eigenschaft usw. für die fünfzig größten Eigenschaften nach Population in der Segmentregel.

![Drei Basiseigenschaften](assets/three-base-traits.png)

Wenn die Segmentregel beispielsweise drei Eigenschaften enthält, wie unten dargestellt, werden folgende Eigenschaften empfohlen:

1. Optimale Übereinstimmung für Eigenschaft 3 (die Eigenschaft mit der größten Population);
1. Best Match für Eigenschaft 1;
1. beste Übereinstimmung für Eigenschaft 2;
1. Zweitbeste Übereinstimmung für Eigenschaft 3;
1. Zweitbeste Übereinstimmung für Eigenschaft 1 usw., bis Sie zu fünfzig Eigenschaften gelangen.

Um Empfehlungen für eine bestimmte Eigenschaft abzurufen, können Sie auf die Eigenschaften in der Segmentregel (1) oder in der empfohlenen Eigenschaftenansicht (2) klicken.

![base-traits-example](assets/three-base-traits-numbered.png)

Wenn Sie auf eine Erstanbietereigenschaft klicken, wird ein Popup-Fenster geöffnet, wie in der Abbildung unten dargestellt. Wenn die empfohlenen Eigenschaften nicht Teil des Segments sind, können Sie sie dem Segment hinzufügen, indem Sie **+** drücken.

![Add-to-Segment](assets/add_to_segments.png)

>[!TIP]
>
>Die ausgeschlossenen Datenquellen aus der Hauptseite werden beim Generieren von Empfehlungen im Popup-Fenster mit Eigenschafteninformationen berücksichtigt. Wenn Sie Datenquellen in dieser Ansicht ausschließen, gelten die Ausschlüsse auch für die Hauptseite.

>[!NOTE]
>
>Empfohlene Eigenschaften können Ihre Erstanbietereigenschaften oder Eigenschaften von Drittanbietern aus Daten-Feeds sein, die Sie in [!UICONTROL Audience Marketplace] abonniert haben.

## Funktionsweise

Um Eigenschaftsempfehlungen zu erstellen, berechnet Audience Manager die [Jaccard-Ähnlichkeit](https://en.wikipedia.org/wiki/Jaccard_index) zwischen der Zieleigenschaft und allen anderen Eigenschaften, auf die Ihr Konto Zugriff hat, einschließlich Drittanbieterdaten. Audience Manager zeigt dann bis zu fünfzig Eigenschaften an, die die höchste Ähnlichkeit aufweisen.

## Ähnlichkeitsbewertung von Eigenschaften {#trait-similarity-score}

Audience Manager berechnen das [!UICONTROL Trait Similarity Score] zwischen zwei Eigenschaften, indem sie die Schnittmenge und Vereinigung anhand der Anzahl der [!UICONTROL UUID]s berechnen und dann die beiden teilen. Für zwei Eigenschaften A und B sieht die Berechnung wie folgt aus:

![jaccard-similarity](assets/jaccard_similarity.png)

Siehe auch die beiden folgenden Beispiele.

### Beispiel 1: Geringe Trait-Ähnlichkeitsbewertung

Bei zwei Eigenschaften A und B, nehmen wir an, dass jede Eigenschaft eine Population von 1.000.000 [!UICONTROL UUID]s hat, von denen 25.000 [!UICONTROL UUID]s für beide Eigenschaften qualifiziert sind.
Mit der obigen Formel führt dies zu Folgendem: 25.000 / 1.975.000 = 0.012. Dies ist ein niedriger Wert [!UICONTROL Trait Similarity Score], die beiden Eigenschaften sind sehr unähnlich.

![Eigenschaftenempfehlungen-niedrige Überschneidung](assets/Trait-Recommendations-Low-overlap.png)

### Beispiel 2: Bewertung der Ähnlichkeit von Eigenschaften

Wenn dieselben Eigenschaften A und B 400.000 [!UICONTROL UUID]s aufweisen, die für beide Eigenschaften qualifiziert sind, ist [!UICONTROL Trait Similarity Score] viel höher:
400.000 / 1.600.000 = 0,25

![Eigenschaftenempfehlungen - hohe Überschneidung](assets/Trait-Recommendations-High-overlap.png)

### Interpretieren der Eigenschaftsähnlichkeitsbewertung

Verwenden Sie die nachstehende Tabelle als grobe Anleitung zur Ähnlichkeit von Eigenschaften. Dieses Handbuch basiert auf den Ähnlichkeitswerten, die bei den meisten Eigenschaften beobachtet wurden.

| [!UICONTROL Trait Similarity Score] | Signifikanz |
|---------|----------|
| 0.1 und höher | Hohe Ähnlichkeit zwischen Eigenschaften |
| 0,03 - 0,1 | Mittlere Ähnlichkeit zwischen Eigenschaften |
| 0.01 - 0.03 | Geringe Ähnlichkeit zwischen Eigenschaften |
| 0-0,01 | Sehr geringe Ähnlichkeit zwischen Eigenschaften |

## Rollenbasierte Zugriffssteuerung (RBAC)

Für Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, benötigen Sie die Berechtigung zum Erstellen und Bearbeiten von Segmenten, um die empfohlenen Eigenschaften anzuzeigen. Die Eigenschaftenempfehlungen, die Sie sehen, sind nur diejenigen aus Datenquellen, auf die Sie über [!UICONTROL RBAC] zugreifen können.

>[!IMPORTANT]
>
>Um [!UICONTROL Marketplace Recommendations] zu einem Segment hinzuzufügen, müssen Benutzer zunächst die entsprechenden Daten-Feeds abonnieren. Nur Benutzer mit Administratorrechten können [!UICONTROL Audience Marketplace]-Daten-Feeds abonnieren.

Weitere Informationen zu [!UICONTROL RBAC] Steuerelementen [hier](../administration/administration-overview.md).

## Einschränkungen

* Derzeit zeigt Audience Manager Ordnereigenschaften nicht als empfohlene Eigenschaften an. Weitere Informationen zu Ordnereigenschaften [hier](../traits/manage-folder-traits.md).
* Bei der Anzeige von Trait Recommendations berücksichtigt Audience Manager die [!DNL Boolean]-Operatoren ([!DNL AND], [!DNL OR], [!DNL NOT]) in Segmentregeln nicht.
