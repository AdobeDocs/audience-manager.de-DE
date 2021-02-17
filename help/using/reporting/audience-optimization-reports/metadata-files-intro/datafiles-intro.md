---
description: Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren und in den Berichten "Audience Optimization"und für "Verfolgbare Protokolldateien"verwenden. Formatieren Sie Ihre Datendateien gemäß den Spezifikationen in diesem Abschnitt.
seo-description: Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren und in den Berichten "Audience Optimization"und für "Verfolgbare Protokolldateien"verwenden. Formatieren Sie Ihre Datendateien gemäß den Spezifikationen in diesem Abschnitt.
seo-title: Datendateien für Berichte zur Zielgruppenoptimierung und ausführbare Protokolldateien
solution: Audience Manager
title: Datendateien für Berichte zur Zielgruppenoptimierung und ausführbare Protokolldateien
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: log files
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 5%

---


# Datendateien für Berichte zur Zielgruppenoptimierung und ausführbare Protokolldateien {#data-files-for-audience-optimization-reports}

Eine Datendatei enthält Impressions-, Klick- oder Konversionsdaten. Bei ordnungsgemäßer Formatierung können Sie diese Daten in Audience Manager importieren, um sie in den [Audience Optimizationen-Berichten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) Ansicht und Eigenschaften mithilfe der Daten über [Verfolgbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md) zu erstellen. Formatieren Sie Ihre Datendateien gemäß den Spezifikationen in diesem Abschnitt.

## Überblick {#overview}

Mit einer ordnungsgemäß benannten und formatierten Datendatei können Sie Impressions-, Klick- oder Konvertierungsdaten in die [Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) importieren. Dies ist nützlich, wenn Sie mit einem Partner arbeiten, der nicht mit [!DNL Audience Manager] integriert ist und mit dessen Daten in dieser Report Suite arbeiten möchten. Dieser Prozess erfordert separate Dateien für Impressions-, Klick- und Konvertierungsdaten. Mischen Sie diese Ereignisse nicht in einer einzigen Datei.

