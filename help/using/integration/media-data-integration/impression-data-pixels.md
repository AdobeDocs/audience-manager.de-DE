---
description: Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Kampagnenattribute an Audience Manager zu senden.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Erfassen von Campaign-Impressionsdaten über Pixel-Aufrufe
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 14%

---

# Erfassen von Campaign-Impressionsdaten über Pixel-Aufrufe{#capturing-campaign-impression-data-via-pixel-calls}

Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Kampagnenattribute an Audience Manager zu senden.

Diese Methode wird oft als „Pixeln des Kreativen“ bezeichnet. Diese Datenpunkte werden von den Ad-Server-Makros von Drittanbietern dynamisch in den [!DNL Audience Manager]-Pixel-Code eingefügt. Diese werden verwendet, um alle Impressionen und Klicks basierend auf den wichtigsten Berichtsattributen der Kampagne zuzuordnen und zu melden. Die aggregierten Daten bieten eine einheitliche Ansicht der Kampagnenleistung, helfen bei der Identifizierung benutzerdefinierter Konversionspfade und helfen Kunden, die Sequenz von Anzeigen-Server-Ereignissen zu verbessern, die zu Konversionen führen.

## Syntax des Ereignisaufrufs

>[!NOTE]
>
>Die Textstile (`monospaced text`, *,*, Klammern `[ ]` `( )` usw.) zeigen Code-Elemente und -Optionen an. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

Der Ereignisaufruf erfasst Impression- und Konversionsdaten und sendet sie an die [!DNL Audience Manager]Datenerfassungs[Server](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Dieser Prozess beruht auf Werbe-Servern von Drittanbietern, wo der Aufruf in ein Creative platziert wird und somit bestimmt wird, welche Inhalte in den Code eingefügt werden. Die Werbeserver von Drittanbietern (z. B. [!DNL DFA]) können diesen Code in jeder Ad-Impression platzieren. Darüber hinaus verwendet ein Anzeigenaufruf kein [!DNL JavaScript] oder Frame-Busting-Techniken, um auf Publisher-Daten außerhalb des Anzeigen-Tags zuzugreifen.

Ereignisaufrufe bestehen aus Schlüssel-Wert-Paaren, die die folgende Syntax verwenden:

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Im Schlüssel-Wert-Paar ist die Wert-Variable eine ID oder ein Makro, die bzw. das vom Anzeigen-Server eingefügt wurde. Wenn das Anzeigen-Tag geladen wird, wird dieses `%macro%` durch die erforderlichen, entsprechenden Werte ersetzt. Dieser Aufruf gibt keine Antwort zurück.

## Unterstützte Schlüssel-Wert-Paare {#supported-key-value-pairs}

Impression-Ereignisaufrufe akzeptieren Daten, die in Schlüssel-Wert-Paare gebildet werden. In der folgenden Tabelle sind die Schlüssel zum Speichern dieser Variablen aufgeführt und beschrieben. Viele dieser Funktionen sind erforderlich, wenn Sie Daten in den [Audience Optimization-Berichten erfassen und analysieren ](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>Numerische Anzeigengruppen-ID vom Anzeigenserver. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrations-Code für Ihren Advertiser. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> Berichte. </p> <p>Optional.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrations-Code für Ihre Geschäftseinheit. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-Busting-Wert. <span class="keyword"> Audience Manager </span> sendet automatisch Header von Cache-Steuerelementen, die von den meisten Browsern und Proxys berücksichtigt werden. Wenn Sie zusätzliches Cache-Busting durchführen möchten, schließen Sie diesen Parameter in einen Ereignisaufruf ein, gefolgt von einer zufälligen Zeichenfolge. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In diesem Kontext instanziiert <code> d_cid </code> ein Schlüssel-Wert-Paar, mit dem Sie einen Mobilgerätetyp mit einer eindeutigen Benutzer-ID (DPUUID) verknüpfen können. Eine feste ID bestimmt den Mobilgerätetyp. Der Wert, der die Benutzer-ID ist, kann variieren. Trennen Sie das Schlüssel-Wert-Paar durch <code> %01 </code>, bei dem es sich um ein nicht druckbares Steuerzeichen handelt. Dieser Parameter akzeptiert die folgenden Schlüssel: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifiziert ein Android-Gerät (GAID). Beispielsweise gibt <code> d_cid = 20914 %01 1234 </code> an, dass der Benutzer 1234 mit einem Android-Gerät verknüpft ist. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifiziert ein iOS-Gerät (IDFA). Beispielsweise gibt <code> d_cid = 20915 %01 5678 </code> an, dass der Benutzer 5678 mit einem iOS-Gerät verknüpft ist. </li> 
    </ul> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numerische Kreativ-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifiziert einen Ereignisaufruf als Impression-Ereignis. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Datenquelle-ID oder Integrations-Code der Plattform, die die Metadaten bereitstellt (z. B. DFA, Atlas, GBM, Media Math usw.). </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> Berichte. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p> <p><code>gdpr</code> kann 0 (die DSGVO gilt nicht) oder 1 (die DSGVO gilt nicht) sein.</p> <p>Der Standardwert ist 0.</p><p>Optional.</p><p>Wenn <code>gdpr=1</code>, sollte der <code>gdpr_consent</code> den IAB-TC-Einverständnisparameter enthalten, um die Daten erfolgreich zu verarbeiten. Andernfalls werden alle Daten gelöscht.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Falls <code>gdpr=1</code>, wird <code>${gdpr_consent_XXXX}</code> durch die <code>gdpr_consent</code> Zeichenfolge und die Anbieter-ID ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Die genaue URL für die Client-Domain erhalten Sie bei Ihrem Adobe Audience Manager-Beratungs- oder Konto-Lead.

## Zusätzliche Funktionalität - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Sie können Pixel-Aufrufe verwenden, um die [Audience Optimization-Berichte zu ](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Unter [Übersicht und Zuordnungen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) finden Sie Informationen darüber, ob die Berichte anhand von Pixeln erstellt werden sollen.

>[!MORELIKETHIS]
>
>* [Daten- und Metadatendateien für das Audience Optimization von Berichten](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
