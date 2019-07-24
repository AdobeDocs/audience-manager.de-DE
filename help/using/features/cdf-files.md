---
description: Grundlegende Informationen zu Kundendatenfeeds (CDF-Dateien) und Anweisungen zum Einstieg. Beginnen Sie hier, wenn Sie möchten, dass Sie CDF-Dateien empfangen oder nur weitere Informationen erhalten.
keywords: second party data; 2. Partei; Daten von Zweitherstellern; zweite Partei
seo-description: Grundlegende Informationen zu Kundendatenfeeds (CDF-Dateien) und Anweisungen zum Einstieg. Beginnen Sie hier, wenn Sie möchten, dass Sie CDF-Dateien empfangen oder nur weitere Informationen erhalten.
seo-title: Kundendatenfeeds
solution: Audience Manager
title: Kundendatenfeeds
uuid: a 5 de 1630-2 c 7 a -4862-9 ba 0-f 8343 cdd 2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you're interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. Dazu gehören Daten wie Benutzer-IDs, Eigenschaften-IDs, Segment-IDs und alle anderen Parameter, die durch einen Ereignisaufruf erfasst werden. Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] versucht, Dateien stündlich zu generieren [!UICONTROL CDF] und in einem sicheren, kundenspezifischen Behälter auf einem [!DNL Amazon S3] Server zu speichern. We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## Erste Schritte {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. Sie können keine Ordner und Dateien anzeigen, die zu anderen Kunden gehören.

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they're ready for download. You're responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Nächste Schritte {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## Definitionen {#definitions}

<!-- cdf-contents-defined.xml -->

A [!UICONTROL CDF] file includes some or all of the fields defined below. For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

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
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Die Zeit des Seitenereignisses oder des Ereignisaufrufs selbst, obwohl er sich möglicherweise näher an diesen Zeiten befindet. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Im Zusammenhang mit der DCS-Stunde im Dateinamen. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Gerät</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. Weitere Informationen finden Sie unter <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Behälter-ID</code> </p> </td> 
   <td colname="col2"> <p>Numerisch </p> </td> 
   <td colname="col3"> <p>Die ID des Containers, der ID-Synchronisierungen auslöst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Neu gestaltete Eigenschaften</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Eigenschaftskennungen, die alle Eigenschaften enthalten, die ein Besucher im Ereignisaufruf (qualifiziert) hat. </p> <p>Beachten Sie, dass das Array Eigenschaften enthalten kann, für die der Besucher bereits qualifiziert war und für die er durch diesen Ereignisaufruf erneut qualifiziert wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Neu gestaltete Segmente</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, die alle Segmente enthalten, die ein Besucher im Ereignisaufruf (qualifiziert) angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Anfrageparameter</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Eine Zeichenfolge, die alle Parameter erfasst (Variablen, IDs, Schlüssel/Wert-Paare usw.) im Ereignisaufruf weitergegeben. </p> <p>Gekürztes Beispiel: </p> <p> <code> d_ rtbd: json, c_ contextdata. a. carriername: mobile, c_ contextdata. a. adid: 92 D 56353-49 C 5-431 E-B 474-FC 528 D 858580, c_ contextdata. a, runmode: Anwendung, c_ contextdata. a. dayssincelastupgrade: 61, d_ cid_ ic: xid % 01 EACB 6 E 40-AC 65-4012-9 FE 9-ABD 59965 E 9 C 4% 11, c_ contextdata. a. prevsessionlength: 583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referrer-Datentyp</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die nicht kodierte URL der verweisenden Seite (falls vorhanden). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP-Datentyp</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die IP-Adresse des Besuchers, der im Ereignisaufruf erfasst wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Mcdevice </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Alle Segmente</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, die zuvor erstellte Segmente und neue Segmente enthalten, für die der Besucher qualifiziert ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Alle Eigenschaften</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von IDs der ersten und dritten Partei, die zuvor neu entwickelte Eigenschaften und neue Eigenschaften enthalten, für die der Besucher seit dem letzten generierten Datenfeed qualifiziert ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. Dazu gehören Datensequenz, Feldtrennzeichen und Trennzeichen, Datendateizuordnung und Beispieldatei.

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] Dateien dürfen keine beschrifteten Spalten oder Feldanzeige enthalten. Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. Also, the [!UICONTROL CDF] file lists each field and array in a specific order. Anhand der Feldkennungen und der Reihenfolge können Sie die Datei ordnungsgemäß analysieren.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feldsequenz </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. Das bedeutet, dass der technische Entwurf Ihres Dateianalyse-Systems keine feste Anzahl von Spalten annehmen sollte (obwohl es eine feste Reihenfolge für vorhandene Spalten annehmen kann). </p> </p> <p>Daten in Ihrer CDF-Datei werden in der unten stehenden Reihenfolge angezeigt. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ereigniszeit </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Gerät </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Behälter-ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Neu gestaltete Eigenschaften </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Neu gestaltete Segmente </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Anfrageparameter </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-Adresse </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud-Geräte-ID (oder MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Alle Segmente </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alle Eigenschaften </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] Dateidaten in der unten stehenden Reihenfolge angezeigt werden.

![](assets/sequence-map.png)

