---
description: Audience Marketplace-Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen (CPM) bereitgestellt werden. Die CPM-Nutzung erfolgt am 5. Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.
seo-description: Audience Marketplace-Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen (CPM) bereitgestellt werden. Die CPM-Nutzung erfolgt am 5. Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.
seo-title: Rechnungsstellung für Datenfeed-Käufer
solution: Audience Manager
title: Rechnungsstellung für Datenfeed-Käufer
topic: DIL-API
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] die Nutzung erfolgt am 5. Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen ([!DNL CPM]) bereitgestellt werden. [!DNL CPM] die Nutzung erfolgt am 5 Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.

[!UICONTROL Audience Marketplace] bietet zwei Möglichkeiten zur Berichterstellung [!DNL CPM] :

* **Berichterstellung auf Segmentebene**: Dies ist die empfohlene [!DNL CPM] Verwendungsberichtsmethode. When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **Berichterstellung auf Datenfeeds**: Diese Methode erfordert, dass Sie je nach den Algorithmen, [!DNL CPM] die in [der Kostenzuordnung für CPM-Datenfeeds beschrieben sind, die Nutzung für jeden Datenfeed einzeln melden](#cost-attribution). Diese Methode ist jedoch mühsam und fehleranfällig als die Berichterstellung auf Segmentebene.

## Report CPM Usage at Segment Level {#segment-level-report}

The [!UICONTROL Segment Usage] tab allows you to report segment-level usage, while displaying the segments grouped by the destinations they are mapped to.

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. Select the **[!UICONTROL Segment Usage]** tab.
3. Geben Sie die Nutzung für Ihre Segmente ein. You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. Klicken Sie auf **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.
   ![confirmation-segment-usage](assets/confirm-segment-usage.png)
7. Klicken Sie auf **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
2. Select the **[!UICONTROL Feed Usage]** tab.
3. Use the [!UICONTROL Search] box to filter the data feeds and identify the ones that you need to report usage for.
4. Klicken Sie auf **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.

   ![confirmation-feed-usage](assets/confirm-feed-usage.png)

7. Klicken Sie auf **[!UICONTROL Confirm]**.

## Massenberichterstellung

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. Sie können Massenberichte verwenden, um sowohl Feed- als auch Segmentnutzung zu melden.

To update [!DNL CPM] usage in bulk:

1. Go to **[!UICONTROL Audience Marketplace > Payables]**.
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. Öffnen Sie die Datei auf Ihrem Computer und füllen Sie den Nutzungsbericht aus.
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] überprüft die Datei, sobald Sie sie hochladen, und fordert Sie auf, alle Fehler in der Datei zu erkennen.

### Massenberichtüberprüfungsfehler

| Fehlermeldung | Beschreibung | Fehlerbehebung |
| ------------- | -------------| -----|
| Ungültige Eingabe | [!DNL Audience Manager] hat eine Änderung im [!DNL CSV] Dateischema erkannt, z. B. fehlende Spalten oder Änderungen an Spaltentiteln. | Vermeiden Sie eine Änderung der Tabellenstruktur. |
| nicht gefunden | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| Doppelte Datensätze gefunden | [!DNL Audience Manager] erkannte Datensätze mit unterschiedlichen Impressionswerten. | Überprüfen Sie den Bericht und stellen Sie sicher, dass Sie keine unterschiedlichen Nutzungswerte für denselben Datenfeed oder dieselbe Segmente melden. |
| Nicht unterstützte Werte | [!DNL Audience Manager] nicht numerische Werte in der [!DNL Audience Manager] Spalte erkannt. | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| Kopfzeilen für erforderliche Felder fehlen | [!DNL Audience Manager] erkannte Tabellenkopfzeilen für Pflichtfelder erkannten. For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Überprüfen Sie den Bericht und stellen Sie sicher, dass die Kopfzeilen der Tabelle nicht manipuliert wurden. |

>[!NOTE]
>Removing rows from the [!DNL CSV] usage report does not have any effect on the existing usage report. [!DNL Audience Manager] verarbeitet nur die Felder, die im Bericht enthalten sind.

