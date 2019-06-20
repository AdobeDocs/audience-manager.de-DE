---
description: Eine Übersicht über die Funktion "Addressable Audience" und Anwendungsfälle.
keywords: DIL 
seo-description: Eine Übersicht über die Funktion "Addressable Audience" und Anwendungsfälle.
seo-title: Addressable Audiences
solution: Audience Manager
title: Addressable Audiences
topic: DIL-API
uuid: 3 eb 1335 a -6949-452 b-b 77 a -697 c 22856 cb 3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

Eine Übersicht über die Funktion &quot;Addressable Audience&quot; und Anwendungsfälle.

## Was ist eine Addressable Audience? {#addressable-audience-description}

Die [!UICONTROL Addressable Audiences] Funktion zeigt Ihnen die Überlappung zwischen den Zielgruppen, die Sie über alle Ihre Eigenschaften hinweg sehen, wo [!DNL Audience Manager] Daten und Ihr ausgewählte Ziel erfasst werden. Um dieses Konzept zu verstehen, sehen Sie sich die unten stehende Abbildung an. Die Überlappung zwischen den einzelnen Kreisen stellt die unterschiedlichen Typen an adressierbaren Zielgruppen dar.

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
   <td colname="col1"> <p> <b>Audience Manager - Ansprechbare Zielgruppe für ein Ziel</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl aller Geräte, die auf Plattformebene auf Plattformebene mit allen Kunden interagiert haben und mit Ihrem ausgewählten Ziel abgeglichen werden können. </p> <p>Diese Metrik ist nützlich, da sie Folgendes zeigt: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Die Größe der gesamten addressable audience, die <span class="keyword"> Audience Manager</span> auf einem bestimmten Targeting-Ziel erreichen kann. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Wie groß der <span class="keyword"> Audience Manager</span> -Profilpool für eine Targeting-Plattform und die Größe ihrer Zielgruppen ist. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zielgruppe für Kunden insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl von Geräten, die entweder eine regelbasierte Eigenschaft in Ihren Eigenschaften oder eine Onboardanmerkung aus Ihren Offline-Dateien während des Look-Back-Fensters haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Addressable Audience Match Rate</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Eine Anzahl der Überlappung von Geräten, die entweder eine regelbasierte Eigenschaft oder eine Onboardanmerkung während des Rückruffensters und der Geräte, die eine ID besitzen, während der Synchronisierung erreicht haben, unabhängig vom Zeitpunkt der Synchronisierung. </p> 
    </draft-comment> <p>Diese Metrik stellt Geräte dar, die: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Entweder eine regelbasierte oder eine aufgenommene Eigenschaft während des Look-Back-Fensters <b>(UND)</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Eine ID wird unabhängig vom Synchronisierungszeitpunkt mit dem ausgewählten Ziel synchronisiert. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kundenübereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Customer Addressable Audience ÷ Customer Total Audience Express as a %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Segmentpopulation insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl aller Geräte, die während des Berichtsabschnitts ein Mitglied Ihres Segments waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die dem Segment während des Berichts-Rückblickzeitraums gehören und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieterdaten sowie Drittanbieter- und Drittanbieter-Daten über Eigenschaften enthalten, die im <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace erworben</a>wurden. </p> <p> <p>Tipp: Bei Verwendung mit dem 1-Tage-Blickzeitraum kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer Segmente zu verstehen. Dies liegt daran, dass die Metrik <span class="wintitle"> "Segment Addressable Audience</span> " die Benutzer darstellt, die im vorherigen Tag ein Segment aufriefen. Kombinieren Sie dies mit der Tatsache, dass <span class="keyword"> Audience Manager</span> <span class="wintitle"> täglich Addressable Audiences</span> aktualisiert, diese Metrik kombiniert und diese Metrik die aktuellste Momentaufnahme Ihrer Segmente bereitstellt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentübereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Segment Addressable Audience ÷ Gesamtsegmentpopulation ausgedrückt als %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

