---
description: Mit ausführbaren Protokolldateien können Sie Mediensignale aus Protokolldateien des Anzeigenservers erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
keywords: actionable logs, alf, ALF
seo-description: Mit ausführbaren Protokolldateien können Sie Mediensignale aus Protokolldateien des Anzeigenservers erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actionable Log Files
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: fcdfe3a81cddc3c899453234d349f7a458c2be61

---


# Actionable Log Files {#actionable-log-files}

[!UICONTROL Actionable Log Files] ermöglichen Ihnen, Mediendaten aus Protokolldateien des Anzeigenservers zu erfassen und mithilfe der Daten Eigenschaften in Audience Manager zu erstellen. Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Codeelemente und Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

## Zielsetzung {#purpose}

[!UICONTROL Actionable Log Files] optimieren Sie die Erfassung von Impressionen, Klicks und Konversionen von Anzeigen-Servern. Verwenden Sie diese Informationen zur Benutzersegmentierung, ohne dass Sie zum Senden von Kampagnenattributen an [!DNL Audience Manager]manuell Pixelmedien benötigen müssen.

## Erste Schritte {#getting-started}

Um damit beginnen zu können, [!UICONTROL Actionable Log Files]müssen Sie Protokolldaten in importieren [!DNL Audience Manager]. Die folgenden Links helfen Ihnen beim Einstieg:

