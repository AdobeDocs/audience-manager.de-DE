---
description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Audience Optimization-Berichte zeigen lesbare Namen in den verschiedenen Berichtsoptionen-Menüs an.
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: Übersicht und Zuordnungen für Metadatendateien
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 2%

---

# Übersicht und Zuordnungen für Metadatendateien{#overview-and-mappings-for-metadata-files}

Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Audience Optimization-Berichte zeigen lesbare Namen in den verschiedenen Berichtsoptionen-Menüs an.

## Überblick {#overview}

Eine Übersicht über Metadaten und ihre Verwendung. Eine Metadatendatei muss von einer Datendatei begleitet werden. Die Inhalte der Metadatendateien stimmen mit den Datendateiinformationen in Bezug auf menschenlesbare Kennzeichnungen in den Berichtsmenüs überein. Weitere Informationen finden Sie unter [Datendateien für das Audience Optimization von Berichten und verwertbaren Protokolldateien](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metadatendateien enthalten Daten zu anderen Daten

Eine Metadatendatei enthält Informationen zu anderen Datentypen. Damit Sie besser verstehen können, wie dies funktioniert, sollten wir überprüfen, wie [!DNL Audience Manager] Daten erhält.

Während eines Impression- oder Klickereignisses empfängt [!DNL Audience Manager] Daten in einer URL-Zeichenfolge, die als &quot;*&quot; bezeichnet*.

Der Ereignisaufruf organisiert Informationen in Gruppen definierter Schlüssel-Wert-Paare. Die Werte in einem Schlüssel-Wert-Paar enthalten numerische Daten. Die Metadatendatei enthält Namen und andere lesbare Informationen entsprechend der ID in jedem Schlüssel-Wert-Paar.

### Metadaten verknüpfen IDs mit lesbaren Namen

Die Metadatendatei ist erforderlich, um eine numerische ID mit einem lesbaren Namen zu verknüpfen. Beispiel: Ein Ereignisaufruf enthält eine kreative ID in einem Schlüssel-Wert-Paar wie dem folgenden: `d_creative:1234`. Ohne eine Metadatendatei würde dieser Kreative in einem Optionsmenü als 1234 angezeigt.

Eine ordnungsgemäß formatierte Metadatendatei kann diesen Kreativen jedoch an einen echten Namen wie „Advertiser Creative A“ binden, einen Namen, den Sie in einem Bericht lesen und erkennen können.

### Wann benötigen Sie eine Metadatendatei?

Wenn Sie die [Audience Optimization-Berichte verwenden möchten, sind in einem Ereignisaufruf zunächst eine Metadatendatei und alle unten aufgeführten Parameter ](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Zweitens benötigen Sie eine Metadatendatei, wenn Sie Ihre eigenen Daten an [!DNL Audience Manager] senden oder wenn Sie Daten in den Berichten anderer Anbieter sehen möchten, mit denen wir nicht integriert sind. Beispielsweise verfügt [!DNL Audience Manager] über eine Integration mit dem [-Click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) von Google. Aufgrund dieser Beziehung können [!DNL Audience Manager] IDs mit Namen und Beschreibungen verknüpfen, die von den Berichtsoptionen verwendet werden. Ohne eine -Integration können wir weiterhin Daten aufnehmen, aber die Berichtsoptionen zeigen numerische IDs anstelle eines beschreibenden Namens an.

![Metadatenmenü-Bild](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Dateizuordnungen {#file-mappings}

In der folgenden Tabelle sind die Schlüssel-Wert-Paare aufgeführt, die die von den [!UICONTROL Audience Optimization]-Berichten verwendeten Daten enthalten. Wenn Sie eine Metadatendatei verwenden müssen, würde sie für Menschen lesbare Informationen enthalten, die den Werten in diesen Schlüssel-Wert-Paaren entsprechen. Die Werte für diese Schlüssel akzeptieren nur Ganzzahlen (Datentyp INT). Hinweis: *Kursiv* gibt einen Variablenplatzhalter an. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

>[!IMPORTANT]
>
>Wenn Sie die [!UICONTROL Audience Optimization] Berichte verwenden, sind *alle* diese Werte im Ereignisaufruf erforderlich.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsoption </th> 
   <th colname="col2" class="entry"> Schlüssel-Wert-Paare für Metadaten </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Dies ist die Datenquellen-ID oder der Integrations-Code des Advertisers, die bzw. der beim Erstellen einer Datenquelle bereitgestellt wurde. Siehe <a href="../../../features/manage-datasources.md#create-data-source"> Erstellen eines Daten-Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geschäftseinheit (BU) </p> </td> 
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
   <td colname="col2"> <p>Akzeptiert zwei verschiedene Schlüssel-Wert-Paare: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einfügungsreihenfolge (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattform </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Dies ist die <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquelle</a> ID für die Plattform, die Metadateninformationen bereitstellt (z. B. DFA, Atlas, GBM, MediaMath usw.). </p> </td> 
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

## Gestalten von Dateinamen, Inhalten und Versandpfaden durch Ereignis-Aufruf-IDs {#how-ids-shape-file-names}

Die von diesen Schlüssel-Wert-Paaren übergebenen IDs helfen beim Erstellen des Metadatendateinamens und seines Inhalts. Die folgenden Abschnitte und Abbildungen zeigen, wie dies funktioniert. In diesen Beispielen wird eine Datei erstellt, die den Namen eines Kreativen in einer Kampagne enthält. Es sind jedoch auch andere Kombinationen möglich.

### Ereignisaufruf

In diesem Beispiel erstellen wir eine Metadatendatei, die kreative Namen in einen [!UICONTROL Audience Optimization]-Bericht einbringt. Dazu müssen wir Kreativ-, Kampagnen- und Datenquellen-IDs aus einem Ereignisaufruf extrahieren.

![Bild des Ereignisaufrufs](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Dateiname

Der Dateiname basiert auf den Kreativ-, Kampagnen- und Datenquellen-IDs. Vergleichen Sie in diesem Fall die Unterschiede zwischen den Schlüssel-Wert-Daten in einem Ereignisaufruf und ihrer Verwendung in einem Dateinamen.

In einem Dateinamen:

* Der Datenquellenschlüssel ändert sich von `d_src` in `dpid`.

* Die Kreativ- und Kampagnen-IDs stellen eine Kategorie und keine tatsächliche Kennung dar.

![Wie wird ein Dateiname erstellt](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Siehe [Benennungskonventionen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Dateiinhalte

In diesem Beispiel spiegeln die Dateiinhalte die Kreativ- und Kampagnen-IDs wider, die beim Ereignisaufruf übergeben werden. Das neue Element hier ist ein lesbarer Name. Nach der Verarbeitung wird der Name in dieser Datei als Option im Kreativ-Menü eines [!UICONTROL Audience Optimization]-Berichts angezeigt.

![Inhalt einer Metadatendatei](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Siehe [Inhaltsformat für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Dateiversand

Nachdem Sie einer Datei einen Namen gegeben und Daten hinzugefügt haben, senden Sie sie an ein von [!DNL Audience Manager] bereitgestelltes Amazon S3-Speicherverzeichnis. Siehe [Bereitstellungsmethoden für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Datendateien zum Audience Optimization von Berichten](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Erfassen von Kampagnenklickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md)
>* [Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe](../../../integration/media-data-integration/impression-data-pixels.md)
