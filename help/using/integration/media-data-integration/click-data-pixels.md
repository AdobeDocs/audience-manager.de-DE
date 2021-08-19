---
description: Klick-Tracking ermöglicht die Messung der Besucherinteraktion in der gesamten Kampagne, da Klick-basierte Aktivitäten für kreative Inhalte von Drittanbietern aufgezeichnet werden.
seo-description: Klick-Tracking ermöglicht die Messung der Besucherinteraktion in der gesamten Kampagne, da Klick-basierte Aktivitäten für kreative Inhalte von Drittanbietern aufgezeichnet werden.
seo-title: Erfassen von Kampagnenklickdaten über Pixelaufrufe
solution: Audience Manager
title: Erfassen von Kampagnenklickdaten über Pixelaufrufe
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign-Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 10%

---

# Erfassen von Kampagnenklickdaten über Pixelaufrufe {#capturing-campaign-click-data-via-pixel-calls}

Klick-Tracking ermöglicht die Messung der Besucherinteraktion in der gesamten Kampagne, da Klick-basierte Aktivitäten für kreative Inhalte von Drittanbietern aufgezeichnet werden. Ähnlich wie bei [Impressions collection](/help/using/integration/media-data-integration/impression-data-pixels.md) wird ein Ereignisaufruf zur Verarbeitung an die [!DNL Audience Manager]-Datenerfassungsserver ([!DNL DCS]) gesendet. Der Besucher wird dann zur vorgesehenen Webadresse weitergeleitet.

>[!NOTE]
>
>Wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder Kundenbetreuer für die genaue [!DNL URL], die für die Client-Domäne spezifisch ist.

## Anforderungen

Für Klick-Tracking-Aufrufe sind die folgenden Parameter erforderlich:

* `d_event=click`: Ein Schlüssel-Wert-Paar, das einen Ereignisaufruf als Klickereignis identifiziert.
* `d_rd=redirect URL`: Ein Schlüssel-Wert-Paar, das eine doppelt kodierte Umleitung enthält  [!DNL URL]. Wenn Sie ein Online-Kodierungs-Tool verwenden, führen Sie die Zeichenfolge über den Kodierer aus und kodieren Sie dann das Ergebnis erneut, damit die Umleitung funktioniert.

Darüber hinaus kann der Aufruf Schlüssel-Wert-Paare enthalten, die für die Eigenschaftsqualifizierung oder zur Bereitstellung von Daten und Metadaten für andere Berichte verwendet werden können.

## Anforderungsbeispiel

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Antwort

Die Antwort leitet den Browser zu dem im Parameter `d_rd` angegebenen [!DNL URL] um. Die Antwortzeichenfolge kann Werte enthalten, die von einem der unten aufgeführten unterstützten Makros generiert werden.

Basierend auf dem obigen Beispiel wird der Browser zu folgendem [!DNL URL] umgeleitet:

`https://adobe.com/callback?creative=123`

## Unterstützte Makros

Klickereignisse unterstützen die in der folgenden Tabelle aufgeführten Makros. Ein Makro ist eine kleine Einheit von eigenständigem Code, der aktiviert wird, wenn das Anzeigen-Tag zum Kampagnen- und Benutzertracking geladen wird. Die Makros werden zusammen mit dem Ziel [!DNL URL] übergeben, sofern sie im folgenden Format gekennzeichnet sind: `%macro%`. Einige Schlüssel haben keine Makros und akzeptieren stattdessen einen hartcodierten ID-Wert. Schlüssel, die hartcodierte Werte akzeptieren, sind erforderlich, wenn Sie Daten in den [Audience Optimization-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) analysieren möchten.

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
   <td colname="col02"> <p>Kein Makro. </p> <p>Akzeptiert einen hartcodierten ID-Wert. </p> </td> 
   <td colname="col2"> <p>Advertiser-ID.</p> <p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen in Zusammenhang steht.</p> <p> Erforderlich für <span class="wintitle"> Audience Optimization</span> -Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>Numerische ID für die Geschäftseinheit. </p> <p> Erforderlich für <span class="wintitle"> Audience Optimization</span> -Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p> Erforderlich für <span class="wintitle"> Audience Optimization</span> -Berichte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Numerische kreative ID vom Anzeigen-Server. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> <p>Häufig mit <code> d_dpuuid</code> verwendet, um eine Datenanbieter-ID mit einer Benutzer-ID zu verknüpfen. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>Vom Datenanbieter bereitgestellte eindeutige Benutzer-ID. </p> <p>Häufig mit <code> d_dpid</code> verwendet, um eine Benutzer-ID mit einer Datenanbieter-ID zu verknüpfen. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). Weitere Informationen zur ECID finden Sie unter <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und die Experience Cloud-ID</a>. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>Die numerische Regions-ID für den DCS-Cluster, der eine Anfrage bereitstellt. Weitere Informationen zum DCS finden Sie unter <a href="../../reference/system-components/components-data-collection.md"> Datenerfassungskomponenten</a>. </p> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Zufällige Nummer, die für das Cache-Busting verwendet wird. </p> <p>Optional. </p> </td> 
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
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Geben Sie die ID des Besuchers direkt in der URL an, anstatt sich auf das Demdex-Cookie zu verlassen. </p> <p>Optional. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a> </p><p><code>gdpr</code> kann 0 (DSGVO trifft nicht zu) oder 1 (DSGVO trifft zu) betragen.</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr=1</code>, wird <code>${gdpr_consent_XXXX}</code> durch die <code>gdpr_consent</code>-Zeichenfolge und die Anbieter-ID ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
 </tbody> 
</table>

## Beispiel für Makros

In diesem Beispiel wird gezeigt, wie die Kreativ-, Adgroup- und Platzierungsmakros übergeben werden. Es wird davon ausgegangen, dass die Werte für jeden Parameter im nicht umgeleiteten Teil des Klick-Tracking-Aufrufs übergeben werden.

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
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Antwort

Basierend auf dem obigen Beispiel wird der Browser zu folgendem [!DNL URL] umgeleitet:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Zusätzliche Funktionen - [!UICONTROL Audience Optimization Reports]

Sie können Pixelaufrufe verwenden, um die [Audience Optimization-Berichte](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) zu unterstützen. Weitere Informationen zur Nutzung von Pixeln zur Leistungsoptimierung von Berichten finden Sie unter [Übersicht und Zuordnungen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).


>[!MORELIKETHIS]
>
>* [Daten- und Metadatendateien für Audience Optimization-Berichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

