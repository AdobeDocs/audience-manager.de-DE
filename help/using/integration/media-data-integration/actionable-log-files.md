---
description: Mit verwertbaren Protokolldateien können Sie Mediensignale aus Werbeserver-Protokolldateien erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfasst Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
keywords: Ausführbare Protokolle, ALF, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actionable Log Files
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---

# Actionable Log Files {#actionable-log-files}

[!UICONTROL Actionable Log Files] ermöglichen es Ihnen, Mediendaten aus den Protokolldateien des Anzeigenservers zu erfassen und die Daten zu verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfasst Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne [&#x200B; (Pixel](../../integration/media-data-integration/impression-data-pixels.md) anhängen zu müssen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument weisen auf Codeelemente und Optionen hin. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

## Zielsetzung {#purpose}

[!UICONTROL Actionable Log Files] optimieren die Art und Weise, wie Sie Impressionen, Klicks und Konversionen von Werbe-Servern erfassen. Verwenden Sie diese Informationen für die Benutzersegmentierung, ohne dass Medien manuell in Pixel umgewandelt werden müssen, um Kampagnenattribute an [!DNL Audience Manager] zu senden.

## Erste Schritte {#getting-started}

Um mit [!UICONTROL Actionable Log Files] zu beginnen, müssen Sie Protokolldaten in [!DNL Audience Manager] importieren. Die folgenden Links helfen Ihnen bei den ersten Schritten:

* [!UICONTROL Google Campaign Manager] finden Sie unter [Importieren von Google Campaign Manager-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *und* Sie Ihren [!DNL Audience Manager].
* [!UICONTROL Google Ad Manager] Protokolle (ehemals Google DFP) finden Sie unter [Importieren von Google Ad Manager-Datendateien in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *.* Sie Ihren [!DNL Audience Manager].
* Weitere Anzeigen-Server-Protokolle finden Sie unter [Daten- und Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *und* Wenden Sie sich an Ihren [!DNL Audience Manager].

Wenn Sie bereits Protokolldaten in [!DNL Audience Manager] importieren, bitten Sie Ihren [!DNL Audience Manager] oder die [Kundenunterstützung](https://helpx.adobe.com/de/contact/enterprise-support.ec.html), [!UICONTROL Actionable Log Files] für Sie zu aktivieren.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Arbeiten mit verwertbaren Protokolldateien {#working-with-actionable-log-files}

Mit [!UICONTROL Actionable Log Files] werden die Informationen aus den Anzeigen-Server-Protokollen auf [!DNL Audience Manager] gleiche Weise erfasst wie Daten aus Echtzeit-Website-Interaktionen. [!DNL Audience Manager] stellt eine Verbindung zu Ihrem Ad-Server-Protokollspeicher her, analysiert die Informationen aus den Protokollen und sendet die Protokolldaten als verwertbare Signale an [Datenerfassungs-Server](../../reference/system-components/components-data-collection.md#dcs-pcs).

Sie müssen weiterhin regelbasierte Eigenschaften einrichten, um die verwertbaren Signale zu erfassen. Erfahren Sie, wie Sie regelbasierte Eigenschaften entweder in der Benutzeroberfläche von [Audience Manager &#x200B;](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oder mit unseren [Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-create.md) einrichten. Scrollen Sie nach unten zum Abschnitt [Verwertbare Signale](../../integration/media-data-integration/actionable-log-files.md#actionable-signals), um eine Liste aller Schlüssel zu erhalten, die Sie in regelbasierten Eigenschaften verwenden können.

>[!IMPORTANT]
>
>Es wird empfohlen, [!UICONTROL Actionable Log Files] *anstelle von*[&#x200B; Pixel-Aufrufen](../../integration/media-data-integration/impression-data-pixels.md) zu implementieren. Wir raten von der Verwendung beider Optionen ab, da dies zu einem Anstieg der Häufigkeitszahlen für Eigenschaften führt.

## Einschaltsignale {#actionable-signals}

Signale sind die [kleinsten Dateneinheiten](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] können Sie Werte für Advertiser, Geschäftseinheit, Kreative und Kampagnen in Impressionsereignissen, Klickereignissen und Konversionsereignissen als Signale aus Werbe-Server-Protokollen erfassen.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] werden für die folgenden Werbeserver unterstützt:
> <br>
>
> * [Google Campaign Manager](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalking und Sizmek](#generic-logs-signals)

Denken Sie daran: Um diese Informationen für die Erstellung und Segmentierung von Audiences verwenden zu können, müssen Sie die regelbasierten Eigenschaften selbst einrichten.

### Verwertbare Signale aus Google Campaign Manager-Protokollen {#dcm-logs-signals}

In der folgenden Tabelle sind die verwertbaren Signale aus [!DNL Google Campaign Manager] Protokolldateien aufgeführt:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Header-Name in Protokolldatei </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
   <th colname="col4" class="entry"> Beispielwert </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Stellt die numerische ID für die Konversionsaktivität in Google Campaign Manager dar. Dieses Feld ist der Aktivitäts-ID von Google Campaign Manager zugeordnet. </p> <p> <p>Tipp: Sie können mehrere oder bestimmte Konversionsaktivitäten in Google Campaign Manager erfassen. Erstellen Sie Eigenschaften mithilfe von <code> d_conversion = activity ID</code> für jede Konversionsaktivität in Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Dieses Feld ist der Konversions-ID in Google Campaign Manager zugeordnet. Gibt die Aktivität an, die der Benutzerkonversion aus Google Campaign Manager vorausgeht. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> für Konvertierungen nach dem Klicken. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> für Post-Impression-Konvertierungen. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> für nicht übereinstimmende Konversionen. Die Konversion kann nicht mit einer vorherigen Aktivität abgeglichen werden. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversionsereignis. Vertreten in Mikrosekunden seit 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Ein Integrations-Code für die Datenquelle Ihres Werbetreibenden. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen zusammenhängt.</p> <p>Dieses Feld ist der Advertiser-Gruppen-ID aus Google Campaign Manager zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Kennung der Geschäftseinheit. Dieses Feld ist der Advertiser-ID aus Google Campaign Manager zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Die von Google Campaign Manager bereitgestellte Kampagnen-ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Die von Google Campaign Manager bereitgestellte Creative-ID. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Der Umsatz in USD, in der Potenz von -6. Multiplizieren Sie dies mit 1.000.000, um einen Dollarbetrag anzuzeigen.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen von Google Campaign Manager und wandelt ihn in ein verwertbares Signal um. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> für Impressionen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> für Klicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> für Konversionen. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Die ID der Datenquelle, die Sie zum Erfassen von Google Campaign Manager-Daten verwenden. Siehe <a href="../../features/manage-datasources.md#create-data-source"> zum Erstellen eines Daten-Source</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden in [!DNL Audience Manager] wie ein Echtzeit-`HTTP` erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversionsereignis von [!DNL Google Campaign Manager]. Aufrufe müssen nicht unbedingt *alle)* Signale im Beispielaufruf enthalten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Bei einer durchschnittlich großen [!DNL Google Campaign Manager]-Protokolldatei von 2 Millionen Zeilen werden alle Eigenschaften, die aus verwertbaren Signalen erstellt werden, innerhalb von etwa einer Stunde nach der Verarbeitung der Protokolle realisiert.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>Der in den [!DNL Google Campaign Manager] angegebene Ereignis-Zeitstempel wird berücksichtigt und an die [!UICONTROL Data Collection Servers] übergeben.
>
>* Wenn für eine Datenzeile in der [!DNL Google Campaign Manager]-Protokolldatei kein Zeitstempel verfügbar ist, wird die Zeit des `HTTP`-Aufrufs als Ereigniszeitstempel verwendet.
>* Wenn die Datenzeile in der [!DNL Google Campaign Manager]-Protokolldatei einen falsch formatierten Zeitstempel enthält, wird die gesamte Zeile ignoriert.

<br>

### Verwertbare Signale aus [!DNL Google Ad Manager] {#ad-manager-logs-signals}

In der folgenden Tabelle sind die verwertbaren Signale aus [!DNL Google Ad Manager] Protokolldateien aufgeführt:


| Header-Name in Protokolldatei | Signal | Beschreibung |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | Die numerische ID für den Zeileneintrag „Zugestellte Werbeleiter“ |
| `OrderId` | `d_orderid` | Die numerische ID für die Ad Manager-Bestellung, die den gelieferten Zeileneintrag und die Kreativität enthielt. |
| `CreativeId` | `d_creative` | Die numerische ID für den bereitgestellten Werbemanager für Kreative. |
| `-` | `d_event` | Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Ad Manager-Protokolldateinamen und wandelt ihn in ein verwertbares Signal um. Akzeptierte Werte sind: <br> <ul><li>d_event = Imp für Impressionen.</li><li>d_event = Klick für Klicks.</li><li>d_event = Konversionen und Aktivitäten.</li></ul> |
| `-` | `d_src` | Die ID der Datenquelle, die Sie zum Erfassen von Ad Manager-Daten verwenden. Siehe [Erstellen einer Daten-Source](/help/using/features/manage-datasources.md). |

Die in der Tabelle beschriebenen Signale werden in Audience Manager wie ein Echtzeit-HTTP-Aufruf erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversionsereignis aus Google Ad Manager. Aufrufe müssen nicht unbedingt alle Signale im Beispielaufruf enthalten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>Der in den [!DNL Google Ad Manager] angegebene Ereignis-Zeitstempel wird berücksichtigt und an die [!UICONTROL Data Collection Servers] übergeben.
>
>
>* Wenn für eine Datenzeile in der [!DNL Google Ad Manager]-Protokolldatei kein Zeitstempel verfügbar ist, wird die Zeit des `HTTP`-Aufrufs als Ereigniszeitstempel verwendet.
>* Wenn die Datenzeile in der [!DNL Google Ad Manager]-Protokolldatei einen falsch formatierten Zeitstempel enthält, wird die gesamte Zeile ignoriert.

<br>

### Verwertbare Signale aus Adobe Advertising Cloud-, Flashtalking- und Sizmek-Anzeigen-Server-Protokollen {#generic-logs-signals}

Zunächst müssen Sie Ihre Anzeigen-Server-Protokolle in unseren Amazon S3-Buckets hinterlegen. Lesen Sie dazu [Datendateien für Audience Optimization-Berichte und verwertbare Protokolldateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *und* Sie Ihren [!DNL Audience Manager]. In der folgenden Tabelle sind die verwertbaren Signale aus den Protokolldateien des Anzeigen-Servers aufgeführt:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Header-Name in Protokolldatei </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
   <th colname="col4" class="entry"> Beispielwert </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Gibt an, ob eine Konversion abgeglichen wird oder nicht. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impression </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Nicht zugeordnet oder unbekannt </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversionsereignis. Verwenden Sie das <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Ein Integrations-Code für die Datenquelle Ihres Werbetreibenden. Beachten Sie, dass dieses Feld nicht mit <a href="../../features/datasources-list-and-settings.md">Audience Manager-Datenquellen verknüpft ist.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Kennung der Geschäftseinheit.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Die Kampagnen-ID aus der Protokolldatei.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Die Creative-ID aus der Protokolldatei. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Kauf- oder anderer Konversionsbetrag. Datentyp: float. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen und wandelt ihn in ein verwertbares Signal um. Siehe <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">Benennungskonventionen für Protokolldateien</a>. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> für Impressionen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> für Klicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> für Konversionen. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Die ID der Datenquelle, die Sie zum Erfassen von Protokolldaten verwenden. Siehe <a href="../../features/manage-datasources.md#create-data-source"> zum Erstellen eines Daten-Source</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden in [!DNL Audience Manager] wie ein Echtzeit-`HTTP` erfasst. Aufrufe müssen nicht unbedingt *alle)* Signale im Beispielaufruf enthalten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Arbeiten mit verwertbaren Signalen in der Benutzeroberfläche von Audience Manager {#actionable-signals-in-ui}

Sie können Ihre eingehenden aktionsfähigen Signale in der [Signalsuche](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) anzeigen.

Wechseln Sie zu **Zielgruppendaten** (1) > **Signale** (2) > **Suche** (3) und wählen Sie den Filter **Verwertbare Protokolldateien** (4) aus.

![Verwertbare Signale in der Benutzeroberfläche](/help/using/integration/assets/alf-in-signals.png)

Um regelbasierte Eigenschaften mit Ihren umsetzbaren Signalen zu erstellen, wählen Sie **umsetzbare Protokolldateien** (1), wählen Sie die umsetzbaren Signale aus, die Sie als Eigenschaftsregeln verwenden möchten (2), und drücken Sie **Eigenschaft aus ausgewählten Signalen erstellen** (3).

![Erstellen von Eigenschaften aus Signalen](/help/using/integration/assets/alf-create-trait.png)


## Nutzungsszenarios {#use-cases}

Ein Vorteil der Implementierung von [!UICONTROL Actionable Log Files] ist die Option, [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md) auf alle [regelbasierten Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) anzuwenden, die umsetzbare Signale enthalten. Auf diese Weise können Sie beispielsweise die Häufigkeit begrenzen, mit der ein Benutzer innerhalb einer Medienkampagne einem bestimmten Kreativen angezeigt wird. Lesen Sie [Sofortige geräteübergreifende Unterdrückung](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md), um zu erfahren, wie Sie dies tun können. Weitere Anwendungsfälle sind:

### Benutzer erneut ansprechen

Targeting von Benutzern, die Creative 123 gesehen, aber nicht geklickt oder konvertiert haben, und Anzeigen von Creative 456. Gehen Sie folgendermaßen vor:

1. Erstellen Sie eine Eigenschaft , um Benutzer zu erfassen, die die kreativen Inhalte gesehen haben. Sagen wir, Sie nennen das Merkmal [!DNL Creative Trait 123]. Verwenden der Eigenschaftsregel:

   `d_creative == 123 AND d_event == imp`

2. Erstellen Sie eine Eigenschaft , um Benutzer zu erfassen, die klicken oder konvertieren. Nehmen wir an, Sie nennen dieses [!DNL Click and Converter]. Verwenden der Eigenschaftsregel:

   `d_event == click OR d_event=conv`

3. Erstellen Sie ein Segment, das mit Benutzern gefüllt werden soll, die Creative 123 gesehen, aber nicht geklickt oder konvertiert haben. Benennen Sie ihn [!DNL Retarget Users] und verwenden Sie die Segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Ordnen Sie die [!DNL Retarget Users] einem Ziel zu und wählen Sie Benutzer im Ziel mit Creative 456 aus.

### Verwenden der Flutlichtaktivität von Google Campaign Manager in Audience Optimization Reports oder Audience Lab

[Flutlicht-Tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) ermöglichen es Werbetreibenden, Benutzerkonversionen zu verfolgen. Mit [!UICONTROL Actionable Log Files] können Sie die [!DNL Google Campaign Manager] Konversionen in den [Audience Optimization-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) oder im [Audience Lab](../../features/audience-lab/audience-lab.md) verfolgen:

1. Erstellen Sie eine Eigenschaft und verwenden Sie die folgende Eigenschaftsregel, um eine Konversion aus den Werbe-Server-Protokollen zu erfassen:

   `d_event == conv AND d_conversion == 123`

   Wählen Sie beim Erstellen des Merkmals in der Audience Manager-[!UICONTROL UI] [!UICONTROL Conversion] als [!UICONTROL Event Type] aus.

2. Nachdem Sie das Merkmal erstellt haben, wird die Konversion im [!UICONTROL Audience Optimization Reports] und im [!UICONTROL Audience Lab] gemeldet.

>[!MORELIKETHIS]
>
>* [Importieren von Google Kampagne Manager-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Berichte zur Zielgruppenoptimierung](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
