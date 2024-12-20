---
description: Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Wenn Sie richtig formatiert sind, können Sie diese Daten in den Audience Manager importieren und in den Audience Optimization-Berichten und für verwertbare Protokolldateien verwenden. Formatieren Sie Ihre Datendateien entsprechend den Spezifikationen in diesem Abschnitt.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Datendateien zum Audience Optimization von Berichten und verwertbaren Protokolldateien
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Datendateien zum Audience Optimization von Berichten und verwertbaren Protokolldateien {#data-files-for-audience-optimization-reports}

Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Wenn Sie richtig formatiert sind, können Sie diese Daten in den Audience Manager importieren, um sie in den [Audience Optimization-Berichten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) anzuzeigen und Eigenschaften mithilfe der Daten über &quot;[ Protokolldateien“ ](/help/using/integration/media-data-integration/actionable-log-files.md). Formatieren Sie Ihre Datendateien entsprechend den Spezifikationen in diesem Abschnitt.

## Überblick {#overview}

Mit einer ordnungsgemäß benannten und formatierten Datendatei können Sie Impression-, Klick- oder Konversionsdaten in die [Audience Optimization-Berichte importieren](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Dies ist nützlich, wenn Sie mit einem Partner arbeiten, der nicht mit [!DNL Audience Manager] integriert ist und Sie mit dessen Daten in dieser Report Suite arbeiten möchten. Dieser Prozess erfordert separate Dateien für Impressions-, Klick- und Konversionsdaten. Diese Ereignisse nicht in einer Datei mischen.

Zu einer Datendatei muss eine Metadatendatei gehören. Die Inhalte der Metadatendateien stimmen mit den Datendateiinformationen in Bezug auf menschenlesbare Kennzeichnungen in den Berichtsmenüs überein. Weitere Informationen finden Sie unter [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Benennungskonventionen für Datendateien {#naming-conventions}

Die folgende Syntax definiert die Struktur eines wohlgeformten Datendateinamens. Hinweis: *Kursiv* gibt einen Variablenplatzhalter an, der sich je nach Dateiinhalt ändert.

**Syntax:** <pre><code><i>Ereignistyp</i>_<i>JJJMMTT</i></code></pre>

In einem Dateinamen:

* Der Ereignistyp gibt an, dass die Datei Impressionen, Klicks oder Konversionen enthält. Erstellen Sie für jeden Ereignistyp eine separate Datei.
* Ein Unterstrich trennt den Ereignistyp und einen Jahr-Monat-Zeitstempel.
* Komprimieren Sie Ihre Dateien vor dem Hochladen mit gzip und speichern Sie sie mit der Dateierweiterung `.gz`.

Benennen Sie Ihre Datendateien angesichts dieser Anforderungen anhand ihres Inhalts wie folgt:

* Impressionsdaten: <pre><code>impressions_<i>yyymmdd</i>.gz</code></pre>
* Klickdaten: <pre><code>clicks_<i>yyymmdd</i>.gz</code></pre>
* Konvertierungsdaten: <pre><code>conversion_<i>yyymmdd</i>.gz</code></pre>

## Inhaltsformat für Datendateien {#content-format}

Die folgende Syntax definiert die Inhaltsstruktur in einer wohlgeformten Datendatei. Beachten Sie *dass* einen Variablenplatzhalter angibt und in einer Datendatei durch eine Beschriftung ersetzt wird.

**Syntax:** <pre><code><i>Kopfzeilenbeschriftung 1</i> | <i>Kopfzeilenbeschriftung 2</i> … <i>Kopfzeilenbeschriftung N</i> | <i>version</i></code></pre>

Im Dateiinhalt:

* Die Kopfzeilenbeschriftungen müssen in der in der folgenden Tabelle angegebenen Reihenfolge angezeigt werden. Impressionen und Klicks verwenden dieselben Beschriftungen. Konvertierungsdateien enthalten zusätzliche Header.
* Wenn Sie keine Daten für eine bestimmte Spalte haben, füllen Sie dieses Feld mit einer `-1`.

* Dateien *müssen* mit einer Versionsnummer enden. Die aktuelle Version ist 1.1.
* Trennen Sie Dateikopfzeilen und -inhalte durch das nicht druckbare ASCII 001-Zeichen. Wenn Sie ASCII 001 nicht verwenden können, trennen Sie die Kopfzeilen und Daten mit einem Tabulatortrennzeichen. Da es sich hierbei um nicht druckbare Zeichen handelt, zeigt das obige Syntaxbeispiel nur für Anzeigezwecke einen `"|"`.

**Feldbezeichnungen**

In der folgenden Tabelle sind die Spaltenüberschriften für Ihre Datendatei aufgeführt und beschrieben. Bei Kopfzeilen wird zwischen Groß- und Kleinschreibung unterschieden und sie müssen in der Tabelle in der Reihenfolge angezeigt werden. Alle Datentypen sind Ganzzahlen (INT), sofern nicht anders angegeben.

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
   <td colname="col2"> <p>Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversionsereignis. Verwenden Sie das <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer-ID </p> </td> 
   <td colname="col2"> <p>Ihre ID für einen Site-Besucher, auch bekannt als eindeutige Benutzer-ID des <span class="term">-Datenanbieters </span> DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Die Datenquellen-ID oder der Integrations-Code für Ihren Advertiser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Kennung der Geschäftseinheit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>campaign-ID </p> </td> 
   <td colname="col2"> <p>Kampagnen-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>creative-id </p> </td> 
   <td colname="col2"> <p>Kreativ-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>site-id </p> </td> 
   <td colname="col2"> <p>Site-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>placement-id </p> </td> 
   <td colname="col2"> <p> Numerische Platzierungs-ID vom Anzeigen-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>insertion-order-id </p> </td> 
   <td colname="col2"> <p>ID des Einfügeauftrags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TACTIC-ID </p> </td> 
   <td colname="col2"> <p>Taktische ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>vertical-id </p> </td> 
   <td colname="col2"> <p>ID für eine Branche oder vertikale Kategorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantität </p> </td> 
   <td colname="col2"> <p> Die Anzahl der in einem Konversionsereignis verkauften Elemente. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umsatz </p> </td> 
   <td colname="col2"> <p>Kauf- oder anderer Konversionsbetrag. Datentyp: float. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Other-Data </p> </td> 
   <td colname="col2"> <p>URL der Konversions-Landingpage. Datentyp: Zeichenfolge. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ereignistyp </p> </td> 
   <td colname="col2"> <p>Konvertierungstyp Gibt an, ob eine Konversion abgeglichen wird oder nicht. Zu den Optionen zählen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Klicken </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Nicht zugeordnet oder unbekannt </li> 
    </ul> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Eine erforderliche Versionsnummer, die am Ende jeder Zeile in einer Impressions-, Klick- oder Konversionsdatendatei angezeigt wird. Die aktuelle Version ist 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bereitstellungsmethoden für Datendateien {#delivery-methods}

Laden Sie Ihre Impressions-, Klick- oder Konversionsdatendateien für Ihr [!DNL Audience Manager]-Konto in ein Amazon S3-Verzeichnis hoch. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.

>[!IMPORTANT]
>
> Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um zu beginnen und ein [!DNL Amazon S3] für Ihre Datendateien einzurichten.

**Syntax und Beispiele für Versandpfade**

Die Daten werden für jeden Kunden in einem separaten Namespace in einem [!DNL Amazon S3] Verzeichnis gespeichert. Der Dateipfad folgt der unten gezeigten Syntax. Hinweis: *Kursiv* gibt einen Variablenplatzhalter an. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

**Syntax:** <pre><code>…/log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>Dateityp</i>_<i>JJJJMMTT</i></code></pre>

In der folgenden Tabelle werden diese Elemente in einem Dateibereitstellungspfad definiert.

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
   <td colname="col2"> <p>Dies ist der Beginn des Speicherpfads für das Verzeichnis. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält Ihren <span class="keyword"> Audience Manager </span> Kunden-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignisaufruf übergeben wird. Sie identifiziert die Agentur, von der die Daten stammen, und verknüpft diese Daten mit einer unterstützenden Metadatendatei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Ein übergeordnetes Verzeichnis für Datendateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Dateitypname, der angibt, welche Art von Daten er enthält, und einen Versandzeitstempel. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel-Upload-Pfad und Dateiname**

Wenn Sie eine Datei hochladen, sieht der Pfad in etwa wie folgt aus:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Dateiverarbeitungszeiten und -aktualisierungen**

Datendateien werden viermal täglich in regelmäßigen Abständen verarbeitet.

Um Ihre Daten zu aktualisieren, senden Sie eine -Datei, die alle Impressionen, Klicks oder Konversionen für einen bestimmten Tag enthält. In diesem Fall ist ein Tag der 24-Stunden-Zeitraum von einer Mitternacht zur nächsten. Als Best Practice empfiehlt sich die Verwendung der UTC-Zeit, um das Tagesintervall festzulegen.

## Nächste Schritte {#next-steps}

Überprüfen Sie die Anforderungen für das Benennen und Erstellen von Metadatendateien. Informationen zu den ersten Schritten finden Sie unter [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
