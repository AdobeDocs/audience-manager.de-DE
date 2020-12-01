---
description: Mit ausführbaren Protokolldateien können Sie Mediensignale aus Protokolldateien des Anzeigenservers erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
keywords: actionable logs, alf, ALF
seo-description: Mit ausführbaren Protokolldateien können Sie Mediensignale aus Protokolldateien des Anzeigenservers erfassen, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne Pixel anhängen zu müssen.
seo-title: Ausführbare Protokolldateien
solution: Audience Manager
title: Ausführbare Protokolldateien
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 3%

---


# Ausführbare Protokolldateien {#actionable-log-files}

[!UICONTROL Actionable Log Files] ermöglichen Ihnen, Mediendaten aus Protokolldateien des Anzeigenservers zu erfassen und mithilfe der Daten Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen von Anzeigen-Servern als Eigenschaften, ohne [Pixel](../../integration/media-data-integration/impression-data-pixels.md) anhängen zu müssen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Codeelemente und Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

## Zielsetzung {#purpose}

[!UICONTROL Actionable Log Files] optimieren Sie die Erfassung von Impressionen, Klicks und Konversionen von Anzeigen-Servern. Verwenden Sie diese Informationen für die Benutzersegmentierung, ohne dass Sie zum Senden von Kampagnen-Attributen an [!DNL Audience Manager] manuell Pixelmedien verwenden müssen.

## Erste Schritte {#getting-started}

Um mit [!UICONTROL Actionable Log Files] zu beginnen, müssen Sie Protokolldaten in [!DNL Audience Manager] importieren. Die folgenden Links helfen Ihnen beim Einstieg:

