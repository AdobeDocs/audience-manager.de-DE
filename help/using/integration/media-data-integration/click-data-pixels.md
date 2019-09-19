---
description: 'null '
seo-description: 'null '
seo-title: Erfassen von Kampagnen-Klickdaten über Pixelaufrufe
solution: Audience Manager
title: Erfassen von Kampagnen-Klickdaten über Pixelaufrufe
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Die Klick-Tracking ermöglicht die Messung des Besuchereinsatzes während der gesamten Kampagne, da sie Klick-basierte Aktivitäten für Kreative von Drittanbietern erfasst. Ähnlich wie bei der Impressionserfassung wird ein Ereignisaufruf zur Verarbeitung an die Audience Manager-Datenerfassungsserver ([!UICONTROL DCS]) gesendet. Der Besucher wird dann zur gewünschten Webadresse weitergeleitet.

## Voraussetzungen

Für Klick-Tracking-Aufrufe sind die folgenden Parameter erforderlich:

* `d_event=click`: Ein Schlüssel-Wert-Paar, das einen Ereignisaufruf als Klickereignis identifiziert.
* `d_rd=redirect URL`: Ein Schlüssel-Wert-Paar, das eine kodierte Umleitung enthält [!DNL URL].

Darüber hinaus kann der Aufruf Schlüssel-Wert-Paare enthalten, die für die Eigenschaftsqualifikation oder zur Bereitstellung von Daten und Metadaten für andere Berichte verwendet werden können.

## Anforderungsbeispiel

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Antwort

Die Antwort leitet den Browser zu dem [!DNL URL] im `d_rd` Parameter angegebenen zurück. Die Antwortzeichenfolge kann Werte enthalten, die von einem der unten aufgeführten unterstützten Makros generiert wurden.

Basierend auf dem obigen Beispiel wird der Browser zu folgenden Elementen umgeleitet [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## Unterstützte Makros

Klickereignisse unterstützen die in der folgenden Tabelle aufgeführten Makros. Ein Makro ist eine kleine Einheit von eigenständigem Code, der aktiviert wird, wenn das Anzeigen-Tag zur Kampagnen- und Benutzerverfolgung geladen wird. Die Makros werden zusammen mit dem Ziel weitergeleitet, [!DNL URL]sofern sie mit folgendem Format gekennzeichnet sind: `%macro%`. Einige Schlüssel haben keine Makros und akzeptieren stattdessen einen hartkodierten ID-Wert. Schlüssel, die hartcodierte Werte akzeptieren, sind erforderlich, wenn Sie Daten in den [Zielgruppenoptimierungsberichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md)analysieren möchten.

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col02" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>Numerische Anzeigengruppen-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Kein Makro. </p> <p>Akzeptiert einen hartkodierten ID-Wert. </p> </td> 
   <td colname="col2"> <p>Advertiser-ID.</p> <p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen in Zusammenhang steht.</p> <p> Erforderlich für Berichte zur <span class="wintitle"> Zielgruppenoptimierung</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>Numerische ID für die Geschäftseinheit. </p> <p> Erforderlich für Berichte zur <span class="wintitle"> Zielgruppenoptimierung</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p> Erforderlich für Berichte zur <span class="wintitle"> Zielgruppenoptimierung</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Numerische kreative ID vom Anzeigen-Server. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> <p>Wird häufig mit <code> d_dpuuid</code> verwendet, um eine Datenanbieter-ID mit einer Benutzer-ID zu verknüpfen. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>Vom Datenanbieter bereitgestellte eindeutige Benutzer-ID. </p> <p>Wird häufig mit <code> d_dpid</code> verwendet, um eine Benutzer-ID mit einer Datenanbieter-ID zu verknüpfen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>Die numerische Regions-ID für den DCS-Cluster, der eine Anforderung bereitstellt. Weitere Informationen zum DCS finden Sie unter <a href="../../reference/system-components/components-data-collection.md"> Datenerfassungskomponenten</a>. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Zufallszahl, die zum Busten des Cache verwendet wird. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID der Quelle, aus der Audience Manager die Metadaten abruft. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uid%</code> </p> </td> 
   <td colname="col2"> <p>Geben Sie die ID des Besuchers direkt in der URL an, anstatt sich auf das Demdex-Cookie zu verlassen. </p> <p>Optional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_apply%</code> </p> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a> </p><p><code>gdpr</code> kann 0 (GDPR ist nicht anwendbar) oder 1 (GDPR gilt) betragen.</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_approval</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_approval%</code> </p> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr = 1</code>, wird <code>%gdpr_consent%</code> durch die Zeichenfolge <code>gdpr_consent</code> ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Beispiel zu Makros

In diesem Beispiel wird veranschaulicht, wie die Makros für Kreativelemente, Adgroup und Platzierung übergeben werden. Es wird davon ausgegangen, dass die Werte für jeden Parameter im nicht umgeleiteten Teil des Clicktracking-Aufrufs weitergegeben werden.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Anfrage

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## Antwort

Basierend auf dem obigen Beispiel wird der Browser zu folgenden Elementen umgeleitet [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_LIKE_THIS]
>
>* [Daten- und Metadatendateien für Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

