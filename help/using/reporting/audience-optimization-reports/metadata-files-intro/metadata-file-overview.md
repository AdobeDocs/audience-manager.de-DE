---
description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zu Audience Optimizationen zeigen lesbare Namen in den verschiedenen Berichtoptionen an.
seo-description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zu Audience Optimizationen zeigen lesbare Namen in den verschiedenen Berichtoptionen an.
seo-title: Überblick und Zuordnungen für Metadatendateien
solution: Audience Manager
title: Überblick und Zuordnungen für Metadatendateien
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: log files
translation-type: tm+mt
source-git-commit: f37ba905d603a3b95fda3ab797bb882f94e0066d
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 4%

---


# Überblick und Zuordnungen für Metadatendateien{#overview-and-mappings-for-metadata-files}

Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zu Audience Optimizationen zeigen lesbare Namen in den verschiedenen Berichtoptionen an.

## Überblick {#overview}

Eine Übersicht über Metadaten und deren Verwendung. Eine Metadatendatei muss von einer Datendatei begleitet sein. Der Inhalt der Metadatendatei stimmt mit den Datendateiinformationen mit den entsprechenden, für Menschen lesbaren Beschriftungen in den Berichtmenüs überein. Weitere Informationen finden Sie unter [Datendateien für Audience Optimizationen-Berichte und ausführbare Protokolldateien](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metadatendateien enthalten Daten zu anderen Daten

Eine Metadatendatei enthält Informationen zu anderen Datentypen. Damit Sie besser verstehen können, wie das funktioniert, sollten Sie überprüfen, wie Daten [!DNL Audience Manager] empfangen werden.

Während eines Impressions- oder Klick-Ereignisses werden Daten in einer URL-Zeichenfolge empfangen, die als [!DNL Audience Manager] Ereignis-Aufruf ** bezeichnet wird.

Der Ereignis-Aufruf organisiert Informationen in Gruppen von definierten Schlüssel/Wert-Paaren. Die Werte in einem Schlüssel-Wert-Paar enthalten numerische Daten. Die Metadatendatei enthält Namen und andere lesbare Informationen, die der ID in jedem Schlüssel-Wert-Paar entsprechen.

### Metadaten-Links-IDs zu lesbaren Namen

Die Metadatendatei ist erforderlich, um eine numerische ID mit einem lesbaren Namen zu verknüpfen. Angenommen, ein Ereignis-Aufruf enthält eine kreative ID in einem Schlüsselwertpaar wie diesem: `d_creative:1234`. Ohne Metadatendatei würde dieses Kreativelement in einem Optionsmenü als 1234 angezeigt.

Eine ordnungsgemäß formatierte Metadatendatei kann dieses kreative Element jedoch mit einem echten Namen wie &quot;Werbetreibende Kreative A&quot;verbinden, einem Namen, den Sie in einem Bericht lesen und erkennen können.

### Wann benötigen Sie eine Metadatendatei?

Zunächst sind eine Metadatendatei und alle unten aufgeführten Parameter für einen Ereignis-Aufruf erforderlich, wenn Sie die [Audience Optimizationen-Berichte](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)verwenden möchten.

Zweitens benötigen Sie eine Metadatendatei, wenn Sie Ihre eigenen Daten an [!DNL Audience Manager] oder wenn Sie Daten aus den Berichten anderer Anbieter sehen möchten, mit denen wir nicht integriert sind. Beispielsweise [!DNL Audience Manager] ist Google mit dem [Dublette-Click-Kampagne-Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) von Google integriert. Aufgrund dieser Beziehung [!DNL Audience Manager] können IDs mit Namen und Beschreibungen verknüpft werden, die von den Berichtsoptionen verwendet werden. Ohne Integration können wir weiterhin Daten erfassen, aber die Berichtsoptionen zeigen numerische IDs anstelle eines beschreibenden Namens an.

![schema des Metadatenmenüs](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata-menu.png)

## Dateizuordnungen {#file-mappings}

In der folgenden Tabelle werden die Schlüssel-Wert-Paare mit den von den [!UICONTROL Audience Optimization] Berichten verwendeten Daten Liste. Wenn Sie eine Metadatendatei verwenden müssen, enthält sie für Menschen lesbare Informationen, die den Werten in diesen Schlüssel/Wert-Paaren entsprechen. Die Werte für diese Schlüssel akzeptieren nur Ganzzahlen (Datentyp INT). Note, *italics* indicates a variable placeholder. Andere Elemente sind Konstanten oder Schlüssel und bleiben unverändert.

>[!IMPORTANT]
>
>Wenn Sie die [!UICONTROL Audience Optimization] Berichte verwenden, sind *alle* Werte im Ereignis-Aufruf erforderlich.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsoption </th> 
   <th colname="col2" class="entry"> Metadaten-Schlüsselwertpaare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Dies ist die Datenquelle-ID oder der Integrationscode des Advertisers, die bzw. der beim Erstellen einer Datenquelle bereitgestellt wird. See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business Unit (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampagne </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kreativ </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange- </p> </td> 
   <td colname="col2"> <p>Akzeptiert zwei verschiedene Schlüssel/Wert-Paare: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einfügereihenfolge (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattform </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Dies ist die <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquellen</a> -ID für die Plattform, die Metadateninformationen bereitstellt (z. B. DFA, Atlas, GBM, MediaMath usw.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktik </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Wie Ereignis IDs für Formdateinamen, -inhalte und -pfade aufruft {#how-ids-shape-file-names}

Die von diesen Schlüssel-Wert-Paaren weitergeleiteten IDs helfen beim Erstellen des Metadaten-Dateinamens und seines Inhalts. Die folgenden Abschnitte und Abbildungen zeigen, wie dies funktioniert. In diesen Beispielen wird eine Datei erstellt, die den Namen eines kreativen Elements in einer Kampagne enthält. Es sind jedoch auch andere Kombinationen möglich.

### Ereignis-Aufruf

In diesem Beispiel erstellen wir eine Metadatendatei, die kreative Namen in einen [!UICONTROL Audience Optimization] Bericht einfügt. Dazu müssen wir kreative IDs, Kampagnen und Datenquellen-IDs aus einem Ereignis-Aufruf extrahieren.

![ereignis-Metadatendatei-Schema](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata-file-event.png)

### Dateiname

Der Dateiname basiert auf den kreativen IDs, der Kampagne und den Datenquellen-IDs. Vergleichen Sie in diesem Fall die Unterschiede zwischen den Schlüsselwertdaten in einem Ereignis-Aufruf und der Verwendung in einem Dateinamen.

In einem Dateinamen:

* Der Datenquellenschlüssel ändert sich in `dpid` von `d_src`.

* Die Kreativ- und Kampagnen-IDs stellen eher eine Kategorie als eine tatsächliche ID dar.

![schema des Metadatendateinamens](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata-file-name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Dateiinhalt

In diesem Beispiel spiegeln die Dateiinhalte die kreativen IDs und Kampagnen-IDs wider, die beim Ereignis-Aufruf übergeben werden. Das neue Element hier ist ein lesbarer Name. Nach der Verarbeitung wird der Name in dieser Datei als Option im Menü &quot;Kreativ&quot;eines [!UICONTROL Audience Optimization] Berichts angezeigt.

![schema für Metadatendateiinhalte](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata-file-contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### File Versand

Nachdem Sie einer Datei einen Namen gegeben und Daten hinzugefügt haben, senden Sie diese an ein Amazon S3-Datenspeicherung-Verzeichnis, das von [!DNL Audience Manager]bereitgestellt wird. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Datendateien für Berichte zur Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Erfassen von Kampagnenklickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md)
>* [Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe](../../../integration/media-data-integration/impression-data-pixels.md)

