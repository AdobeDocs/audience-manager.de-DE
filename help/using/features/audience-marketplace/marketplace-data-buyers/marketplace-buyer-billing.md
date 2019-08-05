---
description: Audience Marketplace-Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen (CPM) bereitgestellt werden. Die CPM-Nutzung erfolgt am 5. Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.
seo-description: Audience Marketplace-Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen (CPM) bereitgestellt werden. Die CPM-Nutzung erfolgt am 5. Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.
seo-title: Rechnungsstellung für Datenfeed-Käufer
solution: Audience Manager
title: Rechnungsstellung für Datenfeed-Käufer
keywords: Berichterstellung auf Segmentebene, Segmentebene, Segmentebene
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: dab5b255f966e63d51cc4d236d37bb0cb4eb960c

---


# Rechnungsstellung für Datenfeed-Käufer {#billing-for-data-feed-buyers}

Audience Marketplace-Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen ([!DNL CPM]) bereitgestellt werden. [!DNL CPM] die Nutzung erfolgt am 5. Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.

<br> 

## So melden Sie CPM-Nutzung {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften im Datenfeed auf Kosten pro Tausender-Anzeigenimpressionen ([!DNL CPM]) bereitgestellt werden. [!DNL CPM] die Nutzung erfolgt am 5 Tag jedes Kalendermonats und enthält Daten für den vorherigen Monat. Flat-Fee-Abonnenten müssen keine Verwendung für die Nutzung vornehmen.

[!UICONTROL Audience Marketplace] bietet zwei Möglichkeiten zur Berichterstellung [!DNL CPM] :

