---
description: Grundlegende Informationen zu CDF-Dateien (Customer Data Feed) und Anweisungen zum Einstieg. Beginnen Sie hier, wenn Sie an CDF-Dateien interessiert sind oder einfach mehr Informationen benötigen.
keywords: Daten von Zweitanbietern;Daten von Zweitanbietern;Daten von Zweitanbietern
seo-description: Grundlegende Informationen zu CDF-Dateien (Customer Data Feed) und Anweisungen zum Einstieg. Beginnen Sie hier, wenn Sie an CDF-Dateien interessiert sind oder einfach mehr Informationen benötigen.
seo-title: Kundendatenfeeds
solution: Audience Manager
title: Kundendatenfeeds
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
translation-type: tm+mt
source-git-commit: c206246a4a586d1148c18e0bce734d07963a85f6

---


# Kundendatenfeeds {#customer-data-feeds}

Grundlegende Informationen zu [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) Dateien und Anleitungen zum Einstieg. Beginnen Sie hier, wenn Sie an [!UICONTROL CDF] Dateien interessiert sind oder einfach mehr Informationen benötigen.

## Dateiinhalt und Zweck {#file-contents-purpose}

<!-- cdf-intro.xml -->

Eine [!UICONTROL CDF] Datei enthält dieselben Daten, die ein [!DNL Audience Manager] Ereignisaufruf ( `/event`) an unsere Server sendet. Dazu gehören Daten wie Benutzer-IDs, Eigenschaften-IDs, Segment-IDs und alle anderen Parameter, die von einem Ereignisaufruf erfasst werden. Interne [!DNL Audience Manager] Systeme verarbeiten Ereignisdaten in einer [!UICONTROL CDF] Datei, deren Inhalt in Felder unterteilt ist, die in einer bestimmten Reihenfolge angezeigt werden. [!DNL Audience Manager] versucht, [!UICONTROL CDF] Dateien stündlich zu generieren und speichert sie in einem sicheren, kundenspezifischen Behälter auf einem [!DNL Amazon S3] Server. Wir stellen diese Dateien zur Verfügung, damit Sie mit [!DNL Audience Manager] Daten arbeiten können, die nicht den durch unsere Benutzeroberfläche festgelegten Beschränkungen unterliegen.

>[!NOTE]
>
>Sie sollten keine [!UICONTROL CDF] Dateien als Proxy verwenden, um den Seitenverkehr zu überwachen, Berichtsdiskrepanzen zu überwinden, Abrechnungen usw. vorzunehmen.

## Erste Schritte {#getting-started}

Es gibt keinen Selbstbedienungsprozess, um die [!UICONTROL CDF] Dateibereitstellung zu starten. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. Während der Implementierung wird Ihr [!DNL Audience Manager] Vertreter:

* Richten Sie den [!DNL Amazon S3] Speicherbehälter ein.
* Geben Sie Ihrem Dateispeicherbehälter schreibgeschützte [!DNL S3] Authentifizierungsberechtigungen an. Sie können keine Ordner und Dateien anderer Kunden anzeigen oder darauf zugreifen.

