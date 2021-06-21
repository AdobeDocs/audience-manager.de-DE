---
description: Mit ausführbaren Protokolldateien können Sie Mediensignale aus Protokolldateien des Anzeigenservers erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfassen von Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
keywords: verwertbare Protokolle, alf, ALF
seo-description: Mit ausführbaren Protokolldateien können Sie Mediensignale aus Protokolldateien des Anzeigenservers erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfassen von Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
seo-title: Ausführbare Protokolldateien
solution: Audience Manager
title: Ausführbare Protokolldateien
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Protokolldateien
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 7c46a246233c3519049197bac824f0ee0db29754
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 3%

---

# Ausführbare Protokolldateien {#actionable-log-files}

[!UICONTROL Actionable Log Files] ermöglichen es Ihnen, Mediendaten aus Anzeigenserver-Protokolldateien zu erfassen und die Daten zum Erstellen von Eigenschaften in Audience Manager zu verwenden. Erfassen Sie Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne [Pixel](../../integration/media-data-integration/impression-data-pixels.md) anhängen zu müssen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Code-Elemente und -Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

## Zielsetzung {#purpose}

[!UICONTROL Actionable Log Files] Optimierung der Erfassung von Impressionen, Klicks und Konversionen von Anzeigen-Servern. Verwenden Sie diese Informationen für die Benutzersegmentierung, ohne die Pixelmedien manuell an [!DNL Audience Manager] senden zu müssen.

## Erste Schritte {#getting-started}

Um mit [!UICONTROL Actionable Log Files] zu beginnen, müssen Sie Protokolldaten in [!DNL Audience Manager] importieren. Die folgenden Links helfen Ihnen bei den ersten Schritten:

