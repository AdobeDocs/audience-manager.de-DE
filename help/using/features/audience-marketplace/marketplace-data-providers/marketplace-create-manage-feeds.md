---
description: Ein Daten-Feed erfordert einen Namen, eine Beschreibung, eine Datenquelle und einen Planungstyp. Feeds werden deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Daten-Feeds in Audience Marketplace > Meine freigegebenen Daten ein. Nur für Datenverkäufer verfügbar.
seo-description: Ein Daten-Feed erfordert einen Namen, eine Beschreibung, eine Datenquelle und einen Planungstyp. Feeds werden deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Daten-Feeds in Audience Marketplace > Meine freigegebenen Daten ein. Nur für Datenverkäufer verfügbar.
seo-title: Erstellen, Bewerten und Verwalten von Daten-Feeds
solution: Audience Manager
title: Erstellen, Bewerten und Verwalten von Daten-Feeds
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 2%

---

# Erstellen, Bewerten und Verwalten von Daten-Feeds {#create-price-and-manage-data-feeds}

## Erstellen eines öffentlichen oder privaten Daten-Feeds {#create-public-private-data-feed}

Ein Daten-Feed erfordert einen Namen, eine Beschreibung, eine Datenquelle und einen Planungstyp. Feeds werden deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Daten-Feeds in **[!UICONTROL Audience Marketplace > My Shared Data]** ein. Nur für Datenverkäufer verfügbar.

<!-- t_data_feed.xml -->

Sie müssen über Administratorrechte verfügen, um einen öffentlichen oder privaten Daten-Feed zu erstellen.
So erstellen Sie einen Daten-Feed:

1. Klicken **[!UICONTROL New Data Feed]**.
1. Benennen Sie den Daten-Feed. Datenkäufer können anhand des Namens nach Ihrem Feed suchen.
1. Geben Sie eine kurze Beschreibung ein (maximal 255 Zeichen).

   Eine gute Beschreibung sollte Ihren Feed genau beschreiben. Sie können beispielsweise Text für Marketing-Kategorien, demografische Daten und die geografische Abdeckung einbeziehen (z. B. [!DNL US] oder Nordamerika). Der Beschreibungstext ist durchsuchbar und hilft Käufern, Ihren Feed zu finden oder zu bewerten. Eine gute Beschreibung ist ein wichtiger Bestandteil der Attraktivität für Abonnenten Ihres Daten-Feeds.
1. Wählen Sie in den **[!UICONTROL Data Source]** -Optionen eine Datenquelle aus. Daten-Feeds sind auf eine einzige Datenquelle beschränkt. Diesem Daten-Feed können nicht mehrere Datenquellen zugewiesen werden.

   >[!IMPORTANT]
   >
   >Alle aktuellen und zukünftigen Eigenschaften, die zu dieser Datenquelle gehören, werden als Teil dieses Feeds mit Ihren Datenkäufern geteilt.

