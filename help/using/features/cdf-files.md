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


# Kundendatenfeeds {#customer-data-feeds}

Grundlegende Informationen zu [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) und Anweisungen zum Einstieg. Beginnen Sie hier, wenn Sie an [!UICONTROL CDF] Dateien interessiert sind oder lediglich weitere Informationen wünschen.

## Dateiinhalt und -zweck {#file-contents-purpose}

<!-- cdf-intro.xml -->

Eine [!UICONTROL CDF] Datei enthält dieselben Daten, die ein [!DNL Audience Manager] Ereignisaufruf an `/event`unsere Server sendet. Dazu gehören Daten wie Benutzer-IDs, Eigenschaften-IDs, Segment-IDs und alle anderen Parameter, die durch einen Ereignisaufruf erfasst werden. Interne [!DNL Audience Manager] Systeme verarbeiten Ereignisdaten in eine [!UICONTROL CDF] Datei mit Inhalten, die in Felder organisiert sind, die in einer festgelegten Reihenfolge erscheinen. [!DNL Audience Manager] versucht, Dateien stündlich zu generieren [!UICONTROL CDF] und in einem sicheren, kundenspezifischen Behälter auf einem [!DNL Amazon S3] Server zu speichern. Wir stellen diese Dateien bereit, damit Sie [!DNL Audience Manager] mit Daten außerhalb der von unserer Benutzeroberfläche festgelegten Beschränkungen arbeiten können.

>[!NOTE]
>
>Sie sollten [!UICONTROL CDF] keine Dateien als Proxy verwenden, um Seiten-Traffic zu überwachen, Berichtsdiskrepanzen zu vereinheitlichen oder für die Rechnungsstellung usw.

## Erste Schritte {#getting-started}

Es gibt keinen Selbstbedienungsprozess zur [!UICONTROL CDF] Dateibereitstellung. Wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder an den Kundendienst, um zu beginnen. Während der Implementierung wird Ihr [!DNL Audience Manager] Kundenbetreuer:

* Richten Sie Ihren [!DNL Amazon S3] Speicherbehälter ein.
* Geben Sie schreibgeschützte [!DNL S3] Authentifizierungsberechtigungen für den Dateispeicherbehälter an. Sie können keine Ordner und Dateien anzeigen, die zu anderen Kunden gehören.

