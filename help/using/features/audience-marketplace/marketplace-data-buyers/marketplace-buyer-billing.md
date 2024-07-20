---
description: Audience Marketplace-Datenkäufer stimmen zu, alle Anzeigenimpressionen zu melden, die mit Eigenschaften bereitgestellt werden, die im Daten-Feed enthalten sind, der auf der Grundlage der Kosten pro Tausend Anzeigenimpressionen (CPM) berechnet wurde. Die CPM-Nutzung ist am 5. Tag jedes Kalendermonats fällig und enthält Daten für den Vormonat. Pauschalgebühren-Abonnenten müssen die Nutzung nicht melden.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Abrechnung für Daten-Feed-Käufer
keywords: Berichterstellung auf Segmentebene, Segmentebene, Segmentebene
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# Abrechnung für Daten-Feed-Käufer {#billing-for-data-feed-buyers}

Audience Marketplace-Datenkäufer erklären sich damit einverstanden, alle Anzeigenimpressionen zu melden, die mit Eigenschaften bereitgestellt werden, die im Daten-Feed enthalten sind, der auf der Grundlage der Kosten pro Tausend Anzeigenimpressionen ([!DNL CPM]) berechnet wurde. [!DNL CPM] wird am 5. Tag jedes Kalendermonats verwendet und enthält Daten für den vorherigen Monat. Pauschalgebühren-Abonnenten müssen die Nutzung nicht melden.

<br>

## So melden Sie die CPM-Nutzung {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] -Datenkäufer stimmen zu, alle Anzeigenimpressionen zu melden, die mit Eigenschaften bereitgestellt werden, die im Daten-Feed enthalten sind, der auf der Grundlage der Kosten pro Tausend Anzeigenimpressionen ([!DNL CPM]) berechnet wurde. [!DNL CPM] Nutzung ist am 5. eines jeden Kalendermonats fällig und enthält Daten für den vorherigen Monat. Pauschalgebühren-Abonnenten müssen die Nutzung nicht melden.

[!UICONTROL Audience Marketplace] bietet zwei Möglichkeiten, um die Verwendung von [!DNL CPM] zu melden:

* **Berichterstellung auf Segmentebene**: Dies ist die empfohlene [!DNL CPM] Verwendungsberichterstellungsmethode. Wenn Sie eine [!DNL CPM] -Nutzung auf Segmentebene melden, werden die entsprechenden Nutzungsmengen im Abschnitt &quot;Berichte auf Daten-Feed-Ebene&quot;automatisch entsprechend den unter [Kostenzuordnung für CPM-Daten-Feeds](#cost-attribution) beschriebenen Algorithmen ausgefüllt.
* **Berichterstellung auf Daten-Feed-Ebene**: Für diese Methode müssen Sie die [!DNL CPM] Nutzung für jeden Daten-Feed einzeln melden, basierend auf den unter [Kostenzuordnung für CPM-Daten-Feeds](#cost-attribution) beschriebenen Algorithmen. Diese Methode ist jedoch mühsamer und fehleranfälliger als Berichte auf Segmentebene.

<br>

## CPM-Berichtverwendung auf Segmentebene {#segment-level-report}

Auf der Registerkarte [!UICONTROL Segment Usage] können Sie die Nutzung auf Segmentebene melden und gleichzeitig die Segmente anzeigen, die nach den Zielen gruppiert sind, denen sie zugeordnet sind.

Nachdem Sie die [!DNL CPM] -Nutzung auf Segmentebene gemeldet haben, weist [!UICONTROL Audience Marketplace] die entsprechenden Daten-Feeds anhand der [Kostenzuordnung für CPM-Daten-Feeds](#cost-attribution) automatisch die korrekte Verwendung zu.

So melden Sie die Verwendung von [!DNL CPM] auf Segmentebene:

1. Wechseln Sie zu &quot;**[!UICONTROL Audience Marketplace > Payables]**&quot;.
1. Wählen Sie die Registerkarte **[!UICONTROL Segment Usage]** aus.
1. Füllen Sie die Nutzung für Ihre Segmente aus. Sie können das Feld &quot;[!UICONTROL Search]&quot;verwenden, um die Segmente zu filtern, wenn Sie nur für einige davon Berichte zur Nutzung erstellen müssen.
1. Klicken Sie auf **[!UICONTROL Edit Segments Usage]**.
1. Geben Sie den Nutzwert [!DNL CPM] in die Spalte [!UICONTROL Usage] ein.
1. Klicken Sie auf **[!UICONTROL Save]** , wenn Sie fertig sind, und überprüfen Sie das Bestätigungsdialogfeld.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Klicken Sie auf **[!UICONTROL Confirm]**.

Sehen Sie sich auch unsere Videodemonstration an, wie Sie die Nutzung auf Segmentebene melden können:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## CPM-Berichtverwendung auf Daten-Feed-Ebene {#feed-level-report}

Die Berichterstellung auf Daten-Feed-Ebene ist aufwändiger und fehleranfälliger, da Sie die [!DNL CPM]-Nutzung für jeden Daten-Feed einzeln berechnen müssen. Es wird empfohlen, stattdessen die Verwendung von [Bericht-CPM auf Segmentebene](#segment-level-report) zu verwenden.

So melden Sie die Verwendung von [!DNL CPM] auf Segmentebene:

1. Wechseln Sie zu &quot;**[!UICONTROL Audience Marketplace > Payables]**&quot;.
2. Wählen Sie die Registerkarte **[!UICONTROL Feed Usage]** aus.
3. Verwenden Sie das Feld &quot;[!UICONTROL Search]&quot;, um die Daten-Feeds zu filtern und die Feeds zu identifizieren, für die Sie die Nutzung melden müssen.
4. Klicken Sie auf **[!UICONTROL Edit Feeds Usage]**.
5. Berechnen Sie die [!DNL CPM] -Nutzung für jeden Daten-Feed anhand der [Kostenzuordnung für CPM-Daten-Feeds](#cost-attribution) und geben Sie ihn in die Spalte [!UICONTROL Usage] ein.
6. Klicken Sie auf **[!UICONTROL Save]** , wenn Sie fertig sind, und überprüfen Sie das Bestätigungsdialogfeld.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Klicken Sie auf **[!UICONTROL Confirm]**.

<br>

## Massenberichte

Um Fehler und Mehraufwand bei der Berichterstellung über die Verwendung von [!DNL CPM] zu reduzieren, können Sie die Massenberichterstellungsoption verwenden, um eine [!DNL CSV] -Datei herunterzuladen, die die Daten-Feeds und Segmente enthält, die Nutzung auszufüllen und sie wieder in [!DNL Audience Manager] hochzuladen. Sie können Massenberichte verwenden, um sowohl die Feed- als auch die Segmentnutzung zu melden.

So aktualisieren Sie die Verwendung von [!DNL CPM] stapelweise:

1. Wechseln Sie zu &quot;**[!UICONTROL Audience Marketplace > Payables]**&quot;.
1. Wählen Sie je nach dem zu aktualisierenden Berichtstyp die Registerkarte **[!UICONTROL Feed Usage]** oder **[!UICONTROL Segment Usage]** aus.
1. Klicken Sie auf **[!UICONTROL Edit Feeds Usage]** oder **[!UICONTROL Edit Segments Usage]**.
1. Klicken Sie auf **[!UICONTROL download the current usage]** , um sicherzustellen, dass Sie eine gültige CSV-Datei verwenden.
1. Öffnen Sie die Datei auf Ihrem Computer und füllen Sie den Nutzungsbericht aus.
1. Klicken Sie auf **[!UICONTROL Choose a CSV file]** , um den aktualisierten Nutzungsbericht hochzuladen.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] überprüft die Datei, sobald Sie sie hochladen, und fordert Sie auf, etwaige Fehler in der Datei zu erkennen.

<br>

### Fehler bei der Massenberichterstellung

| Fehlermeldung | Beschreibung | Fehlerbehebung |
| ------------- | -------------| -----|
| Ungültige Eingabe | [!DNL Audience Manager] hat eine Änderung im [!DNL CSV]-Dateischema erkannt, z. B. fehlende Spalten oder Änderungen an Spaltentiteln. | Ändern Sie die Tabellenstruktur nicht. |
| nicht gefunden | Für [!UICONTROL Segment Level Reporting] konnte [!DNL Audience Manager] die Kombination [!UICONTROL Segment ID] und [!UICONTROL Destination ID] nicht identifizieren. Für [!UICONTROL Feed Level Reporting] konnte [!DNL Audience Manager] die Kombination [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] und [!UICONTROL Use Case] nicht identifizieren. | Überprüfen Sie für [!UICONTROL Segment Level Reporting] die Gültigkeit der Kombinationen [!UICONTROL Segment ID] und [!UICONTROL Destination ID]. Überprüfen Sie für [!UICONTROL Feed Level Reporting] die Gültigkeit der Kombinationen [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] und [!UICONTROL Use Case]. |
| Duplizierte Datensätze gefunden | [!DNL Audience Manager] hat doppelte Datensätze mit unterschiedlichen Impressionswerten erkannt. | Überprüfen Sie den Bericht und stellen Sie sicher, dass Sie keine unterschiedlichen Nutzungswerte für denselben Daten-Feed oder dasselbe Segment melden. |
| Nicht unterstützte Werte | [!DNL Audience Manager] hat nicht numerische Werte in der Spalte [!DNL Audience Manager] erkannt. | Überprüfen Sie den Bericht und stellen Sie sicher, dass Sie in der Spalte [!DNL Audience Manager] nur numerische Werte eingeben. |
| Kopfzeilen für erforderliche Felder fehlen | [!DNL Audience Manager] fehlende Tabellenüberschriften für Pflichtfelder erkannt. Für [!UICONTROL Segment Level Reporting] sind die erforderlichen Felder: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Für [!UICONTROL Feed Level Reporting] sind die erforderlichen Felder: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Überprüfen Sie den Bericht und stellen Sie sicher, dass die Tabellenüberschriften nicht bearbeitet wurden. |

>[!NOTE]
>Das Entfernen von Zeilen aus dem Nutzungsbericht [!DNL CSV] hat keine Auswirkungen auf den vorhandenen Nutzungsbericht. [!DNL Audience Manager] verarbeitet nur die im Bericht enthaltenen Felder.

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
   <td colname="col1"> <p><b>Geben Sie immer die Gesamtzahl der Impressionen an</b> </p> </td> 
   <td colname="col2"> <p>Für CPM-Impressions-Summen: </p>
   <p> Geben Sie die Gesamtzahl der Impressionen ohne Dezimalstellen an. Audience Manager berechnet den CPM automatisch auf Grundlage der von Ihnen gemeldeten Gesamtanzahl.</p><p>Wenn Sie 1.234.567 Impressionen melden müssen, melden Sie sie genau so. Sie müssen die Gesamtzahl der Impressionen nicht durch 1.000 dividieren, um den CPM zu berechnen.</p><p>Eigenschaften, die zur Optimierung Ihres Web- oder App-Inhalts (Inhaltsoptimierung) mithilfe von Tools wie Adobe Target oder einem Analytics-Ziel verwendet werden, tragen nicht zu den Nutzungssummen für CPM-Pläne bei. Datenanbieter erhalten normalerweise einen Ausgleich für die Inhaltsoptimierung durch pauschale Gebührenpläne.</p><p>Weitere Informationen finden Sie unter <a href="#cost-attribution">Kostenzuordnung für CPM-Daten-Feeds</a> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>An das monatliche Berichtsintervall festhalten</b> </p> </td> 
   <td colname="col2"> <p>Das Berichtssystem wird nach dem 5. jedes Monats geschlossen. Wenn Sie die CPM-Nutzung bis dahin nicht melden, müssen Sie diesen Betrag dem Bericht für den folgenden Monat hinzufügen. Angenommen, Sie verwenden 1000 Impressionen im Oktober, verpassen den Berichterstellungszeitraum im Oktober und verwenden 1000 Impressionen im November. In diesem Fall melden Sie die Summe von Oktober und November (2000) im Dezember zwischen dem 1. und dem 5.</p><p><b>Tipp</b>: Sie sollten immer versuchen, die CPM-Nutzung für den vorherigen Monat zwischen dem 1. und 5. Tag des folgenden Monats zu melden.</p><p>Sie können die CPM-Nutzung bis zum 5. des neuen Kalendermonats melden. Dies wird jedoch nicht empfohlen. Die Berichterstellung zur CPM-Nutzung vor dem 5. eines jeden Monats gibt dem Audience Manager Zeit, die Daten zu überprüfen und zu verarbeiten.</p> </td>
  </tr> 
 </tbody> 
</table>

<br>

## Kostenzuordnung für CPM-Daten-Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] müssen Sie die Impressionsmengen für jedes Ihrer Segmente jeden Monat selbst melden. Es wird empfohlen, die [!DNL CPM] -Nutzung auf Segmentebene zu melden, damit die Kostenzuordnung automatisch erfolgt.

<!-- marketplace_cpm_billing.xml -->

### Abrechnungszusammenfassung {#billing-summary}

Sie müssen [!DNL CPM] Datenfeed-Impressionsmengen zwischen dem 1. und dem 5. Tag jedes Kalendermonats senden. Um dies richtig zu machen, empfehlen wir, die Verwendung von [Bericht-CPM auf Segmentebene](#segment-level-report) zu verwenden.

>[!TIP]
>Wenn Sie die [!DNL CPM] -Nutzung auf Segmentebene melden, wird der Abschnitt für die Berichterstellung auf Daten-Feed-Ebene automatisch mit den entsprechenden Nutzungsmengen ausgefüllt.

Wenn Sie [!UICONTROL Report CPM Usage at Data Feed Level] benötigen, müssen Sie alle Impressionen, die für jeden Feed im vorherigen Kalendermonat bereitgestellt wurden, einzeln kompilieren und diese gemäß der in diesem Artikel beschriebenen Abrechnungszuordnung melden.

Nachdem Sie die [!DNL CPM]-Zahl für den vorherigen Kalendermonat gemeldet haben, führt [!DNL Adobe] folgende Schritte aus:

* Erstellen Sie eine Rechnung und rechnen Sie basierend auf der [!DNL CPM] -Rate für jeden abonnierten Daten-Feed.
* Bezahlen Sie die Gebühren von Datenanbietern (Verkäufern) basierend auf Ihrer gemeldeten [!DNL CPM] Verwendung.

>[!IMPORTANT]
>
>Als Käufer müssen alle gemeldeten Impressions-Summen wahr und korrekt sein. Wenn Sie die Summen der Impressionen nicht bis zum 5. Tag jedes Monats melden, müssen Sie die Summen für den nicht gemeldeten Monat im folgenden Monat einbeziehen.

<br>

## Zuweisen von Impressionen auf Feed-Ebene basierend auf Eigenschaftsqualifikationsregeln {#assign-impressions}

Mit dem Nutzungsszenario [!UICONTROL Activation] können Sie Eigenschaften im entsprechenden Daten-Feed verwenden, um Segmente in [Segment Builder](../../../features/segments/segment-builder.md) zu erstellen und diese Segmente einem Ziel zuzuordnen. Mit den booleschen Operatoren [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT] können Sie die Bedingungen für die Eigenschafts- und Segmentqualifizierung festlegen.

Wenn Sie die [Nutzung des Berichts-CPM auf Daten-Feed-Ebene](#feed-level-report) durchführen, müssen Sie Impressionen entsprechend den in den Eigenschaftsqualifikationsregeln verwendeten [!DNL Boolean] -Operatoren proportional für jeden Daten-Feed zuweisen. In der folgenden Tabelle ist aufgeführt, wie Impressionen ordnungsgemäß nach boolescher Regel oder Eigenschaftstyp zugeordnet werden.

>[!TIP]
>[Verwenden des Berichts-CPM auf Segmentebene](#segment-level-report) , damit die Berichterstellung auf Daten-Feed-Ebene automatisch vom Audience Manager erfolgt.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logik oder Typ der Regelqualifikation </th> 
   <th colname="col2" class="entry"> Rechnungsverteilung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> UND</span> </p> </td> 
   <td colname="col2"> <p>Wenden Sie 100 % der bereitgestellten Impressions-Summen auf alle Anbietereigenschaften in einem regelbasierten Segment an, das eine boolesche <span class="wintitle"> UND </span> -Bedingung verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ODER</span> </p> </td> 
   <td colname="col2"> <p>Wenden Sie die gewichtete Zuordnung der bereitgestellten Impressionssummen auf alle Anbietereigenschaften in einem regelbasierten Segment an, das eine boolesche ODER-Bedingung verwendet. Die gewichtete Zuordnung wird anhand der folgenden Formel berechnet:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Wenden Sie 100 % der bereitgestellten Impressionssummen auf alle Anbietereigenschaften in einem regelbasierten Segment an, das eine boolesche Bedingung vom Typ <span class="wintitle"> NOT</span> verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algorithmische Segmente </p> </td> 
   <td colname="col2"> <p>Wenden Sie 100 % der bereitgestellten Impressions-Summen auf alle Anbieter-Feeds in einem Segment an, das algorithmische Eigenschaften enthält. </p> </td> 
  </tr>
 </tbody>
</table>

<br>

## Abrechnungsbeispiele {#billing-examples}

Die folgenden Beispiele veranschaulichen, wie die [!DNL CPM]-Verwendungszuordnung auf Daten-Feed-Ebene erfolgt.

>[!IMPORTANT]
>Es wird empfohlen, stattdessen [CPM-Nutzung auf Segmentebene](#segment-level-report) zu verwenden, damit dieser Prozess automatisch ausgeführt wird.

Betrachten wir das folgende Szenario:

![billing-examples](assets/billing-examples.png)

<br>

### 1. Fall: Segmente mit UND Qualifizierungsregeln

Dieses Segment enthält 3 Eigenschaften von separaten Datenanbietern. Da die Segmentqualifizierung auf einer [!UICONTROL AND] -Bedingung basiert, müssen Besucher die Eigenschaften aller drei Feeds realisieren, um sich für das Segment zu qualifizieren.

![](assets/billing-segment-and.png)

Mit der Bedingung &quot;[!UICONTROL AND]&quot; müssen Sie allen drei Datenanbietern 100 % der im Monat erhaltenen Impressionen zuweisen. Im Abschnitt [!UICONTROL Audience Marketplace > Payables] werden jedem Provider 1.000.000 Impressionen gutgeschrieben.

Dieses Beispiel gilt für Segmente, die [!DNL Boolean] [!UICONTROL NOT] -Operatoren verwenden, oder für Segmente, die algorithmische Eigenschaften enthalten.

<br>

### Fall 2: Segmente mit ODER Qualifizierungsregeln

Dieses Segment enthält 3 Eigenschaften von separaten Datenanbietern. Da die Segmentqualifizierung auf einer [!UICONTROL OR] -Bedingung basiert, müssen Besucher mindestens eine der drei Eigenschaften implementieren, um sich für das Segment zu qualifizieren.

Wir können nicht feststellen, welche Eigenschaft für eine Impression verantwortlich ist, da die Qualifizierung auf einer [!UICONTROL OR] -Bedingung basiert. Daher wird jedem Anbieter im Abschnitt [!UICONTROL Audience Marketplace > Payables] eine gewichtete Zuordnung der Gesamtimpressionen basierend auf der Eigenschaftspopulation gutgeschrieben.

![billing-segment-or](assets/billing-segment-or.png)

<br>

### 3. Fall: Segmente mit Anwendungsfällen für die Modellierung und Aktivierung

In diesem Beispiel wird die Attribution anhand von zwei Data Feed-Anwendungsfällen beschrieben: Modellierung und Aktivierung. Im Beispiel werden zwei Datenanbieter mit den folgenden Informationen betrachtet:

![data-feed](assets/feed-use-cases.png)

In der weiter unten stehenden Tabelle enthält Segment X zwei Eigenschaften, T1 und T2, mit der Segmentregel T1 ODER T2, wobei:

* T1 ist eine Eigenschaft aus Daten-Feed A.
* T2 ist eine algorithmische Eigenschaft, die nach Eigenschaften von Drittanbietern aus Daten-Feed A und Daten-Feed B modelliert wurde.

Das Segment wird einem Ziel zugeordnet und 1.000.000 Impressionen für dieses Segment werden in einem Monat mithilfe von [Berichten auf Segmentebene](#segment-level-report) eingegeben.

Von diesen 1.000.000 Impressionen:

* T1 macht 40 % der Segmentpopulation aus, was 400.000 Impressionen für Feed A bedeutet.
* T2 macht 60 % der Segmentpopulation aus, was 600.000 Impressionen für Feed A und Feed B bedeutet.

Auf der Daten-Feed-Ebene ist die Zuordnungsmethode für Impressionen:

* Daten-Feed A erhält 600.000 Impressionen von Eigenschaft T2 (die anhand von Eigenschaften aus Daten-Feed A und Daten-Feed B modelliert wird, sodass beide die Impressionen erhalten) und 400.000 Impressionen von Eigenschaft T1 (eine Eigenschaft aus Daten-Feed A), insgesamt 1.000 Impressionen.
* Daten-Feed B erhält 600.000 Impressionen von Eigenschaft T2 (siehe Erklärung oben) und 0 Impressionen von Eigenschaft T1.

Die Überblick-Aufschlüsselung nach Daten-Feed und Anwendungsfall sieht wie folgt aus:

![ Feed-Aufschlüsselung](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Für den Anwendungsfall der Modellierung sollten Sie die CPM-Nutzung nur bei Aktivierung melden. Wenn Sie nur ein Modell ausführen, es jedoch nicht aktivieren, ist kein Gebrauchsbericht erforderlich.

<br>

## Abrechnung und Impressionszuordnung für pauschale Feeds {#billing-flat-fee}

Mit einem pauschalen Daten-Feed wird Ihnen monatlich ein fester Betrag in Rechnung gestellt, unabhängig davon, wann das Abonnement beginnt oder wie viele Impressionen Sie verwenden. Die Gebühren werden für die Verwendung in Teilmonaten oder für Intervalle nicht anteilig berechnet. Wie bei der CPM-Abrechnung generiert Adobe eine Rechnung und rechnet Sie zum monatlichen Pauschalpreis für Ihre abonnierten Daten-Feeds.

Nehmen wir beispielsweise an, Sie haben beschlossen, bestimmte Eigenschaften in einem Feed Mitte des Monats zu aktivieren. Sie erhalten weiterhin die volle monatliche Gebühr, unabhängig davon, wann Sie das Abonnement gestartet oder bestimmte Eigenschaften aktiviert haben.