* **Berichterstellung auf Segmentebene**: Dies ist die empfohlene [!DNL CPM] Verwendungsberichtsmethode. Wenn Sie [!DNL CPM] die Nutzung auf Segmentebene melden, wird der Berichtsabschnitt Datenfeeds automatisch mit den entsprechenden Nutzungsbeträgen ausgefüllt, basierend auf den Algorithmen, die in [der Kostenzuordnung für CPM-Datenfeeds beschrieben](#cost-attribution)sind.
* **Berichterstellung auf Datenfeeds**: Diese Methode erfordert, dass Sie je nach den Algorithmen, [!DNL CPM] die in [der Kostenzuordnung für CPM-Datenfeeds beschrieben sind, die Nutzung für jeden Datenfeed einzeln melden](#cost-attribution). Diese Methode ist jedoch mühsam und fehleranfällig als die Berichterstellung auf Segmentebene.

<br> 

## CPM-Auslastung auf Segmentebene melden {#segment-level-report}

Auf der [!UICONTROL Segment Usage] Registerkarte können Sie die Nutzung auf Segmentebene melden und dabei die Segmente anzeigen, die nach den Zielen gruppiert sind, denen sie zugeordnet sind.

Nach der Berichterstellung [!DNL CPM] auf Segmentebene weist automatisch [!UICONTROL Audience Marketplace] die entsprechende Datenfeeds die korrekte Nutzung zu, basierend auf der [Kostenzuordnung für CPM-Datenfeeds](#cost-attribution).

So melden Sie [!DNL CPM] die Nutzung auf Segmentebene an:

1. Gehe **[!UICONTROL Audience Marketplace > Payables]** zu.
2. Wählen Sie die **[!UICONTROL Segment Usage]** Registerkarte.
3. Geben Sie die Nutzung für Ihre Segmente ein. Sie können das [!UICONTROL Search] Kästchen verwenden, um die Segmente zu filtern, wenn Sie nur für einige davon die Nutzung der Berichte benötigen.
4. Klicken Sie auf **[!UICONTROL Edit Segments Usage]**.
5. Geben Sie den [!DNL CPM] Nutzungsbetrag in die [!UICONTROL Usage] Spalte ein.
6. Klicken **[!UICONTROL Save]** Sie auf, wenn Sie fertig sind, und überprüfen Sie das Bestätigungsdialogfeld.
   ![confirmation-segment-usage](assets/confirm-segment-usage.png)
7. Klicken Sie auf **[!UICONTROL Confirm]**.

<br> 

## Bericht-CPM-Nutzung auf Datenfeed-Ebene {#feed-level-report}

Die Berichterstellung auf Datenfeeds ist mühsam und anfällig für Fehlerverarbeitung, da Sie die Nutzung für jeden Datenfeed einzeln berechnen [!DNL CPM] müssen. Es wird empfohlen, stattdessen [die CPM-Auslastung auf Segmentebene](#segment-level-report) zu melden.

So melden Sie [!DNL CPM] die Nutzung auf Segmentebene an:

1. Gehe **[!UICONTROL Audience Marketplace > Payables]** zu.
2. Wählen Sie die **[!UICONTROL Feed Usage]** Registerkarte.
3. Verwenden Sie das [!UICONTROL Search] Feld, um die Datenfeeds zu filtern und diejenigen zu identifizieren, für die Sie die Nutzung von Berichten verwenden müssen.
4. Klicken Sie auf **[!UICONTROL Edit Feeds Usage]**.
5. Berechnen Sie die [!DNL CPM] Nutzung für jeden Datenfeed anhand der [Kostenzuordnung für CPM-Datenfeeds](#cost-attribution)und geben Sie ihn in die [!UICONTROL Usage] Spalte ein.
6. Klicken **[!UICONTROL Save]** Sie auf, wenn Sie fertig sind, und überprüfen Sie das Bestätigungsdialogfeld.

   ![confirmation-feed-usage](assets/confirm-feed-usage.png)

7. Klicken Sie auf **[!UICONTROL Confirm]**.

<br> 

## Massenberichterstellung

Um Fehler und Übergänge bei der Berichterstellung [!DNL CPM] zu reduzieren, können Sie die Massenberichtsoption verwenden, um eine [!DNL CSV] Datei mit den Datenfeeds und Segmenten herunterzuladen, die Nutzung auszufüllen und sie wieder zu laden [!DNL Audience Manager]. Sie können Massenberichte verwenden, um sowohl Feed- als auch Segmentnutzung zu melden.

So aktualisieren [!DNL CPM] Sie die Nutzung stapelweise:

1. Gehe **[!UICONTROL Audience Marketplace > Payables]** zu.
1. Wählen Sie die **[!UICONTROL Feed Usage]** oder **[!UICONTROL Segment Usage]** die Registerkarte abhängig vom Typ der Berichterstellung, die Sie aktualisieren möchten.
1. Klicken **[!UICONTROL Edit Feeds Usage]** oder **[!UICONTROL Edit Segments Usage]**.
1. Klicken **[!UICONTROL download the current usage]** Sie auf, um sicherzustellen, dass Sie eine gültige CSV-Datei verwenden.
1. Öffnen Sie die Datei auf Ihrem Computer und füllen Sie den Nutzungsbericht aus.
1. Klicken **[!UICONTROL Choose a CSV file]** Sie auf, um den aktualisierten Nutzungsbericht hochzuladen.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] überprüft die Datei, sobald Sie sie hochladen, und fordert Sie auf, alle Fehler in der Datei zu erkennen.

<br> 

### Massenberichtüberprüfungsfehler

| Fehlermeldung | Beschreibung | Fehlerbehebung |
| ------------- | -------------| -----|
| Ungültige Eingabe | [!DNL Audience Manager] hat eine Änderung im [!DNL CSV] Dateischema erkannt, z. B. fehlende Spalten oder Änderungen an Spaltentiteln. | Vermeiden Sie eine Änderung der Tabellenstruktur. |
| nicht gefunden | Die [!UICONTROL Segment Level Reporting][!DNL Audience Manager] Kombination [!UICONTROL Segment ID] und [!UICONTROL Destination ID] Kombination konnte nicht identifiziert werden. Für [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] können Sie die [!UICONTROL Data Provider Name][!UICONTROL Feed Name][!UICONTROL Use Case] und die Kombination nicht identifizieren. | Überprüfen [!UICONTROL Segment Level Reporting]Sie die Gültigkeit [!UICONTROL Segment ID] und [!UICONTROL Destination ID] Kombination. Überprüfen Sie die [!UICONTROL Feed Level Reporting]Gültigkeit des [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]und [!UICONTROL Use Case] der Kombination. |
| Doppelte Datensätze gefunden | [!DNL Audience Manager] erkannte Datensätze mit unterschiedlichen Impressionswerten. | Überprüfen Sie den Bericht und stellen Sie sicher, dass Sie keine unterschiedlichen Nutzungswerte für denselben Datenfeed oder dieselbe Segmente melden. |
| Nicht unterstützte Werte | [!DNL Audience Manager] nicht numerische Werte in der [!DNL Audience Manager] Spalte erkannt. | Überprüfen Sie den Bericht und stellen Sie sicher, dass Sie nur numerische Werte in der [!DNL Audience Manager] Spalte eingeben. |
| Kopfzeilen für erforderliche Felder fehlen | [!DNL Audience Manager] erkannte Tabellenkopfzeilen für Pflichtfelder erkannten. Die erforderlichen [!UICONTROL Segment Level Reporting]Felder sind: [!UICONTROL Segment ID][!UICONTROL Destination ID]. Die erforderlichen [!UICONTROL Feed Level Reporting]Felder sind: [!UICONTROL Data Provider Name][!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Überprüfen Sie den Bericht und stellen Sie sicher, dass die Kopfzeilen der Tabelle nicht manipuliert wurden. |

>[!NOTE]
>Das Entfernen von Zeilen aus dem [!DNL CSV] Nutzungsbericht wirkt sich nicht auf den vorhandenen Nutzungsbericht aus. [!DNL Audience Manager] verarbeitet nur die Felder, die im Bericht enthalten sind.

<br> 

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
   <p> Melden Sie die Gesamtzahl der Impressionen ohne Dezimalzahlen. Audience Manager berechnet automatisch den CPM basierend auf der Gesamtanzahl der Berichte.</p><p>Wenn Sie 1.234.567 Impressionen erfassen müssen, melden Sie es genau wie dies. Sie müssen die Gesamtanzahl der Impressionen nicht um 1.000 dividieren, um den CPM zu berechnen.</p><p>Eigenschaften, die zur Optimierung Ihres Web- oder App-Inhalts (Content Optimization) mithilfe von Tools wie Adobe Target oder einem Analytics-Ziel verwendet werden, tragen nicht zur Gesamtnutzung der CPM-Pläne bei. Datenanbieter werden normalerweise für die Inhaltsoptimierung mit einfachen Gebühren kompensiert.</p><p>Weitere Informationen finden Sie unter <a href="#cost-attribution">Kostenzuordnung für CPM-Datenfeeds</a> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Bindung an das monatliche Berichtsintervall</b> </p> </td> 
   <td colname="col2"> <p>Das Berichtsystem wird nach dem 5. jedes Monats geschlossen. Wenn Sie die CPM-Auslastung bis dahin nicht erfassen können, müssen Sie diesen Betrag für den folgenden Monat dem Bericht hinzufügen. Nehmen wir beispielsweise an, Sie verwenden im Oktober 1000 Impressionen, verpassen den Termin für Oktober-Berichte und verwenden im November 1000 Impressionen. In diesem Fall melden Sie den Oktober und November (2000) im Dezember zwischen dem 1. und dem 5. Dezember.</p><p><b>Tipp</b>: Sie sollten immer versuchen, die CPM-Nutzung für den vorherigen Monat zwischen dem 1. und 5. Tag des folgenden Monats zu berichtigen.</p><p>Sie können die CPM-Auslastung als 5. des neuen Kalendermonats festlegen, dies wird jedoch nicht empfohlen. Die Berichterstellung für die CPM vor dem fünften jedes Monats gibt Audience Manager Zeit, die Daten zu überprüfen und zu verarbeiten.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Kostenzuordnung für CPM-Datenfeeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] müssen die Impressionsbeträge jeden Monat für jeden Ihrer Segmente selbst gemeldet werden. Wir empfehlen die Berichterstellung [!DNL CPM] auf Segmentebene, damit Kostenzuordnungen automatisch durchgeführt werden.

<!-- marketplace_cpm_billing.xml -->

### Rechnungszusammenfassung {#billing-summary}

Sie müssen die Impressionsbeträge [!DNL CPM] des Datenfeeds zwischen dem 1. und dem fünften Tag jedes Kalendermonats senden. Hierfür empfehlen wir Ihnen, [die CPM-Auslastung auf Segmentebene zu melden](#segment-level-report).

>[!TIP]
>Wenn Sie die Nutzung auf [!DNL CPM] Segmentebene melden, wird der Berichtsabschnitt der Datenfeeds automatisch mit den entsprechenden Verwendungsbeträgen ausgefüllt.

Sie müssen alle [!UICONTROL Report CPM Usage at Data Feed Level]Impressionen einzeln kompilieren, die für jeden Feed im vorherigen Kalendermonat bereitgestellt wurden, und sie entsprechend der in diesem Artikel beschriebenen Rechnungszuweisung berichtieren.

Nach der Berichtsnummer [!DNL CPM] für den vorherigen Kalendermonat [!DNL Adobe] gehen Sie wie folgt vor:

* Erstellen Sie eine Rechnung und Rechnungen entsprechend der [!DNL CPM] Rate für jeden abonnierten Datenfeed.
* Gebührenpflichtige Daten (Verkäufer) entrichten, die auf der verwendeten [!DNL CPM] Verwendung basieren.

>[!IMPORTANT]
>
>Als Käufer müssen alle gemeldeten Impressionen wahr und genau sein. Wenn die Impressionssummen nicht am 5. Tag jedes Monats gemeldet werden, müssen Sie im folgenden Monat Summen für den nicht gemeldeten Monat einbeziehen.

<br> 

## Impressionen auf Feed-Ebene basierend auf Eigenschaften-Qualifizierungsregeln zuweisen {#assign-impressions}

Mit dem [!UICONTROL Activation] Verwendungsfall können Sie Eigenschaften im entsprechenden Datenfeed verwenden, um Segmente im [Segmentaufbau](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) zu erstellen und diese Segmente einem Ziel zuzuordnen. Die booleschen Operatoren [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL NOT] Sie können die Bedingungen für Eigenschaften und Segmentqualifizierung festlegen.

Wenn Sie [die CPM-Auslastung auf Datenfeed-Ebene](#feed-level-report)melden, müssen Sie die Impressionen für jeden Datenfeed proportional zuweisen, gemäß den [!DNL Boolean] Operatoren in den Eigenschaftenregeln. In der folgenden Tabelle sind die korrekten Zuordnungen von Impressionen nach Boolescher Regel oder Eigenschaftstyp aufgeführt.

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
   <td colname="col2"> <p>Wenden Sie 100% der bereitgestellten Impressionssummen auf alle Provider-Eigenschaften in einem regelbasierten Segment an, das eine boolesche <span class="wintitle"> UND</span> -Bedingung verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ODER</span> </p> </td> 
   <td colname="col2"> <p>Wenden Sie gewichtete Zuordnungen der gelieferten Impressionssummen auf alle Provider-Eigenschaften in einem regelbasierten Segment an, das eine boolesche ODER-Bedingung verwendet. Die gewichtete Zuordnung wird mithilfe der folgenden Formel berechnet:</p><p><code>(Trait-Population/Segmentpopulation) * Anzahl der Impressionen * Kosten des CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NICHT</span> </p> </td> 
   <td colname="col2"> <p>Wenden Sie 100% der bereitgestellten Impressionssummen auf alle Provider-Eigenschaften in einem regelbasierten Segment an, das eine boolesche <span class="wintitle"> NOT</span> -Bedingung verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algorithmische Segmente </p> </td> 
   <td colname="col2"> <p>Wenden Sie 100% der bereitgestellten Impressionssummen auf alle Anbieter-Feeds in einem Segment an, das algorithmische Eigenschaften enthält. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Rechnungsbeispiele {#billing-examples}

Die folgenden Beispiele zeigen, wie [!DNL CPM] die Verwendungszuordnung auf Datenfeed-Ebene durchgeführt wird.

>[!IMPORTANT]
>Es wird empfohlen, [dass Sie die CPM-Auslastung auf Segmentebene](#segment-level-report) verwenden, um diesen Vorgang automatisch durchführen zu lassen.

Betrachten wir das folgende Szenario:

![Rechnungsstellung](assets/billing-examples.png)

<br> 

### Fall 1: Segmente mit UND Qualifizierungsregeln

Dieses Segment enthält 3 Eigenschaften aus separaten Datenanbietern. Da die Segmentqualifizierung auf einer [!UICONTROL AND] Bedingung basiert, müssen Besucher die Eigenschaften aus allen drei Feeds erstellen, um das Segment zu qualifizieren.

![](assets/billing-segment-and.png)

Mit einer [!UICONTROL AND] Bedingung müssen Sie 100% der während des Monats empfangenen Impressionen allen drei Datenanbietern zuweisen. Im [!UICONTROL Audience Marketplace > Payables] Abschnitt werden alle Anbieter mit 1.000.000 Impressionen gutgeschrieben.

Dieses Beispiel gilt für Segmente, die [!DNL Boolean][!UICONTROL NOT] Operatoren verwenden oder für Segmente mit algorithmischen Eigenschaften.

<br> 

### Fall 2: Segmente mit ODER Qualifizierungsregeln

Dieses Segment enthält 3 Eigenschaften aus separaten Datenanbietern. Da Segmentqualifizierung auf einer [!UICONTROL OR] Bedingung basiert, müssen Besucher mindestens eine der drei Eigenschaften ermitteln, die für das Segment qualifiziert sind.

Wir können nicht feststellen, welche Eigenschaft für eine Impression verantwortlich ist, da die Qualifikation auf einer [!UICONTROL OR] Bedingung basiert. Infolgedessen können Sie im Abschnitt [!UICONTROL Audience Marketplace > Payables] jeden Anbieter mit einer gewichteten Zuordnung der Impressionen basierend auf der Eigenschaftenpopulation vergleichen.

![rechnungsstellung-segment-or](assets/billing-segment-or.png)

<br> 

### Fall 3: Segmente mit Anwendungsfällen für Modellierung und Aktivierung

In diesem Beispiel wird die Zuordnung basierend auf zwei Anwendungsfällen im Datenfeed beschrieben - Modeling und Aktivierung. In diesem Beispiel betrachten wir zwei Datenanbieter mit folgenden Informationen:

![data-feed](assets/feed-use-cases.png)

In der Tabelle unten enthält Segment X zwei Eigenschaften, T 1 und T 2 mit der Segmentregel T 1 OR T 2, wobei Folgendes gilt:

* T 1 ist eine Eigenschaft aus Data Feed A;
* T 2 ist eine algorithmische Eigenschaft, die nach Eigenschaften von Drittanbietern aus Data Feed A und Data Feed B modelliert wird.

Das Segment wird einem Ziel zugeordnet und es werden 1.000.000 Impressionen für dieses Segment in einem Monat unter Verwendung [von Segmentebene-Berichterstellung eingegeben](#segment-level-report).

Von diesen 1.000.000 Impressionen:

* T 1 bildet 40% der Segmentpopulation, was zu 400.000 Impressionen für Feed A führt.
* T 2 besteht aus 60% der Segmentpopulation, was zu 600.000 Impressionen für Feed A und Feed B führt.

Auf Datenfeeds werden die Impressionen wie folgt zugeordnet:

* Datenfeed A Empfängt 600.000 Impressionen aus Trait T 2 (was auf Eigenschaften aus Data Feed A und Data Feed B modelliert wird, d. h. beide erhalten die Impressionen) und 400.000 Impressionen aus der Eigenschaft T 1 (was eine Eigenschaft aus Data Feed A ist), insgesamt 1.000,8 000 Impressionen.
* Data Feed B Empfängt 600.000 Impressionen aus der Eigenschaft T 2 (siehe Erläuterung oben) und 0 Impressionen von Eigenschaften T 1.

Die vorsichtliche Aufschlüsselung nach Datenfeed und Anwendungsfall lautet wie folgt:

![Feed-Aufschlüsselung](assets/feed-breakdown-alt.png)

<br> 

## Rechnungsstellung und Impression-Zuordnung für einfache gebührenpflichtige Datenfeeds {#billing-flat-fee}

Ein Flat-Fee-Feed sendet jeden Monat einen festen Betrag, unabhängig davon, wann das Abonnement beginnt oder wie viele Impressionen Sie verwenden. Gebühren werden nicht für eine teilweise monatliche Nutzung oder Intervalle berechnet. Wie bei der CPM-Abrechnung generiert Adobe eine Rechnung und rechnet Sie mit der monatlichen Gebühr für Ihre abonnierten Datenfeeds auf.

Nehmen wir an, Sie haben sich entschieden, bestimmte Eigenschaften in einem Feed in der Mitte des Monats zu aktivieren. Unabhängig davon, wann Sie das Abonnement gestartet oder spezifische Eigenschaften aktiviert haben, werden Sie immer noch mit der vollen monatlichen Gebühr in Rechnung gestellt.