Dateibenachrichtigungen und [!UICONTROL CDF] -dateien werden in Ihrem [!DNL S3] Bucket angezeigt, sobald sie zum Download bereit sind. Sie sind für die Überwachung und das Herunterladen von Dateien aus Ihrem zugewiesenen [!DNL S3] Verzeichnis verantwortlich. Siehe Benachrichtigungen zur Verarbeitung von [Kundendaten-Feed-Dateien](#cdf-file-processing-notifications).

## Nächste Schritte {#next-steps}

Die folgenden Abschnitte und die häufig gestellten Fragen zum [Kundendatenfeed](../faq/faq-cdf.md) helfen Ihnen, sich mit diesem Dienst vertraut zu machen.

## Benutzerdaten-Feed-Inhalt definiert {#cdf-defined}

Listet die Datenelemente und Arrays in einer [!UICONTROL CDF] Datei in der Reihenfolge ihres Aussehens auf und definiert sie. Definitionen umfassen Datentypen, aber diese Informationen sind nicht Teil einer [!UICONTROL CDF] Datei.

## Definitionen {#definitions}

<!-- cdf-contents-defined.xml -->

Eine [!UICONTROL CDF] Datei enthält einige oder alle unten definierten Felder. Informationen zur internen Dateiorganisation finden Sie unter Struktur der [Kundendaten-Feed-Datei](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Datentyp </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Ereigniszeit</code> </p> </td> 
   <td colname="col2"> <p>Zeitstempel </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt, zu dem eine CDF-Datei von den <span class="wintitle"> Datenerfassungsservern</span> verarbeitet wurde. Der Zeitstempel verwendet das Format <i>yyyy-mm-dd hh:mm:ss</i> und wird in der UTC-Zeitzone eingestellt. </p> <p> <p>Hinweis: Die Ereigniszeit <i>ist nicht</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Der Zeitpunkt des Seitenereignisses oder des Ereignisaufrufs selbst, auch wenn er in der Nähe dieser Zeiten liegen kann. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Im Zusammenhang mit der DCS-Stunde im Dateinamen. <a href="#different-processing-times">Siehe auch </a> Zeiten für Kundendaten-Feed-Dateien und Zeiten für Dateiinhalte.... </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Gerät</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Dies ist die <span class="wintitle"> Unique User ID</span> (UUID), eine 38-stellige Geräte-ID für Ihren Site-Besucher. Weitere Informationen finden Sie unter <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Behälter-ID</code> </p> </td> 
   <td colname="col2"> <p>Numerisch </p> </td> 
   <td colname="col3"> <p>Die ID des Containers, der ID auslöst, wird synchronisiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realisierte Eigenschaften</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Eigenschaften-IDs, die alle Eigenschaften enthalten, die ein Besucher im Ereignisaufruf implementiert (qualifiziert) hat. </p> <p>Beachten Sie, dass das Array Eigenschaften enthalten kann, für die sich der Besucher zuvor qualifiziert hatte und für die er sich durch diesen Ereignisaufruf erneut qualifiziert hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realisierte Segmente</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, die alle Segmente enthalten, die ein Besucher im Ereignisaufruf (qualifiziert) durchgeführt hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Anfrageparameter</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Eine Zeichenfolge, die alle Parameter erfasst (Variablen, IDs, Schlüssel-Wert-Paare, Anzeigen-IDs für Geräte usw.) beim Ereignisaufruf weitergegeben. </p> <p>Kurzes Beispiel: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.did:92D56353-49C5-431E-B474-FC528D585810,c_contextData a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Typ der Referrer-Daten</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die nicht kodierte URL der verweisenden Seite (sofern vorhanden). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP-Datentyp</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die IP-Adresse des Besuchers, der im Ereignisaufruf erfasst wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die <span class="keyword"> Experience Cloud</span> ID (MID), die dem Site-Besucher zugewiesen ist. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Alle Segmente</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, die zuvor realisierte Segmente und neue Segmente enthalten, für die der Besucher qualifiziert ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Alle Eigenschaften</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Eigenschaften-IDs von Erstanbietern und Drittanbietern, die zuvor realisierte Eigenschaften und neue Eigenschaften enthalten, für die sich der Besucher seit dem letzten generierten Datenfeed qualifiziert hat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Struktur der Benutzerdaten-Feed-Datei {#cdf-file-structure}

Listet die Datenstruktur einer [!UICONTROL CDF] Datei auf und definiert sie. Dazu gehören Datensequenzen, Feldtrennzeichen und Trennzeichen, eine Datendateizuordnung und eine Musterdatei.

## Datenfeldkennungen und -sequenz {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] Dateien enthalten keine gekennzeichneten Spalten oder Feldkopfzeilen. Stattdessen definiert eine [!UICONTROL CDF] Datei Felder und Arrays mit nicht druckbaren [!DNL ASCII] Zeichen. Die [!UICONTROL CDF] Datei listet außerdem jedes Feld und Array in einer bestimmten Reihenfolge auf. Anhand der Feldkennungen und der Reihenfolge können Sie die Datei richtig analysieren.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF-Dateielement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Feldtrennzeichen und Trennzeichen </p> </td> 
   <td colname="col2"> <p>Diese nicht druckbaren Zeichen definieren die Elemente und die Struktur Ihrer CDF-Datei: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Strg + A (ASCII <code> 001</code> oder <code> ^ A</code>) trennt Daten in einzelnen Feldern mit einem nicht druckbaren Leerzeichen. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Strg+b (ASCII <code> 002</code> oder <code> ^ B</code>) trennt Daten, Array- und Anforderungsparameter. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Strg + C (ASCII <code> 003</code> oder <code> ^ C</code>) definiert Schlüssel/Wert-Paare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feldsequenz </p> </td> 
   <td colname="col2"> <p> <p>Wichtig: Audience Manager<span class="keyword"> </span> behält sich das Recht vor, neue Felder am Ende der CDF-Datei in zukünftigen Versionen hinzuzufügen. Das bedeutet, dass das technische Design Ihres Dateianalysesystems keine feste Anzahl von Spalten annehmen sollte (obwohl es eine feste Reihenfolge für vorhandene Spalten annehmen kann). </p> </p> <p>Daten in Ihrer CDF-Datei werden in der unten stehenden Reihenfolge angezeigt. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7"> Ereigniszeit </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Gerät </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Behälter-ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9"> Realisierte Eigenschaften </li> 
      <li id="li_1591180564374204852785C6FFCA4F74"> Realisierte Segmente </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Anfrageparameter </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-Adresse </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud-Geräte-ID (oder MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595"> Alle Segmente </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alle Eigenschaften </li> 
     </ol> </p> <p>Feldbeschreibungen finden Sie unter Inhalt des <a href="#cdf-defined"> Kundendatenfeeds definiert</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF-Dateizuordnung {#cdf-file-map}

[!UICONTROL CDF] Dateidaten werden in der unten stehenden Reihenfolge angezeigt.

![](assets/sequence-map.png)

## Identifizieren von Arrays

Arrays in einer [!UICONTROL CDF] Datei beginnen und enden mit dem `Ctrl + a` Feldtrenner. Dadurch wird das erste Element in einem Array wie ein eigenständiges Datenfeld angezeigt. Das Array der realisierten Eigenschaften beginnt beispielsweise mit `^A1234`. Das Array-Trennzeichen und die ID `^B5678` folgen diesem Eintrag. Daher könnten Sie glauben, dass das erste Element im Array der realisierten Eigenschaften ID 5678 ist (da es mit `^B`beginnt). Dies ist nicht der Fall, weshalb Sie mit der Reihenfolge und Struktur einer Datendatei vertraut sein müssen. Auch wenn das erste Element im realisierten Eigenschaftenarray (oder einem der anderen Arrays in einer [!UICONTROL CDF] Datei) mit beginnt `^A`, definiert die Reihenfolge des Erscheinungsbilds oder der Position in der Datei den Anfang eines Arrays. Und das erste Element in einem Array wird immer vom vorherigen Eintrag durch `^A`getrennt.

## Beispiel-CDF-Datei {#sample-file}

Eine Beispieldatei [!UICONTROL CDF] könnte wie folgt aussehen. Wir haben Zeilenumbrüche in dieses Beispiel eingefügt, um es an die Seite anzupassen.

![](assets/CDF-sample.png)

## Benennungskonventionen für Kundendatenfeed-Dateien {#cdf-naming-conventions}

In den folgenden Abschnitten werden die Elemente in Ihrem [!UICONTROL CDF] Dateinamen aufgelistet und definiert.

## CDF-Dateiname: Syntax und Beispiel {#cdf-file-name}

<!-- cdf-file-name.xml -->

Ein typischer [!UICONTROL CDF] Dateiname enthält die unten aufgeführten Elemente. Note, *italics* indicates a variable placeholder:

### Syntax

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Beispiel 

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In Ihrem [!DNL S3] Speicherbehälter werden die Dateien in aufsteigender Reihenfolge nach Partner-ID ([!UICONTROL PID]), Tag und Stunde sortiert.

## CDF-Dateinamenelemente definiert {#cdf-file-name-elements}

In der folgenden Tabelle sind die Elemente in einem [!UICONTROL CDF] Dateinamen aufgeführt und definiert.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateinamenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Dies ist der standardmäßige Stammspeicherbehälter für Ihre CDF-Datei auf einem Amazon S3-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Name <i>des S3-Behälters</i></code> </p> </td> 
   <td colname="col2"> <p>Der Name des schreibgeschützten S3-Behälters, der Ihre CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem Ihre Datei verarbeitet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitwert, der in 24-Stunden-Notation ausgedrückt und in der UTC-Zeitzone eingestellt wird. <a href="#different-processing-times">Siehe auch </a> Zeiten für Kundendaten-Feed-Dateien und Zeiten für Dateiinhalte.... </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>Partner-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Ihre Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM-Prozess-ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Eine interne <span class="keyword"> Audience Manager</span> -Prozess-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Eine gzip-Dateierweiterung. CDF-Dateien werden gzip-komprimiert. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Benachrichtigungen zur Verarbeitung von Daten-Feeds {#cdf-file-processing-notifications}

[!DNL Audience Manager] schreibt eine `.info` Datei in Ihr [!DNL S3] Verzeichnis, um Sie darüber zu informieren, wann [!UICONTROL Customer Data File] ([!UICONTROL CDF]) zum Download bereit ist. Die `.info` Datei enthält auch [!DNL JSON] formatierte Metadaten zum Inhalt Ihrer [!UICONTROL CDF] Dateien. In diesem Abschnitt finden Sie Informationen zur Syntax und den Feldern, die von dieser Benachrichtigungsdatei verwendet werden.

## Beispielinformationsdatei {#sample-info-file}

<!-- cdf-notifications.xml -->

Jede `.info` Datei enthält einen `Files` und einen `Totals` -Abschnitt. Der `Files` Abschnitt enthält ein Array, das für jede stündliche Datei spezifische Metriken enthält. Der `Totals` Abschnitt enthält Metriken, die an einem bestimmten Tag in all Ihren [!UICONTROL CDF] Dateien aggregiert werden. Der Inhalt Ihrer `.info` Datei könnte dem folgenden Beispiel ähneln.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Felder für Infodateien definiert {#info-file-fields-defined}

In den folgenden Tabellen werden die Elemente in einer [!UICONTROL CDF] `.info` Datei aufgelistet und definiert.

### Dateiobjekt

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Dateien</code> </p> </td> 
   <td colname="col2"> <p>Startet das Array, das Metadaten zu Ihren CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Der Amazon S3 ETag. Die Zahl nach dem Bindestrich zeigt die Anzahl der Teile, die zum Erstellen der Datei während des mehrteiligen Uploads verwendet wurden. Das <code> ETag</code> ist nicht identisch mit der MD5-Prüfsumme der Datei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Der Dateiname. Siehe <a href="#cdf-naming-conventions"> Benutzerdaten-Feed-Dateibenennungskonventionen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Eine Indexnummer für jede Datei. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Gesamtobjekt

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Gesamt</code> </p> </td> 
   <td colname="col2"> <p>Startet das Objekt, das aggregierte Daten zu allen CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Tag</code> </p> </td> 
   <td colname="col2"> <p>Der Tag, an dem die Daten verfügbar sind. Verwendet das Format <i>yyyy-mm-dd</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Stunde</code> </p> </td> 
   <td colname="col2"> <p>Die Stunde, für die Daten verfügbar sind. Verwendet das 24-Stunden-Format, das in der UTC-Zeitzone festgelegt ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtgröße aller CDF-Dateien für dieses Datum in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der Dateien, die in Ihren S3-Ordner hochgeladen wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Die Uhrzeiten für den Kundendatenfeed-Dateinamen und die Dateiinhaltszeiten sind unterschiedlich {#different-processing-times}

Ihre [!UICONTROL CDF] Datei enthält Zeitstempel im Dateinamen und im Dateiinhalt. Diese Zeitstempel zeichnen unterschiedliche Ereignisprozesse für dieselbe [!UICONTROL CDF] Datei auf. Es ist nicht ungewöhnlich, dass unterschiedliche Zeitstempel im Namen und Inhalt derselben Datei angezeigt werden. Die Kenntnis jedes Zeitstempels kann Ihnen dabei helfen, gängige Fehler beim Arbeiten mit diesen Daten oder beim Versuch, sie nach Zeit zu sortieren, zu vermeiden.

## Suchen von CDF-Datei-Zeitstempeln {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] -Dateien die Zeit in zwei verschiedenen Speicherorten unterschiedlich aufzeichnen.

![](assets/cdf-timestamp.png)

## Die Unterschiede zwischen Zeitstempeln {#understanding-timestamps}

Die folgende Tabelle enthält weitere Details zu Ihren [!UICONTROL CDF] Datei-Zeitstempeln sowie Informationen zur ordnungsgemäßen Verwendung.

| Zeitstempelposition | Beschreibung |
|--- |--- |
| Dateiname | Der Zeitstempel im Namen der CDF-Datei kennzeichnet den Zeitpunkt, zu dem die Bereitstellung der Datei vorbereitet [!DNL Audience Manager] wurde. Dieser Zeitstempel wird in der UTC-Zeitzone eingestellt. Es verwendet den `hour=` Parameter, wobei die Uhrzeit als 2-stellige Stunde in 24-Stunden-Notation formatiert wird. Diese Zeit kann sich von der in den Dateiinhalten aufgezeichneten Ereigniszeit unterscheiden. BREAKWbeim Arbeiten mit CDF-Dateien werden Sie manchmal bemerken, dass Ihr S3-Behälter für eine bestimmte Stunde leer ist. Ein leerer Behälter bedeutet:<ul><li>Es gibt keine Daten für diese bestimmte Stunde. </li><li> Unsere Server sind unter hoher Belastung und können keine Dateien für eine bestimmte Stunde verarbeiten. Wenn der Server erfasst, werden die Dateien, die in früheren Zeitbehälterdateien enthalten sein sollten, in einen Behälter mit einem späteren Zeitwert gelegt. Dies wird beispielsweise angezeigt, wenn eine Datei, die im 17-Stunden-Bucket enthalten sein sollte, im 18-Stunden-Bucket (mit `hour=18` dem Dateinamen) angezeigt wird. In diesem Fall hat der Server wahrscheinlich die Verarbeitung der Datei in Stunde 17 begonnen, konnte sie jedoch nicht innerhalb dieses Zeitintervalls abschließen. Stattdessen wird die Datei in den nächsten Stundenzähler verschoben.</li></ul><br>**Wichtig**: Verwenden Sie nicht den Zeitstempel für Dateinamen, um Ereignisse nach Zeit zu gruppieren. Wenn Sie nach Zeit gruppieren müssen, verwenden Sie den `EventTime` Zeitstempel im Dateiinhalt. |
| Dateiinhalt | Der Zeitstempel im Inhalt der CDF-Datei kennzeichnet den Zeitpunkt, zu dem die Datenerfassungsserver mit der Verarbeitung der Datei begonnen haben. Dieser Zeitstempel wird in der UTC-Zeitzone eingestellt. Es verwendet das `EventTime` Feld, wobei die Uhrzeit als *`yyyy-mm-dd hh:mm:ss`*. Diese Zeit ist nahe an der tatsächlichen Zeit des Ereignisses auf der Seite, kann jedoch von der Stundenanzeige im Dateinamen abweichen. <br> **Tipp**: Im Gegensatz zum `hour=` Zeitstempel im Dateinamen können Sie Daten nach Zeit gruppieren `EventTime` lassen. |

>[!MORE_LIKE_THIS]
>
>* [Häufig gestellte Fragen zum Kundendatenfeed](../faq/faq-cdf.md)

