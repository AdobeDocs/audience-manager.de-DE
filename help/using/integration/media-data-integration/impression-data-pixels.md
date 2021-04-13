---
description: Eine Methode zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Attribute der Kampagne an Audience Manager zu senden.
seo-description: Eine Methode zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Attribute der Kampagne an Audience Manager zu senden.
seo-title: Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe
solution: Audience Manager
title: Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign-Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 20%

---

# Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe{#capturing-campaign-impression-data-via-pixel-calls}

Eine Methode zum Senden von Mediendaten an Audience Manager verwendet Anzeigenservermakros, um Attribute der Kampagne an Audience Manager zu senden.

Diese Methode wird oft als &quot;Verpixeln des kreativen Elements&quot;bezeichnet. Diese Datenpunkte werden von den Drittanbieter-Anzeigenservermakros dynamisch in den [!DNL Audience Manager]-Pixelcode eingefügt, die dazu verwendet werden, alle Impressionen und Klicks basierend auf den Hauptattributen der Berichte der Kampagne zuzuordnen und zu melden. Die aggregierten Daten bieten eine einheitliche Ansicht der Performance von Kampagnen, helfen bei der Identifizierung benutzerspezifischer Konversionspfade und helfen Kunden, die Sequenz von Anzeigen-Server-Ereignissen zu verbessern, die zu Konversionen führen.

## Ereignis-Aufrufsyntax

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) kennzeichnen Codeelemente und -optionen. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

Der Ereignisaufruf erfasst Impressions- und Konversionsdaten und sendet diese an die [!DNL Audience Manager] [Datenerfassungs-Server](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Dieser Prozess beruht auf Werbe-Servern von Drittanbietern, wo der Aufruf in ein Creative platziert wird und somit bestimmt wird, welche Inhalte in den Code eingefügt werden. Die Werbeserver von Drittanbietern (z. B. [!DNL DFA]) können diesen Code in jeder Ad-Impression platzieren. Darüber hinaus verwendet ein Anzeigenaufruf kein [!DNL JavaScript] oder Frame-Busting-Techniken, um auf Publisher-Daten außerhalb des Anzeigen-Tags zuzugreifen.

Ereignis-Aufrufe bestehen aus Schlüssel-Wert-Paaren, die die folgende Syntax verwenden:

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Im Schlüssel-Wert-Paar ist die Wertvariable eine ID oder ein Makro, die bzw. das vom Anzeigenserver eingefügt wird. Beim Laden des Ad-Tags wird `%macro%` durch die erforderlichen entsprechenden Werte ersetzt. Dieser Aufruf gibt keine Antwort zurück.

## Unterstützte Schlüssel-Wert-Paare {#supported-key-value-pairs}

Impression Ereignis-Aufrufe akzeptieren Daten, die zu Schlüssel/Wert-Paaren gebildet werden. In der folgenden Tabelle sind die Listen und die Tasten beschrieben, mit denen diese Variablen gespeichert werden. Viele davon sind erforderlich, wenn Sie Daten in den [Audience Optimizationen-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) erfassen und analysieren möchten.

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
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihren Advertiser. </p> <p>Erforderlich für <span class="wintitle">-Berichte der Audience Optimization </span>. </p> <p>Optional.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode für Ihre Geschäftseinheit. </p> <p>Erforderlich für <span class="wintitle">-Berichte der Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-Busting-Wert. <span class="keyword"> Audience Manager sendet  </span> automatisch Cachesteuerungs-Kopfzeilen, die von den meisten Browsern und Proxys berücksichtigt werden. Wenn Sie zusätzliche Cache-Busting durchführen möchten, fügen Sie diesen Parameter in einen Ereignis-Aufruf ein, gefolgt von einer zufälligen Zeichenfolge. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numerische Kampagnen-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle">-Berichte der Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In diesem Zusammenhang instanziiert <code> d_cid </code> ein Schlüssel-Wert-Paar, mit dem Sie einen Mobilgerätetyp einer eindeutigen Benutzer-ID (DPUUID) zuordnen können. Eine feste ID bestimmt den Mobilgerätetyp. Der Wert, bei dem es sich um die Benutzer-ID handelt, kann variieren. Trennen Sie das Schlüssel-Wert-Paar durch <code> %01 </code>, das ein nicht druckbares Steuerzeichen ist. Dieser Parameter akzeptiert die folgenden Schlüssel: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">2014: Identifiziert ein Android-(GAID-)Gerät. <code> d_cid = 20914 %01 1234 </code> gibt beispielsweise an, dass Benutzer 1234 mit einem Android-Gerät verknüpft ist. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">2015: Identifiziert ein iOS-Gerät (IDFA). <code> d_cid = 20915 %01 5678 </code> gibt beispielsweise an, dass Benutzer 5678 mit einem iOS-Gerät verknüpft ist. </li> 
    </ul> <p>Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numerische kreative ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle">-Berichte der Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifiziert einen Ereignis-Aufruf als Impression-Ereignis. </p> <p>Erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Numerische Platzierungs-ID vom Anzeigen-Server. </p> <p> Optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Numerische Site-ID vom Anzeigen-Server. </p> <p>Erforderlich für <span class="wintitle">-Berichte der Audience Optimization </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Datenquellen-ID oder Integrationscode der Plattform, die die Metadaten bereitstellt (z. B. DFA, Atlas, GBM, Medienmathematik usw.). </p> <p>Erforderlich für <span class="wintitle">-Berichte der Audience Optimization </span>. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p> <p><code>gdpr</code> kann 0 (GDPR gilt nicht) oder 1 (GDPR gilt) betragen.</p> <p>Der Standardwert ist 0.</p><p>Optional.</p><p>Wenn <code>gdpr=1</code>, dann sollte der Parameter <code>gdpr_consent</code> den IAB TC-Zustimmungsparameter enthalten, um die Daten erfolgreich zu verarbeiten. Andernfalls werden alle Daten gelöscht.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Im Zusammenhang mit <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">dem Audience Manager-Plug-in für IAB TCF.</a></p><p> Wenn <code>gdpr=1</code>, wird <code>${gdpr_consent_XXXX}</code> durch die <code>gdpr_consent</code>-Zeichenfolge und die Anbieter-ID ersetzt (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB-Spezifikation</a>).</p> <p>Der Standardwert ist 0.</p><p>Optional.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Wenden Sie sich an Ihren Adobe Audience Manager Consulting oder Kundenbetreuer, um die exakte URL für die Kundendomäne zu erhalten.

## Zusätzliche Funktionen - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Sie können Pixelaufrufe verwenden, um die [Audience Optimization-Berichte](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) zu aktivieren. Siehe [Übersicht und Zuordnungen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md), wenn Sie Pixel verwenden möchten, um die Berichte zu aktivieren.

>[!MORELIKETHIS]
>
>* [Daten- und Metadatendateien für Audience Optimizationen-Berichte](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

