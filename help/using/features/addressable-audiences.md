---
description: Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.
keywords: DIL 
seo-description: Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.
seo-title: Addressable Audiences
solution: Audience Manager
title: Addressable Audiences
topic: DIL-API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.

## Was ist eine adressierbare Zielgruppe? {#addressable-audience-description}

Die [!UICONTROL Addressable Audiences] Funktion zeigt die Überschneidung zwischen den Zielgruppen, die Sie sehen, in all Ihren Eigenschaften, in denen Daten gesammelt werden, und dem ausgewählten Ziel [!DNL Audience Manager] an. Um Ihnen zu helfen, dieses Konzept zu verstehen, schauen Sie sich die folgende Abbildung an. Die Überschneidung zwischen den einzelnen Kreisen stellt die verschiedenen Arten adressierbarer Zielgruppen dar.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Addressable Audience Manager for a Destination</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl aller Geräte, die während des Rückblickzeitraums mit allen Audience Manager-Kunden auf Plattformebene interagiert haben und die mit Ihrem ausgewählten Ziel übereinstimmen können. </p> <p>Diese Metrik ist nützlich, da sie Ihnen Folgendes zeigt: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Die Größe der gesamten adressierbaren Zielgruppe, die <span class="keyword"> Audience Manager</span> auf ein bestimmtes Targeting-Ziel erreichen kann. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Wie groß der <span class="keyword"> Audience Manager</span> -Profilpool für eine Targeting-Plattform und die Größe ihrer Zielgruppen ist. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zielgruppe insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl von Geräten, die während des Lookback-Fensters entweder eine regelbasierte Eigenschaft Ihrer Eigenschaften oder eine integrierte Eigenschaft aus Ihren Offlinedateien realisiert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Addressable Audience Match Rate</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Anzahl der Überschneidungen von Geräten, die während des Lookback-Fensters entweder eine regelbasierte Eigenschaft oder eine integrierte Eigenschaft erreicht haben, sowie von Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten Ziel unabhängig von der Zeit der Synchronisierung erfolgt. </p> 
    </draft-comment> <p>Diese Metrik stellt Geräte dar, die: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Sie haben während des Lookback-Fensters entweder eine regelbasierte oder eine Onboard-Eigenschaft realisiert <b>UND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Verwenden Sie unabhängig vom Zeitpunkt der Synchronisierung eine ID-Synchronisierung mit dem ausgewählten Ziel. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kunden-Übereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Kunden-Addressable Audience: Gesamtanzahl der Kunden, ausgedrückt als %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Segmentpopulation insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Zählung aller Geräte, die während des Rückblickzeitraums in Ihrem Segment Mitglied waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die während des Rückblickzeitraums zum Segment gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieter-Daten sowie Daten von Zweitanbietern und Drittanbietern über Eigenschaften enthalten, die im <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>erfasst werden. </p> <p> <p>Tipp: Bei Verwendung mit der Rückblickzeit von 1 Tag können Sie mit dieser Metrik den aktuellen Status Ihrer Segmente verstehen. Dies liegt daran, dass die Metrik " <span class="wintitle"> Segment Addressable Audience</span> "die Benutzer darstellt, die während des Vortags in einem Segment geblieben sind. Kombinieren Sie dies mit der Tatsache, dass <span class="keyword"> Audience Manager</span> <span class="wintitle"> Addressable Audiences</span> täglich aktualisiert, wobei diese Metrik und der Lookback-Zeitraum die aktuellste Momentaufnahme Ihrer Segmente bieten. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentübereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Segment Addressable Audience: Segmentpopulation insgesamt, ausgedrückt als %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

Die [!UICONTROL Addressable Audience] Funktion verwandelt dieses abstrakte Konzept in quantifizierbare Daten. In [!DNL Audience Manager]dieser Funktion werden Zielgruppenüberschneidungen mit Datenvisualisierungen angezeigt, die auf einen Blick neben numerischen Daten in Tabellenform Informationen bereitstellen.

[!UICONTROL Addressable Audiences] befindet sich in **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **[!UICONTROL Integrated Platforms > Device-Based]** aus, um die Metriken adressierbarer Zielgruppen anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der Einstiegsseite Addressable Audiences sehen können, stellen Folgendes dar:

| Metrik | Beschreibung |
---------|----------|
| **Addressable Audience (devices)** | Diese Metrik stellt die Zielgruppe für Kunden dar (siehe Tabelle oben) *für die letzten 30 Tage.* |
| **Übereinstimmungsrate** | Diese Metrik stellt die Addressable Audience Match Rate (siehe Tabelle oben) *für die letzten 30 Tage* dar. |
| **Addressable Audience (devices) auf Lebensdauer** | Eine Anzahl aller Geräte, die während der Berichtausblickszeit mit allen Audience Manager-Kunden auf Plattformebene interagiert haben und die mit diesem Ziel abgeglichen werden könnten. Weitere Informationen finden Sie unter Metriken auf [Plattformebene](/help/using/features/addressable-audiences.md#platform-level-metrics) . |

Klicken Sie auf den Namen eines Server-zu-Server-Ziels, um Ihre adressierbaren Zielgruppendaten anzuzeigen. Beachten Sie, dass diese Funktion nur Daten für Server-zu-Server-Ziele zurückgibt und für den Zugriff Administratorberechtigungen erforderlich sind.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten kann Ihnen dabei helfen,

* **** Prognosen und Planung: Mit [!UICONTROL Segment Addressable Audience] Daten erhalten Sie mehr Granularität in den Segmenten, die Sie für Zielgruppen-Targeting und -Aktivierung an ein Ziel senden möchten.

* **** Leistungsüberprüfungen: Die [!UICONTROL Addressable Audiences] Funktion ist auch ein Tool zur Fehlerbehebung. Sie können damit die Kampagnenleistung überprüfen, die Reichweite der Kampagne verstehen und mit Targeting-/Aktivierungspartnern abgleichen, wenn die erwarteten Ergebnisse nicht angezeigt werden.

### Anzeigen von Daten von Drittanbietern und Auswirkungen auf Übereinstimmungsraten

Vor dem Kauf von Daten von Drittanbietern zur Zielgruppenerfassung können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie vor dem Kauf neuer Daten eine fundierte Entscheidung treffen. Die ID-Synchronisierung für erworbene Drittanbieterdaten beruht nicht nur auf der Überschneidung Ihrer Daten, sondern auch auf den Fußspuren von Drittanbietern mit allen anderen [!DNL Audience Manager] Kunden. Ihr [!DNL Adobe] Berater kann Sie bei der Ermittlung zusätzlicher relevanter Datenquellen unterstützen, um die Prospektionskampagnen zu optimieren.

### Mobilbenutzer und Übereinstimmungsraten

Beim Versuch, eine Verbindung zu [!DNL Safari] Benutzern mit mobilen Apps herzustellen, bestehen Lücken, wenn keine Drittanbieter-Cookies vorhanden sind. Dadurch ist es schwierig, Benutzer mit einigen Partnern zu synchronisieren, da nur die [!DNL Adobe] IDs für synchronisierte Drittanbieter-Cookies in den Medienbereitstellungsprotokollen bereitgestellt werden. Dies ist ein Grund, warum Sie möglicherweise [niedrige Übereinstimmungsraten](../features/addressable-audiences.md#low-match-rates) für Ihre Ziele sehen.

## Datumsbereiche in adressierbaren Zielgruppen und Zielen {#date-ranges}

In den folgenden Abschnitten erfahren Sie, wie die verfügbaren Datumsbereiche aussehen und wie die Daten aus jedem Intervall in den Berichten für einen [!UICONTROL Addressable Audience] oder [!UICONTROL Destination]einen Zeitraum ausfallen.

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für Ihre [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) verwenden dieselben Datumsbereichsintervalle. Zu den Datumsbereichsoptionen zählen:

* [!UICONTROL Last 1 Day] (Dieses Intervall läuft von Mitternacht bis Mitternacht des vorherigen 24-Stunden-Zeitraums. Es handelt sich nicht um eine reale oder aktuelle Metrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Daten und Datumsbereiche werden in der [!DNL UTC] Zeitzone festgelegt. Siehe [Zeitzonen in Audience Manager](../reference/aam-time-zones.md).

## Daten im Datumsbereich {#date-range-intervals}

Die [!UICONTROL Addressable Audience] und [!UICONTROL Destination] Metriken geben die Anzahl der individuellen Benutzer für das ausgewählte Zeitintervall zurück. Ein Besucher wird beispielsweise nur einmal gezählt, auch wenn er Ihre Site mehrmals aufsucht. Der erste Besuch ist der individuelle Besuch und wird aufgezeichnet. Die nachfolgenden Besuche werden zurückgegeben und nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder älter. Und die Daten werden aus jedem Berichtintervall gelöscht, sobald die Zeit vergeht. Nehmen wir beispielsweise an, dass nach Auswahl der [!UICONTROL Last 30 Days] Option zwei Besucher angezeigt werden. In den Berichten werden folgende Besucher aufgeführt:

* *Wird* in die Ergebnisse einbezogen, die von den längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *Wird* nicht in kürzeren Intervallen vor der [!UICONTROL Last 30 Day] Option (aktuell, 7 Tage und 14 Tage) einbezogen.

Und am 31. Tag erscheinen diese Besucher nur an den 60 Tagen, 90 Tagen und [!UICONTROL Lifetime] Ergebnissen. Sie sind aus dem 30-Tage-Intervall gealtert. Besucher verlieren nicht das [!UICONTROL Lifetime] Intervall.

## Addressable Audience Metrics {#addressable-audience-metrics}

In diesem Abschnitt werden die von [!UICONTROL Addressable Audiences]Ihnen bereitgestellten Metriktypen beschrieben.

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten zu Eigenschaften zurück, die realisiert werden, wenn Besucher zu Ihrer Site kommen oder wenn Sie eingehende Datendateien an [!DNL Audience Manager]senden. Diese Metrik bietet einen umfassenden Überblick über die Zielgruppengröße für Ihr Konto.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Benutzeradressierbare Zielgruppe</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Anzahl der Überschneidungen von Geräten, die während des Lookback-Fensters entweder eine regelbasierte Eigenschaft oder eine integrierte Eigenschaft erreicht haben, sowie von Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten Ziel unabhängig von der Zeit der Synchronisierung erfolgt. </p> 
    </draft-comment> <p>Diese Metrik stellt Geräte dar, die: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Sie haben während des Lookback-Fensters entweder eine regelbasierte oder eine Onboard-Eigenschaft realisiert <b>UND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Verwenden Sie unabhängig vom Zeitpunkt der Synchronisierung eine ID-Synchronisierung mit dem ausgewählten Ziel. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zielgruppe insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl von Geräten, die während des Lookback-Fensters entweder eine regelbasierte Eigenschaft Ihrer Eigenschaften oder eine integrierte Eigenschaft aus Ihren Offlinedateien realisiert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kunden-Übereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Kunden-Addressable Audience: Gesamtanzahl der Kunden, ausgedrückt als %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Übereinstimmungsmetriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zur Segmentmitgliedschaft zurück. Sie bieten eine detailliertere und genauere Ansicht der Zielgruppengröße für jedes Ihrer Segmente.

>[!NOTE]
>
>Die Art und Weise, wie das Lookback-Fenster auf Segmentebene angewendet wird, unterscheidet sich von der auf Kundenebene. Besucher können vor 10 Tagen zur Site kommen und eine Eigenschaft realisieren. Sie könnten sich seitdem für ein Segment qualifizieren und vor 2 Tagen aus dem Segment aussteigen. Wenn der 7-Tage-Rückblick angewendet wird, werden diese Besucher auf Segmentebene gezählt, nicht jedoch auf Kundenebene.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die während des Rückblickzeitraums zum Segment gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieter-Daten sowie Daten von Zweitanbietern und Drittanbietern über Eigenschaften enthalten, die im <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>erfasst werden. </p> <p> <p>Tipp: Bei Verwendung mit der Rückblickzeit von 1 Tag können Sie mit dieser Metrik den aktuellen Status Ihrer Segmente verstehen. Dies liegt daran, dass die Metrik " <span class="wintitle"> Segment Addressable Audience</span> "die Benutzer darstellt, die während des Vortags in einem Segment geblieben sind. Kombinieren Sie dies mit der Tatsache, dass <span class="keyword"> Audience Manager</span> <span class="wintitle"> Addressable Audiences</span> täglich aktualisiert, wobei diese Metrik und der Lookback-Zeitraum die aktuellste Momentaufnahme Ihrer Segmente bieten. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentpopulation insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Zählung aller Geräte, die während des Rückblickzeitraums in Ihrem Segment Mitglied waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentübereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Segment Addressable Audience: Segmentpopulation insgesamt, ausgedrückt als %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriken auf Plattformebene {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle Audience Manager-Kunden erfasst wurden. Sie können eine umfassendere Ansicht der Zielgruppe des Kunden im Vergleich zu den zusammengefassten Audience Manager-Kunden bieten.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Addressable Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl aller Geräte, die während des Rückblickzeitraums mit allen Audience Manager-Kunden auf Plattformebene interagiert haben und die mit Ihrem ausgewählten Ziel übereinstimmen können. </p> <p>Diese Metrik ist nützlich, da sie Ihnen Folgendes zeigt: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Die Größe der gesamten adressierbaren Zielgruppe, die <span class="keyword"> Audience Manager</span> auf ein bestimmtes Targeting-Ziel erreichen kann. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Wie groß der <span class="keyword"> Audience Manager</span> -Profilpool für eine Targeting-Plattform und die Größe ihrer Zielgruppen ist. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vergleichen von Kunden- und Segmentadressierbaren Zielgruppen{#comparing-metrics}

Sie sollten die [!UICONTROL Customer Addressable Audience] und die [!UICONTROL Segment Addressable Audience] Metriken nicht vergleichen, um festzustellen, ob eine bedeutsamer ist als die andere. Dabei handelt es sich um separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, wird jede davon aus verschiedenen Datensätzen abgeleitet. Daher sollten Sie keine Schlussfolgerungen daraus ziehen, wenn eine Metrik größer als die andere ist. Sie können beim Vergleich nur Folgendes sagen:

* [!UICONTROL Customer Addressable Audiences] basiert auf Eigenschaften *für Ihre eigenen Erstanbieterdaten*. Diese Metrik bietet einen umfassenden Überblick über Ihre Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] basiert auf Segmentqualifikationen *für Ihre eigenen Erstanbieterdaten sowie auf Zweit- und Drittanbieterdaten*. Diese Metrik bietet eine granulare, genauere Ansicht Ihrer adressierbaren Zielgruppen in einer Targeting-Plattform.

## Ursachen für niedrige Übereinstimmungsraten für Addressable Audiences {#low-match-rates}

Häufige Elemente, die für niedrige [!UICONTROL Addressable Audience] Übereinstimmungsraten oder Diskrepanzen in den gemeldeten Zahlen verantwortlich sind.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ursache </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Mobile Traffic</b> </p> </td> 
   <td colname="col2"> <p>Die meisten Server-zu-Server-Integrationen basieren auf Synchronisierungsprozessen, die durch Drittanbieter-Cookies erleichtert werden. Mobile Umgebungen verwenden jedoch keine Drittanbieter-Cookies. Die Anzahl der adressierbaren Zielgruppen scheint daher im Vergleich zur Segmentgröße gering zu sein. </p> <p>Ab Januar 2018 können Sie mobile Zielgruppen in denselben Google- und Adobe Advertising Cloud-Zielen aktivieren, die für cookie-basierte Zielgruppen eingerichtet wurden. Dies bedeutet, dass Sie Segmente mit kombinierter Cookie- und Mobil-ID-Mitgliedschaft an Ihre Google- und Advertising Cloud-Ziele senden können. Beachten Sie jedoch, dass Addressable Audiences nur die Überschneidung zwischen Cookie-IDs und Zielen anzeigen. Audience Manager sendet 100 % der mobilen Zielgruppen an Ziele, aber mobile Zielgruppen werden nicht anhand der Metrik "Addressable Audience"gemessen. </p> <p> <p><b>Hinweis</b>:  Nehmen wir beispielsweise ein Segment mit einer Bevölkerung von 1.000.000 Einwohnern. Wenn Sie dieses Segment einem Google- oder Adobe Advertising Cloud-Ziel zuordnen, wird möglicherweise eine Addressable Audience von 700.000 Geräten und eine Übereinstimmungsrate von 70 % angezeigt. Die Mitgliedschaft bei 700.000 besteht aus Cookie-IDs mit einer ID-Synchronisierung mit dem Ziel. Ihre Addressable Audience könnte sogar viel höher sein, da adressierbare mobile IDs in dieser Metrik nicht angezeigt werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari-Traffic</b> </p> </td> 
   <td colname="col2"> <p>Safari blockiert Drittanbieter-Cookies. Dadurch wird verhindert, dass Audience Manager IDs mit dem Ziel synchronisiert. Mit der Einführung von <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>können Sie erwarten, dass Ihre Zielgruppen keine Safari-Benutzer einschließen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Verfolgte Medienimpressionen</b> </p> </td> 
   <td colname="col2"> <p>Aufgrund der Best Practices für den Anzeigenserver werden ID-Synchronisierungen nicht in Anzeigen-Tags vorgenommen. Kunden, die eine große Menge an Offsite-Werbung betreiben, synchronisieren Benutzer nicht mit Drittanbieterintegrationen in diesen Umgebungen. Darüber hinaus könnten durch eine große Menge erfasster Medienimpressionsdaten adressierbare Zielgruppenzahlen reduziert werden. </p> </td>
  </tr> 
 </tbody> 
</table>

## Fehlerbehebung mit Addressable Audiences {#troubleshooting}

Zusätzlich zu den Übereinstimmungsraten, die überschritten werden, können Sie diese auch [!UICONTROL Addressable Audiences] als Fehlerbehebungswerkzeug verwenden.

<!-- addressable-audiences-troubleshooting.xml -->

Nehmen wir beispielsweise an, Sie senden ein Segment an ein Ziel und dieses Ziel zeigt niedrige Berichtszahlen an. Wenn Sie die [!UICONTROL Addressable Audience] Ergebnisse überprüfen, wird Ihnen angezeigt, ob es sich um ein technisches Problem oder nur um einen Fall niedriger Übereinstimmungsraten handelt. Eine niedrige Übereinstimmungsrate zeigt, dass Ihr Ziel für Ihre ausgewählten Segmente nicht besonders gut ist. Ein Unterschied zwischen Audience Manager und dem Ziel in den insgesamt adressierbaren Zielgruppenzahlen deutet jedoch auf eine Integration, Synchronisierung oder ein anderes technisches Problem hin. Wenden Sie sich in diesen Fällen an Ihren Kundenbetreuer.