Eine Datendatei muss von einer Metadatendatei begleitet sein. Der Inhalt der Metadatendatei stimmt mit den Datendateiinformationen mit den entsprechenden, für Menschen lesbaren Beschriftungen in den Berichtmenüs überein. Weitere Informationen finden Sie unter [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Namenskonventionen für Datendateien {#naming-conventions}

Die folgende Syntax definiert die Struktur eines gut formatierten Datendateinamens. Hinweis: *kursiv* gibt einen variablen Platzhalter an, der sich je nach Dateiinhalt ändert.

**Syntax:** <pre><i>Ereignistyp</i>_<i>yyymmdd</i></code></pre>

In einem Dateinamen:

* Der Ereignistyp gibt an, dass die Datei Impressionen, Klicks oder Konvertierungen enthält. Erstellen Sie für jeden Ereignistyp eine separate Datei.
* Ein Unterstrich trennt den Ereignistyp und einen Datums-Zeitstempel für ein Jahr.
* Komprimieren Sie Ihre Dateien vor dem Hochladen mit gzip und speichern Sie sie mit der Dateierweiterung `.gz`.

Benennen Sie Ihre Datendateien unter Berücksichtigung dieser Anforderungen nach ihrem Inhalt wie folgt:

* Impressionsdaten: <pre>impressions_<i>yyymmdd</i>.gz</code></pre>
* Klickdaten: <pre>clicks_<i>yyymmdd</i>.gz</code></pre>
* Konversionsdaten: <pre>conversions_<i>yyymmdd</i>.gz</code></pre>

## Inhaltsformat für Datendateien {#content-format}

Die folgende Syntax definiert die Inhaltsstruktur in der gut formatierten Datendatei. Hinweis: *italics* gibt einen Variablenplatzhalter an und wird durch eine Beschriftung in einer tatsächlichen Datendatei ersetzt.

**Syntax:** <pre><i>Kopfzeilenbeschriftung 1</i> |  <i>Kopfzeilenbeschriftung 2</i> ...  <i>Kopfzeilenbeschriftung n</i> |  <i>Version</i></code></pre>

Inhalt der Datei:

* Die Kopfzeilenbeschriftungen müssen in der Reihenfolge wie in der folgenden Tabelle angezeigt werden. Impressionen und Klicks verwenden dieselben Bezeichnungen. Konvertierungsdateien enthalten zusätzliche Header.
* Wenn Sie keine Daten für eine bestimmte Spalte haben, füllen Sie dieses Feld mit einem `-1`.

* Die Dateien *müssen mit einer Versionsnummer enden.* Die aktuelle Version ist 1.1.
* Trennen Sie Datei-Kopfzeilen und -Inhalte mit dem nicht druckbaren ASCII-Zeichen 001. Wenn Sie ASCII 001 nicht verwenden können, trennen Sie die Kopfzeilen und Daten durch ein Tabulatortrennzeichen. Da es sich hierbei um nicht druckbare Zeichen handelt, zeigt das Syntaxbeispiel oben nur eine Pipe `"|"` für Anzeigezwecke.

**Feldbezeichnungen**

In der folgenden Tabelle sind die Spaltenüberschriften für die Datendatei Listen aufgeführt. Bei Kopfzeilen wird die Groß-/Kleinschreibung beachtet und sie müssen in der Tabelle in der richtigen Reihenfolge angezeigt werden. Sofern nicht anders angegeben, sind alle Datentypen Ganzzahlen (INT).

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
   <td colname="col2"> <p>Ein UTC-Datum und eine UTC-Uhrzeit für das Impression-, Klick- oder Konversions-Ereignis. Verwenden Sie das Format <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Benutzer-ID </p> </td> 
   <td colname="col2"> <p>Ihre ID für einen Site-Besucher, auch bekannt als <span class="term"> Datenanbieter Unique User ID</span> oder DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Die Datenquellen-ID oder der Integrationscode für Ihren Advertiser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Geschäftseinheit-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampagne-ID </p> </td> 
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
   <td colname="col2"> <p>Einfügebestellungs-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>Tactic ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal-ID </p> </td> 
   <td colname="col2"> <p>ID für eine Branche oder Kategorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantität </p> </td> 
   <td colname="col2"> <p> Die Anzahl der in einem Konversions-Ereignis verkauften Artikel. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umsatz </p> </td> 
   <td colname="col2"> <p>Kauf- oder sonstiger Umrechnungsbetrag. Datentyp: Float. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>other-data </p> </td> 
   <td colname="col2"> <p>URL der Konversions-Landingpage. Datentyp: Zeichenfolge. </p> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ereignis-Typ </p> </td> 
   <td colname="col2"> <p>Konvertierungstyp Gibt an, ob eine Konvertierung übereinstimmt oder nicht. Zu den Optionen zählen: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Klicken </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Nicht zugeordnet oder unbekannt </li> 
    </ul> <p> <i>Nur für Konversionsdatendateien.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Eine erforderliche Versionsnummer, die am Ende jeder Zeile in einer Impression-, Klick- oder Konvertierungsdatendatei angezeigt wird. Die aktuelle Version ist 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Versand-Methoden für Datendateien {#delivery-methods}

Laden Sie Ihre Impressions-, Klick- oder Konvertierungsdatendateien in einen Amazon S3-Ordner für Ihr [!DNL Audience Manager]-Konto hoch. Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.

>[!IMPORTANT]
>
> Wenden Sie sich an Ihren Audience Manager- oder Kundendienst, um zu beginnen und einen [!DNL Amazon S3]-Ordner für Ihre Datendateien einzurichten.

**Versand-Pfadsyntax und Beispiele**

Die Daten werden in einem separaten Namensraum für jeden Kunden in einem [!DNL Amazon S3]-Verzeichnis gespeichert. Der Dateipfad folgt der unten stehenden Syntax. Hinweis: *kursiv* gibt einen Variablenplatzhalter an. Andere Elemente sind Konstanten oder Schlüssel und bleiben unverändert.

**Syntax:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>Dateityp</i>_<i>yyyyymmdd</i></code></pre>

In der folgenden Tabelle werden diese Elemente in einem Dateipfad definiert.

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
   <td colname="col2"> <p>Dies ist der Beginn des Ordnerpfads für die Datenspeicherung. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält Ihre <span class="keyword"> Audience Manager</span> Kunden-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignis-Aufruf übergeben wird. Er identifiziert die Agentur, von der die Daten stammen, und verknüpft diese Daten mit einer unterstützenden Metadatendatei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Ein Ordner auf höherer Ebene für Datendateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Dateitypname, der angibt, welche Art von Daten er enthält, und ein Versand-Zeitstempel. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispielpfad und Dateiname für das Hochladen**

Wenn Sie eine Datei hochladen, sieht der Pfad wie folgt aus:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Dateiverarbeitungszeiten und -aktualisierungen**

Datendateien werden in regelmäßigen Abständen viermal am Tag verarbeitet.

Um Ihre Daten zu aktualisieren, senden Sie eine Datei, die alle Impressionen, Klicks oder Konversionen für einen bestimmten Tag enthält. In diesem Fall ist ein Tag der 24-Stunden-Zeitraum von einer Mitternacht zur nächsten. Als Best Practice sollten Sie die UTC-Zeit verwenden, um Ihr Tagesintervall zu definieren.

## Nächste Schritte {#next-steps}

Überprüfen Sie die Anforderungen für die Benennung und Erstellung von Metadatendateien. Beginnen Sie mit [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
