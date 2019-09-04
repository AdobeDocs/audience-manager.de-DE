---
description: 'null '
seo-description: 'null '
seo-title: Erfassen von Kampagnenklickdaten über Pixelaufrufe
solution: Audience Manager
title: Erfassen von Kampagnenklickdaten über Pixelaufrufe
uuid: 7 c 3797 f 7-9674-493 d -972 b -38 be 0584 fede
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Durch Klick-Tracking können Besucherinteraktionen in Ihrer gesamten Kampagne gemessen werden, da sie klickbasierte Aktivitäten für kreative Elemente von Drittanbietern erfasst. Ähnlich wie bei der Impressionen wird zur Verarbeitung ein Ereignisaufruf an die Datenerfassungsserver von Audience Manager ([!UICONTROL DCS]) gesendet. Anschließend wird der Besucher zur gewünschten Internetadresse weitergeleitet.

## Voraussetzungen

Klick-Tracking-Aufrufe erfordern die folgenden Parameter:

* `d_event=click`: Ein Schlüssel-Wert-Paar, das einen Ereignisaufruf als Klickereignis bezeichnet.
* `d_rd=redirect URL`: Ein Schlüssel-Wert-Paar, das eine kodierte Umleitung [!DNL URL]enthält.

Darüber hinaus kann der Aufruf Schlüssel-Wert-Paare enthalten, die für die Eigenschaftsqualifizierung oder zur Bereitstellung von Daten und Metadaten für andere Berichte verwendet werden können.

## Beispiel anfordern

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Antwort

Die Antwort leitet den Browser an die [!DNL URL] angegebene im `d_rd` Parameter weiter. Die Antwortzeichenfolge kann Werte enthalten, die durch einen der unten aufgeführten unterstützten Makros generiert wurden.

Basierend auf dem obigen Beispiel wird der Browser an [!DNL URL]Folgendes weitergeleitet:

[!DNL `https://adobe.com/callback?creative=123`]

## Unterstützte Makros

Klickereignisse unterstützen die in der folgenden Tabelle aufgeführten Makros. Ein Makro ist eine kleine Einheit von selbstenthalten Code, die aktiviert wird, wenn das Anzeigen-Tag für Kampagne und Benutzerverfolgung geladen wird. Die Makros werden zusammen mit dem Ziel [!DNL URL]weitergeleitet, sofern sie mit dem folgenden Format markiert sind: `%macro%`. Einige Schlüssel verfügen nicht über Makros und akzeptieren stattdessen einen hartkodierten ID-Wert. Schlüssel, die hartkodierte Werte akzeptieren, sind erforderlich, wenn Sie Daten in den [Zielgruppenoptimierungsberichten analysieren möchten](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ adgroup %</code> </p> </td> 
   <td colname="col2"> <p>Numerische Anzeigengruppen-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col02"> <p>Kein Makro. </p> <p>Akzeptiert einen hartkodierten ID-Wert. </p> </td> 
   <td colname="col2"> <p>Advertiser-ID.</p> <p>Ein Integrationscode für die Datenquelle Ihres Werbetreibenden. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen in Zusammenhang steht.</p> <p> Erforderlich für <span class="wintitle"> Berichte</span> zur Zielgruppenoptimierung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ bu %</code> </p> </td> 
   <td colname="col2"> <p>Numerische ID für die Geschäftseinheit. </p> <p> Erforderlich für <span class="wintitle"> Berichte</span> zur Zielgruppenoptimierung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ campaign %</code> </p> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p> Erforderlich für <span class="wintitle"> Berichte</span> zur Zielgruppenoptimierung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ creative %</code> </p> </td> 
   <td colname="col2"> <p>Numerische Creative ID vom Anzeigenserver. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ id %</code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> <p>Wird häufig mit <code> d_ dpuuid</code> verwendet, um eine Datenanbieter-ID mit einer Benutzer-ID zu verknüpfen. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ dpuuid %</code> </p> </td> 
   <td colname="col2"> <p>Eindeutige Benutzer-ID, die vom Datenanbieter bereitgestellt wird. </p> <p>Wird häufig mit <code> d_ dpid</code> verwendet, um eine Benutzer-ID mit einer Datenanbieter-ID zu verknüpfen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ placement</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ placement %</code> </p> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ region</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ region %</code> </p> </td> 
   <td colname="col2"> <p>Die ID für die numerische Region des DCS-Clusters, der von Diensten eine Anforderung enthält. Weitere Informationen zum DCS finden Sie unter <a href="../../reference/system-components/components-data-collection.md"> Datenerfassungskomponenten</a>. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> % r_ rand %</code> </p> </td> 
   <td colname="col2"> <p>Zufallszahl für Cache-Busting. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ site %</code> </p> </td> 
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ src %</code> </p> </td> 
   <td colname="col2"> <p>DPID der Quelle, aus der Audience Manager die Metadaten abruft. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ uuid %</code> </p> </td> 
   <td colname="col2"> <p>Geben Sie die ID des Besuchers direkt in der URL an, anstatt sich auf Demdex-Cookies verlassen zu müssen. </p> <p>Optional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ apply %</code> </p> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a> </p><p><code>gdpr</code> kann 0 sein (GDPR nicht angewendet) oder 1 (GDPR angewendet).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_ consent</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ consent %</code> </p> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/aam-gdpr/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr = 1</code>, wird <code>%gdpr_consent%</code> durch die Zeichenfolge <code>gdpr_consent</code> ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Beispiel für Makros

Dieses Beispiel demonstriert, wie Sie die kreativen Elemente, Adgruppen und Platzierungsmakros weiterleiten. Es geht davon aus, dass die Werte für jeden Parameter im nicht umgeleiteten Teil des click-tracking-Aufrufs übergeben werden.

<ul class="simplelist"> 
 <li> <code> creative = 1235 </code> </li> 
 <li> <code> campaign = 4709 </code> </li> 
 <li> <code> adgroup = 3408 </code> </li> 
 <li> <code> placement = 1001 </code> </li> 
 <li> <code> src = 203 </code> </li> 
</ul>

## Anfrage

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## Antwort

Basierend auf dem obigen Beispiel wird der Browser an [!DNL URL]Folgendes weitergeleitet:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ LIKE_ THIS]
>
>* [Daten- und Metadatendateien für Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