* Informationen zu [!UICONTROL Google Campaign Manager]-Protokollen finden Sie unter [Importieren von Google Campaign Manager-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *und* wenden Sie sich an Ihren [!DNL Audience Manager]-Berater.
* Informationen zu [!UICONTROL Google Ad Manager] (ehemals Google DFP)-Protokollen finden Sie unter [Importieren von Google Ad Manager-Datendateien in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *und* kontaktieren Sie Ihren [!DNL Audience Manager]-Berater.
* Weitere Adserver-Protokolle finden Sie unter [Daten- und Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *und* Wenden Sie sich an Ihren [!DNL Audience Manager] -Berater.

Wenn Sie bereits Protokolldaten in [!DNL Audience Manager] importieren, bitten Sie Ihren [!DNL Audience Manager] -Berater oder [Kundenunterstützung](https://helpx.adobe.com/de/contact/enterprise-support.ec.html), [!UICONTROL Actionable Log Files] für Sie zu aktivieren.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Arbeiten mit ausführbaren Protokolldateien {#working-with-actionable-log-files}

Mit [!UICONTROL Actionable Log Files] werden die Informationen aus den Adserver-Protokollen in [!DNL Audience Manager] auf dieselbe Weise erfasst wie Daten aus Echtzeit-Website-Interaktionen. [!DNL Audience Manager] stellt eine Verbindung zu Ihrem Protokollspeicher des Adservers her, analysiert die Informationen aus den Protokollen und sendet die Protokolldaten als umsetzbare Signale an unsere  [Datenerfassungsserver](../../reference/system-components/components-data-collection.md#dcs-pcs).

Sie müssen weiterhin regelbasierte Eigenschaften einrichten, um die umsetzbaren Signale zu erfassen. Erfahren Sie, wie Sie regelbasierte Eigenschaften entweder in der [Audience Manager-Benutzeroberfläche](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oder mithilfe unserer [Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-create.md) einrichten. Scrollen Sie nach unten zum Abschnitt [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) , um eine Liste aller Schlüssel zu erhalten, die Sie in regelbasierten Eigenschaften verwenden können.

>[!IMPORTANT]
>
>Es wird empfohlen, [!UICONTROL Actionable Log Files] *anstelle von* [Pixelaufrufe](../../integration/media-data-integration/impression-data-pixels.md) zu implementieren. Wir halten die Verwendung beider Optionen ab, da dies zu einer Erhöhung der Häufigkeitszahlen für Eigenschaften führt.

## Umsetzbare Signale {#actionable-signals}

Signale sind die [kleinsten Dateneinheiten](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] ermöglichen es Ihnen, Advertiser-, Business Unit-, Kreativ- und Kampagnenwerte in Impressionsereignissen, Klickereignissen und Konversionsereignissen als Signale aus Anzeigenserverprotokollen zu erfassen.

Denken Sie daran, dass Sie zur Verwendung dieser Informationen für die Erstellung und Segmentierung von Zielgruppen die regelbasierten Eigenschaften selbst einrichten müssen.

### Ausführbare Signale von Google Campaign Manager protokollieren {#dcm-logs-signals}

In der Tabelle sind die aussagekräftigen Signale aus den Protokolldateien [!DNL Google Campaign Manager] aufgeführt:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Headername in Protokolldatei </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
   <th colname="col4" class="entry"> Beispielwert </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Stellt die numerische ID für die Konversionsaktivität in Google Campaign Manager dar. Dieses Feld wird der Aktivitäts-ID von Google Campaign Manager zugeordnet. </p> <p> <p>Tipp: Sie können mehrere oder spezifische Konversionsaktivitäten über Google Campaign Manager erfassen. Erstellen Sie Eigenschaften mit <code> d_conversion = activity ID</code> für jede Konversionsaktivität aus dem Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Dieses Feld wird der Konversions-ID in Google Campaign Manager zugeordnet. Gibt die Aktivität an, die der Benutzerkonversion von Google Campaign Manager vorausgeht. </p> <p>Zulässige Werte sind: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> für Konversionen nach dem Klicken. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> für Post-Impression-Konversionen. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> für nicht übereinstimmende Konversionen. Die Konversion kann nicht mit einer vorherigen Aktivität abgeglichen werden. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversionsereignis. Repräsentiert in Mikrosekunden seit 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen in Zusammenhang steht.</p> <p>Dieses Feld wird der Advertiser-Gruppen-ID von Google Campaign Manager zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Kennung der Geschäftseinheit. Dieses Feld wird der Advertiser-ID von Google Campaign Manager zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Die vom Google Campaign Manager bereitgestellte Kampagnen-ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Die vom Google Campaign Manager bereitgestellte Creative ID. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Der Verkaufsbetrag in USD, in Höhe von -6. Multiplizieren Sie mit 1.000.000, um als Dollarbetrag zu sehen.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen von Google Campaign Manager und wandelt ihn in ein umsetzbares Signal um. </p> <p>Zulässige Werte sind: </p> <p> 
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
   <td colname="col3"> <p>Die ID der Datenquelle, die Sie zum Erfassen von Google Campaign Manager-Daten verwenden. Siehe <a href="../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden in [!DNL Audience Manager] wie ein Echtzeit-Aufruf von `HTTP` erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversionsereignis von [!DNL Google Campaign Manager]. Aufrufe müssen nicht unbedingt *alle* die Signale im Beispielaufruf enthalten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Für eine im Durchschnitt 2 Millionen Zeilen große Protokolldatei [!DNL Google Campaign Manager] werden alle Eigenschaften, die aus umsetzbaren Signalen erstellt werden, innerhalb von etwa einer Stunde nach der Verarbeitung der Protokolle realisiert.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>Der in den [!DNL Google Campaign Manager]-Protokollen angegebene Ereigniszeitstempel wird berücksichtigt und an [!UICONTROL Data Collection Servers] weitergegeben.
>
>* Wenn für eine Datenzeile in der Protokolldatei [!DNL Google Campaign Manager] kein Zeitstempel verfügbar ist, verwenden wir die Zeit des `HTTP`-Aufrufs als Zeitstempel des Ereignisses.
>* Wenn die Datenzeile in der Protokolldatei [!DNL Google Campaign Manager] einen falsch formatierten Zeitstempel enthält, wird die gesamte Zeile ignoriert.


<br>

### Ausführbare Signale von [!DNL Google Ad Manager] logs {#ad-manager-logs-signals}

In der Tabelle sind die aussagekräftigen Signale aus den Protokolldateien [!DNL Google Ad Manager] aufgeführt:


| Headername in Protokolldatei | Signal | Beschreibung |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | Numerische ID für das bereitgestellte Ad Manager-Zeilenelement |
| `OrderId` | `d_orderid` | Die numerische ID für die Anzeigenmanagerreihenfolge, die das bereitgestellte Zeilenelement und das Kreativelement enthielt. |
| `CreativeId` | `d_creative` | Die numerische ID für die bereitgestellten Ad Manager-Kreativelemente. |
| `-` | `d_event` | Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Namen der Ad Manager-Protokolldatei und wandelt ihn in ein umsetzbares Signal um. Zulässige Werte sind: <br> <ul><li>d_event = imp für Impressionen.</li><li>d_event = Klick für Klicks.</li><li>d_event = conv für Konversionen und Aktivitäten.</li></ul> |
| `-` | `d_src` | Die ID der Datenquelle, die Sie zum Erfassen von Ad Manager-Daten verwenden. Siehe [Erstellen einer Datenquelle](/help/using/features/manage-datasources.md). |

Die in der Tabelle beschriebenen Signale werden in Audience Manager wie ein Echtzeit-HTTP-Aufruf erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversionsereignis von Google Ad Manager. Aufrufe müssen nicht unbedingt alle Signale in den Beispielaufruf einschließen.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>Der in den [!DNL Google Ad Manager]-Protokollen angegebene Ereigniszeitstempel wird berücksichtigt und an [!UICONTROL Data Collection Servers] weitergegeben.
>
>* Wenn für eine Datenzeile in der Protokolldatei [!DNL Google Ad Manager] kein Zeitstempel verfügbar ist, verwenden wir die Zeit des `HTTP`-Aufrufs als Zeitstempel des Ereignisses.
>* Wenn die Datenzeile in der Protokolldatei [!DNL Google Ad Manager] einen falsch formatierten Zeitstempel enthält, wird die gesamte Zeile ignoriert.


<br> 

### Ausführbare Signale von generischen Anzeigenserverprotokollen {#generic-logs-signals}

Zunächst müssen Sie Ihre Adserver-Protokolle in unseren Amazon S3-Buckets hinterlegen. Lesen Sie dazu [Datendateien für Audience Optimization-Berichte und ausführbare Protokolldateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *und* wenden Sie sich an Ihren [!DNL Audience Manager] -Berater. In der Tabelle sind die aussagekräftigen Signale aus allgemeinen Protokolldateien aufgeführt:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Headername in Protokolldatei </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
   <th colname="col4" class="entry"> Beispielwert </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Gibt an, ob eine Konvertierung übereinstimmt oder nicht. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impression </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Klicken </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Nicht zugeordnet oder unbekannt </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversionsereignis. Verwenden Sie das Format <code>yyyy-MM-dd HH:mm:ss</code> . </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dieses Feld nicht mit <a href="../../features/datasources-list-and-settings.md">Audience Manager-Datenquellen verknüpft ist.</a></p></td> 
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
   <td colname="col3"> <p>Die Creative ID aus der Protokolldatei. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Kauf- oder anderer Konversionsbetrag. Datentyp: Float. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen und wandelt ihn in ein umsetzbares Signal um. Siehe <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">Namenskonventionen für Protokolldateien</a>. </p> <p>Zulässige Werte sind: </p> <p> 
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
   <td colname="col3"> <p>Die ID der Datenquelle, die Sie zum Erfassen von Protokolldaten verwenden. Siehe <a href="../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden in [!DNL Audience Manager] wie ein Echtzeit-Aufruf von `HTTP` erfasst. Aufrufe müssen nicht unbedingt *alle* die Signale im Beispielaufruf enthalten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Arbeiten mit ausführbaren Signalen in der Audience Manager-Benutzeroberfläche {#actionable-signals-in-ui}

Sie können Ihre eingehenden verwertbaren Signale in der [Signalsuche](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) -Schnittstelle anzeigen.

Gehen Sie zu **Zielgruppendaten** (1) > **Signale** (2) > **Suche** (3) und wählen Sie den Filter **Ausführbare Protokolldateien** (4) aus.

![Umsetzbare Signale in der Benutzeroberfläche](/help/using/integration/assets/alf-in-signals.png)

Um regelbasierte Eigenschaften mithilfe Ihrer umsetzbaren Signale zu erstellen, wählen Sie **Ausführbare Protokolldateien** (1), wählen Sie die umsetzbaren Signale aus, die Sie als Eigenschaftsregeln verwenden möchten (2), und drücken Sie die Taste **Eigenschaft aus ausgewählten Signalen erstellen** (3).

![Erstellen von Eigenschaften aus Signalen](/help/using/integration/assets/alf-create-trait.png)


## Nutzungsszenarios {#use-cases}

Ein Vorteil der Implementierung von [!UICONTROL Actionable Log Files] besteht darin, [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md)-Steuerelemente auf alle [regelbasierten Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) anzuwenden, die umsetzbare Signale enthalten. Auf diese Weise können Sie beispielsweise die Häufigkeit begrenzen, mit der ein Benutzer innerhalb einer Medienkampagne einen bestimmten kreativen Inhalt anzeigt. Lesen Sie [Sofortige geräteübergreifende Unterdrückung](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) , um zu erfahren, wie Sie dies durchführen. Weitere Anwendungsfälle sind:

### Retargeting-Benutzer

Retargeting von Benutzern, die Creative 123 gesehen haben, aber nicht geklickt oder konvertiert haben und ihnen kreative Inhalte zeigen 456. Gehen Sie folgendermaßen vor:

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die das Kreativ gesehen haben. Angenommen, Sie benennen die Eigenschaft [!DNL Creative Trait 123]. Verwenden Sie die Eigenschaftsregel:

   `d_creative == 123 AND d_event == imp`

2. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die klicken oder konvertieren. Nehmen wir an, Sie nennen diesen [!DNL Click and Converter]. Verwenden Sie die Eigenschaftsregel:

   `d_event == click OR d_event=conv`

3. Erstellen Sie ein Segment, das mit Benutzern gefüllt wird, die kreative Inhalte 123 gesehen, aber nicht geklickt oder konvertiert haben. Benennen Sie ihn [!DNL Retarget Users] und verwenden Sie die Segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Ordnen Sie das Segment [!DNL Retarget Users] einem Ziel zu und wählen Sie Benutzer im Ziel mit kreativem Code 456 als Ziel aus.

### Verwenden der Floodlight-Aktivität von Google Campaign Manager in den Audience Optimization-Berichten oder in Audience Lab

[Floodlight ](https://support.google.com/dcm/partner/answer/4293719?hl=en) tagsenfähige Advertiser zur Verfolgung von Benutzerkonversionen. Mit [!UICONTROL Actionable Log Files] können Sie die [!DNL Google Campaign Manager] Konversionen in den [Audience Optimization-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) oder in [Audience Lab](../../features/audience-lab/audience-lab.md) verfolgen:

1. Erstellen Sie eine Eigenschaft und verwenden Sie die folgende Eigenschaftsregel, um eine Konversion aus den Adserver-Protokollen zu erfassen:

   `d_event == conv AND d_conversion == 123`

   Wählen Sie beim Erstellen der Eigenschaft im Audience Manager [!UICONTROL UI] [!UICONTROL Conversion] als [!UICONTROL Event Type] aus.

2. Nachdem Sie die Eigenschaft erstellt haben, beginnt die Konvertierung mit der Berichterstellung für die Werte [!UICONTROL Audience Optimization Reports] und [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importieren von Google Kampagne Manager-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
* [Berichte zur Zielgruppenoptimierung](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

