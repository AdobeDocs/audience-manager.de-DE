---
description: Eine Methode zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Kampagnenattribute an Audience Manager zu senden.
seo-description: Eine Methode zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Kampagnenattribute an Audience Manager zu senden.
seo-title: Erfassen von Kampagnenimpressionsdaten über Pixelabrufe
solution: Audience Manager
title: Erfassen von Kampagnenimpressionsdaten über Pixelabrufe
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
translation-type: tm+mt
source-git-commit: 7f71a099157e81c8d17cf018a4c84a69e2205bb4

---


# Erfassen von Kampagnenimpressionsdaten über Pixelabrufe{#capturing-campaign-impression-data-via-pixel-calls}

Eine Methode zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Kampagnenattribute an Audience Manager zu senden.

Diese Methode wird oft als "Verpixeln des kreativen Elements"bezeichnet. Diese Datenpunkte werden von den Drittanbieter-Anzeigenservermakros dynamisch in den [!DNL Audience Manager] Pixelcode eingefügt, die dazu verwendet werden, alle Impressionen und Klicks basierend auf den wichtigen Berichterstellungsattributen der Kampagne zuzuordnen und zu melden. Die aggregierten Daten bieten eine einheitliche Ansicht der Kampagnenleistung, helfen bei der Identifizierung benutzerspezifischer Konversionspfade und helfen Kunden, die Sequenz von Anzeigenserverereignissen zu verbessern, die zu Konversionen führen.

## Ereignisaufrufsyntax

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) kennzeichnen Codeelemente und -optionen. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

Der Ereignisaufruf erfasst Impressions- und Konversionsdaten und sendet diese an die [!DNL Audience Manager] [Datenerfassungs-Server](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). Dieser Prozess beruht auf Werbe-Servern von Drittanbietern, wo der Aufruf in ein Creative platziert wird und somit bestimmt wird, welche Inhalte in den Code eingefügt werden. Die Werbeserver von Drittanbietern (z. B. [!DNL DFA]) können diesen Code in jeder Ad-Impression platzieren. Darüber hinaus verwendet ein Anzeigenaufruf kein [!DNL JavaScript] oder Frame-Busting-Techniken, um auf Publisher-Daten außerhalb des Anzeigen-Tags zuzugreifen.

Ereignisaufrufe bestehen aus Schlüssel-Wert-Paaren, die die folgende Syntax verwenden:

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=Cache-Busterwert
</pre>

Im Schlüssel-Wert-Paar ist die Wertvariable eine ID oder ein Makro, die bzw. das vom Anzeigenserver eingefügt wird. Beim Laden des Ad-Tags `%macro%` wird dieser durch die erforderlichen entsprechenden Werte ersetzt. Dieser Aufruf gibt keine Antwort zurück.

## Unterstützte Schlüssel-Wert-Paare {#supported-key-value-pairs}

Impressionsereignisaufrufe akzeptieren Daten, die zu Schlüssel-Wert-Paaren gebildet werden. In der folgenden Tabelle sind die Tasten aufgeführt und beschrieben, mit denen diese Variablen gespeichert werden. Viele davon sind erforderlich, wenn Sie Daten in den [Zielgruppenoptimierungsberichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md)erfassen und analysieren möchten.

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
   <td colname="col2"> <p>Numerische Anzeigengruppen-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihren Advertiser. </p> <p>Erforderlich für <span class="wintitle"> Berichte zur Zielgruppenoptimierung </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihre Geschäftseinheit. </p> <p>Erforderlich für <span class="wintitle"> Berichte zur Zielgruppenoptimierung </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-Busting-Wert. <span class="keyword"> Audience Manager sendet </span> automatisch Cachesteuerungs-Kopfzeilen, die von den meisten Browsern und Proxys berücksichtigt werden. Wenn Sie zusätzliche Cache-Busting durchführen möchten, fügen Sie diesen Parameter in einen Ereignisaufruf ein, gefolgt von einer zufälligen Zeichenfolge. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Berichte zur Zielgruppenoptimierung </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In diesem Zusammenhang instanziiert <code> d_cid ein Schlüssel-Wert-Paar, mit dem Sie einen Mobilgerätetyp einer eindeutigen Benutzer-ID (DPUUID) zuordnen </code> können. Eine feste ID bestimmt den Mobilgerätetyp. Der Wert (die Benutzer-ID) kann variieren. Trennen Sie das Schlüssel-Wert-Paar durch <code> %01 </code>, das ein nicht druckbares Steuerzeichen ist. Dieser Parameter akzeptiert die folgenden Schlüssel: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">2014: Identifiziert ein Android-(GAID-)Gerät. Beispiel: <code> d_cid = 20914 %01 1234 </code> besagt, dass Benutzer 1234 mit einem Android-Gerät verknüpft ist. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">2015: Identifiziert ein iOS-Gerät (IDFA). Beispiel: <code> d_cid = 20915 %01 5678 </code> besagt, dass Benutzer 5678 mit einem iOS-Gerät verknüpft ist. </li> 
    </ul> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numerische kreative ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Berichte zur Zielgruppenoptimierung </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifiziert einen Ereignisaufruf als Impressionsereignis. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Berichte zur Zielgruppenoptimierung </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode der Plattform, die die Metadaten bereitstellt (z. B. DFA, Atlas, GBM, Media Math usw.) </p> <p>Erforderlich für <span class="wintitle"> Berichte zur Zielgruppenoptimierung </span> . </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p> <p><code>gdpr</code> kann 0 (GDPR ist nicht anwendbar) oder 1 (GDPR gilt) betragen.</p> <p>Der Standardwert ist 0.</p><p>Optional.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_approval</code> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr = 1</code>, wird <code>%gdpr_consent%</code> durch die Zeichenfolge <code>gdpr_consent</code> ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Wenden Sie sich an Ihren Adobe Audience Manager-Berater oder führen Sie einen Kundenbetreuer, um die exakte URL der jeweiligen Clientdomäne anzuzeigen.

>[!MORE_LIKE_THIS]
>
>* [Daten- und Metadatendateien für Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

