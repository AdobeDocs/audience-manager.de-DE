---
description: Ein Daten-Feed erfordert einen Namen, eine Beschreibung, eine Datenquelle und einen Plantyp. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Daten-Feeds unter Audience Marketplace > Meine freigegebenen Daten ein. Nur für Datenverkäufer verfügbar.
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: Erstellen, Bewerten und Verwalten von Daten-Feeds
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 1%

---

# Erstellen, Bewerten und Verwalten von Daten-Feeds {#create-price-and-manage-data-feeds}

## Erstellen eines öffentlichen oder privaten Daten-Feeds {#create-public-private-data-feed}

Ein Daten-Feed erfordert einen Namen, eine Beschreibung, eine Datenquelle und einen Plantyp. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie in **[!UICONTROL Audience Marketplace > My Shared Data]** öffentliche oder private Daten-Feeds ein. Nur für Datenverkäufer verfügbar.

<!-- t_data_feed.xml -->

Sie müssen über Administratorrechte verfügen, um einen öffentlichen oder privaten Daten-Feed zu erstellen.
Erstellen eines Daten-Feeds:

1. Klicken Sie auf **[!UICONTROL New Data Feed]**.
1. Benennen Sie den Daten-Feed. Datenkäufer können anhand des Namens nach Ihrem Feed suchen.
1. Geben Sie eine kurze Beschreibung ein (maximal 255 Zeichen).

   Eine gute Beschreibung sollte Ihren Feed genau beschreiben. Sie können beispielsweise Text für Marketing-Kategorien, Demografie und geografische Abdeckung (z. B. [!DNL US] oder Nordamerika) einbeziehen. Beschreibungstext ist durchsuchbar und hilft Käufern, Ihren Feed zu finden oder zu bewerten. Eine gute Beschreibung ist ein wichtiger Teil, um Abonnentinnen und Abonnenten für Ihren Daten-Feed zu gewinnen.
1. Wählen Sie eine Datenquelle aus den **[!UICONTROL Data Source]**. Daten-Feeds sind auf eine einzige Datenquelle beschränkt. Diesem Daten-Feed können nicht mehrere Datenquellen zugewiesen werden.

   >[!IMPORTANT]
   >
   >Alle aktuellen und zukünftigen Eigenschaften, die zu dieser Datenquelle gehören, werden als Teil dieses Feeds mit Ihren Datenkäufern geteilt.

