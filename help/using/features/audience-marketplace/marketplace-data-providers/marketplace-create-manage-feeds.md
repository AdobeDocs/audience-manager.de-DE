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


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

Für einen Datenfeed sind ein Name, eine Beschreibung, eine Datenquelle und ein Planungstyp erforderlich. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. Nur für Datenverkäufer verfügbar.

## Create a Public or Private Data Feed {#create-public-private-data-feed}

Für einen Datenfeed sind ein Name, eine Beschreibung, eine Datenquelle und ein Planungstyp erforderlich. Feeds sind deaktiviert, bis Sie den Feed speichern und aktivieren. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Nur für Datenverkäufer verfügbar.

<!-- t_data_feed.xml -->

Sie müssen über Administratorrechte verfügen, um einen öffentlichen oder privaten Datenfeed zu erstellen.
So erstellen Sie einen Datenfeed:

1. Klicken Sie auf **[!UICONTROL New Data Feed]**.
1. Benennen Sie den Datenfeed. Datenkäufer können anhand des Namens nach Ihrem Feed suchen.
1. Geben Sie eine kurze Beschreibung ein (maximal 255 Zeichen).

   Eine gute Beschreibung sollte Ihren Feed genau beschreiben. For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). Der Text der Beschreibung ist durchsuchbar und hilft den Käufern, Ihren Feed zu suchen oder zu bewerten. Eine gute Beschreibung ist ein wichtiger Aspekt, um Abonnenten Ihren Datenfeed anzuziehen.
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >Alle aktuellen und zukünftigen Eigenschaften, die zu dieser Datenquelle gehören, werden als Teil dieses Feeds für Ihre Datenkäufer freigegeben.

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   Feeds können mehrere Pläne enthalten. Pläne können mehrere Anwendungsfälle enthalten. For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. So speichern und aktivieren Sie einen Datenfeed
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Klicken Sie auf **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* Gespeicherte und aktivierte Datenfeeds können nicht gelöscht werden.
   >* Käufer sehen nur aktive Feeds.


### Optional: Erstellen eines privaten Datenfeeds

In the [!UICONTROL Settings] section, move the slider to:

* **[!UICONTROL Private]** und **[!UICONTROL Branded]**: Die [!UICONTROL Marketplace] Liste des Käufers zeigt den Namen des Verkäufers in der Spalte Anbieter an und alle anderen Daten werden ausgeblendet.

