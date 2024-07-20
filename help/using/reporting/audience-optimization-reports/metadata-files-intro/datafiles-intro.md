---
description: Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren und in den Audience Optimization-Berichten und für ausführbare Protokolldateien verwenden. Formatieren Sie Ihre Datendateien gemäß den Spezifikationen in diesem Abschnitt.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Datendateien für Audience Optimization-Berichte und ausführbare Protokolldateien
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Datendateien für Audience Optimization-Berichte und ausführbare Protokolldateien {#data-files-for-audience-optimization-reports}

Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren, um sie in den [Audience Optimization-Berichten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) anzuzeigen und Eigenschaften mithilfe der Daten über [ausführbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md) zu erstellen. Formatieren Sie Ihre Datendateien gemäß den in diesem Abschnitt beschriebenen Spezifikationen.

## Überblick {#overview}

Mit einer ordnungsgemäß benannten und formatierten Datendatei können Sie Impressions-, Klick- oder Konversionsdaten in die [Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) importieren. Dies ist nützlich, wenn Sie mit einem Partner arbeiten, der nicht in [!DNL Audience Manager] integriert ist, und mit dessen Daten in dieser Report Suite arbeiten möchten. Dieser Prozess erfordert separate Dateien für Impression-, Klick- und Konversionsdaten. Mischen Sie diese Ereignisse nicht in einer Datei.

Eine Datendatei muss von einer Metadatendatei begleitet sein. Der Inhalt der Metadatendatei stimmt mit den Datendateiinformationen mit den zugehörigen, für Menschen lesbaren Bezeichnungen in den Berichtmenüs überein. Weitere Informationen finden Sie unter [Überblick und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Namenskonventionen für Datendateien {#naming-conventions}

Die folgende Syntax definiert die Struktur eines korrekt formatierten Datendateinamens. Hinweis: *kursiv* gibt einen Variablenplatzhalter an, der sich je nach Dateiinhalt ändert.

**Syntax:** <pre><code><i>Ereignistyp</i>_<i>yyymmdd</i></code></pre>

Dateiname:

* Der Ereignistyp gibt an, dass die Datei Impressionen, Klicks oder Konversionen enthält. Erstellen Sie für jeden Ereignistyp eine separate Datei.
* Ein Unterstrich trennt den Ereignistyp und einen Jahresmonatszeitstempel.
* Komprimieren Sie vor dem Hochladen Ihre Dateien mit gzip und speichern Sie sie mit der Dateierweiterung `.gz` .

Benennen Sie Ihre Datendateien anhand dieser Anforderungen anhand ihres Inhalts wie folgt:

* Impressionsdaten: <pre><code>impressions_<i>yyymmdd</i>.gz</code></pre>
* Klickdaten: <pre><code>clicks_<i>yyymmdd</i>.gz</code></pre>
* Konversionsdaten: <pre><code>conversions_<i>yyymmdd</i>.gz</code></pre>

## Inhaltsformat für Datendateien {#content-format}

Die folgende Syntax definiert die Inhaltsstruktur in einer korrekt formatierten Datendatei. Hinweis: *kursiv* gibt einen Variablenplatzhalter an und wird in einer eigentlichen Datendatei durch eine Beschriftung ersetzt.

**Syntax:** <pre><code><i>Kopfzeilenbeschriftung 1</i> | <i>Kopfzeilenbezeichnung 2</i> ... <i>Kopfzeilenbeschriftung n</i> | <i>version</i></code></pre>

Im Dateiinhalt:

* Die Kopfzeilenbeschriftungen müssen in der Reihenfolge angezeigt werden, wie in der Tabelle unten dargestellt. Impressionen und Klicks verwenden dieselben Bezeichnungen. Konvertierungsdateien enthalten zusätzliche Header.
* Wenn Sie keine Daten für eine bestimmte Spalte haben, füllen Sie dieses Feld mit einem &quot;`-1`&quot;.

* Die Dateien *müssen* mit einer Versionsnummer enden. Die aktuelle Version ist 1.1.
* Trennen Sie Dateiüberschriften und -inhalte durch das nicht druckbare ASCII-001-Zeichen. Wenn Sie ASCII 001 nicht verwenden können, trennen Sie die Kopfzeilen und Daten durch ein Tabulatortrennzeichen. Da es sich hierbei um nicht druckbare Zeichen handelt, zeigt das oben stehende Syntaxbeispiel nur das senkrechte Strich `"|"` für Anzeigezwecke.

**Feldbezeichnungen**

In der folgenden Tabelle sind die Spaltenüberschriften für Ihre Datendatei aufgeführt und beschrieben. Bei Kopfzeilen wird zwischen Groß- und Kleinschreibung unterschieden und sie müssen in der Tabelle in der Reihenfolge angezeigt werden. Sofern nicht anders angegeben, sind alle Datentypen Ganzzahlen (INT).

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
   <td colname="col2"> <p>Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversionsereignis. Verwenden Sie das Format <code> yyyy-MM-dd HH:mm:ss</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Ihre ID für einen Site-Besucher, auch als <span class="term"> eindeutige Benutzer-ID des Datenanbieters</span> oder DPUUID bezeichnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Die Datenquellen-ID oder der Integrationscode für Ihren Advertiser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Kennung der Geschäftseinheit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
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
   <td colname="col1"> <p>Platzierungs-ID </p> </td> 
   <td colname="col2"> <p> Numerische Platzierungs-ID vom Anzeigen-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>Einfügebestellkennung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>Tactic ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal-ID </p> </td> 
   <td colname="col2"> <p>Kennung für einen vertikalen Markt oder eine Kategorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantität </p> </td> 
   <td colname="col2"> <p> Die Anzahl der bei einem Konversionsereignis verkauften Artikel. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umsatz </p> </td> 
   <td colname="col2"> <p>Kauf- oder anderer Konversionsbetrag. Datentyp: Gleitkommazahl. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sonstige-Daten </p> </td> 
   <td colname="col2"> <p>URL der Konversions-Landingpage. Datentyp: Zeichenfolge. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ereignistyp </p> </td> 
   <td colname="col2"> <p>Konvertierungstyp. Gibt an, ob eine Konvertierung übereinstimmt oder nicht. Zu den Optionen zählen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Klicken Sie </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Nicht zugeordnet oder unbekannt </li> 
    </ul> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Eine erforderliche Versionsnummer, die am Ende jeder Zeile in einer Impression-, Klick- oder Konversionsdatendatei angezeigt wird. Die aktuelle Version ist 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bereitstellungsmethoden für Datendateien {#delivery-methods}

Laden Sie Ihre Impression-, Klick- oder Konversionsdatendateien in ein Amazon S3-Verzeichnis für Ihr [!DNL Audience Manager] -Konto hoch. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.

>[!IMPORTANT]
>
> Wenden Sie sich an Ihren Audience Manager-Berater oder die Kundenunterstützung, um zu beginnen und ein [!DNL Amazon S3] -Verzeichnis für Ihre Datendateien einzurichten.

**Syntax und Beispiele für Bereitstellungspfad**

Die Daten werden in einem separaten Namespace für jeden Kunden in einem [!DNL Amazon S3] -Verzeichnis gespeichert. Der Dateipfad folgt der unten dargestellten Syntax. Hinweis: *kursiv* gibt einen Variablenplatzhalter an. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

**Syntax:** <pre><code>../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>Dateityp</i>_<i>yyymmdd</i></code></pre>

Die folgende Tabelle definiert jedes dieser Elemente in einem Dateibereitstellungspfad.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateiparameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Dies ist der Anfang des Ordnerspeicherpfads. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält Ihre <span class="keyword"> Audience Manager</span>-Kunden-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignisaufruf übergeben wird. Er identifiziert die Agentur, aus der die Daten stammen, und verknüpft diese Daten mit einer unterstützenden Metadatendatei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Ein Ordner auf höherer Ebene für Datendateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Dateiname, der angibt, welche Art von Daten er enthält, und ein Versandzeitstempel. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel-Upload-Pfad und Dateiname**

Wenn Sie eine Datei hochladen, sieht der Pfad in etwa wie folgt aus:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Zeiten und Aktualisierungen der Dateiverarbeitung**

Datendateien werden viermal täglich in regelmäßigen Abständen verarbeitet.

Um Ihre Daten zu aktualisieren, senden Sie eine Datei, die alle Impressionen, Klicks oder Konversionen für einen bestimmten Tag enthält. In diesem Fall ist ein Tag der 24-Stunden-Zeitraum von einem Mitternacht zum nächsten. Als Best Practice empfiehlt sich möglicherweise die Verwendung der UTC-Zeit, um Ihr Tagesintervall zu definieren.

## Nächste Schritte {#next-steps}

Überprüfen Sie die Anforderungen zum Benennen und Erstellen von Metadatendateien. Informationen zu den ersten Schritten finden Sie unter [Überblick und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
