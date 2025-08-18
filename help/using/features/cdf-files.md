---
description: Grundlegende Informationen zu CDF-Dateien (Customer Data Feed) und Anweisungen zu den ersten Schritten. Beginnen Sie hier, wenn Sie an CDF-Dateien interessiert sind oder einfach weitere Informationen wünschen.
keywords: Daten von Zweitanbietern;Daten von Zweitanbietern;Daten von Zweitanbietern;Daten von Zweitanbietern
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Kundendaten-Feeds
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Grundlegende Informationen zu [!UICONTROL Customer Data Feed] ([!UICONTROL CDF])-Dateien und Anweisungen zu den ersten Schritten. Beginnen Sie hier, wenn Sie an [!UICONTROL CDF]-Dateien interessiert sind oder einfach weitere Informationen wünschen.

## Dateiinhalte und -zweck {#file-contents-purpose}

Eine [!UICONTROL CDF]-Datei enthält dieselben Daten, die ein [!DNL Audience Manager]-Ereignisaufruf (`/event`) an unsere Server sendet. Dazu gehören Daten wie Benutzer-IDs, [!UICONTROL trait IDs], [!UICONTROL segment IDs] und alle anderen Parameter, die von einem Ereignisaufruf erfasst werden. Interne [!DNL Audience Manager] verarbeitet Ereignisdaten in eine [!UICONTROL CDF] Datei, deren Inhalt in Feldern organisiert ist, die in einer festgelegten Reihenfolge erscheinen. [!DNL Audience Manager] versucht, [!UICONTROL CDF] Dateien stündlich zu generieren und speichert sie in einem sicheren, kundenspezifischen Behälter auf einem [!DNL Amazon S3]. Wir stellen Ihnen diese Dateien zur Verfügung, damit Sie mit [!DNL Audience Manager] Daten außerhalb der durch unsere Benutzeroberfläche gesetzten Grenzen arbeiten können.

>[!IMPORTANT]
>
>Beachten Sie die folgenden Einschränkungen beim Arbeiten mit CDF-Dateien:
>
>* Stellen Sie vor der Einrichtung der CDF-Dateibereitstellung sicher, dass Sie über die entsprechenden Berechtigungen von Drittanbieterdatenanbietern für den Export von Drittanbieter-Eigenschaften verfügen. Audience Manager unterstützt derzeit keine Funktion in der Benutzeroberfläche, um Exportberechtigungen für die CDF-Dateibereitstellung von Drittanbietern anzufordern. Wenden Sie sich daher bitte unabhängig an diese.
>* Sie sollten [!UICONTROL CDF]-Dateien nicht als Proxy verwenden, um den Seiten-Traffic zu überwachen, Berichtsdiskrepanzen auszugleichen, Abrechnungen zu erstellen usw.

## Erste Schritte {#getting-started}

Es gibt keinen Self-Service-Prozess, um [!UICONTROL CDF] Dateibereitstellung zu starten. Wenden Sie sich an Ihren [!DNL Audience Manager] oder die Kundenunterstützung, um zu beginnen. Während der Implementierung hat Ihr [!DNL Audience Manager] folgende Aufgaben:

* Richten Sie Ihren [!DNL Amazon S3] Speicher-Bucket ein.
* Geben Sie für Ihren Dateispeicher-Bucket schreibgeschützte [!DNL S3]-Authentifizierungsdaten an. Sie können keine Verzeichnisse und Dateien sehen oder darauf zugreifen, die zu anderen Kunden gehören.

