---
description: Für einen Datenfeed sind ein Name, eine Beschreibung, eine Datenquelle und ein Planungstyp erforderlich. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Datenfeeds in Audience Marketplace > Meine Freigegebenen Daten ein. Nur für Datenverkäufer verfügbar.
seo-description: Für einen Datenfeed sind ein Name, eine Beschreibung, eine Datenquelle und ein Planungstyp erforderlich. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Datenfeeds in Audience Marketplace > Meine Freigegebenen Daten ein. Nur für Datenverkäufer verfügbar.
seo-title: Erstellen, Preis und Verwalten von Datenfeeds
solution: Audience Manager
title: Erstellen, Preis und Verwalten von Datenfeeds
topic: DIL-API
uuid: e 28 c 20 b 3-33 fc -4485-8 ee 9-8530 d 126 f 741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Erstellen, Preis und Verwalten von Datenfeeds {#create-price-and-manage-data-feeds}

Für einen Datenfeed sind ein Name, eine Beschreibung, eine Datenquelle und ein Planungstyp erforderlich. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Richten Sie öffentliche oder private Datenfeeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]ein. Nur für Datenverkäufer verfügbar.

## Erstellen eines öffentlichen oder privaten Datenfeeds {#create-public-private-data-feed}

Für einen Datenfeed sind ein Name, eine Beschreibung, eine Datenquelle und ein Planungstyp erforderlich. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Nur für Datenverkäufer verfügbar.

<!-- t_data_feed.xml -->

Sie müssen über Administratorrechte verfügen, um einen öffentlichen oder privaten Datenfeed zu erstellen.
So erstellen Sie einen Datenfeed:

1. Klicken Sie auf **[!UICONTROL New Data Feed]**.
1. Benennen Sie den Datenfeed. Datenkäufer können anhand des Namens nach Ihrem Feed suchen.
1. Geben Sie eine kurze Beschreibung ein (maximal 255 Zeichen).

   Eine gute Beschreibung sollte Ihren Feed genau beschreiben. Sie können beispielsweise Text für Marketingkategorien, Demografie und geografische Abdeckung (z. B. [!DNL US] Nordamerika) einbeziehen. Der Text der Beschreibung ist durchsuchbar und hilft den Käufern, Ihren Feed zu suchen oder zu bewerten. Eine gute Beschreibung ist ein wichtiger Aspekt, um Abonnenten Ihren Datenfeed anzuziehen.
1. Wählen Sie eine Datenquelle aus den **[!UICONTROL Data Source]** Optionen.

   >[!IMPORTANT]
   >
   >Alle aktuellen und zukünftigen Eigenschaften, die zu dieser Datenquelle gehören, werden als Teil dieses Feeds für Ihre Datenkäufer freigegeben.

