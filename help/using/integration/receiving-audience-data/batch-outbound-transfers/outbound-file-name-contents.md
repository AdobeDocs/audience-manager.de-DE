---
description: Beschreibt die erforderlichen Felder, die Syntax und die Konventionen zum Benennen einer ausgehenden Datendatei.
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: Name der ausgehenden Datendatei Syntax und Beispiele
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 5%

---

# Name der ausgehenden Datendatei: Syntax und Beispiele{#outbound-data-file-name-syntax-and-examples}

Beschreibt die erforderlichen Felder, die Syntax und die Konventionen zum Benennen einer ausgehenden Datendatei.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Die Stilelemente (`monospaced text`, *Kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument weisen auf Codeelemente und Optionen hin. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax- und Dateinamenelemente {#syntax-file-name}

Ausgehende Dateinamen enthalten die folgenden Elemente. Alle folgenden Elemente sind optional.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parameter

Die Tabelle definiert die Elemente in einem Namen für eine ausgehende Datendatei.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateinamenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Bezieht sich auf die Datenübertragungsmethoden. Zu den Übertragungsmethoden gehören: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Übertragung über SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - Weiterleitung an <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>Ziel-ID. </p> <p>In <span class="keyword"> Audience Manager-</span> ist ein Ziel die Instanz der Integration, in der Sie Ihre Zielgruppensegmente zuordnen können. Abhängig von den Geschäftsanforderungen können Kunden über mehrere Ziele verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter- oder Datenquellen-ID. Diese ID identifiziert den Typ der im Dateiinhalt vorhandenen Benutzer-ID. Die häufigsten Benutzer-ID-Schlüssel sind: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser-ID-</span> (Roh, ungehasht) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple-ID für Advertisers-</span> (unbearbeitet, ungehasht) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">Anbieter-ID - Benutzer-IDs von Drittanbietern (Web/Cookie) </li> 
     </ul> </p> <p>Weitere Informationen finden Sie unter <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html?lang=de">Globale Data Sources</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> Die Kundenkennung der Drittanbieterplattform. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Der Synchronisierungsmodus ist ein Makro-Platzhalter, der dem Dateinamen je nach Synchronisierungstyp eine Bezeichnung hinzufügt. Zu den Synchronisierungstypen gehören vollständig und inkrementell. Sie werden im Dateinamen als <code> iter </code> oder <code> full </code> angezeigt. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Gibt eine „iterative“ oder inkrementelle Synchronisierung an. Eine inkrementelle Datei enthält nur neue Daten, die seit der letzten Synchronisierung erfasst wurden. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Gibt eine „vollständige“ Synchronisierung an. Eine vollständig synchronisierte Datei enthält alte Daten und alle neuen Daten, die seit der letzten Synchronisierung erfasst wurden. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Ein 13-stelliger UNIX-Zeitstempel in Millisekunden in der UTC-Zeitzone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Identifiziert einen Teil einer Datei, der in mehrere Teile aufgeteilt wurde, um die Verarbeitungszeit zu verbessern. Die Zahl gibt an, zu welchem Teil der Originaldatei die Daten gehören.</p>  <p>Wenn die Aufspaltungsgröße weniger als 100 Teile beträgt, muss die Ganzzahl mindestens 3 Ziffern lang sein, denen Nullen vorangestellt sind.</p>  <p>Die Originaldatei hat keine Aufspaltungsnummer. Die erste aufgeteilte Datei endet mit 001. Siehe Beispiele unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP-Komprimierung. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateinamen {#file-name-examples}

### Szenario 1

Dateien, die an einen [!DNL Amazon S3] Speicherort gesendet werden, mit *`PID_ALIAS="XYZCustomer"`* und mit [!DNL Google Advertiser IDs] im Dateiinhalt.

Z. B. inkrementelle Dateien:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Z. B. vollständige Dateien:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Szenario 2

Dateien werden ohne *`PID_ALIAS`* und mit [!DNL Apple Advertiser IDs] im Dateiinhalt an [!DNL FTP] Speicherort gesendet:

Z. B. inkrementelle Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Z. B. vollständige Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Szenario 3**: Dateien werden an [!DNL FTP] Speicherort gesendet, mit *`PID_ALIAS="XYZCustomer"`* und mit Benutzer-ID von Drittanbietern im Dateiinhalt ( *`Vendor ID=45454`*):

Z. B. inkrementelle Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Z. B. vollständige Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Inhalte ausgehender Datendateien: Syntax und Parameter {#outbound-contents-syntax}

Beschreibt die erforderlichen Felder, Syntax und Konventionen zum Organisieren von Informationen in einer ausgehenden Datendatei. Formatieren Sie Ihre Daten entsprechend diesen Spezifikationen.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Die Stilelemente (`monospaced text`, *Kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument weisen auf Codeelemente und Optionen hin. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

### Syntax

Die Felder in der Datendatei werden in der folgenden Reihenfolge angezeigt:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parameter

Die Tabelle listet Variablen auf, die den Inhalt einer Datendatei definieren.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>Eine eindeutige Benutzer-ID, die von <span class="keyword"> Audience Manager-</span> zugewiesen wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Trennen Sie die UUID- und Segmentdaten durch ein Leerzeichen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>Die Segment-ID, zu der ein Besucher gehört. Trennen Sie mehrere Segmente durch ein Komma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>Die Segment-ID, von der der Benutzer ausgeschlossen wurde. Trennen Sie mehrere Segmente durch ein Komma. Bei einer vollständigen Synchronisierung können Sie die entfernten Segmente ignorieren, da die Datendatei die vollständige Liste der aktuellen Segmente für den Benutzer enthält. In den meisten Fällen möchten Sie mehr über Segmente wissen, zu denen ein Benutzer gehört, als über die Segmente, aus denen er entfernt wurde. Siehe auch <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Name der ausgehenden Datendatei: Syntax und Beispiele </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiel: Grundlegendes Dateiformat

Eine ordnungsgemäß formatierte Datendatei könnte dem folgenden Beispiel ähneln. Dieser Dateieintrag gibt an, dass ein Benutzer für die Segmente 24, 26 und 27 qualifiziert ist. Bei Bedarf werden die `UUID`- und Segment-IDs durch ein Leerzeichen getrennt. Ein weiteres Leerzeichen trennt die Gruppen von Segment-IDs. In diesem Beispiel gehört ein Benutzer zu den Segmenten 24, 26 und 27. Sie wurden aus den Segmenten 25 und 28 entfernt.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