1. Wählen Sie [!UICONTROL Plan Types] die gewünschten Optionen aus und klicken Sie auf **[!UICONTROL Add Plan]**.

   Feeds können mehrere Pläne enthalten. Pläne können mehrere Anwendungsfälle enthalten. Weitere Informationen finden Sie [Plantypen für Daten-Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Klicken Sie auf **[!UICONTROL Save]** , um Ihren Daten-Feed zu speichern *ohne* zu aktivieren.
1. Speichern und Aktivieren eines Daten-Feeds:
   1. Schieben Sie den **[!UICONTROL Availability]** auf **[!UICONTROL Active]**.
   1. Klicken Sie auf **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Gespeicherte und aktivierte Daten-Feeds können nicht gelöscht werden.
   >* Käufer sehen nur aktive Feeds.

### Optional: Erstellen eines privaten Daten-Feeds

Bewegen Sie den Schieberegler im [!UICONTROL Settings] Abschnitt zu:

* **[!UICONTROL Private]** und **[!UICONTROL Branded]**: Die [!UICONTROL Marketplace] des Käufers zeigt den Namen des Verkäufers in der Spalte Anbieter an und alle anderen Daten sind ausgeblendet.

* **[!UICONTROL Private]** und **[!UICONTROL Unbranded]**: In der [!UICONTROL Marketplace] des Käufers werden nur der Name und die Beschreibung des Daten-Feeds angezeigt. Der Name des Datenanbieters wird als [!UICONTROL Private Seller] angezeigt.

Informationen dazu, wie ein privater Feed für Käufer aussieht, finden Sie im Abschnitt zu Käufern in [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Deaktivieren des Daten-Feeds eines Abonnenten {#deactivate-data-feed}

Als [!UICONTROL Audience Marketplace] Datenanbieter können Sie den Käuferzugriff auf einen abonnierten Daten-Feed sperren. Möglicherweise möchten Sie einen Käufer aus einem Feed entfernen, z. B. wegen verspäteter Zahlung/Nichtzahlung von Gebühren oder wenn er Eigenschaftendaten falsch verwendet.

<!-- marketplace-deactiva4te-subscribers.xml -->

So widerrufen Sie einen Abonnenten:

1. Suchen Sie [!UICONTROL My Shared Data] den Feed, den der Abonnent verwendet.

   >[!NOTE]
   >
   >Daten-Feeds mit überfälligen Konten werden mit einem Dreieck-/Ausrufezeichen-Symbol gekennzeichnet.

1. Klicken Sie in der Spalte [!UICONTROL Subscribers] auf die blaue Zahl, die die Abonnenten für diesen Feed zählt. Dadurch wird die Seite mit den Abonnementdetails geöffnet.
1. Schieben Sie den **[!UICONTROL Subscription]** auf **[!UICONTROL Off]**. Dadurch wird ein Bestätigungsdialogfeld geöffnet.
1. Klicken Sie im [!UICONTROL Confirmation]-Pop auf **[!UICONTROL Yes]** , um ein Abonnement zu deaktivieren, oder auf **[!UICONTROL Cancel]** , um zu beenden, ohne Abonnementänderungen vorzunehmen.

### Was passiert, nachdem ein Abonnent deaktiviert wurde?

Wenn Sie den Zugriff auf einen Daten-Feed sperren, erhalten alle Admin-Benutzer im Konto des Käufers eine Benachrichtigungs-E-Mail. Die E-Mail enthält einen Anhang, in dem die widerrufenen Eigenschaften aufgeführt sind. Diese Liste hilft Abonnentinnen und Abonnenten, deaktivierte Eigenschaften in ihren Segmenten und Modellen zu finden und zu entfernen.

### Abrechnung und Deaktivierung von Feeds

Nachdem Sie den Zugriff auf einen Daten-Feed entfernt haben, sind Abonnentinnen und Abonnenten für die Gebühren des vorherigen oder aktuellen Monats verantwortlich, je nachdem, wann Sie den Feed deaktiviert haben.

## Plantypen für Daten-Feeds {#plan-types}

[!DNL Plan types] sind wesentliche Komponenten eines [!UICONTROL Audience Marketplace] Daten-Feeds. Als Datenanbieter können Sie damit mehrere Anwendungsfälle und Preisoptionen für Ihre Feeds erstellen. Darüber hinaus kann es eine gute Strategie sein, für jeden Daten-Feed einige Pläne zu erstellen. Dies bietet Käufern verschiedene Optionen, aus denen sie auswählen können, wenn sie nach Daten suchen, die sie modellieren oder an ein Ziel senden möchten.

[Erstellen eines Daten-Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) um [!UICONTROL Plan Types] auszuwählen.

![](assets/plan_types.png)

## Plantypen und Optionen für Anwendungsfälle {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Mit den [!UICONTROL Use Case] können Verkäufer steuern, wie Käufer Ihre Daten verwenden können.

### Segmente und Überschneidungen

Bei einem **[!UICONTROL Segments and Overlap]** Anwendungsfall wird ein Plan erstellt, mit dem Käufer Eigenschaftsdaten in einem &quot;[-zu-Eigenschaft-Überschneidungsbericht“ ](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) können. Darüber hinaus können Käufer Ihre Daten zu Segmenten hinzufügen und Vergleiche mit den Berichten [Segment-zu-Eigenschaft](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) und [Segment-zu-Segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) vornehmen.

Jeder Daten-Feed muss mindestens einen [!UICONTROL Segments and Overlap] Anwendungsfall enthalten. Käufer können keine anderen Pläne in einem Daten-Feed abonnieren, wenn der Feed keinen [!UICONTROL Segments and Overlap] Anwendungsfall enthält, entweder allein oder in Kombination mit einem anderen Anwendungsfall.

Überschneidungsvergleiche können Käufern helfen:

* **Reichweite der Zielgruppe erweitern** Geringe Überschneidungen deuten darauf hin, dass Ihre Eigenschaften Benutzer enthalten, die der Käufer noch nie gesehen hat. Daher möchten Käufer möglicherweise, dass diese Eigenschaften neue Benutzende zu ihren Zielgruppensegmenten hinzufügen.
* **Verbessern vorhandener Zielgruppen:** hohe Überschneidung deutet darauf hin, dass Ihre Eigenschaften Benutzer enthalten, die denen ähneln, die ein Käufer bereits kennt. Daher wünschen sich Käufer möglicherweise, dass diese Eigenschaften zielgerichtete, inkrementelle Verbesserungen an den entwickelten Zielgruppen vornehmen.

Bewerten Sie diesen Anwendungsfall wie folgt:

* Maßeinheit: Pauschalgebühr
* Preis: Kostenlos ($0.00)

### Modellierung

Bei einem **[!UICONTROL Modeling]** Anwendungsfall wird ein Plan erstellt, mit dem Käufer Ihre Eigenschaften mit ihren vergleichen können [algorithmische Modellierung](../../../features/algorithmic-models/understanding-models.md#understanding-models). Käufer schauen sich die Modellergebnisse an, um neue Zielgruppen in Ihren Daten zu finden, die ähnliche Konversionsattribute wie ihre eigenen aufweisen. Bewerten Sie diesen Anwendungsfall wie folgt:

* Maßeinheit: Pauschalgebühr
* Preis: Rabatt oder Marktpreis

### Aktivierung

Ein **[!UICONTROL Activation]** Anwendungsfall ermöglicht es Käufern, Daten an ein [Ziel“ ](../../../features/destinations/destinations.md) senden. Bei diesem Anwendungsbeispiel können Käufer keine Daten mit einem Überschneidungsbericht oder in einem algorithmischen Modell vergleichen. Bewerten Sie diesen Anwendungsfall wie folgt:

* Maßeinheit: [!DNL CPM]
* Preis: [!DNL CPM] Marktpreis

## Abrechnungs- und Preisoptionen {#billing}

Die Abrechnungs- und Preisoptionen steuern, wie Käufer für Ihre Daten zahlen.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Abrechnungszyklus</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Monatlich im Rückstand</span></b> ist die einzige Option. Der Abrechnungszyklus endet am 10. Tag jedes Monats. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Maßeinheit</span></b> </td> 
   <td colname="col2">Datenkäufer müssen eine CPM-Gebühr oder Pauschalgebühr berechnen. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Bei der Preisgestaltung für CPM müssen Datenerwerber die Nutzung selbst melden. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Bei Flatfee-Preisen melden Datenkäufer keine Nutzung, da ihnen ein fester Tarif berechnet wird. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preis</span></b> </td>
   <td colname="col2"> Der Betrag, den ein Verkäufer dem Käufer als CPM-Tarif oder Pauschalgebühr in Dollar berechnet. </td>
  </tr> 
 </tbody> 
</table>

## Planhinweise {#plan-notes}

Nehmen Sie sich im Feld **[!UICONTROL Additional Notes]** etwas Zeit, um jeden Datenplan in einem Feed zu beschreiben. Eine gute, kurze Beschreibung hilft Käufern, den Inhalt oder den Zweck jedes Plans in einem Daten-Feed zu verstehen. Käufer können bei der Suche oder Auswertung neuer Datenquellen Daten-Feed- und Planbeschreibungen lesen.

## Verwalten privater Daten-Feed-Anfragen {#manage-private-requests}

Provider-Workflows für die Verwaltung privater Feed-Anfragen von Käufern.

Um Käuferanfragen zu überprüfen, zu genehmigen oder abzulehnen, navigieren Sie zu [!UICONTROL My Shared Data] und:

<!-- t_private_feed_workflows.xml -->

1. Klicken Sie auf den Namen des privaten Daten-Feeds.
2. Klicken Sie auf **[!UICONTROL Access Requests]** , um alle Käufer zu überprüfen, die Zugriff auf Ihren Daten-Feed wünschen.
3. Klicken Sie im Abschnitt [!UICONTROL Allow Access] jeder Anfrage auf das Häkchen, um eine Anfrage zu genehmigen, oder auf das X, um den Zugriff zu verweigern.
4. Bestätigen oder brechen Sie die ausgewählte Aktion im Bestätigungs-Popup ab.

## Rabatte für Datenanbieter {#discounts}

[!UICONTROL Audience Marketplace] können Sie mit Rabatten den veröffentlichten Preis eines Daten-Feeds für einzelne Abonnenten senken. Sie können Abonnentinnen und Abonnenten, die eine Abonnementanfrage gesendet haben, oder Abonnentinnen und Abonnenten, die Details zu einem Daten-Feed angefordert haben, Rabatte anbieten. Rabatte gelten für [!DNL CPM]- und Pauschalangebote. Rabatte können hilfreich sein, wenn Sie Neukunden Abonnementanreize bieten oder die Kundentreue belohnen möchten.

## Anwenden von Rabatten auf einen Daten-Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Um einen Feed zu rabattieren, fügen Sie dem Rabattfeld einen Rabattbetrag in % hinzu und bestätigen Sie Ihre Änderungen. Datenanbieter können Daten-Feeds in [!UICONTROL Audience Marketplace] wie folgt reduzieren:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In diesen Beispielen hat der Verkäufer dem [!UICONTROL Software Audience]-Daten-Feed 10 % Rabatt hinzugefügt.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Ermäßigte Feeds überprüfen {#review-discounted-feeds}

Datenanbieter können alle ihre Abonnenten und ermäßigten Feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]** sehen.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md)