1. Wählen Sie in [!UICONTROL Plan Types] die gewünschten Optionen aus und klicken Sie auf **[!UICONTROL Add Plan]**.

   Feeds können mehrere Pläne enthalten. Pläne können mehrere Anwendungsfälle enthalten. Weitere Informationen finden Sie unter [Plantypen für Daten-Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Klicken Sie auf **[!UICONTROL Save]** , um Ihren Daten-Feed *zu speichern, ohne* zu aktivieren.
1. So speichern und aktivieren Sie einen Daten-Feed:
   1. Verschieben Sie den Regler **[!UICONTROL Availability]** auf **[!UICONTROL Active]**.
   1. Klicken **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Gespeicherte und aktivierte Daten-Feeds können nicht gelöscht werden.
   >* Käufer sehen nur aktive Feeds.


### Optional: Erstellen eines privaten Daten-Feeds

Verschieben Sie im Abschnitt [!UICONTROL Settings] den Regler zu:

* **[!UICONTROL Private]** und  **[!UICONTROL Branded]**: Die  [!UICONTROL Marketplace] Liste des Käufers zeigt den Namen des Verkäufers in der Spalte &quot;Anbieter&quot;an und alle anderen Daten sind ausgeblendet.

* **[!UICONTROL Private]** und  **[!UICONTROL Unbranded]**: Die  [!UICONTROL Marketplace] Liste des Käufers enthält nur den Daten-Feed-Namen und die Beschreibung. Der Name des Datenanbieters wird als [!UICONTROL Private Seller] angezeigt.

Informationen dazu, wie private Feeds für Käufer aussehen, finden Sie im Abschnitt &quot;Käufer&quot;unter [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Deaktivieren des Daten-Feeds eines Abonnenten {#deactivate-data-feed}

Als [!UICONTROL Audience Marketplace]-Datenanbieter können Sie den Käuferzugriff auf einen abonnierten Daten-Feed widerrufen. Sie können einen Käufer aus einem Feed entfernen, wenn er z. B. verspätete Zahlung/Nichtbezahlung von Gebühren oder unsachgemäße Verwendung von Eigenschaftsdaten erfolgt.

<!-- marketplace-deactiva4te-subscribers.xml -->

So widerrufen Sie einen Abonnenten:

1. Suchen Sie in [!UICONTROL My Shared Data] den Feed, den der Abonnent verwendet.

   >[!NOTE]
   >
   >Daten-Feeds mit überfälligen Konten werden mit einem Dreieck-/Ausrufezeichen-Symbol gekennzeichnet.

1. Klicken Sie in der Spalte [!UICONTROL Subscribers] auf die blaue Zahl, die Abonnenten für diesen Feed zählt. Dadurch wird die Seite mit den Abonnementdetails geöffnet.
1. Verschieben Sie den Regler **[!UICONTROL Subscription]** auf **[!UICONTROL Off]**. Dadurch wird ein Bestätigungsdialogfenster geöffnet.
1. Klicken Sie im Pop-up [!UICONTROL Confirmation] auf **[!UICONTROL Yes]** , um ein Abonnement zu deaktivieren, oder auf **[!UICONTROL Cancel]** , um es zu beenden, ohne Abonnementänderungen vorzunehmen.

### Was passiert, nachdem Sie einen Abonnenten deaktiviert haben?

Wenn Sie den Zugriff auf einen Daten-Feed sperren, wird eine Benachrichtigungs-E-Mail an alle Administratorbenutzer im Konto des Datenkäufers gesendet. Die E-Mail enthält einen Anhang, in dem gesperrte Eigenschaften aufgelistet werden. Diese Liste hilft Abonnenten dabei, deaktivierte Eigenschaften aus ihren Segmenten und Modellen zu finden und zu entfernen.

### Abrechnung und Feed-Deaktivierung

Nachdem Sie den Zugriff auf einen Daten-Feed entfernt haben, sind die Abonnenten für die Gebühren für den vorherigen oder aktuellen Monat verantwortlich, je nachdem, wann Sie den Feed deaktiviert haben.

## Planungstypen für Daten-Feeds {#plan-types}

[!DNL Plan types] sind wichtige Komponenten in einem  [!UICONTROL Audience Marketplace] Daten-Feed. Als Datenanbieter können Sie damit mehrere Anwendungsfälle und Preisoptionen für Ihre Feeds erstellen. Darüber hinaus kann es eine gute Strategie sein, für jeden Daten-Feed einige Pläne zu erstellen. Dadurch erhalten Käufer verschiedene Optionen, unter denen sie nach Daten suchen, die sie modellieren oder an ein Ziel senden können.

[Erstellen Sie einen ](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) Datenfeed zur Auswahl  [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Planungstypen und Anwendungsfalloptionen {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Mit den [!UICONTROL Use Case] -Einstellungen können Verkäufer steuern, wie Käufer Ihre Daten verwenden können.

### Segmente und Überlagerungen

Ein **[!UICONTROL Segments and Overlap]**-Anwendungsfall erstellt einen Plan, der es Käufern ermöglicht, Eigenschaftsdaten in einem [Bericht zur Eigenschaftenüberschneidung](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) zu vergleichen. Darüber hinaus können Käufer Ihre Daten zu Segmenten hinzufügen und Vergleiche mit den Berichten [Segment-zu-Merkmal](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) und [Segment-zu-Segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) anstellen.

Jeder Daten-Feed muss mindestens einen [!UICONTROL Segments and Overlap] Anwendungsfall enthalten. Käufer können keine anderen Pläne in einem Daten-Feed abonnieren, wenn der Feed keinen [!UICONTROL Segments and Overlap]-Anwendungsfall enthält, weder als solche noch in Kombination mit einem anderen Anwendungsfall.

Überschneidungen können Käufern helfen,

* **Reichweite der Zielgruppe erweitern:**  Geringe Überschneidungen deuten darauf hin, dass Ihre Eigenschaften Benutzer enthalten, die der Käufer noch nicht gesehen hat. Daher möchten Käufer möglicherweise, dass diese Eigenschaften ihren Zielgruppensegmenten neue Benutzer hinzufügen.
* **Vorhandene Zielgruppen verbessern:**  Eine hohe Überschneidung deutet darauf hin, dass Ihre Eigenschaften Benutzer enthalten, die denen ähneln, von denen ein Käufer bereits weiß. Daher möchten Käufer möglicherweise, dass diese Eigenschaften dazu beitragen, gezielte, inkrementelle Verbesserungen an entwickelten Zielgruppen vorzunehmen.

Geben Sie diesen Anwendungsfall wie folgt an:

* Maßeinheit: Pauschalgebühr
* Preis: Kostenlos ($0.00)

### Modellierung

Ein **[!UICONTROL Modeling]**-Anwendungsfall erstellt einen Plan, mit dem Käufer Ihre Eigenschaften mit [algorithmischer Modellierung](../../../features/algorithmic-models/understanding-models.md#understanding-models) vergleichen können. Käufer betrachten die Modellergebnisse, um neue Zielgruppen in Ihren Daten zu finden, die ähnliche Konversionsattribute wie ihre eigenen aufweisen. Geben Sie diesen Anwendungsfall wie folgt an:

* Maßeinheit: Pauschalgebühr
* Preis: Abzinsungssatz oder Marktpreis

### Activation

Mit einem **[!UICONTROL Activation]**-Anwendungsfall können Käufer Daten an ein [Ziel](../../../features/destinations/destinations.md) senden. Bei diesem Anwendungsfall können Käufer keine Daten mit einem Überschneidungsbericht oder einem algorithmischen Modell vergleichen. Geben Sie diesen Anwendungsfall wie folgt an:

* Maßeinheit: [!DNL CPM]
* Preis: [!DNL CPM] Marktzinssatz

## Abrechnungs- und Preisoptionen {#billing}

Die Abrechnungs- und Preisoptionen steuern, wie Käufer Ihre Daten bezahlen.

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
   <td colname="col2"> <b><span class="uicontrol"> Die einzige Option ist die monatliche </span></b> Zahlungsrückstände. Der Abrechnungszyklus endet am 10. Tag jedes Monats. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Maßeinheit</span></b> </td> 
   <td colname="col2">Laden Sie die Datenkäufer auf einen CPM-Tarif oder eine Pauschalgebühr. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Bei CPM-Preisen müssen Datenkäufer die Nutzung selbst melden. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Bei pauschalen Gebühren melden Datenkäufer die Nutzung nicht, da ihnen ein Festpreis berechnet wird. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preis</span></b> </td>
   <td colname="col2"> Der Betrag, den ein Verkäufer dem Käufer als CPM-Satz oder Pauschalpreis in Dollar berechnet. </td>
  </tr> 
 </tbody> 
</table>

## Planungshinweise {#plan-notes}

Nehmen Sie im Feld **[!UICONTROL Additional Notes]** einige Zeit in Anspruch, um jeden Datenplan in einem Feed zu beschreiben. Eine gute, kurze Beschreibung hilft Käufern, den Inhalt oder Zweck jedes Plans in einem Daten-Feed zu verstehen. Käufer können beim Suchen oder Auswerten neuer Datenquellen Datenfeed lesen und Beschreibungen planen.

## Verwalten von privaten Daten-Feed-Anforderungen {#manage-private-requests}

Anbieter-Workflows zum Verwalten von privaten Feed-Anforderungen von Käufern.

Gehen Sie zu [!UICONTROL My Shared Data], um Käuferanfragen zu überprüfen, zu genehmigen oder abzulehnen und:

<!-- t_private_feed_workflows.xml -->

1. Klicken Sie auf den Namen des privaten Daten-Feeds.
2. Klicken Sie auf **[!UICONTROL Access Requests]** , um alle Käufer zu überprüfen, die Zugriff auf Ihren Daten-Feed wünschen.
3. Klicken Sie im Abschnitt [!UICONTROL Allow Access] jedes Anfragefelds auf das Häkchen, um eine Anforderung zu genehmigen, oder auf das X, um den Zugriff zu verweigern.
4. Bestätigen oder brechen Sie die im Bestätigungs-Popup ausgewählte Aktion ab.

## Rabatte für Datenanbieter {#discounts}

Mit Rabatten in [!UICONTROL Audience Marketplace] können Sie den veröffentlichten Preis eines Daten-Feeds für einzelne Abonnenten reduzieren. Sie können Abonnenten, die eine Abonnementanforderung gesendet haben, oder Abonnenten, die Details zu einem Daten-Feed angefordert haben, Rabatte anbieten. Rabatte gelten für [!DNL CPM] und pauschale Feeds. Rabatte können hilfreich sein, wenn Sie Abonnementanreize für neue Kunden bereitstellen oder die Kundentreue belohnen möchten.

## Rabatte auf einen Daten-Feed anwenden {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Um einen Feed zu diskontieren, fügen Sie dem Rabattfeld einen Rabattbetrag in % hinzu und bestätigen Sie Ihre Änderungen. Datenanbieter können einen Rabatt für Daten-Feeds in [!UICONTROL Audience Marketplace] gewähren, indem sie entweder:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In diesen Beispielen hat der Verkäufer dem Datenfeed [!UICONTROL Software Audience] einen Rabatt von 10 % hinzugefügt.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Überprüfen Sie die vergünstigten Feeds {#review-discounted-feeds}

Datenanbieter können alle ihre Abonnenten und diskontierten Feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]** sehen.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md)