## Identifizieren von Arrays

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. Dadurch wird das erste Element in einem Array wie ein eigenständiges Datenfeld angezeigt. For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). Dies ist nicht der Fall. Daher müssen Sie mit der Sequenz und der Struktur einer Datendatei vertraut sein. Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. Wir haben Zeilenumbrüche in dieses Beispiel eingefügt, um es an die Seite anzupassen.

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **Syntax**

<pre><code>s 3: //aam-cdf/your<i>s 3 bucket name</i>/day =<i>yyyy-mm-dd</i>/hour =<i>hh</i>/<i>AAM_ CDF_ partner ID_ AAM process id</i>_0.gz</code>
</pre>

* **Beispiel**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateinamenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s 3: //aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Dies ist der standardmäßige Stammspeicherbehälter für Ihre CDF-Datei auf einem Amazon S 3-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>Name des S 3-Behälters</i></code> </p> </td> 
   <td colname="col2"> <p>Der Name des schreibgeschützten S 3-Behälters, der Ihre CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day =<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem die Datei verarbeitet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour =<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitwert, ausgedrückt in 24-Stunden-Notation und in der UTC-Zeitzone. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>Partner-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Ihre Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>AAM-Prozess-ID</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Eine GZIP-Dateierweiterung. CDF-Dateien werden komprimiert komprimiert. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] schreibt eine `.info` Datei in den [!DNL S3] Ordner, damit Sie wissen können, wann Ihre [!UICONTROL Customer Data File] ([!UICONTROL CDF]) zum Herunterladen bereit ist. The `.info` file also includes [!DNL JSON] formatted metadata about the contents of your [!UICONTROL CDF] files. Lesen Sie diesen Abschnitt, um Informationen über die Syntax und die von dieser Benachrichtigungsdatei verwendeten Felder zu erhalten.

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. The `Files` section contains an array that holds specific metrics for each hourly file. The `Totals` section contains metrics aggregated across all your [!UICONTROL CDF] files for a particular day. The contents of your `.info` file could look similar to the following example.

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

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

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
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Das Amazon S 3 etag. Die Zahl, die dem Bindestrich folgt, zeigt die Anzahl der Teile an, die zum Erstellen der Datei während des mehrteiligen Hochladevorgangs verwendet werden. The <code> ETag</code> is not identical to the MD5 checksum of the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>Der Dateiname. See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filesequencenumber</code> </p> </td> 
   <td colname="col2"> <p>Eine Indexnummer für jede Datei. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Gesamt-Objekt

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
   <td colname="col2"> <p>Startet das Objekt, das aggregierte Daten über alle CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Tag</code> </p> </td> 
   <td colname="col2"> <p>Der Tag, an dem die Daten verfügbar sind. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Stunde</code> </p> </td> 
   <td colname="col2"> <p>Die Stunde, für die Daten verfügbar sind. Verwendet 24-Stunden-Format in UTC-Zeitzone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtgröße aller CDF-Dateien für dieses Datum in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der Dateien, die in den S 3-Ordner hochgeladen wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

Your [!UICONTROL CDF] file contains timestamps in the file name and file contents. These timestamps record different event processes for the same [!UICONTROL CDF] file. Es ist nicht ungewöhnlich, unterschiedliche Zeitstempel im Namen und Inhalt derselben Datei anzuzeigen. Die Kenntnis der einzelnen Zeitstempel kann Ihnen bei der Vermeidung allgemeiner Fehler helfen, wenn Sie mit diesen Daten arbeiten oder sie nach der Zeit sortieren möchten.

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] Dateien in zwei separaten Positionen unterschiedlich aufzeichnen.

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| Speicherort des Zeitstempels | Beschreibung |
|--- |--- |
| Dateiname | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. Dieser Zeitstempel wird in der UTC-Zeitzone festgelegt. It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. Diese Zeit kann sich auf die im Dateiinhalt aufgezeichnete Ereigniszeit unterscheiden. Breakwhen working with CDF files. Manchmal bemerken Sie, dass der S 3-Behälter für eine bestimmte Stunde leer ist. Ein leerer Behälter kann Folgendes bedeuten:<ul><li>Es gibt keine Daten für diese Stunde. </li><li> Unsere Server befinden sich unter hohen Lasten und können Dateien für eine bestimmte Stunde nicht verarbeiten. Wenn der Server sich ansammelt, werden die Dateien, die in früheren Zeitleisten-Bucket-Dateien verstreichen sollten, mit einem späteren Zeitwert in einem Behälter zusammengefasst. For example, you'll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). In diesem Fall hat der Server die Verarbeitung Ihrer Datei in Stunden 17 wahrscheinlich gestartet, konnte ihn aber nicht innerhalb dieses Zeitintervalls abschließen. Stattdessen wird die Datei an den nächsten stündlichen Zeitbehälter gesendet.</li></ul><br>**Wichtig**: Verwenden Sie nicht den Dateinamenzeitstempel, um Ereignisse nach Zeit zu gruppieren. If you need to group by time, use the `EventTime` timestamp in the file contents. |
| Dateiinhalt | Der Zeitstempel in Ihrem CDF-Dateiinhalt markiert den Zeitpunkt, zu dem die Datenerfassungsserver die Verarbeitung der Datei gestartet haben. Dieser Zeitstempel wird in der UTC-Zeitzone festgelegt. It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **Tipp**: Im Gegensatz zum `hour=` Zeitstempel im Dateinamen können Sie die Daten nach Zeit gruppieren `EventTime` . |

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zu Kundendaten](../faq/faq-cdf.md)