Dateibenachrichtigungen und [!UICONTROL CDF] Dateien werden in Ihrem [!DNL S3] Behälter angezeigt, wenn sie zum Herunterladen bereit sind. Sie sind für die Überwachung und das Herunterladen von Dateien aus Ihrem zugewiesenen [!DNL S3] Ordner verantwortlich. Siehe [Feed zur Verarbeitung von Datendateidaten für Kunden](#cdf-file-processing-notifications).

## Nächste Schritte {#next-steps}

Die folgenden Abschnitte und die häufig gestellten Fragen [zum Kunden-Feed helfen](../faq/faq-cdf.md) Ihnen dabei, sich mit diesem Dienst vertraut zu machen.

## Feed für Kundendaten definiert {#cdf-defined}

Listet die Datenelemente und Arrays in einer [!UICONTROL CDF] Datei nach Reihenfolge auf. Definitionen enthalten Datentypen, diese Informationen sind jedoch nicht Teil einer [!UICONTROL CDF] Datei.

## Definitionen {#definitions}

<!-- cdf-contents-defined.xml -->

Eine [!UICONTROL CDF] Datei enthält einige oder alle unten definierten Felder. Informationen zur internen Dateiorganisation finden Sie unter [Data Data Feed-Struktur](#cdf-file-structure).

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
   <td colname="col3"> <p>Der Zeitpunkt, zu dem eine CDF-Datei von den <span class="wintitle"> Datenerfassungsservern</span> (Data Collection Servers, DCS) verarbeitet wurde. Der Zeitstempel verwendet das <i>HH jjjj-mm-tt: mm: ss</i> -Format und wird in der UTC-Zeitzone festgelegt. </p> <p> <p>Hinweis: Die Ereigniszeit <i></i>lautet nicht: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Die Zeit des Seitenereignisses oder des Ereignisaufrufs selbst, obwohl er sich möglicherweise näher an diesen Zeiten befindet. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Im Zusammenhang mit der DCS-Stunde im Dateinamen. Siehe auch <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times…</a> </li> 
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
   <td colname="col3"> <p>Die <span class="keyword"> dem Site-Besucher zugewiesene Experience Cloud</span> ID (MID). Siehe auch <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies und theexperience Cloud ID-Dienst</a>. </p> </td> 
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

## Feed-Dateistruktur für Kundendaten {#cdf-file-structure}

Listet die Datenstruktur einer [!UICONTROL CDF] Datei auf und definiert sie. Dazu gehören Datensequenz, Feldtrennzeichen und Trennzeichen, Datendateizuordnung und Beispieldatei.

## Datenfeldkennung und -sequenz {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] Dateien dürfen keine beschrifteten Spalten oder Feldanzeige enthalten. Stattdessen definiert eine [!UICONTROL CDF] Datei Felder und Arrays mit nicht druckbaren [!DNL ASCII] Zeichen. Außerdem werden in der [!UICONTROL CDF] Datei alle Felder und Array in einer bestimmten Reihenfolge aufgelistet. Anhand der Feldkennungen und der Reihenfolge können Sie die Datei ordnungsgemäß analysieren.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Strg + A (ASCII <code> 001</code> oder <code> ^ A</code>) trennt Daten in einzelnen Feldern mit einem Leerzeichen ohne Drucken. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Strg + b (ASCII <code> 002</code> oder <code> ^ B</code>) trennt Daten ein Array und Anforderungsparameter. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Strg + c (ASCII <code> 003</code> oder <code> ^ C</code>) definiert Schlüssel-Wert-Paare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feldsequenz </p> </td> 
   <td colname="col2"> <p> <p>Wichtig: <span class="keyword"> Audience Manager</span> behält sich das Recht vor, in zukünftigen Versionen neue Felder am Ende der CDF-Datei hinzuzufügen. Das bedeutet, dass der technische Entwurf Ihres Dateianalyse-Systems keine feste Anzahl von Spalten annehmen sollte (obwohl es eine feste Reihenfolge für vorhandene Spalten annehmen kann). </p> </p> <p>Daten in Ihrer CDF-Datei werden in der unten stehenden Reihenfolge angezeigt. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ereigniszeit </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Gerät </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Behälter-ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Neu gestaltete Eigenschaften </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Neu gestaltete Segmente </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Anfrageparameter </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-Adresse </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud-Geräte-ID (oder MID). Siehe auch <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies und der Experience Cloud ID-Dienst</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Alle Segmente </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alle Eigenschaften </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF-Dateizuordnung {#cdf-file-map}

[!UICONTROL CDF] Dateidaten in der unten stehenden Reihenfolge angezeigt werden.

![](assets/sequence-map.png)

## Identifizieren von Arrays

Arrays in einer [!UICONTROL CDF] Datei starten und enden mit `Ctrl + a` dem Feldtrennzeichen. Dadurch wird das erste Element in einem Array wie ein eigenständiges Datenfeld angezeigt. Beispielsweise beginnt das bereitgestellte Trasein-Array mit `^A1234`. Das Array-Trennzeichen und die ID `^B5678` folgen diesem Eintrag. Aus diesem Grund könnten Sie glauben, dass das erste Element im bereitgestellte Eigenschaften-Array ID 5678 lautet (weil es beginnt `^B`). Dies ist nicht der Fall. Daher müssen Sie mit der Sequenz und der Struktur einer Datendatei vertraut sein. Auch wenn das erste Element im bereitgestellte Eigenschaftsarray (oder einer der anderen Arrays in einer [!UICONTROL CDF] Datei) mit `^A`beginnt, definiert die Reihenfolge der Darstellung oder Position in der Datei den Anfang eines Arrays. And, the first element in an array is always separated from the preceding entry by `^A`.

## Beispiel-CDF-Datei {#sample-file}

Eine Beispieldatei [!UICONTROL CDF] könnte wie folgt aussehen. Wir haben Zeilenumbrüche in dieses Beispiel eingefügt, um es an die Seite anzupassen.

![](assets/CDF-sample.png)

## Benennungskonventionen für Kundendatenfeeds {#cdf-naming-conventions}

Die folgenden Abschnitte sind aufgelistet und definieren die Elemente in Ihrem [!UICONTROL CDF] Dateinamen.

## CDF-Dateiname: Syntax und Beispiel {#cdf-file-name}

<!-- cdf-file-name.xml -->

Ein typischer [!UICONTROL CDF] Dateiname enthält die unten aufgeführten Elemente. Hinweis: *Kursiv* zeigt einen Variablenplatzhalter an:

* **Syntax**

<pre><code>s 3: //aam-cdf/your<i>s 3 bucket name</i>/day =<i>yyyy-mm-dd</i>/hour =<i>hh</i>/<i>AAM_ CDF_ partner ID_ AAM process id</i>_0.gz</code>
</pre>

* **Beispiel**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In Ihrem [!DNL S3] Speicherbehälter werden Dateien in aufsteigender Reihenfolge nach Partner-ID ([!UICONTROL PID]), Tag und Stunde sortiert.

## CDF-Dateinamenselemente definiert {#cdf-file-name-elements}

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
   <td colname="col2"> <p>Ein Zeitwert, ausgedrückt in 24-Stunden-Notation und in der UTC-Zeitzone. Siehe auch <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times…</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>Partner-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Ihre Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>AAM-Prozess-ID</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>Eine interne <span class="keyword"> Audience Manager</span> -Prozess-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Eine GZIP-Dateierweiterung. CDF-Dateien werden komprimiert komprimiert. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Benachrichtigungen zur Verarbeitung von Kundendatendateien {#cdf-file-processing-notifications}

[!DNL Audience Manager] schreibt eine `.info` Datei in den [!DNL S3] Ordner, damit Sie wissen können, wann Ihre [!UICONTROL Customer Data File] ([!UICONTROL CDF]) zum Herunterladen bereit ist. Die `.info` Datei enthält [!DNL JSON] außerdem formatierte Metadaten zum Inhalt Ihrer [!UICONTROL CDF] Dateien. Lesen Sie diesen Abschnitt, um Informationen über die Syntax und die von dieser Benachrichtigungsdatei verwendeten Felder zu erhalten.

## Beispielinfo-Datei {#sample-info-file}

<!-- cdf-notifications.xml -->

Jede `.info` Datei enthält einen `Files` und `Totals` einen Abschnitt. Der `Files` Abschnitt enthält ein Array, das bestimmte Metriken für jede stündliche Datei enthält. Der `Totals` Abschnitt enthält Metriken, die für einen bestimmten [!UICONTROL CDF] Tag aggregiert werden. Der Inhalt Ihrer `.info` Datei könnte dem folgenden Beispiel ähnlich aussehen.

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

## Felddateifelder definiert {#info-file-fields-defined}

In der folgenden Tabelle sind die Elemente in einer [!UICONTROL CDF]`.info` Datei aufgeführt und definiert.

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
   <td colname="col2"> <p>Das Amazon S 3 etag. Die Zahl, die dem Bindestrich folgt, zeigt die Anzahl der Teile an, die zum Erstellen der Datei während des mehrteiligen Hochladevorgangs verwendet werden. Das <code> etag</code> ist nicht mit der MD 5-Prüfsumme der Datei identisch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>Der Dateiname. Siehe Feed-Dateibenennungskonventionen <a href="#cdf-naming-conventions"> für Kunden</a>. </p> </td> 
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
   <td colname="col2"> <p>Der Tag, an dem die Daten verfügbar sind. Verwendet <i>das Format JJJJ-MM</i> -TT. </p> </td> 
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

## Feed-Dateinamen des Kundendatensatzes und Dateiinhaltszeiten sind unterschiedlich {#different-processing-times}

Ihre [!UICONTROL CDF] Datei enthält Zeitstempel im Dateinamen und im Dateiinhalt. Diese Zeitstempel zeichnen verschiedene Ereignisprozesse für dieselbe [!UICONTROL CDF] Datei auf. Es ist nicht ungewöhnlich, unterschiedliche Zeitstempel im Namen und Inhalt derselben Datei anzuzeigen. Die Kenntnis der einzelnen Zeitstempel kann Ihnen bei der Vermeidung allgemeiner Fehler helfen, wenn Sie mit diesen Daten arbeiten oder sie nach der Zeit sortieren möchten.

## Suchen von CDF-Datei-Zeitstempeln {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] Dateien in zwei separaten Positionen unterschiedlich aufzeichnen.

![](assets/cdf-timestamp.png)

## Unterschiede zwischen Zeitstempel {#understanding-timestamps}

In der folgenden Tabelle finden Sie weitere Informationen zu Ihren [!UICONTROL CDF] Dateizeitstempeln sowie Informationen darüber, wie sie ordnungsgemäß verwendet werden.

| Speicherort des Zeitstempels | Beschreibung |
|--- |--- |
| Dateiname | Der Zeitstempel in Ihrem CDF-Dateinamen markiert den Zeitpunkt, zu dem [!DNL Audience Manager] die Vorbereitung Ihrer Datei auf die Bereitstellung begonnen hat. Dieser Zeitstempel wird in der UTC-Zeitzone festgelegt. Es verwendet den `hour=` Parameter, wobei die Uhrzeit eine zweistellige Stunde in der 24-Stunden-Notation ist. Diese Zeit kann sich auf die im Dateiinhalt aufgezeichnete Ereigniszeit unterscheiden. Breakwhen working with CDF files. Manchmal bemerken Sie, dass der S 3-Behälter für eine bestimmte Stunde leer ist. Ein leerer Behälter kann Folgendes bedeuten:<ul><li>Es gibt keine Daten für diese Stunde. </li><li> Unsere Server befinden sich unter hohen Lasten und können Dateien für eine bestimmte Stunde nicht verarbeiten. Wenn der Server sich ansammelt, werden die Dateien, die in früheren Zeitleisten-Bucket-Dateien verstreichen sollten, mit einem späteren Zeitwert in einem Behälter zusammengefasst. Sie sehen dies beispielsweise, wenn eine Datei, die sich im Behälter der Stunde 17 befinden sollte, im 18-Stunden-Behälter (mit `hour=18` dem Dateinamen) angezeigt werden soll. In diesem Fall hat der Server die Verarbeitung Ihrer Datei in Stunden 17 wahrscheinlich gestartet, konnte ihn aber nicht innerhalb dieses Zeitintervalls abschließen. Stattdessen wird die Datei an den nächsten stündlichen Zeitbehälter gesendet.</li></ul><br>**Wichtig**: Verwenden Sie nicht den Dateinamenzeitstempel, um Ereignisse nach Zeit zu gruppieren. Wenn Sie nach Zeit gruppieren möchten, verwenden Sie den `EventTime` Zeitstempel im Dateiinhalt. |
| Dateiinhalt | Der Zeitstempel in Ihrem CDF-Dateiinhalt markiert den Zeitpunkt, zu dem die Datenerfassungsserver die Verarbeitung der Datei gestartet haben. Dieser Zeitstempel wird in der UTC-Zeitzone festgelegt. Verwendet das `EventTime` Feld mit der Uhrzeitformatierung *`yyyy-mm-dd hh:mm:ss`*. Diese Zeit befindet sich nahe an der tatsächlichen Uhrzeit des Ereignisses auf der Seite, kann jedoch vom Stundenindikator im Dateinamen abweichen. <br> **Tipp**: Im Gegensatz zum `hour=` Zeitstempel im Dateinamen können Sie die Daten nach Zeit gruppieren `EventTime` . |

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zu Kundendaten](../faq/faq-cdf.md)

