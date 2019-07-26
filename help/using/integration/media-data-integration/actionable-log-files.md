---
description: Anhand verfolgbarer Protokolldateien können Sie Mediendaten aus Google DCM-Protokolldateien erfassen und die Daten verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen aus Ad-Servern als Eigenschaften, ohne Pixelaufrufe verwenden zu müssen.
keywords: nachvollziehbare Protokolle
seo-description: Anhand verfolgbarer Protokolldateien können Sie Mediendaten aus Google DCM-Protokolldateien erfassen und die Daten verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen aus Ad-Servern als Eigenschaften, ohne Pixelaufrufe verwenden zu müssen.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actionable Log Files
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Actionable Log Files {#actionable-log-files}

[!UICONTROL Actionable Log Files] können Sie Mediendaten aus [!DNL Google DCM] Protokolldateien erfassen und die Daten verwenden, um Eigenschaften in Audience Manager zu erstellen. Erfassen Sie Impressionen, Klicks und Konversionen aus Ad-Servern als Eigenschaften, ohne Pixelaufrufe verwenden zu müssen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../reference/code-style-elements.md).

## Zielsetzung {#purpose}

[!UICONTROL Actionable Log Files] optimieren Sie die Erfassung von Impressionen, Klicks und Konversionen von Anzeigenservern. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Erste Schritte {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {important = "high"}
>
>[!UICONTROL Actionable Log Files] nur mit [!DNL Google DCM] Protokolldateien arbeiten.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] stellt eine Verbindung zu Ihrem [!DNL Google Cloud] Speicher her, analysiert die Informationen aus [!DNL DCM] Protokollen und sendet die Protokolldaten als verfolgbare Signale an unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md#dcs-pcs).

Sie müssen weiterhin regelbasierte Eigenschaften einrichten, um die verfolgbaren Signale zu erfassen. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {important = "high"}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Wir deklonen die Verwendung beider Optionen, da dies zu einer Erhöhung der Frequenzzahlen für Eigenschaften führt.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] ermöglicht es Ihnen, Advertiser, Geschäftseinheiten, kreative Elemente und Kampagnenwerte in Impressionsereignissen, Click-Ereignissen und Konversionsereignissen als Signale aus [!DNL DCM] Protokollen zu erfassen.

Denken Sie daran, dass Sie die regelbasierten Eigenschaften selbst einrichten, um diese Informationen für die Erstellung und Segmentierung von Zielgruppen zu verwenden. The table lists the actionable signals from [!DNL DCM] log files:

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
   <td colname="col2"> <p>Nur für Konversionsereignisse verfügbar. </p> <p>Stellt die numerische ID für die Konversionsaktivität in DCM dar. Dieses Feld wird der Aktivitäts-ID von DCM zugeordnet. </p> <p> <p>Tipp: Sie können mehrere oder spezifische Konversionsaktivitäten von DCM erfassen. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
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
   <td colname="col2"> <p>Advertiser-ID. Dieses Feld wird der Advertiser-Gruppen-ID von DCM zugeordnet. </p> </td> 
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
   <td colname="col2"> <p>Die ID der Datenquelle, die Sie zur Erfassung von DCM-Daten verwenden. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important = "high"}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn't available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.


## Nutzungsszenarios {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. So können Sie beispielsweise festlegen, wie oft ein Benutzer ein bestimmtes kreatives Element in einer Medienkampagne anzeigt. Zu den weiteren Anwendungsfällen gehören:

### Benutzer retargeting

Targeting von Benutzern, die kreative 123 Artikel gesehen, aber nicht auf oder konvertiert und Creative Creative Suite 456 angezeigt haben. Gehen Sie wie folgt vor:

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die die kreativen Elemente gesehen haben. Let's say you name the trait [!DNL Creative Trait 123]. Verwenden Sie die Eigenschaftenregel:

   `d_creative == 123 AND d_event == imp`

1. Erstellen Sie eine Eigenschaft, um Benutzer zu erfassen, die klicken oder konvertieren. Let's say you name this one [!DNL Click and Converter]. Verwenden Sie die Eigenschaftenregel:

   `d_event == click OR d_event=conv`

1. Erstellen Sie ein Segment, das mit Benutzern gefüllt wird, die kreative 123 Artikel gesehen, aber nicht auf oder umgerechnet haben. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Verwenden der DCM Floodlight-Aktivität in den Zielgruppenoptimierungsberichten oder in Audience Lab

[Mit Floodlight-Tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) können Advertiser Benutzerkonvertierungen verfolgen. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Erstellen Sie eine Eigenschaft und verwenden Sie die folgende Eigenschaftenregel, um eine Konvertierung aus den Anzeigen-Serverprotokollen zu erfassen:

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ THIS]
>
>* [DCM-Datendateien in Audience Manager importieren](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Zielgruppenoptimierungsberichte](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

