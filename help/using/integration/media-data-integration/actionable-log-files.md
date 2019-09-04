---
description: Anhand verfolgbarer Protokolldateien können Sie Mediendaten aus Google DCM-Protokolldateien erfassen und die Daten verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen aus Ad-Servern als Eigenschaften, ohne Pixelaufrufe verwenden zu müssen.
keywords: nachvollziehbare Protokolle
seo-description: Anhand verfolgbarer Protokolldateien können Sie Mediendaten aus Google DCM-Protokolldateien erfassen und die Daten verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen aus Ad-Servern als Eigenschaften, ohne Pixelaufrufe verwenden zu müssen.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actionable Log Files
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Actionable Log Files {#actionable-log-files}

[!UICONTROL Actionable Log Files] können Sie Mediendaten aus [!DNL Google DCM] Protokolldateien erfassen und die Daten verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen aus Ad-Servern als Eigenschaften, ohne Pixelaufrufe verwenden zu müssen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

## Zielsetzung {#purpose}

[!UICONTROL Actionable Log Files] optimieren Sie die Erfassung von Impressionen, Klicks und Konversionen von Anzeigenservern. Verwenden Sie diese Informationen zur Benutzersegmentierung, ohne Medien manuell zum Senden von Kampagnenattributen manuell zu verwenden [!DNL Audience Manager].

## Erste Schritte {#getting-started}

Um mit unseren [!UICONTROL Actionable Log Files]Zielgruppenoptimierungsberichten zu beginnen und unsere [Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/audience-optimization-reports.md)zu verwenden, müssen [!DNL Audience Manager]Sie DCM-Protokolldaten importieren. Siehe [Importieren von DCM-Datendateien in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *und* wenden Sie sich an Ihren [!DNL Audience Manager] Berater.

Wenn [!UICONTROL DCM] Sie bereits Protokolldaten importieren, bitten [!DNL Audience Manager]Sie Ihren [!DNL Audience Manager] Berater oder [die Kundenunterstützung](https://helpx.adobe.com/contact/enterprise-support.ec.html) , für Sie zu aktivieren [!UICONTROL Actionable Log Files] .

>[!NOTE] {important = "high"}
>
>[!UICONTROL Actionable Log Files] nur mit [!DNL Google DCM] Protokolldateien arbeiten.

## Arbeiten mit verfolgbaren Protokolldateien {#working-with-actionable-log-files}

Mit den [!UICONTROL Actionable Log Files]Informationen aus [!DNL DCM] Protokollen werden auf [!DNL Audience Manager] dieselbe Weise erfasst wie Daten aus Echtzeit-Website-Interaktionen. [!DNL Audience Manager] stellt eine Verbindung zu Ihrem [!DNL Google Cloud] Speicher her, analysiert die Informationen aus [!DNL DCM] Protokollen und sendet die Protokolldaten als verfolgbare Signale an unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md#dcs-pcs).

Sie müssen weiterhin regelbasierte Eigenschaften einrichten, um die verfolgbaren Signale zu erfassen. Hier erfahren Sie, wie Sie regelbasierte Eigenschaften entweder in der [Benutzeroberfläche von Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oder in unseren [Massen-Management-Tools einrichten](../../reference/bulk-management-tools/bulk-create.md). Blättern Sie nach unten zum Abschnitt ["Umsetzbare Signale](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) " für eine Liste aller Schlüssel, die Sie in regelbasierten Eigenschaften verwenden können.

Bei [!DNL DCM] einer Protokolldatei mit einer durchschnittlichen Größe von 2 Millionen werden alle Eigenschaften, die aus umsetzbaren Signalen erstellt wurden, innerhalb von etwa einer Stunde nach der Verarbeitung der Protokolle erstellt.

>[!IMPORTANT] {important = "high"}
>
>Es wird empfohlen, [!UICONTROL Actionable Log Files]*anstelle* [von Pixelaufrufen die Implementierung](../../integration/media-data-integration/impression-data-pixels.md)vorzunehmen. Wir deklonen die Verwendung beider Optionen, da dies zu einer Erhöhung der Frequenzzahlen für Eigenschaften führt.

## Umsetzbare Signale {#actionable-signals}

Signal sind die [kleinsten Dateneinheiten](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] ermöglicht es Ihnen, Advertiser, Geschäftseinheiten, kreative Elemente und Kampagnenwerte in Impressionsereignissen, Click-Ereignissen und Konversionsereignissen als Signale aus [!DNL DCM] Protokollen zu erfassen.

Denken Sie daran, dass Sie die regelbasierten Eigenschaften selbst einrichten, um diese Informationen für die Erstellung und Segmentierung von Zielgruppen zu verwenden. Die Tabelle listet die verfolgbaren Signale aus [!DNL DCM] Protokolldateien auf:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Signal </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Beispielwert </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>Gibt den Ereignistyp von DCM an. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event = imp</code> für Impressionen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event = Klicken</code> Sie auf Klicks. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event = conv</code> für Konversionen. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, klicken, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Stellt die numerische ID für die Konversionsaktivität in DCM dar. Dieses Feld wird der Aktivitäts-ID von DCM zugeordnet. </p> <p> <p>Tipp: Sie können mehrere oder spezifische Konversionsaktivitäten von DCM erfassen. Erstellen Sie Eigenschaften mit <code> d_ conversion = Aktivitäts-ID</code> für jede Konversionsaktivität von DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversiontype</code> </p> </td> 
   <td colname="col2"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Dieses Feld wird der Konversions-ID in DCM zugeordnet. Gibt die Aktivität vor der Benutzerkonversion von DCM an. </p> <p>Akzeptierte Werte sind: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> für Nach-Klick-Konversionen. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> für Post-Impressionen. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> für nicht übereinstimmende Konvertierungen. Die Konversion kann nicht mit einer vorherigen Aktivität abgeglichen werden. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>Advertiser-ID.</p> <p>Ein Integrationscode für die Datenquelle Ihres Werbetreibenden. Beachten Sie, dass dies nicht mit Audience Manager-Datenquellen in Zusammenhang steht.</p> <p>Dieses Feld wird der Advertiser-Gruppen-ID von DCM zugeordnet. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>Geschäftsentitäts-ID. Dieses Feld wird der Advertiser-ID von DCM zugeordnet. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>Die von DCM bereitgestellte Kampagnen-ID. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>Die von DCM bereitgestellte Creative ID. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>Die ID der Datenquelle, die Sie zur Erfassung von DCM-Daten verwenden. Siehe <a href="../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Die in der Tabelle beschriebenen Signale werden [!DNL Audience Manager] wie ein Echtzeitanruf `HTTP` erfasst. Der unten stehende Beispielaufruf enthält Informationen zu einem Konversionsereignis. [!DNL DCM] Aufrufe müssen nicht notwendigerweise *alle* Signale im Beispielaufruf enthalten.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important = "high"}
>
>Der in den [!DNL DCM] Protokollen bereitgestellte Ereigniszeitstempel wird berücksichtigt und an diese [!UICONTROL Data Collection Servers]weitergegeben.
>
>* Wenn für eine Datenzeile in der [!DNL DCM] Protokolldatei kein Zeitstempel verfügbar ist, wird der Zeitpunkt des `HTTP` Aufrufs als Ereigniszeitstempel verwendet.
>* Wenn die Datenzeile in der [!DNL DCM] Protokolldatei einen falsch formatierten Zeitstempel enthält, ignorieren wir die gesamte Zeile.


## Nutzungsszenarios {#use-cases}

Ein Vorteil der Implementierung [!UICONTROL Actionable Log Files] ist die Anwendung [von Neuigkeit- und Frequenzsteuerelementen](../../features/segments/recency-and-frequency.md) auf [regelbasierte Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) , die umsetzbare Signale enthalten. So können Sie beispielsweise festlegen, wie oft ein Benutzer ein bestimmtes kreatives Element in einer Medienkampagne anzeigt. Zu den weiteren Anwendungsfällen gehören:

### Benutzer retargeting

Targeting von Benutzern, die kreative 123 Artikel gesehen, aber nicht auf oder konvertiert und Creative Creative Suite 456 angezeigt haben. Gehen Sie wie folgt vor:

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die die kreativen Elemente gesehen haben. Nehmen wir an, Sie benennen die Eigenschaft [!DNL Creative Trait 123]. Verwenden Sie die Eigenschaftenregel:

   `d_creative == 123 AND d_event == imp`

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die klicken oder konvertieren. Nehmen wir an, Sie benennen diesen [!DNL Click and Converter]Namen. Verwenden Sie die Eigenschaftenregel:

   `d_event == click OR d_event=conv`

1. Erstellen Sie ein Segment, das mit Benutzern gefüllt wird, die kreative 123 Artikel gesehen, aber nicht auf oder umgerechnet haben. Benennen [!DNL Retarget Users] Sie ihn und verwenden Sie die Segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

1. Ordnen Sie das Segment [!DNL Retarget Users] einem Ziel zu und geben Sie als Ziel für Benutzer ein Ziel von 456 ein.

### Verwenden der DCM Floodlight-Aktivität in den Zielgruppenoptimierungsberichten oder in Audience Lab

[Mit Floodlight-Tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) können Advertiser Benutzerkonvertierungen verfolgen. Mit [!UICONTROL Actionable Log Files]können Sie die [!DNL DCM] Konversionen in den [Zielgruppenoptimierungsberichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) oder [in Audience Lab verfolgen](../../features/audience-lab/audience-lab.md):

1. Erstellen Sie eine Eigenschaft und verwenden Sie die folgende Eigenschaftenregel, um eine Konvertierung aus den Anzeigen-Serverprotokollen zu erfassen:

   `d_event == conv AND d_conversion == 123`

   Wenn Sie die Eigenschaft im Audience Manager [!UICONTROL UI]erstellen, wählen [!UICONTROL Conversion] Sie als " [!UICONTROL Event Type].

2. Sobald Sie die Eigenschaft erstellt haben, wird die Konversion im- und [!UICONTROL Audience Optimization Reports][!UICONTROL Audience Lab]ab.

>[!MORE_ LIKE_ THIS]
>
>* [DCM-Datendateien in Audience Manager importieren](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

