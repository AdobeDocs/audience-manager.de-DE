---
description: Eine Datendatei enthält Impressionen, Klicks oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren und in den Berichten zur Zielgruppenoptimierung anzeigen. Formatieren Sie Ihre Datendateien gemäß diesen Spezifikationen in diesem Abschnitt.
seo-description: Eine Datendatei enthält Impressionen, Klicks oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren und in den Berichten zur Zielgruppenoptimierung anzeigen. Formatieren Sie Ihre Datendateien gemäß diesen Spezifikationen in diesem Abschnitt.
seo-title: Datendateien für Zielgruppenoptimierungsberichte
solution: Audience Manager
title: Datendateien für Zielgruppenoptimierungsberichte
uuid: c 19 eb 0 c 7-47 c 1-4 cdf -8 a 6 c-cd 15 fe 04 c 379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

Eine Datendatei enthält Impressionen, Klicks oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren und in den Berichten zur Zielgruppenoptimierung anzeigen. Formatieren Sie Ihre Datendateien gemäß diesen Spezifikationen in diesem Abschnitt.

## Überblick {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. Für diesen Prozess sind separate Dateien für Impressionen, Klicks und Konversionsdaten erforderlich. Mischen Sie diese Ereignisse nicht in einer einzelnen Datei.

Eine Datendatei muss von einer Metadatendatei begleitet werden. Der Inhalt der Metadatendatei stimmt mit Datendateiinformationen zu verwandten, menschen lesbaren Beschriftungen in den Berichtmenüs überein. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

Die folgende Syntax definiert die Struktur eines gut formatierten Datendateinamens. Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**Syntax:** <pre><code><i>Ereignistyp</i>_<i>yyyymmtt</i></code></pre>

In einem Dateinamen:

* Der Ereignistyp zeigt an, dass die Datei Impressionen, Klicks oder Konversionen enthält. Erstellen Sie für jeden Ereignistyp eine separate Datei.
* Ein Unterstrich trennt den Ereignistyp und einen Jahreszeitstempel.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

Geben Sie anhand dieser Anforderungen die Datendateien anhand ihres Inhalts wie folgt ein:

* Impressionsdaten: <pre><code>impressions_<i>yyyymmdd<i>.gz</code></pre>
* Klickdaten: <pre><code>clicks_<i>yyyymmdd</i>.gz</code></pre>
* Konversionsdaten: <pre><code>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

Die folgende Syntax definiert die Inhaltsstruktur in einer gut formatierten Datendatei. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**Syntax:** <pre><code><i>header label 1</i> | <i>header label 2</i> … <i>header label n</i> | <i>version</i></code></pre>

Im Dateiinhalt:

* Die Kopfzeilenbeschriftungen müssen in der Reihenfolge wie in der folgenden Tabelle angezeigt werden. Impressionen und Klicks verwenden dieselben Beschriftungen. Konvertierungsdateien enthalten zusätzliche Kopfzeilen.
* If you don't have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. Die aktuelle Version ist 1.1.
* Trennen Sie Dateiüberschriften und -inhalte mit dem nicht druckbaren ASCII 001-Zeichen. Wenn Sie ASCII 001 nicht verwenden können, trennen Sie die Header und Daten mit einem Tabulatortrennzeichen. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**Feldbeschriftungen**

In der folgenden Tabelle sind die Spaltenüberschriften für Ihre Datendatei aufgelistet und beschrieben. Bei Kopfzeilen muss die Groß- und Kleinschreibung beachtet werden und sie muss in der Tabelle als "Bestellt" erscheinen. Alle Datentypen sind Ganzzahlen (INT), wenn nicht anders angegeben.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Zeitstempel </p> </td> 
   <td colname="col2"> <p>Ein UTC-Datum und eine Uhrzeit für die Impression, Klicken oder Konversionsereignis. Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer-ID </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Die Datenquellen-ID oder der Integrationscode für Ihren Werbetreibenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Geschäftsentitäts-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampagnen-ID </p> </td> 
   <td colname="col2"> <p>Kampagnen-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>Creative-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>Site-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> Numerische Platzierungs-ID vom Anzeigen-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einfüge-Reihenfolge-ID </p> </td> 
   <td colname="col2"> <p>Einfübestell-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktic-ID </p> </td> 
   <td colname="col2"> <p>Taktik-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikale ID </p> </td> 
   <td colname="col2"> <p>ID für eine Branche oder Kategorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantität </p> </td> 
   <td colname="col2"> <p> Die Anzahl der in einem Konversionsereignis verkauften Artikel. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umsatz </p> </td> 
   <td colname="col2"> <p>Kauf oder andere Konversionsbeträge. Datentyp: Float. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sonstige Daten </p> </td> 
   <td colname="col2"> <p>URL der Konversions-Landingpage. Datentyp: Zeichenfolge. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ereignistyp </p> </td> 
   <td colname="col2"> <p>Konversionstyp. Gibt an, ob eine Konversion übereinstimmt oder nicht. Zu den Optionen zählen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Klicken Sie auf </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Nicht zugewiesen oder unbekannt </li> 
    </ul> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Eine erforderliche Versionsnummer, die am Ende jeder Zeile in einer Impression-, Klick- oder Konversionsdatendatei angezeigt wird. Die aktuelle Version ist 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. In diesem Abschnitt finden Sie Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.

**Auslieferungspfadsyntax und Beispiele**

Die Daten werden in einem separaten Namespace für jeden Kunden in einem Amazon S 3-Ordner gespeichert. Der Dateipfad folgt der unten aufgeführten Syntax. Note, *italics* indicates a variable placeholder. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

**Syntax:** <pre><code>…/log_ incapture/pid = <i>AAM ID<i>/dpid = <i>d_ src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

Die folgende Tabelle definiert alle diese Elemente in einem Dateibereitstellungspfad.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateiparameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ incapture/</code> </p> </td> 
   <td colname="col2"> <p>Dies ist der Anfang des Ordnerspeicherpfades. Wenn alles eingerichtet ist, erhalten Sie den vollständigen Pfad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignisaufruf weitergegeben wird. Es identifiziert die Agentur, von der die Daten stammen, und verknüpft diese mit einer unterstützenden Metadatendatei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Protokolle</code> </p> </td> 
   <td colname="col2"> <p> Ein Ordner mit höherer Ebene für Datendateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>Dateityp</i>_<i>yyyymmtt</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Dateitypname, der angibt, welche Art von Daten es enthält und einen Bereitstellungszeitstempel. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel für Upload-Pfad und Dateiname**

Wenn Sie eine Datei hochladen, sieht der Pfad wie folgt aus:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Dateiverarbeitungszeiten und -updates**

Datendateien werden viermal täglich verarbeitet.

Um Ihre Daten zu aktualisieren, senden Sie eine Datei, die alle Impressionen, Klicks oder Konversionen für einen bestimmten Tag enthält. In diesem Fall ist ein Tag der 24-Stunden-Zeitraum von einem Mitternacht bis zum nächsten. Es empfiehlt sich, die UTC-Zeit zur Definition Ihres Tagesintervalls zu verwenden.

## Nächste Schritte {#next-steps}

Überprüfen Sie die Anforderungen für die Benennung und Erstellung von Metadatendateien. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
