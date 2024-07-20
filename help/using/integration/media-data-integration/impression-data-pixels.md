---
description: Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Adserver-Makros, um Kampagnenattribute an Audience Manager zu senden.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 16%

---

# Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe{#capturing-campaign-impression-data-via-pixel-calls}

Ein Ansatz zum Senden von Mediendaten an Audience Manager verwendet Adserver-Makros, um Kampagnenattribute an Audience Manager zu senden.

Diese Methode wird häufig als &quot;Verpixeln der kreativen Inhalte&quot;bezeichnet. Diese Datenpunkte werden von den Makros des Drittanbieters für Anzeigen-Server dynamisch in den [!DNL Audience Manager]-Pixelcode eingefügt, mit denen alle Impressionen und Klicks basierend auf den wichtigsten Berichtsattributen der Kampagne zugeordnet und gemeldet werden. Die aggregierten Daten bieten eine einheitliche Sicht auf die Kampagnenleistung, helfen beim Identifizieren benutzerdefinierter Konversionspfade und helfen Kunden, die Sequenz der Adserver-Ereignisse zu verbessern, die zu Konversionen führen.

## Syntax von Ereignisaufrufen

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) kennzeichnen Codeelemente und -optionen. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

Der Ereignisaufruf erfasst Impressions- und Konversionsdaten und sendet sie an die [!DNL Audience Manager] [Datenerfassungsserver](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Dieser Prozess beruht auf Werbe-Servern von Drittanbietern, wo der Aufruf in ein Creative platziert wird und somit bestimmt wird, welche Inhalte in den Code eingefügt werden. Die Werbeserver von Drittanbietern (z. B. [!DNL DFA]) können diesen Code in jeder Ad-Impression platzieren. Darüber hinaus verwendet ein Anzeigenaufruf kein [!DNL JavaScript] oder Frame-Busting-Techniken, um auf Publisher-Daten außerhalb des Anzeigen-Tags zuzugreifen.

Ereignisaufrufe bestehen aus Schlüssel-Wert-Paaren, die die folgende Syntax verwenden:

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Im Schlüssel-Wert-Paar ist die Wertvariable eine ID oder ein Makro, die vom Anzeigen-Server eingefügt wird. Wenn das Anzeigen-Tag geladen wird, wird dieser `%macro%` durch die erforderlichen, entsprechenden Werte ersetzt. Dieser Aufruf gibt keine Antwort zurück.

## Unterstützte Schlüssel-Wert-Paare {#supported-key-value-pairs}

Aufrufe von Impressionsereignissen akzeptieren Daten, die zu Schlüssel-Wert-Paaren gebildet werden. In der folgenden Tabelle sind die Schlüssel aufgeführt und beschrieben, die zum Speichern dieser Variablen verwendet werden. Viele davon sind erforderlich, wenn Sie Daten in den [Audience Optimization-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) erfassen und analysieren möchten.

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
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihren Advertiser. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> -Berichte. </p> <p>Optional.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihre Geschäftseinheit. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> -Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-Busting-Wert. <span class="keyword"> Audience Manager </span> sendet automatisch Cache-Control-Header, die von den meisten Browsern und Proxys berücksichtigt werden. Wenn Sie zusätzliche Cache-Busting durchführen möchten, fügen Sie diesen Parameter in einen Ereignisaufruf ein, gefolgt von einer zufälligen Zeichenfolge. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> -Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In diesem Kontext instanziiert <code> d_cid </code> ein Schlüssel-Wert-Paar, mit dem Sie einen Mobilgerätetyp einer eindeutigen Benutzer-ID (DPUUID) zuordnen können. Eine feste ID bestimmt den Mobilgerätetyp. Der -Wert, d. h. die Benutzer-ID, kann variieren. Trennen Sie das Schlüssel-Wert-Paar durch <code> %01 </code>, das ein nicht druckbares Steuerzeichen ist. Dieser Parameter akzeptiert die folgenden Schlüssel: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifiziert ein Android (GAID)-Gerät. Beispiel: <code> d_cid = 20914 %01 1234 </code> gibt an, dass Benutzer 1234 mit einem Android-Gerät verknüpft ist. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifiziert ein iOS (IDFA)-Gerät. Beispiel: <code> d_cid = 20915 %01 5678 </code> gibt an, dass Benutzer 5678 mit einem iOS-Gerät verknüpft ist. </li> 
    </ul> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numerische kreative ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> -Berichte. </p> </td> 
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
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> -Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrations-Code der Plattform, die die Metadaten bereitstellt (z. B. DFA, Atlas, GBM, Media Math usw.). </p> <p>Erforderlich für <span class="wintitle"> Audience Optimization </span> -Berichte. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p> <p><code>gdpr</code> kann 0 (DSGVO trifft nicht zu) oder 1 (DSGVO trifft zu) betragen.</p> <p>Der Standardwert ist 0.</p><p>Optional.</p><p>Wenn <code>gdpr=1</code>, sollte der Parameter <code>gdpr_consent</code> den IAB TC-Zustimmungsparameter enthalten, damit die Daten erfolgreich verarbeitet werden können. Andernfalls werden alle Daten gelöscht.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr=1</code>, wird <code>${gdpr_consent_XXXX}</code> durch die Zeichenfolge <code>gdpr_consent</code> und die Anbieter-ID ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Wenden Sie sich an Ihren Adobe Audience Manager-Berater oder -Kundenbetreuer, um die genaue URL für die Kundendomäne zu erhalten.

## Zusätzliche Funktion - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Sie können Pixelaufrufe verwenden, um die [Audience Optimization-Berichte](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) zu aktivieren. Siehe [Überblick und Zuordnungen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) , wenn Sie die Berichte mit Pixel versorgen möchten.

>[!MORELIKETHIS]
>
>* [Daten- und Metadatendateien für Audience Optimization-Berichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