## [!DNL CPM] Best Practices für die Berichterstellung

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Empfehlungen </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Immer die Gesamtzahl der Impressionen melden</b> </p> </td> 
   <td colname="col2"> <p>Für CPM-Impressionssummen: </p>
   <p> Melden Sie die Gesamtzahl der Impressionen ohne Dezimalzahlen. Audience Manager berechnet automatisch den CPM basierend auf der Gesamtanzahl der Berichte.</p><p>Wenn Sie 1.234.567 Impressionen erfassen müssen, melden Sie es genau wie dies. Sie müssen die Gesamtanzahl der Impressionen nicht um 1.000 dividieren, um den CPM zu berechnen.</p><p>Eigenschaften, die zur Optimierung Ihres Web- oder App-Inhalts (Content Optimization) mithilfe von Tools wie Adobe Target oder einem Analytics-Ziel verwendet werden, tragen nicht zur Gesamtnutzung der CPM-Pläne bei. Datenanbieter werden normalerweise für die Inhaltsoptimierung mit einfachen Gebühren kompensiert.</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Bindung an das monatliche Berichtsintervall</b> </p> </td> 
   <td colname="col2"> <p>Das Berichtsystem wird nach dem 5. jedes Monats geschlossen. Wenn Sie die CPM-Auslastung bis dahin nicht erfassen können, müssen Sie diesen Betrag für den folgenden Monat dem Bericht hinzufügen. Nehmen wir beispielsweise an, Sie verwenden im Oktober 1000 Impressionen, verpassen den Termin für Oktober-Berichte und verwenden im November 1000 Impressionen. In diesem Fall melden Sie den Oktober und November (2000) im Dezember zwischen dem 1. und dem 5. Dezember.</p><p><b>Tipp</b>: Sie sollten immer versuchen, die CPM-Nutzung für den vorherigen Monat zwischen dem 1. und 5. Tag des folgenden Monats zu berichtigen.</p><p>Sie können die CPM-Auslastung als 5. des neuen Kalendermonats festlegen, dies wird jedoch nicht empfohlen. Die Berichterstellung für die CPM vor dem fünften jedes Monats gibt Audience Manager Zeit, die Daten zu überprüfen und zu verarbeiten.</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>Als Käufer müssen alle gemeldeten Impressionen wahr und genau sein. Wenn die Impressionssummen nicht am 5. Tag jedes Monats gemeldet werden, müssen Sie im folgenden Monat Summen für den nicht gemeldeten Monat einbeziehen.

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

The [!UICONTROL Activation] use case lets you use traits in the corresponding data feed to create segments in [Segment Builder](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) and map those segments to a destination. The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. In der folgenden Tabelle sind die korrekten Zuordnungen von Impressionen nach Boolescher Regel oder Eigenschaftstyp aufgeführt.

>[!TIP]
>[Bericht-CPM-Nutzung auf Segmentebene](#segment-level-report) , damit die Datenfeeds-Berichterstellung automatisch von Audience Manager durchgeführt werden kann.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regelqualifizierungslogik oder Typ </th> 
   <th colname="col2" class="entry"> Rechnungsverteilung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> UND</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ODER</span> </p> </td> 
   <td colname="col2"> <p>Wenden Sie gewichtete Zuordnungen der gelieferten Impressionssummen auf alle Provider-Eigenschaften in einem regelbasierten Segment an, das eine boolesche ODER-Bedingung verwendet. Die gewichtete Zuordnung wird mithilfe der folgenden Formel berechnet:</p><p><code>(Trait-Population/Segmentpopulation) * Anzahl der Impressionen * Kosten des CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NICHT</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algorithmische Segmente </p> </td> 
   <td colname="col2"> <p>Wenden Sie 100% der bereitgestellten Impressionssummen auf alle Anbieter-Feeds in einem Segment an, das algorithmische Eigenschaften enthält. </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

Betrachten wir das folgende Szenario:

![Rechnungsstellung](assets/billing-examples.png)

### Fall 1: Segmente mit UND Qualifizierungsregeln

Dieses Segment enthält 3 Eigenschaften aus separaten Datenanbietern. Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

With an [!UICONTROL AND] condition, you must assign 100% of the impressions received during the month to all three data providers. In the [!UICONTROL Audience Marketplace > Payables] section, you credit each provider with 1,000,000 impressions.

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### Fall 2: Segmente mit ODER Qualifizierungsregeln

Dieses Segment enthält 3 Eigenschaften aus separaten Datenanbietern. Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![rechnungsstellung-segment-or](assets/billing-segment-or.png)

>[!MORE_ LIKE_ THIS]
>
>* [Rechnungsstellung und Impression-Zuordnung für einfache gebührenpflichtige Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

Ein Flat-Fee-Feed sendet jeden Monat einen festen Betrag, unabhängig davon, wann das Abonnement beginnt oder wie viele Impressionen Sie verwenden. Gebühren werden nicht für eine teilweise monatliche Nutzung oder Intervalle berechnet. Wie bei der CPM-Abrechnung generiert Adobe eine Rechnung und rechnet Sie mit der monatlichen Gebühr für Ihre abonnierten Datenfeeds auf.

Nehmen wir an, Sie haben sich entschieden, bestimmte Eigenschaften in einem Feed in der Mitte des Monats zu aktivieren. Unabhängig davon, wann Sie das Abonnement gestartet oder spezifische Eigenschaften aktiviert haben, werden Sie immer noch mit der vollen monatlichen Gebühr in Rechnung gestellt.