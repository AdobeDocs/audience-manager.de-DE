---
description: Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Anzeigen-Server-Makros, um Kampagnenattribute an Audience Manager zu senden.
seo-description: Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Anzeigen-Server-Makros, um Kampagnenattribute an Audience Manager zu senden.
seo-title: Erfassen von Kampagnenimpressionsdaten über Pixelabrufe
solution: Audience Manager
title: Erfassen von Kampagnenimpressionsdaten über Pixelabrufe
uuid: 6 ac 44100-4 c 55-4992-8835-0 d 578 bb 4 e 5 c 2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Erfassen von Kampagnenimpressionsdaten über Pixelabrufe{#capturing-campaign-impression-data-via-pixel-calls}

Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Anzeigen-Server-Makros, um Kampagnenattribute an Audience Manager zu senden.

Diese Methode wird häufig als "Kreatives Element" bezeichnet. Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. Die aggregierten Daten bieten eine einheitliche Ansicht der Kampagnenleistung, helfen bei der Identifizierung benutzerspezifischer Konversionspfade und helfen Kunden dabei, die Sequenz von Anzeigenserverereignissen zu verbessern, die zu Konversionen führen.

## Syntax für Ereignisaufruf

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) kennzeichnen Codeelemente und -optionen. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

Der Ereignisaufruf erfasst Impressions- und Konversionsdaten und sendet diese an die [!DNL Audience Manager] [Datenerfassungs-Server](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). Dieser Prozess beruht auf Werbe-Servern von Drittanbietern, wo der Aufruf in ein Creative platziert wird und somit bestimmt wird, welche Inhalte in den Code eingefügt werden. Die Werbeserver von Drittanbietern (z. B. [!DNL DFA]) können diesen Code in jeder Ad-Impression platzieren. Darüber hinaus verwendet ein Anzeigenaufruf kein [!DNL JavaScript] oder Frame-Busting-Techniken, um auf Publisher-Daten außerhalb des Anzeigen-Tags zuzugreifen.

Ereignisaufrufe bestehen aus Schlüssel/Wert-Paaren, die die folgende Syntax verwenden:

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

Im Schlüssel-Wert-Paar ist die Wert-Variable eine ID oder ein vom Anzeigenserver eingefügter Makro. When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. Dieser Aufruf gibt keine Antwort zurück.

## Supported Key-Value Pairs {#supported-key-value-pairs}

Impressionsereignisse akzeptieren Daten, die in Schlüssel/Wert-Paaren aufgeteilt sind. In der folgenden Tabelle sind die Schlüssel aufgeführt und beschrieben, die zum Aufnehmen dieser Variablen verwendet werden. Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>Numerische Anzeigengruppen-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihren Werbetreibenden. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihre Geschäftseinheit. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ break </code> </p> </td> 
   <td colname="col2"> <p>Cache-Busting-Wert. <span class="keyword"> Audience Manager </span> sendet automatisch Cachesteuerungsheader, die von den meisten Browsern und Proxys beachtet werden. Wenn Sie weitere Cache-Busting durchführen möchten, fügen Sie diesen Parameter in einen Ereignisaufruf ein, gefolgt von einer zufälligen Zeichenfolge. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). Eine feste ID bestimmt den Mobilgerätetyp. Der Wert, die Benutzer-ID, kann variieren. Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. Dieser Parameter akzeptiert die folgenden Schlüssel: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifiziert ein Android-Gerät (GAID). <code> d_ cid = 20914% 01 1234 </code> sagt beispielsweise, dass der Benutzer 1234 mit einem Android-Gerät verknüpft ist. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifiziert ein ios-Gerät (IDFA). <code> d_ cid = 20915% 01 5678 </code> besagt beispielsweise, dass der Benutzer 5678 mit einem ios-Gerät verknüpft ist. </li> 
    </ul> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>Numerische Creative ID vom Anzeigenserver. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event = imp </code> </td> 
   <td colname="col2"> <p>Identifiziert einen Ereignisaufruf als Impressionsereignis. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode der Plattform, die die Metadaten bereitstellt (z. B. DFA, Atlas, GBM, Media Math usw.). </p> <p>Required for <span class="wintitle"> Audience Optimization </span> reports. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p> <p><code>gdpr</code> kann 0 sein (GDPR nicht angewendet) oder 1 (GDPR angewendet).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_ consent</code> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr = 1</code>, wird <code>%gdpr_consent%</code> durch die Zeichenfolge <code>gdpr_consent</code> ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Bitte wenden Sie sich an Ihren Adobe Audience Manager-Consulting oder -kontointeressenten für die genaue URL, die speziell für die Kundendomäne gelten soll.

>[!MORE_ LIKE_ THIS]
>
>* [Daten- und Metadatendateien für Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

