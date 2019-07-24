---
description: Beschreibt die erforderlichen Felder, Syntax und Konventionen zum Benennen einer ausgehenden Datendatei.
seo-description: Beschreibt die erforderlichen Felder, Syntax und Konventionen zum Benennen einer ausgehenden Datendatei.
seo-title: Syntax und Beispiele für ausgehende Datendateiname
solution: Audience Manager
title: Syntax und Beispiele für ausgehende Datendateiname
uuid: effdcaf 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Outbound Data File Name: Syntax and Examples{#outbound-data-file-name-syntax-and-examples}

Beschreibt die erforderlichen Felder, Syntax und Konventionen zum Benennen einer ausgehenden Datendatei.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax and File Name Elements {#syntax-file-name}

Ausgehende Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

```
SYNC-TYPE_ DID_ MASTER-DPID_ [PID-ALIAS]_ SYNC-MODE_ TIMESTAMP[- SPLIT_NUMBER].sync[.gz]
```

### Parameter

Die Tabelle definiert die Elemente in einem ausausgehenden Datendateinamen.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateinamenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNCHRONISIERUNG </i></code> </p> </td> 
   <td colname="col2"> <p>Bezieht sich auf die Datenübertragungsmethoden. Zu den Übertragungsmethoden gehören: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Übertragen mit SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S 3 </span> - Übertragen auf <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>Ziel-ID. </p> <p>In <span class="keyword"> Audience Manager </span>, a destination is the instance of the integration where you can map your targetable segments. Kunden können je nach Geschäftsanforderung über mehrere Ziele verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER-DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Datenprovider oder Datenquellen-ID. Diese ID identifiziert den Typ der Benutzer-ID im Dateiinhalt. Die meisten gängigen Benutzer-ID-Schlüssel sind: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">Anbieter-ID - Drittanbieter-IDs (Web/Cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID-ALIAS </i></code> </p> </td> 
   <td colname="col2"> Die Kundenkennung der Drittanbieterplattform. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNCHRONISIERUNG </i></code> </p> </td> 
   <td colname="col2"> <p>Der Synchronisierungsmodus ist ein Makro-Platzhalter, der dem Dateinamen je nach Synchronisierungstyp eine Beschriftung hinzufügt. Synchronisierungstypen sind vollständig und inkrementell. They'll appear in the file name as <code> iter </code> or <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Gibt eine "iterative" oder inkrementelle Synchronisierung an. Eine inkrementelle Datei enthält nur neue Daten, die seit der letzten Synchronisierung erfasst wurden. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> voll </code>: Gibt eine vollständige Synchronisierung an. Eine vollständig synchronisierte Datei enthält alte Daten und alle neuen Daten, die seit der letzten Synchronisierung erfasst wurden. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Ein 13-stelliger UNIX-Zeitstempel in Millisekunden in der UTC-Zeitzone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [<code><i>-SPLIT_NUMBER </i></code>] </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Identifiziert den Teil einer Datei, der in mehrere Teile aufgeteilt wurde, um die Verarbeitungszeiten zu verbessern. Die Zahl gibt an, zu welchem Teil der Originaldatei die Daten gehören. </p> <p>Die Originaldatei hat keine Unterteilungsnummer. Die erste geteilte Datei beginnt mit 1. Siehe Beispiele unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP-Komprimierung. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

### Szenario 1

Files sent over to an [!DNL Amazon S3] location, with *`PID-ALIAS="XYZCustomer"`* and with [!DNL Google Advertiser IDs] in the file content.

Z.B. inkrementelle Dateien:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-1.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-10.sync.gz </code> </li> 
</ul>

Z.B. vollständige Dateien:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000-1.sync.gz </code> </li> 
</ul>

### Szenario 2

Files sent over to [!DNL FTP] location, without *`PID-ALIAS`* and with [!DNL Apple Advertiser IDs] in the file content:

Z.B. inkrementelle Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000-1.sync.gz </code> </li> 
</ul>

Z.B. vollständige Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000-1.sync.gz </code> </li> 
</ul>

**Szenario 3**: Dateien, die an [!DNL FTP] den Speicherort gesendet werden, mit *`PID-ALIAS="XYZCustomer"`* und mit Benutzer-ID des Drittanbieters im Dateiinhalt ( *`Vendor ID=45454`*):

Z.B. inkrementelle Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-1.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-10.sync.gz </code> </li> 
</ul>

Z.B. vollständige Dateien:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200-1.sync.gz </code> </li> 
</ul>

## Outbound Data File Contents: Syntax and Parameters {#outbound-contents-syntax}

Beschreibt die erforderlichen Felder, die Syntax und die Konventionen, mit denen Informationen in einer ausgehenden Datendatei organisiert werden. Formatieren Sie Ihre Daten gemäß diesen Spezifikationen.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

### Syntax

Felder in der Datendatei werden in dieser Reihenfolge angezeigt:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parameter

In der Tabelle sind Variablen aufgelistet, die den Inhalt einer Datendatei definieren.

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
   <td colname="col2"> <p>A unique user ID assigned by <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; SPACE &gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Die UUID und Segmentdaten durch einen Leerzeichen trennen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>Die Segment-ID, zu der ein Besucher gehört. Trennen Sie mehrere Segmente durch ein Komma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_ SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>Die Segment-ID, von der der Benutzer disqualifiziert wurde. Trennen Sie mehrere Segmente durch ein Komma. Mit einer vollständigen Synchronisierung können Sie die entfernten Segmente ignorieren, da die Datendatei die vollständige Liste der aktuellen Segmente für den Benutzer enthält. In der Regel möchten Sie wissen, zu welchen Segmenten ein Benutzer gehört, und nicht zu denen, aus denen er entfernt wurde. See also <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Outbound Data File Name: Syntax and Examples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiel: Basisdateiformat

Eine ordnungsgemäß formatierte Datendatei könnte dem folgenden Beispiel ähnlich aussehen. Dieser Dateieintrag zeigt an, dass sich ein Benutzer für Segmente 24, 26 und 27 qualifiziert. As required, a space separates the `UUID` and segment IDs. Ein anderer Leerraum trennt die Sätze der Segment-IDs. In diesem Beispiel gehört ein Benutzer zu Segmenten 24, 26 und 27. Sie wurden aus den Segmenten 25 und 28 entfernt.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