Die [!UICONTROL Addressable Audience] Funktion verwandelt dieses abstrakte Konzept in quantifizierbare Daten. In [!DNL Audience Manager]zeigt diese Funktion Zielgruppenüberlappungen mit Datenvisualisierungen an, die zusammen mit numerischen Daten in Tabellenform einen Überblick liefern.

[!UICONTROL Addressable Audiences] befindet **[!UICONTROL Audience Data > Destinations]**. Wählen **[!UICONTROL Integrated Platforms > Device-Based]** Sie diese Option, um adressierbare Zielgruppen-Metriken anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der Landingpage Addressable Audiences sehen können, stehen zur Verfügung:

| Metrik | Beschreibung |
---------|----------|
| **Addressable Audience (devices)** | Diese Metrik stellt die Kundenaddressable Audience (in der Tabelle oben beschrieben) *für die letzten 30 Tage dar.* |
| **Übereinstimmungsrate** | Diese Metrik stellt die Addressable Audience Match Rate (in der Tabelle oben beschrieben) *für die letzten 30 Tage dar*. |
| **Lebensdauernutzbare Zielgruppe (Geräte)** | Eine Anzahl aller Geräte, die auf Plattformebene auf Plattformebene mit allen Kunden interagiert haben und mit diesem Ziel abgeglichen werden können. Weitere Informationen finden Sie unter [Metriken](/help/using/features/addressable-audiences.md#platform-level-metrics) auf Plattformebene. |

Klicken Sie auf den Namen eines Server-to-Server-Ziels, um Ihre adressierbaren Zielgruppendaten anzuzeigen. Beachten Sie, dass diese Funktion nur Daten für Server-zu-Server-Ziele zurückgibt und für Zugriff Administratorberechtigungen erforderlich sind.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten kann Ihnen bei Folgendem helfen:

* **Prognosen und Planung:**[!UICONTROL Segment Addressable Audience] erhalten mehr Granularität zu den Segmenten, die Sie an ein Ziel für Zielgruppentargeting und -aktivierung senden möchten.

* **Leistungsüberprüfungen:** Die [!UICONTROL Addressable Audiences] Funktion ist außerdem ein Werkzeug zur Fehlerbehebung. Damit können Sie die Kampagnenleistung überprüfen, die Reichweite der Kampagne verstehen und Sie mit Targeting-/Aktivierungspartnern vergleichen, wenn Sie die erwarteten Ergebnisse nicht sehen.

### Untersuchen von Drittanbieterdaten und Auswirkungen auf Übereinstimmungsraten

Vor dem Kauf von Drittanbieterdaten für die Zielgruppenakquise können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie eine fundierte Entscheidung treffen, bevor Sie neue Daten kaufen. Die ID-Synchronisierungen für erworbene Drittanbieter-Daten hängen nicht nur von der Überlappung Ihrer Daten, sondern von den Hostdrucken von Drittanbietern mit allen anderen [!DNL Audience Manager] Kunden ab. Ihr [!DNL Adobe] Berater kann Ihnen dabei helfen, weitere relevante Datenquellen zur Optimierung von Kampagnen zu identifizieren.

### Mobile Benutzer und Übereinstimmungsraten

Beim Versuch, eine Verbindung zu einer Verbindung [!DNL Safari] oder mobilen App-Benutzern herzustellen, bei denen keine Drittanbieter-Cookies vorhanden sind, gibt es Lücken. Dadurch ist es schwierig, Benutzer mit einigen Partnern zu synchronisieren, da in den Medienbereitstellungsprotokollen nur solche [!DNL Adobe] IDs für synchronisierte Drittanbieter-Cookies bereitgestellt werden. Dies ist ein Grund dafür, warum [Sie niedrige Übereinstimmungsraten](../features/addressable-audiences.md#low-match-rates) für Ihre Ziele sehen können.

## Datumsbereiche in Adressierbaren Zielgruppen und Zielen {#date-ranges}

Lesen Sie die unten stehenden Abschnitte für verfügbare Datumsbereiche und wie Daten aus jedem Intervall in den Berichten für einen [!UICONTROL Addressable Audience] oder [!UICONTROL Destination].

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für Ihre [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) verwenden dieselben Datumsbereichsintervalle. Die Datumsbereichsoptionen umfassen:

* [!UICONTROL Last 1 Day] (Dieses Intervall wird von Mitternacht bis Mitternacht des letzten 24 Stunden ausgeführt. Es handelt sich nicht um eine reale oder aktuelle Metrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Datumsangaben und Datumsbereiche werden in der [!DNL UTC] Zeitzone festgelegt. Siehe [Zeitzonen in Audience Manager](../reference/aam-time-zones.md).

## Daten in Datumsbereichsintervallen {#date-range-intervals}

Die [!UICONTROL Addressable Audience] und [!UICONTROL Destination] Metriken geben individuelle Benutzer für das ausgewählte Zeitintervall zurück. Ein Besucher wird beispielsweise nur einmal gezählt, auch wenn er mehrmals auf Ihre Site gelangt. Der erste Besuch ist der eindeutige Besuch und wird aufgezeichnet. Die nachfolgenden Besuche kehren wieder zurück und werden nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder ältere Zeiträume. Außerdem werden die Daten aus jedem Berichtsintervall im Zeitverlauf gesendet. Nehmen wir an, Sie sehen zwei Besucher, nachdem Sie die [!UICONTROL Last 30 Days] Option ausgewählt haben. Diese Besucher können in den Berichten:

* *Wird in den Ergebnissen* berücksichtigt, die von längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *Wird nicht in die kürzeren Intervalle* einbezogen, die vor der [!UICONTROL Last 30 Day] Option stehen (aktuelle, 7 Tage und 14 Tage).

Und am Tag 31 erscheinen diese Besucher nur in den 60 Tagen, 90 Tagen und [!UICONTROL Lifetime] den Ergebnissen. Sie haben aus dem 30-Tage-Intervall herausgefallen. Besucher verlassen sich nicht aus dem [!UICONTROL Lifetime] Intervall.

## Addressable Audience Metrics {#addressable-audience-metrics}

In diesem Abschnitt werden die verfügbaren Metriktypen beschrieben [!UICONTROL Addressable Audiences].

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten für Eigenschaften zurück, die beim Aufrufen Ihrer Site oder beim Senden von eingehenden Datendateien durch die Besucher realisiert wurden [!DNL Audience Manager]. Diese Metrik bietet eine umfassende Ansicht der Zielgruppengröße für Ihr Konto.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Kundenadressierbare Zielgruppe</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Eine Anzahl der Überlappung von Geräten, die entweder eine regelbasierte Eigenschaft oder eine Onboardanmerkung während des Rückruffensters und der Geräte, die eine ID besitzen, während der Synchronisierung erreicht haben, unabhängig vom Zeitpunkt der Synchronisierung. </p> 
    </draft-comment> <p>Diese Metrik stellt Geräte dar, die: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Entweder eine regelbasierte oder eine aufgenommene Eigenschaft während des Look-Back-Fensters <b>(UND)</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Eine ID wird unabhängig vom Synchronisierungszeitpunkt mit dem ausgewählten Ziel synchronisiert. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zielgruppe für Kunden insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl von Geräten, die entweder eine regelbasierte Eigenschaft in Ihren Eigenschaften oder eine Onboardanmerkung aus Ihren Offline-Dateien während des Look-Back-Fensters haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kundenübereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Customer Addressable Audience ÷ Customer Total Audience Express as a %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Übereinstimmungsmetriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zur Segmentmitgliedschaft zurück. Sie helfen Ihnen, eine granularere und präzisere Ansicht der Zielgruppengröße für jeden Ihrer Segmente bereitzustellen.

>[!NOTE]
>
>Die Art und Weise, wie das Look-Back-Fenster auf Segmentebene angewendet wird, unterscheidet sich vom Kundenlevel. Besucher können auf die Site gelangen und eine Eigenschaft vor 10 Tagen erstellen. Sie könnten sich dann für ein Segment qualifizieren, da es vor zwei Tagen aus dem Segment abgebrochen wird. Wenn die Suche nach einem Tag erfolgt, werden diese Besucher auf Segmentebene, jedoch nicht auf Kundenebene gezählt.

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
   <td colname="col2"> <p>Die Anzahl der Benutzer, die dem Segment während des Berichts-Rückblickzeitraums gehören und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieterdaten sowie Drittanbieter- und Drittanbieter-Daten über Eigenschaften enthalten, die im <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace erworben</a>wurden. </p> <p> <p>Tipp: Bei Verwendung mit dem 1-Tage-Blickzeitraum kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer Segmente zu verstehen. Dies liegt daran, dass die Metrik <span class="wintitle"> "Segment Addressable Audience</span> " die Benutzer darstellt, die im vorherigen Tag ein Segment aufriefen. Kombinieren Sie dies mit der Tatsache, dass <span class="keyword"> Audience Manager</span> <span class="wintitle"> täglich Addressable Audiences</span> aktualisiert, diese Metrik kombiniert und diese Metrik die aktuellste Momentaufnahme Ihrer Segmente bereitstellt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentpopulation insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl aller Geräte, die während des Berichtsabschnitts ein Mitglied Ihres Segments waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentübereinstimmungsrate</b> </p> </td> 
   <td colname="col2"> <p>Segment Addressable Audience ÷ Gesamtsegmentpopulation ausgedrückt als %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriken auf Plattformebene {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle Audience Manager-Kunden erfasst wurden. Sie können eine umfassendere Ansicht der Zielgruppe des Kunden im Vergleich zu den aggregierten Audience Manager-Kunden bereitstellen.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager - Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>Eine Anzahl aller Geräte, die auf Plattformebene auf Plattformebene mit allen Kunden interagiert haben und mit Ihrem ausgewählten Ziel abgeglichen werden können. </p> <p>Diese Metrik ist nützlich, da sie Folgendes zeigt: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Die Größe der gesamten addressable audience, die <span class="keyword"> Audience Manager</span> auf einem bestimmten Targeting-Ziel erreichen kann. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Wie groß der <span class="keyword"> Audience Manager</span> -Profilpool für eine Targeting-Plattform und die Größe ihrer Zielgruppen ist. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vergleich von Kunden- und Segment Addressable Audiences{#comparing-metrics}

Sie sollten die [!UICONTROL Customer Addressable Audience] und [!UICONTROL Segment Addressable Audience] Metriken nicht vergleichen, um festzustellen, ob eine aussagekräftiger als die andere ist. Dies sind separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, werden diese aus verschiedenen Datensätzen abgeleitet. In diesem Fall sollten Sie keine Schlüsse auflösen, wenn eine Metrik größer als die andere ist. Sie können Folgendes sagen:

* [!UICONTROL Customer Addressable Audiences] is based on trait realizations *for your own, first-party data*. Diese Metrik bietet eine umfassende, umfassende Ansicht Ihrer Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] auf Segmentqualifizierung *für Ihre eigenen Erstanbieterdaten sowie Daten aus zweiter und dritter Partei basiert*. Diese Metrik bietet eine granulare, präzisere Ansicht Ihrer addressierbaren Zielgruppen auf einer Targeting-Plattform.

## Ursachen für niedrige Übereinstimmungsraten für adressierbare Zielgruppen {#low-match-rates}

Allgemeine Elemente, die für niedrige [!UICONTROL Addressable Audience] Übereinstimmungsraten oder Diskrepanzen in gemeldeten Zahlen verantwortlich sind.

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
   <td colname="col1"> <p> <b>Mobiler Traffic</b> </p> </td> 
   <td colname="col2"> <p>Die meisten Server-zu-Server-Integrationen basieren auf Synchronisierungsprozessen, die von Drittanbieter-Cookies unterstützt werden. Mobile Umgebungen verwenden jedoch keine Drittanbieter-Cookies. Somit erscheinen Ihre Addressable Audience-Zahlen im Vergleich zur Segmentgröße möglicherweise niedrig. </p> <p>Ab Januar 2018 können Sie mobile Zielgruppen in denselben Google- und Adobe Advertising Cloud-Zielen aktivieren, die für Cookie-basierte Zielgruppen eingerichtet wurden. Sie können zwar Segmente mit kombinierten Cookies und einer mobilen ID-Mitgliedschaft an Ihre Google- und Advertising Cloud-Ziele senden, beachten Sie jedoch, dass Addressable Audiences nur die Überlappung zwischen Cookie-IDs und Zielen anzeigen. Audience Manager sendet 100% der mobilen Zielgruppen an Ziele, mobile Zielgruppen werden jedoch nicht von der Metrik "Addressable Audience" gemessen. </p> <p> <p><b>Hinweis</b>: Nehmen Sie z. B. ein Segment mit einer Bevölkerung von 1.000.000 an. Wenn Sie dieses Segment einem Google- oder Adobe Advertising Cloud-Ziel zuordnen, wird möglicherweise eine Addressable Audience of 700.000 devices und eine Übereinstimmungsrate von 70% angezeigt. Die Mitgliedschaft 700.000 besteht aus Cookie-IDs, die eine ID-Synchronisierung mit dem Ziel enthalten. Ihr Addressable Audience kann tatsächlich viel höher ausfallen, da adressierbare mobile IDs nicht in dieser Metrik angezeigt werden. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari-Traffic</b> </p> </td> 
   <td colname="col2"> <p>Safari blockiert Drittanbieter-Cookies. Dadurch wird verhindert, dass Audience Manager IDs mit dem Ziel synchronisiert. Mit der Einführung von <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>können Sie erwarten, dass Ihre adressierbaren Zielgruppen keine Safari-Benutzer enthalten. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Verfolgte Medienimpressionen</b> </p> </td> 
   <td colname="col2"> <p>Aufgrund der Best Practices des Werbeservers werden ID-Synchronisierungen nicht innerhalb von Anzeigentags vorgenommen. Kunden, die eine große Menge an Offsite-Werbung durchführen, synchronisieren Benutzer nicht mit Drittanbieterintegrationen in diesen Umgebungen. Außerdem kann eine große Menge an erfassten Medienimpressionsdaten die adressierbaren Zielgruppenzahlen reduzieren. </p> </td>
  </tr> 
 </tbody> 
</table>

## Fehlerbehebung mit Addressable Audiences {#troubleshooting}

Zusätzlich zu den übereinstimmenden Übereinstimmungsraten können Sie auch [!UICONTROL Addressable Audiences] als Fehlerbehebung verwenden.

<!-- addressable-audiences-troubleshooting.xml -->

Nehmen wir an, Sie senden ein Segment an ein Ziel und dieses Ziel zeigt niedrige Berichtszahlen an. Das Überprüfen der [!UICONTROL Addressable Audience] Ergebnisse zeigt Ihnen, ob es sich um ein technisches Problem oder nur um eine geringe Übereinstimmungsrate handelt. Bei einer niedrigen Übereinstimmungsrate ist Ihr Ziel nicht so gut für Ihre ausgewählten Segmente geeignet. Ein Unterschied in den gesamten addressable audience numbers zwischen Audience Manager und dem Ziel deutet jedoch auf eine Integration, Synchronisierung oder ein anderes technisches Problem hin. Wenden Sie sich in diesen Fällen an Ihren Kundenbetreuer.