1. Wählen Sie in die [!UICONTROL Plan Types]gewünschten Optionen aus und klicken **[!UICONTROL Add Plan]** Sie auf.

   Feeds können mehrere Pläne enthalten. Pläne können mehrere Anwendungsfälle enthalten. Weitere Informationen finden Sie unter [Planen von Typen für Datenfeeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Klicken **[!UICONTROL Save]** Sie auf, um Ihre Datengebühr *zu speichern, ohne* sie zu aktivieren.
1. So speichern und aktivieren Sie einen Datenfeed
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Klicken Sie auf **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* Gespeicherte und aktivierte Datenfeeds können nicht gelöscht werden.
   >* Käufer sehen nur aktive Feeds.


### Optional: Erstellen eines privaten Datenfeeds

Verschieben Sie den Schieberegler im Abschnitt [!UICONTROL Settings] nach:

* **[!UICONTROL Private]** und **[!UICONTROL Branded]**: Die [!UICONTROL Marketplace] Liste des Käufers zeigt den Namen des Verkäufers in der Spalte Anbieter an und alle anderen Daten werden ausgeblendet.

* **[!UICONTROL Private]** und **[!UICONTROL Unbranded]**: Die [!UICONTROL Marketplace] Liste des Käufers zeigt nur den Datenfeednamen und die Beschreibung an. The data provider name appears as [!UICONTROL Private Seller].

Wenn Sie sehen möchten, wie ein privater Feed den Käufern entspricht, lesen Sie den Abschnitt Käufer in [privaten Datenfeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ THIS]
>
>* [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Deaktivieren des Daten-Feeds eines Abonnenten {#deactivate-data-feed}

Als [!UICONTROL Audience Marketplace] Datenanbieter können Sie den Zugriff von Käufern auf einen abonnierten Datenfeed sperren. Möglicherweise möchten Sie einen Käufer aus einem Feed aus Gründen wie verspätet Zahlung/gebührenpflichtige Gebühren entfernen oder wenn sie Eigenschaftendaten nicht ordnungsgemäß verwenden.

<!-- marketplace-deactiva4te-subscribers.xml -->

So sperren Sie einen Abonnenten:

1. Suchen Sie in [!UICONTROL My Shared Data]den Feed, den der Abonnent verwendet.

   >[!NOTE]
   >
   >Datenfeeds mit überfälligen Konten werden mit einem Dreieck-/Ausrufezeichen gekennzeichnet.

1. Klicken Sie in der [!UICONTROL Subscribers] Spalte auf die blaue Zahl, die Abonnenten für diesen Feed zählt. Dadurch wird die Abonnementdetailseite geöffnet.
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. Dadurch wird ein Bestätigungsdialogfenster geöffnet.
1. Klicken [!UICONTROL Confirmation] Sie im Popup, **[!UICONTROL Yes]** um ein Abonnement zu deaktivieren oder **[!UICONTROL Cancel]** beenden, ohne Abonnementänderungen vorzunehmen.

### Was passiert, nachdem Sie einen Abonnenten deaktiviert haben

Durch den Widerruf des Zugriffs auf einen Datenfeed wird eine Benachrichtigungs-E-Email an alle Administratorbenutzer im Konto des Datenkäufers gesendet. Die E-Mail enthält eine Anlage, die gesperrte Eigenschaften auflistet. Diese Liste hilft Abonnenten beim Suchen und Entfernen deaktivierter Eigenschaften aus ihren Segmenten und Modellen.

### Deaktivierung von Rechnungsstellung und Feed

Nachdem Sie den Zugriff auf einen Datenfeed aufgehoben haben, sind Abonnenten für Gebühren für den vorherigen oder aktuellen Monat verantwortlich, je nachdem, wann Sie den Feed deaktiviert haben.

## Planen von Typen für Datenfeeds {#plan-types}

[!DNL Plan types] sind wesentliche Komponenten in einem [!UICONTROL Audience Marketplace] Datenfeed. Als Datenanbieter können Sie mehrere Anwendungsfälle und Preisoptionen für Ihre Feeds erstellen. Außerdem kann es eine gute Strategie sein, einige Pläne für jeden Datenfeed zu erstellen. Dadurch erhalten Käufer verschiedene Optionen, aus denen sie auswählen können, wann sie nach Daten gesucht oder an ein Ziel gesendet werden.

[Erstellen Sie einen Datenfeed](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) , der ausgewählt [!UICONTROL Plan Types]werden soll.

![](assets/plan_types.png)

## Plantypen und Verwendungsfalloptionen {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Mit den [!UICONTROL Use Case] Einstellungen können Einzelhändler steuern, wie Käufer Ihre Daten nutzen können.

### Segmente und Überlappung

Ein **[!UICONTROL Segments and Overlap]** Anwendungsfall erstellt einen Plan, mit dem Käufer Eigenschaftsdaten in einem Überlappungsbericht [zu Trait-to-Trait vergleichen können](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Darüber hinaus können Käufer Ihre Daten zu Segmenten hinzufügen und Vergleiche mit den Berichten [Segment zu Merkmal](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) und [Segment zu Segmenten](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) vornehmen.

Jeder Datenfeed muss mindestens einen [!UICONTROL Segments and Overlap] Verwendungsfall enthalten. Käufer können andere Pläne in einem Datenfeed nicht abonnieren, wenn der Feed keinen [!UICONTROL Segments and Overlap] Anwendungsfall enthält, entweder alleine oder in Kombination mit einem anderen Verwendungsfall.

Überlappungsvergleiche können Käufer unterstützen:

* **Reichweite der Zielgruppe erweitern:** Niedrige Überlappung empfiehlt, dass Ihre Eigenschaften Benutzer enthalten, die der Käufer zuvor nicht gesehen hat. Aus diesem Grund möchten Käufer möglicherweise, dass diese Eigenschaften neue Benutzer ihren Zielgruppensegmenten hinzufügen.
* **Vorhandene Zielgruppen verbessern:** Hohe Überlappung empfiehlt, dass Ihre Eigenschaften Benutzer enthalten, die den bereits bekannten Käufern ähnlich sind. Daher können Käufer diese Eigenschaften möglicherweise dazu beitragen, gezielte, inkrementelle Verbesserungen an entwickelten Zielgruppen zu erreichen.

Preis für diesen Verwendungsfall wie folgt:

* Maßeinheit: Pauschalgebühr
* Preis: Kostenlos ($ 0,00)

### Modellierung

Ein **[!UICONTROL Modeling]** Anwendungsfall erstellt einen Plan, mit dem Käufer Ihre Eigenschaften mit dem [algorithmischen Modellierung vergleichen können](../../../features/algorithmic-models/understanding-models.md#understanding-models). Käufer sehen sich die Modellergebnisse an, um neue Zielgruppen in Ihren Daten zu finden, die ähnliche Konversionsattribute eigenständig teilen. Preis für diesen Verwendungsfall wie folgt:

* Maßeinheit: Pauschalgebühr
* Preis: Sonderpreis oder Marktpreis

### Activation

Mit einem **[!UICONTROL Activation]** Verwendungsfall können Käufer Daten an ein [Ziel senden](../../../features/destinations/destinations.md). Bei diesem Verwendungsfall können Käufer Daten nicht mit einem Überlappungsbericht oder einem algorithmischen Modell vergleichen. Preis für diesen Verwendungsfall wie folgt:

* Maßeinheit: [!DNL CPM]
* Preis: [!DNL CPM] Marktrate

## Rechnungsstellung und Preisoptionen {#billing}

Mit den Rechnungsstellungs- und Preisoptionen wird gesteuert, wie Käufer für Ihre Daten zahlen.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Rechnungsstellungszyklus</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Die einzige Option</span></b> ist "Monatlich" . Der Rechnungszyklus endet am 10. jedes Monats. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Maßeinheit</span></b> </td> 
   <td colname="col2">Errechnung von Käufern bei einer CPM- oder Pauschalgebühr. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Mit den CPM-Preisen sind Datenkäufer für die Selbstbedienung erforderlich. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Gebühren für einfache Gebühren werden nicht von Datenkäufern erfasst, da ihnen eine feste Rate berechnet wird. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Preis</span></b> </td>
   <td colname="col2"> Der Betrag, den ein Verkäufer dem Käufer als CPM-Rate oder reduzierter Gebühr in Dollar berechnet. </td>
  </tr> 
 </tbody> 
</table>

## Plannotizen {#plan-notes}

In diesem **[!UICONTROL Additional Notes]** Feld können Sie die einzelnen Datenpläne in einem Feed etwas näher beschreiben. Eine gute Beschreibung hilft den Käufern, den Inhalt oder Zweck jedes Plans in einem Datenfeed zu verstehen. Käufer können Datenfeeds lesen und Beschreibungen planen, wenn sie nach neuen Datenquellen suchen oder diese auswerten.

## Private Datenfeed-Anforderungen verwalten {#manage-private-requests}

Anbieter-Workflows zur Verwaltung privater Feed-Anfragen von Käufern.

Zum Überprüfen, Genehmigen oder Ablehnen von Käuferanforderungen gehen Sie zu [!UICONTROL My Shared Data] und:

<!-- t_private_feed_workflows.xml -->

1. Klicken Sie auf den Namen des privaten Datenfeeds.
2. Klicken **[!UICONTROL Access Requests]** Sie auf, um alle Käufer zu prüfen, die Zugriff auf Ihren Datenfeed haben möchten.
3. Klicken Sie im [!UICONTROL Allow Access] Abschnitt jedes Anforderungsfelds auf das Häkchen, um eine Anforderung zu genehmigen, oder auf das X, um den Zugriff zu verweigern.
4. Bestätigen oder brechen Sie Ihre ausgewählte Aktion im Bestätigungspopup ab.

>[!MORE_ LIKE_ THIS]
>
>* [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Rabatte für Datenanbieter {#discounts}

In [!UICONTROL Audience Marketplace]können Sie mit Rabatten den veröffentlichten Preis eines Datenfeeds für einzelne Abonnenten verringern. Sie können Rabatte für Abonnenten anbieten, die eine Abonnementanforderung eingereicht haben oder Abonnenten, die Details zu einem Datenfeed angefordert haben. Rabatte gelten für [!DNL CPM] und einfache Ratenfeeds. Rabatte können hilfreich sein, wenn Sie Abonnementanreize für neue Kunden bereitstellen oder Kundentreue belohnen möchten.

## Anwenden von Rabatten auf einen Datenfeed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Zum Rabatt auf einen Feed fügen Sie dem Rabattfeld einen Rabatt als % hinzu und bestätigen Sie die Änderungen. Datenanbieter können einen Rabatt auf Datenfeeds entweder [!UICONTROL Audience Marketplace] aus folgenden Quellen durchführen:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In diesen Beispielen hat der Verkäufer dem [!UICONTROL Software Audience] Datenfeed 10% Rabatt hinzugefügt.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review-Feeds überprüfen {#review-discounted-feeds}

Datenanbieter können alle Abonnenten anzeigen und Feeds abbrechen **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)