Dateibenachrichtigungen und [!UICONTROL CDF] werden in Ihrem [!DNL S3] angezeigt, wenn sie zum Download bereit sind. Sie sind für das Überwachen und Herunterladen von Dateien aus Ihrem zugewiesenen [!DNL S3]-Verzeichnis verantwortlich. Siehe [Verarbeitungsbenachrichtigungen für CDF-Dateien](#cdf-file-processing-notifications).

## Nächste Schritte {#next-steps}

Die folgenden Abschnitte und die [Häufig gestellte Fragen zu Kundendaten](../faq/faq-cdf.md) können Ihnen dabei helfen, sich mit diesem Service vertraut zu machen.

## [!UICONTROL Customer Data Feed] Inhalte definiert {#cdf-defined}

Listet die Datenelemente und Arrays in einer [!UICONTROL CDF] auf und definiert sie in der Reihenfolge ihres Erscheinungsbildes. Definitionen beinhalten Datentypen, diese Informationen sind jedoch nicht Teil einer [!UICONTROL CDF].

>[!IMPORTANT]
>
>Ereignispixel sind in CDF-Konfigurationen standardmäßig ausgeschlossen. Stellen Sie sicher, dass Sie in Ihrer Anfrage an die Kundenunterstützung angeben, wenn Sie möchten, dass Ereignis-Pixel in Ihre CDF-Dateien aufgenommen werden. Jedes Ereignis-Pixel wird als eindeutige Zeile in Ihren CDF-Dateien aufgefüllt.

## Definitionen {#definitions}

Eine [!UICONTROL CDF]-Datei enthält einige oder alle der unten definierten Felder. Informationen zur internen Dateiorganisation finden Sie unter [Struktur der Daten-Feed-Datei](#cdf-file-structure).

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
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Zeitstempel </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt, zu dem eine CDF-Datei von den <span class="wintitle"> Datenerfassungs-Servern (DCS</span> verarbeitet wurde. Der Zeitstempel verwendet das Format <i>JJJJ-MM-TT hh:mm:ss</i> und wird in der UTC-Zeitzone festgelegt. </p> <p> <p>Hinweis: Die Ereigniszeit <i>ist nicht</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Die Zeit des Seitenereignisses oder des Ereignisaufrufs selbst, obwohl sie nahe an diesen Zeiten liegen kann. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Bezieht sich auf die DCS-Stunde im Dateinamen. Siehe auch <a href="#different-processing-times"> von Kundendaten-Feed-Dateinamen und Dateiinhaltszeiten …</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Dies ist die <span class="wintitle"> Unique User ID</span> (UUID), eine 38-stellige Geräte-ID für Ihren Site-Besucher. Siehe auch <a href="../reference/ids-in-aam.md"> ID-Index in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numerisch </p> </td> 
   <td colname="col3"> <p>Die ID des Containers, der die ID-Synchronisierung auslöst. Dieses Feld wird nur ausgefüllt, wenn Sie die Container-ID im Feld <i>d_nsid</i> innerhalb Ihrer Site-Implementierung festlegen. Andernfalls wird der Standardwert 0 nicht in die CDF-Dateien aufgenommen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Eigenschafts-IDs, das alle Eigenschaften enthält, die ein Besucher im Ereignisaufruf realisiert (für sie qualifiziert) hat. </p> <p>Beachten Sie, dass das Array Eigenschaften enthalten kann, für die sich der Besucher zuvor qualifiziert hatte und für die er sich durch diesen Ereignisaufruf erneut qualifiziert hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, das alle Segmente enthält, die ein Besucher im Ereignisaufruf realisiert (für sie qualifiziert) hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Eine Zeichenfolge, die alle Parameter (Variablen, IDs, Schlüssel-Wert-Paare, Geräte-Werbe-IDs usw.) erfasst, die beim Ereignisaufruf übergeben werden. </p> <p>Verkürztes Beispiel: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die nicht kodierte URL der verweisenden Seite (falls vorhanden). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die IP-Adresse für den Besucher, die im Ereignisaufruf erfasst wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die <span class="keyword"> Experience Cloud</span> ID (MID), die dem Site-Besucher zugewiesen wurde. Siehe auch <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=de" format="https" scope="external"> von Cookies und der Adobe Experience Platform Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, das zuvor realisierte Segmente und neue Segmente enthält, für die der Besucher qualifiziert ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Trait-IDs von Erstanbietern und Drittanbietern, das zuvor realisierte Eigenschaften und neue Eigenschaften enthält, für die sich der Besucher seit dem letzten generierten Daten-Feed qualifiziert hat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Dateistruktur {#cdf-file-structure}

Listet die Datenstruktur einer [!UICONTROL CDF] auf und definiert sie. Dazu gehören die Datensequenz, Feldtrennzeichen und -trennzeichen, eine Datendateizuordnung und eine Beispieldatei.

## Datenfeldkennungen und Sequenzen {#identifiers-and-sequence}

[!UICONTROL CDF] Dateien enthalten keine Spalten mit Beschriftungen oder Feldüberschriften. Stattdessen definiert eine [!UICONTROL CDF] Felder und Arrays mit nicht druckbaren [!DNL ASCII]. Außerdem listet die Datei [!UICONTROL CDF] jedes Feld und Array in einer bestimmten Reihenfolge auf. Wenn Sie die Feldkennungen und die Reihenfolge verstehen, können Sie die Datei ordnungsgemäß analysieren.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Strg + A (ASCII <code> 001</code> oder <code> ^A</code>) trennt Daten in einzelnen Feldern mit einem nicht druckbaren Leerzeichen. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Strg + B (ASCII <code> 002</code> oder <code> ^B</code>) trennt Daten von einem Array und Anfrageparametern. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Strg+C (ASCII <code> 003</code> oder <code> ^C</code>) definiert Schlüssel-Wert-Paare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feldsequenz </p> </td> 
   <td colname="col2"> <p> <p>Wichtig: <span class="keyword"> Audience Manager</span> behält sich das Recht vor, in zukünftigen Versionen neue Felder am Ende der CDF-Datei hinzuzufügen. Das bedeutet, dass das technische Design Ihres Datei-Parsing-Systems keine feste Anzahl von Spalten annehmen sollte (obwohl es eine feste Reihenfolge für vorhandene Spalten annehmen kann).</p> </p> <p>Die Daten in Ihrer CDF-Datei werden in der unten gezeigten Reihenfolge angezeigt. /N kann anstelle eines dieser Felder angezeigt werden, was einen Nullwert angibt.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ereigniszeit </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Gerät </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Behälter-ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Realisierte Eigenschaften </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Realisierte Segmente </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Anfrageparameter </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-Adresse </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud-Geräte-ID (oder MID) Siehe auch <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=de" format="https" scope="external"> von Cookies und der Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Alle Segmente </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alle Eigenschaften </li> 
     </ol> </p> <p>Beschreibungen der Felder finden Sie unter <a href="#cdf-defined"> von definierten Inhalten für Kundendaten-Feeds</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Dateizuordnung {#cdf-file-map}

[!UICONTROL CDF] Dateidaten werden in der unten gezeigten Reihenfolge angezeigt.

![](assets/sequence-map.png)

## Arrays identifizieren

Arrays in einer [!UICONTROL CDF] beginnen und enden mit dem `Ctrl + a`. Dadurch erscheint das erste Element in einem Array wie ein eigenständiges Datenfeld. Beispielsweise beginnt das realisierte [!UICONTROL traits]-Array mit `^A1234`. Das Array-Trennzeichen und die ID `^B5678` folgen diesem Eintrag. Daher könnten Sie versucht sein zu glauben, dass das erste Element im realisierten [!UICONTROL traits] die ID 5678 ist (da es mit `^B` beginnt). Dies ist nicht der Fall, weshalb Sie mit der Reihenfolge und Struktur einer Datendatei vertraut sein müssen. Obwohl das erste Element im realisierten [!UICONTROL trait]-Array (oder eines der anderen Arrays in einer [!UICONTROL CDF]-Datei) mit `^A` beginnt, definiert die Reihenfolge der Darstellung oder Position in der Datei den Beginn eines Arrays. Und das erste Element in einem Array wird immer durch `^A` vom vorangehenden Eintrag getrennt.

## [!UICONTROL CDF] {#sample-file}

Eine Beispieldatei für [!UICONTROL CDF] könnte in etwa wie folgt aussehen. Wir haben Zeilenumbrüche in dieses Beispiel eingefügt, damit es auf die Seite passt.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Dateibenennungskonventionen {#cdf-naming-conventions}

In den folgenden Abschnitten werden die Elemente in Ihrem [!UICONTROL CDF]-Dateinamen aufgelistet und definiert.

## [!UICONTROL CDF] Dateiname: Syntax und Beispiel {#cdf-file-name}

Ein typischer [!UICONTROL CDF]-Dateiname enthält die unten aufgeführten Elemente. Hinweis: *Kursiv* gibt einen Variablenplatzhalter an:

### Syntax

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Beispiel

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

In Ihrem [!DNL S3]-Speicher-Bucket werden die Dateien in aufsteigender Reihenfolge nach Partner-ID ([!UICONTROL PID]), Tag und Stunde sortiert.

## [!UICONTROL CDF] Dateinamenelemente definiert {#cdf-file-name-elements}

In der folgenden Tabelle werden die -Elemente in einem [!UICONTROL CDF]-Dateinamen aufgelistet und definiert.

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
   <td colname="col2"> <p>Dies ist der standardmäßige Root-Speicher-Bucket für Ihre CDF-Datei auf einem Amazon S3-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Der Name des schreibgeschützten S3-Buckets, der Ihre CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem Ihre Datei verarbeitet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitwert, der in 24-Stunden-Notation ausgedrückt und in der UTC-Zeitzone festgelegt ist. Siehe auch <a href="#different-processing-times"> von Kundendaten-Feed-Dateinamen und Dateiinhaltszeiten …</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Ihre Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Die Dateisequenz identifizierende Werte. Die Sequenz wird wie folgt inkrementiert: 0_0_0 , 0_1_0, 0_2_0….1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Eine gzip-Dateierweiterung. CDF-Dateien werden gzip-komprimiert. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] von Dateiverarbeitungsbenachrichtigungen {#cdf-file-processing-notifications}

[!DNL Audience Manager] schreibt eine `.info`-Datei in Ihr [!DNL S3]-Verzeichnis, um Sie darüber zu informieren, wann Ihr [!UICONTROL Customer Data File] ([!UICONTROL CDF]) zum Download bereit ist. Die `.info` enthält auch [!DNL JSON] formatierte Metadaten zum Inhalt Ihrer [!UICONTROL CDF]. In diesem Abschnitt finden Sie Informationen über die Syntax und die von dieser Benachrichtigungsdatei verwendeten Felder.

## Beispiel-Informationsdatei {#sample-info-file}

Jede `.info` enthält einen `Files` und `Totals` Abschnitt. Der Abschnitt `Files` enthält ein -Array, das spezifische Metriken für jede stündliche Datei enthält. Der Abschnitt `Totals` enthält Metriken, die für alle [!UICONTROL CDF]-Dateien eines bestimmten Tages aggregiert wurden. Der Inhalt Ihrer `.info` könnte dem folgenden Beispiel ähneln.

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

## Definierte Felder der Informationsdatei {#info-file-fields-defined}

In den folgenden Tabellen werden die Elemente in einer [!UICONTROL CDF] `.info`-Datei aufgelistet und definiert.

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
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Startet das -Array, das Metadaten zu Ihren CDF-Dateien enthält </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Das Amazon S3 E-Tag. Die Zahl nach dem Bindestrich zeigt die Anzahl der Teile an, die während des mehrteiligen Uploads zur Erstellung der Datei verwendet wurden. Der <code> ETag</code> ist nicht identisch mit der MD5-Prüfsumme der Datei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Der Dateiname. Siehe <a href="#cdf-naming-conventions"> Konventionen für die Benennung von Kundendaten-Feeds</a>. </p> </td> 
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
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Startet das -Objekt, das aggregierte Daten zu allen CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Der Tag, für den die Daten verfügbar sind. Verwendet das <i>JJJJ-MM-TT</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Die Stunde, für die Daten verfügbar sind. Verwendet das in der UTC-Zeitzone festgelegte 24-Stunden-Format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtgröße aller CDF-Dateien für dieses Datum in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtzahl der in Ihr S3-Verzeichnis hochgeladenen Dateien. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Zeiten für Dateinamen und Dateiinhalt sind unterschiedlich {#different-processing-times}

Ihre [!UICONTROL CDF] enthält Zeitstempel im Dateinamen und im Dateiinhalt. Diese Zeitstempel zeichnen verschiedene Ereignisprozesse für dieselbe [!UICONTROL CDF] auf. Es ist nicht ungewöhnlich, dass im Namen und Inhalt derselben Datei unterschiedliche Zeitstempel angezeigt werden. Wenn Sie die einzelnen Zeitstempel verstehen, können Sie häufige Fehler bei der Arbeit mit diesen Daten oder beim Versuch, sie nach Zeit zu sortieren, vermeiden.

## Suchen [!UICONTROL CDF] Dateizeitstempeln {#locating-timestamps}

[!UICONTROL CDF] Dateien zeichnen die Zeit an zwei verschiedenen Orten unterschiedlich auf.

![](assets/cdf-timestamp.png)

## Unterschiede zwischen Zeitstempeln {#understanding-timestamps}

Die folgende Tabelle enthält zusätzliche Informationen zu den Zeitstempeln Ihrer [!UICONTROL CDF]-Datei sowie Informationen zu ihrer ordnungsgemäßen Verwendung.

| Zeitstempelposition | Beschreibung |
|--- |--- |
| Dateiname | Der Zeitstempel in Ihrem [!DNL CDF]-Dateinamen markiert den Zeitpunkt, zu dem [!DNL Audience Manager] mit der Vorbereitung Ihrer Datei für den Versand begonnen haben. Dieser Zeitstempel wird in der [!DNL UTC] Zeitzone festgelegt. Dabei wird der `hour=`-Parameter verwendet, wobei die Zeit als 2-stellige Stunde in 24-Stunden-Notation formatiert ist. Diese Zeit kann sich von der im Dateiinhalt aufgezeichneten Ereigniszeit unterscheiden. Beim Arbeiten mit [!DNL CDF] Dateien werden Sie manchmal feststellen, dass Ihr [!DNL S3] für eine bestimmte Stunde leer ist. Ein leerer Bucket bedeutet entweder:<ul><li>Es gibt keine Daten für eine bestimmte Stunde. </li><li> Unsere Server sind stark ausgelastet und können Dateien für eine bestimmte Stunde nicht verarbeiten. Wenn der Server abholt, werden die Dateien, die in einem früheren Zeitfenster-Bucket-Dateien enthalten sein sollten, in einen Bucket mit einem späteren Zeitwert verschoben. Sie sehen dies beispielsweise, wenn eine Datei, die im Bucket „Stunde 17“ enthalten sein sollte, im Bucket „Stunde 18“ angezeigt wird (mit `hour=18` im Dateinamen). In diesem Fall hat der Server wahrscheinlich in Stunde 17 mit der Verarbeitung Ihrer Datei begonnen, konnte sie jedoch nicht innerhalb dieses Zeitintervalls abschließen. Stattdessen wird die Datei an den nächsten stündlichen Zeitbereich gepusht.</li></ul><br>**Wichtig**: Verwenden Sie nicht den Zeitstempel des Dateinamens, um Ereignisse nach Zeit zu gruppieren. Wenn Sie nach Zeit gruppieren müssen, verwenden Sie den `EventTime` Zeitstempel im Dateiinhalt. |
| Dateiinhalte | Der Zeitstempel im Inhalt der [!DNL CDF]-Datei markiert den Zeitpunkt, zu dem die [!DNL Data Collection Servers] mit der Verarbeitung der Datei begonnen hat. Dieser Zeitstempel wird in der [!DNL UTC] Zeitzone festgelegt. Es verwendet das Feld `EventTime` , wobei die Zeit als *`yyyy-mm-dd hh:mm:ss`* formatiert ist. Diese Zeit liegt nahe an der tatsächlichen Zeit des Ereignisses auf der Seite, kann sich jedoch von der Stundenanzeige im Dateinamen unterscheiden. <br> **Tipp**: Im Gegensatz zum `hour=` Zeitstempel im Dateinamen können Sie `EventTime` verwenden, um Daten nach Zeit zu gruppieren. |

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Kundendaten-Feeds](../faq/faq-cdf.md)