* **[!UICONTROL Private]** und **[!UICONTROL Unbranded]**: Die [!UICONTROL Marketplace] Liste des Käufers zeigt nur den Datenfeednamen und die Beschreibung an. The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ THIS]
>
>* [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Deaktivieren des Daten-Feeds eines Abonnenten {#deactivate-data-feed}

As an [!UICONTROL Audience Marketplace] data provider, you can revoke buyer access to a subscribed data feed. Möglicherweise möchten Sie einen Käufer aus einem Feed aus Gründen wie verspätet Zahlung/gebührenpflichtige Gebühren entfernen oder wenn sie Eigenschaftendaten nicht ordnungsgemäß verwenden.

<!-- marketplace-deactiva4te-subscribers.xml -->

So sperren Sie einen Abonnenten:

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >Datenfeeds mit überfälligen Konten werden mit einem Dreieck-/Ausrufezeichen gekennzeichnet.

1. In the [!UICONTROL Subscribers] column, click the blue number that counts subscribers for that feed. Dadurch wird die Abonnementdetailseite geöffnet.
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. Dadurch wird ein Bestätigungsdialogfenster geöffnet.
1. In the [!UICONTROL Confirmation] pop, click **[!UICONTROL Yes]** to deactivate a subscription or **[!UICONTROL Cancel]** to quit without making subscription changes.

### Was passiert, nachdem Sie einen Abonnenten deaktiviert haben

Durch den Widerruf des Zugriffs auf einen Datenfeed wird eine Benachrichtigungs-E-Email an alle Administratorbenutzer im Konto des Datenkäufers gesendet. Die E-Mail enthält eine Anlage, die gesperrte Eigenschaften auflistet. Diese Liste hilft Abonnenten beim Suchen und Entfernen deaktivierter Eigenschaften aus ihren Segmenten und Modellen.

### Deaktivierung von Rechnungsstellung und Feed

Nachdem Sie den Zugriff auf einen Datenfeed aufgehoben haben, sind Abonnenten für Gebühren für den vorherigen oder aktuellen Monat verantwortlich, je nachdem, wann Sie den Feed deaktiviert haben.

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] sind wesentliche Komponenten in einem [!UICONTROL Audience Marketplace] Datenfeed. Als Datenanbieter können Sie mehrere Anwendungsfälle und Preisoptionen für Ihre Feeds erstellen. Außerdem kann es eine gute Strategie sein, einige Pläne für jeden Datenfeed zu erstellen. Dadurch erhalten Käufer verschiedene Optionen, aus denen sie auswählen können, wann sie nach Daten gesucht oder an ein Ziel gesendet werden.

[Erstellen Sie einen Datenfeed](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) , der ausgewählt [!UICONTROL Plan Types]werden soll.

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

The [!UICONTROL Use Case] settings let sellers control how buyers can use your data.

### Segmente und Überlappung

A **[!UICONTROL Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a [trait-to-trait overlap report](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

Überlappungsvergleiche können Käufer unterstützen:

* **Reichweite der Zielgruppe erweitern:** Niedrige Überlappung empfiehlt, dass Ihre Eigenschaften Benutzer enthalten, die der Käufer zuvor nicht gesehen hat. Aus diesem Grund möchten Käufer möglicherweise, dass diese Eigenschaften neue Benutzer ihren Zielgruppensegmenten hinzufügen.
* **Vorhandene Zielgruppen verbessern:** Hohe Überlappung empfiehlt, dass Ihre Eigenschaften Benutzer enthalten, die den bereits bekannten Käufern ähnlich sind. Daher können Käufer diese Eigenschaften möglicherweise dazu beitragen, gezielte, inkrementelle Verbesserungen an entwickelten Zielgruppen zu erreichen.

Preis für diesen Verwendungsfall wie folgt:

* Maßeinheit: Pauschalgebühr
* Preis: Kostenlos ($ 0,00)

### Modellierung

A **[!UICONTROL Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). Käufer sehen sich die Modellergebnisse an, um neue Zielgruppen in Ihren Daten zu finden, die ähnliche Konversionsattribute eigenständig teilen. Preis für diesen Verwendungsfall wie folgt:

* Maßeinheit: Pauschalgebühr
* Preis: Sonderpreis oder Marktpreis

### Activation

An **[!UICONTROL Activation]** use case lets buyers send data to a [destination](../../../features/destinations/destinations.md). Bei diesem Verwendungsfall können Käufer Daten nicht mit einem Überlappungsbericht oder einem algorithmischen Modell vergleichen. Preis für diesen Verwendungsfall wie folgt:

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

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

## Plan Notes {#plan-notes}

In the **[!UICONTROL Additional Notes]** field, take some time to describe each data plan in a feed. Eine gute Beschreibung hilft den Käufern, den Inhalt oder Zweck jedes Plans in einem Datenfeed zu verstehen. Käufer können Datenfeeds lesen und Beschreibungen planen, wenn sie nach neuen Datenquellen suchen oder diese auswerten.

## Manage Private Data Feed Requests {#manage-private-requests}

Anbieter-Workflows zur Verwaltung privater Feed-Anfragen von Käufern.

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. Klicken Sie auf den Namen des privaten Datenfeeds.
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. Bestätigen oder brechen Sie Ihre ausgewählte Aktion im Bestätigungspopup ab.

>[!MORE_ LIKE_ THIS]
>
>* [Private Daten-Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. Sie können Rabatte für Abonnenten anbieten, die eine Abonnementanforderung eingereicht haben oder Abonnenten, die Details zu einem Datenfeed angefordert haben. Discounts apply to [!DNL CPM] and flat rate feeds. Rabatte können hilfreich sein, wenn Sie Abonnementanreize für neue Kunden bereitstellen oder Kundentreue belohnen möchten.

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Zum Rabatt auf einen Feed fügen Sie dem Rabattfeld einen Rabatt als % hinzu und bestätigen Sie die Änderungen. Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)