* Weitere Informationen zu [!UICONTROL Google Campaign Manager]-Protokollen finden Sie unter [Google Kampagne Manager-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *importieren und* wenden Sie sich an Ihren [!DNL Audience Manager]-Berater.
* Informationen zu [!UICONTROL Google Ad Manager]-Protokollen (zuvor Google DFP) finden Sie unter [Google Ad Manager-Datendateien in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *importieren und* [!DNL Audience Manager]-Berater.
* Weitere Anzeigen-Server-Protokolle finden Sie unter [Daten- und Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *und* Wenden Sie sich an Ihren [!DNL Audience Manager]-Berater.

Wenn Sie bereits Protokolldaten in [!DNL Audience Manager] importieren, wenden Sie sich an Ihren [!DNL Audience Manager]-Berater oder [Kundendienst](https://helpx.adobe.com/de/contact/enterprise-support.ec.html), um [!UICONTROL Actionable Log Files] zu aktivieren.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Arbeiten mit ausführbaren Protokolldateien {#working-with-actionable-log-files}

Mit [!UICONTROL Actionable Log Files] werden die Informationen aus den Anzeigenserverprotokollen auf die gleiche Weise wie Daten aus Website-Interaktionen in Echtzeit erfasst. [!DNL Audience Manager] [!DNL Audience Manager] stellt eine Verbindung zu Ihrer Datenspeicherung des Anzeigenserverprotokolls her, analysiert die Informationen aus den Protokollen und sendet die Protokolldaten als umsetzbare Signale an unsere  [Datenerfassungsserver](../../reference/system-components/components-data-collection.md#dcs-pcs).

Sie müssen weiterhin regelbasierte Eigenschaften einrichten, um die umsetzbaren Signale zu erfassen. Erfahren Sie, wie Sie regelbasierte Eigenschaften entweder in der [Audience Manager-Benutzeroberfläche](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oder mithilfe unserer [Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-create.md) einrichten. Führen Sie einen Bildlauf nach unten zum Abschnitt [Umsetzbare Signale](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) durch, um eine Liste aller Schlüssel zu erhalten, die Sie in regelbasierten Eigenschaften verwenden können.

>[!IMPORTANT]
>
>Es wird empfohlen, [!UICONTROL Actionable Log Files] *anstelle von* [Pixelaufrufe](../../integration/media-data-integration/impression-data-pixels.md) zu implementieren. Wir halten beide Optionen nicht für sinnvoll, da dies zu einer Erhöhung der Häufigkeitsangaben für Eigenschaften führt.

## Funktionierbare Signale {#actionable-signals}

Die Signale sind die kleinsten Dateneinheiten [unter [!DNL Audience Manager]. ](../../reference/signal-trait-segment.md) [!UICONTROL Actionable Log Files] Ermöglicht Ihnen die Erfassung von Werbe-, Business Unit-, Kreativ- und Kampagne-Werten in Impressionsservern, Klick-Ereignissen und Konversions-Ereignissen als Ereignis aus Anzeigenserverprotokollen.

Um diese Informationen für die Erstellung und Segmentierung von Audiencen zu verwenden, müssen Sie die regelbasierten Eigenschaften selbst einrichten.

### Verfolgbare Signale aus Google Kampagne Manager-Protokollen {#dcm-logs-signals}

Die Tabelle Liste die aussagekräftigen Signale aus den Protokolldateien [!DNL Google Campaign Manager]:

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
   <td colname="col3"> <p>Nur für Konversions-Ereignis verfügbar. </p> <p>Stellt die numerische ID für die Konversions-Aktivität in Google Kampagne Manager dar. Dieses Feld wird der Aktivitäten-ID von Google Kampagne Manager zugeordnet. </p> <p> <p>Tipp: Sie können mehrere oder spezifische Konvertierungs-Aktivitäten aus Google Kampagne Manager erfassen. Erstellen Sie Eigenschaften mit <code> d_conversion = activity ID</code> für jede Konvertierungs-Aktivität aus Google Kampagne Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Nur für Konversions-Ereignis verfügbar. </p> <p>Dieses Feld ist der Konversions-ID im Google Kampagne Manager zugeordnet. Gibt die Aktivität an, die der Benutzerkonversion von Google Kampagne Manager vorausgeht. </p> <p>Akzeptierte Werte sind: </p> <p> 
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
   <td colname="col3">Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversions-Ereignis. In Mikrosekunden seit 1970-01-01 00:00:00 UTC vertreten.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dies nicht mit den Datenquellen des Audience Managers in Zusammenhang steht.</p> <p>Dieses Feld wird der Advertiser-Gruppen-ID aus Google Kampagne Manager zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Geschäftseinheit-ID. Dieses Feld wird der Advertiser-ID von Google Kampagne Manager zugeordnet. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Die vom Google Kampagne Manager bereitgestellte Kampagnen-ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Die vom Google Kampagne Manager bereitgestellte Creative-ID. </p> </td> 
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
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen von Google Kampagne Manager und wandelt ihn in ein umsetzbares Signal um. </p> <p>Akzeptierte Werte sind: </p> <p> 
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
   <td colname="col3"> <p>Die ID der Datenquelle, mit der Sie Google Kampagne Manager-Daten erfassen. Siehe <a href="../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden in [!DNL Audience Manager] wie ein echter `HTTP`-Aufruf erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversions-Ereignis von [!DNL Google Campaign Manager]. Aufrufe müssen nicht unbedingt *alle* die Signale in den Beispielaufruf einschließen.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Bei einer Protokolldatei mit mittlerer Größe von 2 Mio. Zeilen werden alle Eigenschaften, die aus umsetzbaren Signalen erstellt werden, innerhalb von etwa einer Stunde nach der Verarbeitung der Protokolle realisiert.[!DNL Google Campaign Manager]

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>Der in den [!DNL Google Campaign Manager]-Protokollen angegebene Ereignis-Zeitstempel wird berücksichtigt und an das [!UICONTROL Data Collection Servers] weitergeleitet.
>
>* Wenn für eine Datenzeile in der Protokolldatei [!DNL Google Campaign Manager] kein Zeitstempel verfügbar ist, wird die Uhrzeit des Aufrufs `HTTP` als Ereignis-Zeitstempel verwendet.
>* Wenn die Datenzeile in der Protokolldatei [!DNL Google Campaign Manager] einen fehlerhaften Zeitstempel enthält, wird die gesamte Zeile ignoriert.


<br>

### Umsetzbare Signale von [!DNL Google Ad Manager] Protokollen {#ad-manager-logs-signals}

Die Tabelle Liste die aussagekräftigen Signale aus den Protokolldateien [!DNL Google Ad Manager]:


| Header Name in Protokolldatei | Signal | Beschreibung |
---------|----------|---------
| `LineItemId` | `d_lineitem` | Die numerische ID für den bereitgestellten Ad-Manager-Zeileneintrag |
| `OrderId` | `d_orderid` | Die numerische ID für die Anzeigenmanagerreihenfolge, die den bereitgestellten Zeileneintrag und das kreative Element enthielt. |
| `CreativeId` | `d_creative` | Die numerische ID für das bereitgestellte Ad Manager-Kreativelement. |
| `-` | `d_event` | Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen von Ad Manager und wandelt ihn in ein umsetzbares Signal um. Akzeptierte Werte sind: <br> <ul><li>d_Ereignis = imp für Impressionen.</li><li>d_Ereignis = Klicken für Klicks.</li><li>d_Ereignis = conv für Konversionen und Aktivitäten.</li></ul> |
| `-` | `d_src` | Die ID der Datenquelle, mit der Sie Ad Manager-Daten erfassen. Siehe [Erstellen einer Datenquelle](/help/using/features/manage-datasources.md). |

Die in der Tabelle beschriebenen Signale werden in Audience Manager wie ein Echtzeit-HTTP-Aufruf erfasst. Der folgende Beispielaufruf enthält Informationen zu einem Konversions-Ereignis von Google Ad Manager. Aufrufe müssen nicht unbedingt alle Signale in den Beispielaufruf einschließen.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>Der in den [!DNL Google Ad Manager]-Protokollen angegebene Ereignis-Zeitstempel wird berücksichtigt und an das [!UICONTROL Data Collection Servers] weitergeleitet.
>
>* Wenn für eine Datenzeile in der Protokolldatei [!DNL Google Ad Manager] kein Zeitstempel verfügbar ist, wird die Uhrzeit des Aufrufs `HTTP` als Ereignis-Zeitstempel verwendet.
>* Wenn die Datenzeile in der Protokolldatei [!DNL Google Ad Manager] einen fehlerhaften Zeitstempel enthält, wird die gesamte Zeile ignoriert.


<br> 

### Verfolgbare Signale aus generischen Anzeigenserverprotokollen {#generic-logs-signals}

Zunächst müssen Sie Ihre Anzeigenserverprotokolle in unseren Amazon S3-Buckets hinterlegen. Lesen Sie dazu [Datendateien für Audience Optimizationen-Berichte und zu verarbeitende Protokolldateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *und* wenden Sie sich an Ihren [!DNL Audience Manager]-Berater. Die Tabelle Liste die aussagekräftigen Signale aus generischen Protokolldateien:

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
   <td colname="col3"> <p> Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversions-Ereignis. Verwenden Sie das Format <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Ein Integrationscode für die Datenquelle Ihres Advertisers. Beachten Sie, dass dieses Feld nicht mit <a href="../../features/datasources-list-and-settings.md">Audience Manager-Datenquellen verwandt ist.</a></p></td> 
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
   <td colname="col3"> <p>Gibt den Ereignistyp an. Audience Manager liest den Ereignistyp aus dem Protokolldateinamen und wandelt ihn in ein umsetzbares Signal um. Siehe <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">Benennungskonventionen für Protokolldateien</a>. </p> <p>Akzeptierte Werte sind: </p> <p> 
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
   <td colname="col3"> <p>Die ID der Datenquelle, mit der Sie Protokolldaten erfassen. Siehe <a href="../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden in [!DNL Audience Manager] wie ein echter `HTTP`-Aufruf erfasst. Aufrufe müssen nicht unbedingt *alle* die Signale in den Beispielaufruf einschließen.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Arbeiten mit funktionsfähigen Signalen in der Benutzeroberfläche des Audience Managers {#actionable-signals-in-ui}

Sie können Ihre eingehenden umsetzbaren Signale in der [Signalsuche](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md)-Schnittstelle Ansicht haben.

Wechseln Sie zu **Audience Data** (1) > **Signals** (2) > **Search** (3) und wählen Sie den Filter **Umsetzbare Protokolldateien** (4).

![Umsetzbare Signale in der Benutzeroberfläche](/help/using/integration/assets/alf-in-signals.png)

Um regelbasierte Eigenschaften mit Ihren umsetzbaren Signalen zu erstellen, wählen Sie **Umsetzbare Protokolldateien** (1), wählen Sie die umsetzbaren Signale aus, die Sie als Eigenschaftsregeln verwenden möchten (2), und drücken Sie **Eigenschaft aus ausgewählten Signalen erstellen** (3).

![Eigenschaften aus Signalen erstellen](/help/using/integration/assets/alf-create-trait.png)


## Nutzungsszenarios {#use-cases}

Ein Vorteil der Implementierung von [!UICONTROL Actionable Log Files] ist die Option, [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md)-Steuerelemente auf alle [regelbasierten Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) anzuwenden, die brauchbare Signale enthalten. Auf diese Weise können Sie z. B. die Häufigkeit begrenzen, mit der ein Benutzer ein bestimmtes kreatives Element innerhalb einer Media-Kampagne anzeigt. Lesen Sie [Sofortige geräteübergreifende Unterdrückung](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md), um zu erfahren, wie Sie dies tun. Weitere Anwendungsfälle sind:

### Retargeting-Benutzer

Retarget-Benutzer, die kreative Elemente des Typs 123 gesehen haben, aber nicht auf &quot;Kreativ&quot;geklickt oder konvertiert haben, und ihnen kreative Elemente des Typs 456 zeigen. Führen Sie folgende Schritte aus:

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die das kreative Element gesehen haben. Nehmen wir an, Sie benennen die Eigenschaft [!DNL Creative Trait 123]. Verwenden Sie die Eigenschaftsregel:

   `d_creative == 123 AND d_event == imp`

2. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die klicken oder konvertieren. Nehmen wir an, Sie benennen dieses [!DNL Click and Converter]. Verwenden Sie die Eigenschaftsregel:

   `d_event == click OR d_event=conv`

3. Erstellen Sie ein Segment, das mit Benutzern gefüllt wird, die kreative Elemente 123 gesehen haben, aber nicht klicken oder konvertieren. Benennen Sie es [!DNL Retarget Users] und verwenden Sie die Segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Ordnen Sie das Segment [!DNL Retarget Users] einem Ziel- und Zielgruppe-Benutzer im Ziel mit dem kreativen 456 zu.

### Verwenden Sie die Floodlight-Aktivität von Google Kampagne Manager in den Audience Optimizationen-Berichten oder im Audience Lab

[Floodlight-](https://support.google.com/dcm/partner/answer/4293719?hl=en) Anzeigenkunden zur Verfolgung von Benutzerkonversionen. Mit [!UICONTROL Actionable Log Files] können Sie die [!DNL Google Campaign Manager]-Konvertierungen in den [Audience Optimizationen-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) oder im [Audience-Lab](../../features/audience-lab/audience-lab.md) verfolgen:

1. Erstellen Sie eine Eigenschaft und verwenden Sie die folgende Eigenschaftsregel, um eine Konvertierung aus den Anzeigenserverprotokollen zu erfassen:

   `d_event == conv AND d_conversion == 123`

   Wählen Sie beim Erstellen der Eigenschaft im Audience Manager [!UICONTROL UI] [!UICONTROL Conversion] als [!UICONTROL Event Type] aus.

2. Nachdem Sie die Eigenschaft erstellt haben, beginnt die Konvertierung mit der Berichterstattung in [!UICONTROL Audience Optimization Reports] und [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importieren von Google Kampagne Manager-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Berichte zur Zielgruppenoptimierung](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