* Protokolle [!UICONTROL Google DCM] finden Sie unter [DCM-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) importieren *und* wenden Sie sich an Ihren [!DNL Audience Manager] Berater.
* Weitere Anzeigenserverprotokolle finden Sie unter [Daten- und Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *und* wenden Sie sich an Ihren [!DNL Audience Manager] Berater.

Wenn Sie bereits Protokolldaten importieren, bitten Sie Ihren [!DNL Audience Manager] Berater oder die [!DNL Audience Manager]Kundenunterstützung[ , diese ](https://helpx.adobe.com/contact/enterprise-support.ec.html) [!UICONTROL Actionable Log Files]für Sie zu aktivieren.

>[!IMPORTANT]
>
> Anfang 2020 [!UICONTROL Actionable Log Files] wird die Verfügbarkeit neuer Werbeserver erweitert. Bitten Sie zunächst Ihren [!DNL Audience Manager] Berater oder [Kundendienst](https://helpx.adobe.com/contact/enterprise-support.ec.html) .

## Arbeiten mit ausführbaren Protokolldateien {#working-with-actionable-log-files}

Damit [!UICONTROL Actionable Log Files]werden die Informationen aus den Anzeigenserverprotokollen auf [!DNL Audience Manager] dieselbe Weise erfasst wie Daten aus Website-Interaktionen in Echtzeit. [!DNL Audience Manager] stellt eine Verbindung zum Protokollspeicher Ihres Anzeigenservers her, analysiert die Informationen aus den Protokollen und sendet die Protokolldaten als umsetzbare Signale an unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md#dcs-pcs).

Sie müssen weiterhin regelbasierte Eigenschaften einrichten, um die umsetzbaren Signale zu erfassen. Erfahren Sie, wie Sie regelbasierte Eigenschaften entweder in der Benutzeroberfläche[ des ](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)Audience Manager oder mithilfe unserer [Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-create.md)einrichten. Blättern Sie nach unten zum Abschnitt [Akzeptable Signale](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) , um eine Liste aller Schlüssel anzuzeigen, die Sie in regelbasierten Eigenschaften verwenden können.

>[!IMPORTANT]
>
>Wir empfehlen die Implementierung [!UICONTROL Actionable Log Files] anstelle von ** Pixelaufrufen[](../../integration/media-data-integration/impression-data-pixels.md). Wir halten beide Optionen nicht für sinnvoll, da dies zu einer Erhöhung der Häufigkeitsangaben für Eigenschaften führt.

## Aktive Signale {#actionable-signals}

Signale sind die [kleinsten Dateneinheiten](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] Ermöglicht Ihnen die Erfassung von Advertiser-, Business Unit-, Kreativ- und Kampagnenwerten in Impressionsereignissen, Klickereignissen und Konversionsereignissen als Signale aus Anzeigenserverprotokollen.

Denken Sie daran, dass Sie die regelbasierten Eigenschaften selbst einrichten müssen, um diese Informationen für die Erstellung und Segmentierung von Zielgruppen zu verwenden.

### Verfolgbare Signale aus Google DCM-Protokollen {#dcm-logs-signals}

Die Tabelle enthält die aussagekräftigen Signale aus [!DNL DCM] Protokolldateien:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Header Name in Protokolldatei </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
   <th colname="col4" class="entry"> Beispielwert </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Stellt die numerische ID für die Konversionsaktivität in DCM dar. Dieses Feld ist der Aktivitäts-ID von DCM zugeordnet. </p> <p> <p>Tipp: Sie können mehrere oder spezifische Konversionsaktivitäten von DCM erfassen. Erstellen Sie Eigenschaften <code> d_conversion = activity ID</code> für jede Konversionsaktivität von DCM. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Dieses Feld ist der Konversions-ID in DCM zugeordnet. Gibt die Aktivität an, die der Benutzerkonversion von DCM vorausgeht. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> für Konvertierungen nach dem Klicken. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> für Konvertierungen nach Impressionen. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> für nicht übereinstimmende Konvertierungen. Die Konvertierung kann nicht mit einer vorherigen Aktivität abgeglichen werden. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Ein UTC-Datum und eine Uhrzeit für Impression, Klick oder Konversionsereignis. In Mikrosekunden seit 1970-01-01 00:00:00 UTC vertreten.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen in Zusammenhang steht.</p> <p>Dieses Feld ist der Advertiser-Gruppen-ID von DCM zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Geschäftseinheit-ID. Dieses Feld ist der Advertiser-ID von DCM zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Die von DCM bereitgestellte Kampagnen-ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Die von DCM bereitgestellte Creative-ID. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Der Verkaufsbetrag in USD, bis zu einer Stärke von -6. Multipliziert mit 1.000.000, um als Dollarbetrag zu sehen.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem DCM-Protokolldateinamen und wandelt ihn in ein umsetzbares Signal um. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> für Impressionen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> für Klicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> für Konvertierungen. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Die ID der Datenquelle, mit der Sie DCM-Daten erfassen. Siehe Erstellen <a href="../../features/manage-datasources.md#create-data-source"> einer Datenquelle</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden [!DNL Audience Manager] wie ein Echtzeitaufruf `HTTP` erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversionsereignis von [!DNL DCM]. Aufrufe müssen nicht unbedingt *alle* Signale in den Beispielaufruf einschließen.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Bei einer [!DNL DCM] Protokolldatei von durchschnittlich 2 Millionen Zeilen werden alle Eigenschaften, die aus umsetzbaren Signalen erstellt werden, innerhalb von etwa einer Stunde nach der Verarbeitung der Protokolle realisiert.

>[!NOTE] {important=&quot;high&quot;}
>
>Der in den [!DNL DCM] Protokollen angegebene Ereigniszeitstempel wird berücksichtigt und an den übergeben [!UICONTROL Data Collection Servers].
>
>* Wenn für eine Datenzeile in der [!DNL DCM] Protokolldatei kein Zeitstempel verfügbar ist, wird die Uhrzeit des `HTTP` Aufrufs als Zeitstempel für das Ereignis verwendet.
>* Wenn die Datenzeile in der [!DNL DCM] Protokolldatei einen fehlerhaften Zeitstempel enthält, wird die gesamte Zeile ignoriert.


<br> 

### Umsetzbare Signale aus generischen Anzeigenserverprotokollen {#generic-logs-signals}

Zunächst müssen Sie Ihre Anzeigenserverprotokolle in unseren Amazon S3-Behältern hinterlegen. Lesen Sie dazu die [Datendateien für Zielgruppenoptimierungsberichte und die ausführbaren Protokolldateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *und* wenden Sie sich an Ihren [!DNL Audience Manager] Berater. Die Tabelle enthält die aussagekräftigen Signale aus generischen Protokolldateien:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Header Name in Protokolldatei </th> 
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
   <td colname="col3"> <p> Ein UTC-Datum und eine Uhrzeit für Impression, Klick oder Konversionsereignis. Verwenden Sie das <code>yyyy-MM-dd HH:mm:ss</code> Format. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dieses Feld nicht mit <a href="../../features/datasources-list-and-settings.md">Audience Manager-Datenquellen in Zusammenhang steht.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Geschäftseinheit-ID.  </p> </td> 
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
   <td colname="col3"> Kauf- oder sonstiger Umrechnungsbetrag. Datentyp: Float. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen und wandelt ihn in ein umsetzbares Signal um. Siehe Benennungsregeln für <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">Protokolldateien</a>. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> für Impressionen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> für Klicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> für Konvertierungen. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Die ID der Datenquelle, mit der Sie Protokolldaten erfassen. Siehe Erstellen <a href="../../features/manage-datasources.md#create-data-source"> einer Datenquelle</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden [!DNL Audience Manager] wie ein Echtzeitaufruf `HTTP` erfasst. Aufrufe müssen nicht unbedingt *alle* Signale in den Beispielaufruf einschließen.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Arbeiten mit ausführbaren Signalen in der Benutzeroberfläche von Audience Manager {#actionable-signals-in-ui}

Sie können Ihre eingehenden umsetzbaren Signale in der [Signalsuche](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) anzeigen.

Wechseln Sie zu **Zielgruppendaten** (1) > **Signale** (2) > **Suche** (3) und wählen Sie den Filter **Aktive Protokolldateien** (4).

![Umsetzbare Signale in der Benutzeroberfläche](/help/using/integration/assets/alf-in-signals.png)

Um regelbasierte Eigenschaften mit den umsetzbaren Signalen zu erstellen, wählen Sie &quot; **Umsetzbare Protokolldateien** &quot;(1), wählen Sie die umsetzbaren Signale aus, die Sie als Eigenschaftsregeln verwenden möchten (2) und drücken Sie die **Taste &quot;Eigenschaften aus ausgewählten Signalen** erstellen&quot;(3).

![Eigenschaften aus Signalen erstellen](/help/using/integration/assets/alf-create-trait.png)


## Nutzungsszenarios {#use-cases}

Ein Vorteil der Implementierung [!UICONTROL Actionable Log Files] ist die Möglichkeit, [Neuigkeits- und Häufigkeitskontrollen](../../features/segments/recency-and-frequency.md) auf alle [regelbasierten Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) anzuwenden, die brauchbare Signale enthalten. Auf diese Weise können Sie z. B. die Häufigkeit begrenzen, mit der einem Benutzer innerhalb einer Medienkampagne ein bestimmtes kreatives Element angezeigt wird. Lesen Sie [Sofortige geräteübergreifende Unterdrückung](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) , um zu erfahren, wie Sie dies tun. Weitere Anwendungsfälle sind:

### Retargeting-Benutzer

Retarget-Benutzer, die kreative Elemente des Typs 123 gesehen haben, aber nicht auf &quot;Kreativ&quot;geklickt oder konvertiert haben, und ihnen kreative Elemente des Typs 456 zeigen. Führen Sie folgende Schritte aus:

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die das kreative Element gesehen haben. Nehmen wir an, Sie benennen die Eigenschaft [!DNL Creative Trait 123]. Verwenden Sie die Eigenschaftsregel:

   `d_creative == 123 AND d_event == imp`

2. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die klicken oder konvertieren. Nehmen wir an, Sie nennen das hier [!DNL Click and Converter]. Verwenden Sie die Eigenschaftsregel:

   `d_event == click OR d_event=conv`

3. Erstellen Sie ein Segment, das mit Benutzern gefüllt wird, die kreative Elemente 123 gesehen haben, aber nicht klicken oder konvertieren. Benennen Sie ihn [!DNL Retarget Users] und verwenden Sie die Segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Ordnen Sie das Segment einem Ziel [!DNL Retarget Users] zu und richten Sie Benutzer im Ziel mit kreativem 456-Element ein.

### Verwenden Sie die DCM Floodlight-Aktivität in den Zielgruppenoptimierungsberichten oder im Audience Lab

[Floodlight-Tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) ermöglichen es Advertisers, Benutzerkonversionen zu verfolgen. Mit [!UICONTROL Actionable Log Files]dieser Funktion können Sie die [!DNL DCM] Konversionen in den [Zielgruppenoptimierungsberichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) oder im [Audience Lab](../../features/audience-lab/audience-lab.md)verfolgen:

1. Erstellen Sie eine Eigenschaft und verwenden Sie die folgende Eigenschaftsregel, um eine Konvertierung aus den Anzeigenserverprotokollen zu erfassen:

   `d_event == conv AND d_conversion == 123`

   Wählen Sie beim Erstellen der Eigenschaft im Audience Manager [!UICONTROL UI]die Option [!UICONTROL Conversion] als [!UICONTROL Event Type].

2. Nachdem Sie die Eigenschaft erstellt haben, beginnt die Konvertierung in der [!UICONTROL Audience Optimization Reports] und in zu melden [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [DCM-Datendateien in Audience Manager importieren](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

