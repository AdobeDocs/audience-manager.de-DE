---
description: Grundlegende Informationen zu CDF-Dateien (Customer Data Feed) und Anweisungen zu den ersten Schritten. Beginnen Sie hier, wenn Sie an CDF-Dateien interessiert sind oder einfach mehr Informationen benötigen.
keywords: Zweitanbieterdaten; Zweitanbieter; Zweitanbieterdaten; Zweitanbieter
seo-description: Grundlegende Informationen zu CDF-Dateien (Customer Data Feed) und Anweisungen zu den ersten Schritten. Beginnen Sie hier, wenn Sie an CDF-Dateien interessiert sind oder einfach mehr Informationen benötigen.
seo-title: Kundendaten-Feeds
solution: Audience Manager
title: Kundendaten-Feeds
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Kundendaten-Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Grundlegende Informationen zu [!UICONTROL Customer Data Feed] ([!UICONTROL CDF])-Dateien und Anweisungen zu den ersten Schritten. Beginnen Sie hier, wenn Sie [!UICONTROL CDF] Dateien empfangen möchten oder einfach mehr Informationen benötigen.

## Dateiinhalt und Zweck {#file-contents-purpose}

Eine [!UICONTROL CDF]-Datei enthält dieselben Daten, die ein [!DNL Audience Manager]-Ereignisaufruf (`/event`) an unsere Server sendet. Dazu gehören Daten wie Benutzer-IDs, [!UICONTROL trait IDs], [!UICONTROL segment IDs] und alle anderen Parameter, die von einem Ereignisaufruf erfasst werden. Interne Systeme [!DNL Audience Manager] verarbeiten Ereignisdaten in einer [!UICONTROL CDF]-Datei, deren Inhalt in Felder unterteilt ist, die in einer bestimmten Reihenfolge angezeigt werden. [!DNL Audience Manager] versucht,  [!UICONTROL CDF] Dateien stündlich zu generieren und speichert sie in einem sicheren, kundenspezifischen Behälter auf einem  [!DNL Amazon S3] Server. Wir stellen diese Dateien bereit, damit Sie mit [!DNL Audience Manager] Daten außerhalb der durch unsere Benutzeroberfläche festgelegten Grenzen arbeiten können.

>[!IMPORTANT]
>
>Beachten Sie beim Arbeiten mit CDF-Dateien die folgenden Einschränkungen:
>
>* Stellen Sie vor der Einrichtung der CDF-Dateibereitstellung sicher, dass Sie über die entsprechenden Berechtigungen von Drittanbietern für den Export von Eigenschaften von Drittanbietern verfügen. Audience Manager unterstützt derzeit keine Funktionalität in der Benutzeroberfläche, um die Exportberechtigung für CDF-Dateien von Datenanbietern von Drittanbietern anzufordern. Wenden Sie sich daher an diese unabhängig.
>* Sie sollten keine [!UICONTROL CDF]-Dateien als Proxy verwenden, um den Seiten-Traffic zu überwachen, Berichtsdiskrepanzen abzustimmen oder Abrechnungen usw. vorzunehmen.


## Erste Schritte {#getting-started}

Es gibt keinen Self-Service-Prozess zum Starten der [!UICONTROL CDF] Dateibereitstellung. Wenden Sie sich an Ihren [!DNL Audience Manager]-Berater oder an die Kundenunterstützung, um zu beginnen. Während der Implementierung wird Ihr [!DNL Audience Manager]-Support-Mitarbeiter:

* Richten Sie den Speicher-Bucket [!DNL Amazon S3] ein.
* Geben Sie Ihrem Dateispeicherbehälter schreibgeschützte [!DNL S3] Authentifizierungsberechtigungen an. Sie können Verzeichnisse und Dateien, die zu anderen Kunden gehören, nicht sehen oder darauf zugreifen.

Dateibenachrichtigungen und [!UICONTROL CDF] -Dateien werden in Ihrem [!DNL S3] -Bucket angezeigt, wenn sie zum Download bereit sind. Sie sind für die Überwachung und das Herunterladen von Dateien aus Ihrem zugewiesenen [!DNL S3]-Verzeichnis verantwortlich. Siehe [Verarbeitungsbenachrichtigungen für CDF-Dateien](#cdf-file-processing-notifications).

## Nächste Schritte {#next-steps}

Die folgenden Abschnitte und die [FAQ zu Kundendaten-Feeds](../faq/faq-cdf.md) können Ihnen dabei helfen, sich mit diesem Dienst besser vertraut zu machen.

## [!UICONTROL Customer Data Feed] Definierte Inhalte {#cdf-defined}

Führt die Datenelemente und Arrays in einer [!UICONTROL CDF]-Datei in der Reihenfolge ihres Erscheinungsbilds auf und definiert sie. Definitionen umfassen Datentypen, diese Informationen sind jedoch nicht Teil einer [!UICONTROL CDF]-Datei.

## Definitionen {#definitions}

Eine [!UICONTROL CDF]-Datei enthält einige oder alle unten definierten Felder. Informationen zur internen Dateiorganisation finden Sie unter [Struktur der CDF-Datei](#cdf-file-structure).

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
   <td colname="col3"> <p>Der Zeitpunkt, zu dem eine CDF-Datei von den <span class="wintitle"> Datenerfassungsservern</span> (DCS) verarbeitet wurde. Der Zeitstempel verwendet das Format <i>yyyy-mm-dd hh:mm:ss</i> und wird in der UTC-Zeitzone festgelegt. </p> <p> <p>Hinweis: Die Ereigniszeit <i>ist nicht</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Der Zeitpunkt des Seitenereignisses oder des Ereignisaufrufs selbst, auch wenn er zu diesen Zeiten nahe liegen kann. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Bezieht sich auf die DCS-Stunde im Dateinamen. Siehe auch <a href="#different-processing-times"> Zeitpunkte für CDF-Dateien und Zeiten für Dateiinhalte ...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Dies ist die <span class="wintitle"> Unique User-ID</span> (UUID), die eine 38-stellige Geräte-ID für Ihren Site-Besucher darstellt. Weitere Informationen finden Sie unter <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numerisch </p> </td> 
   <td colname="col3"> <p>Die ID des Containers, der ID-Synchronisierungen auslöst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Eigenschaften-IDs, die alle Eigenschaften enthalten, die ein Besucher im Ereignisaufruf realisiert (für die er qualifiziert ist) hat. </p> <p>Beachten Sie, dass das -Array Eigenschaften enthalten kann, für die sich der Besucher zuvor qualifiziert hatte und für die er sich durch diesen Ereignisaufruf erneut qualifiziert hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, die alle Segmente enthalten, die ein Besucher im Ereignisaufruf realisiert (für die er qualifiziert ist) hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Eine Zeichenfolge, die alle Parameter erfasst (Variablen, IDs, Schlüssel-Wert-Paare, Geräte-Werbe-IDs usw.) beim Ereignisaufruf übergeben wird. </p> <p>Kurzes Beispiel: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die nicht kodierte URL der verweisenden Seite (falls vorhanden). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die IP-Adresse des Besuchers, der im Ereignisaufruf erfasst wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die dem Site-Besucher zugewiesene <span class="keyword">-Experience Cloud</span>-ID (MID). Siehe auch <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und der Adobe Experience Platform Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segment-IDs, die zuvor realisierte Segmente und neue Segmente enthalten, für die der Besucher qualifiziert ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerisches Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Erstanbieter- und Drittanbieter-Eigenschafts-IDs, die zuvor realisierte Eigenschaften und neue Eigenschaften enthalten, für die sich der Besucher seit dem letzten generierten Daten-Feed qualifiziert hat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Dateistruktur {#cdf-file-structure}

Listet die Datenstruktur einer [!UICONTROL CDF]-Datei auf und definiert sie. Dazu gehören Datensequenz, Feldtrennzeichen und Trennzeichen, eine Datendateizuordnung und eine Beispieldatei.

## Datenfeld-IDs und -Sequenzen {#identifiers-and-sequence}

[!UICONTROL CDF] -Dateien enthalten keine gekennzeichneten Spalten oder Feldkopfzeilen. Stattdessen definiert eine [!UICONTROL CDF]-Datei Felder und Arrays mit nicht druckbaren [!DNL ASCII]-Zeichen. Außerdem werden in der Datei [!UICONTROL CDF] jedes Feld und Array in einer bestimmten Reihenfolge aufgelistet. Mithilfe der Kennungen und der Reihenfolge der Felder können Sie die Datei richtig analysieren.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF-Dateielement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Feldtrennzeichen und -trennzeichen </p> </td> 
   <td colname="col2"> <p>Diese nicht druckbaren Zeichen definieren die Elemente und die Struktur Ihrer CDF-Datei: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Strg + A (ASCII <code> 001</code> oder <code> ^A</code>) trennt Daten in einzelnen Feldern mit einer nicht druckbaren Leerzeichen. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Strg + b (ASCII <code> 002</code> oder <code> ^B</code>) trennt Daten, ein Array und Anforderungsparameter. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Strg + C (ASCII <code> 003</code> oder <code> ^C</code>) definiert Schlüssel-Wert-Paare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feldsequenz </p> </td> 
   <td colname="col2"> <p> <p>Wichtig: <span class="keyword"> Audience Manager</span> behält sich das Recht vor, neue Felder am Ende der CDF-Datei in zukünftigen Versionen hinzuzufügen. Das bedeutet, dass das technische Design Ihres Dateianalysesystems keine feste Anzahl von Spalten annehmen sollte (obwohl es eine feste Reihenfolge für vorhandene Spalten annehmen kann). </p> </p> <p>Daten in Ihrer CDF-Datei werden in der unten gezeigten Reihenfolge angezeigt. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ereigniszeit </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Gerät </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Behälter-ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Realisierte Eigenschaften </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Realisierte Segmente </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Anfrageparameter </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-Adresse </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud Device ID (oder MID). Siehe auch <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und der Adobe Experience Platform Identity-Dienst</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Alle Segmente </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alle Eigenschaften </li> 
     </ol> </p> <p>Feldbeschreibungen finden Sie unter <a href="#cdf-defined"> Definierte Kundendaten-Feed-Inhalte</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Dateizuordnung {#cdf-file-map}

[!UICONTROL CDF] -Dateidaten werden in der unten gezeigten Reihenfolge angezeigt.

![](assets/sequence-map.png)

## Identifizieren von Arrays

Arrays in einer [!UICONTROL CDF]-Datei beginnen und enden mit dem `Ctrl + a`-Feldtrennzeichen. Dadurch wird das erste Element in einem Array wie ein eigenständiges Datenfeld angezeigt. Beispielsweise beginnt das realisierte [!UICONTROL traits]-Array mit `^A1234`. Das Array-Trennzeichen und die ID `^B5678` folgen diesem Eintrag. Daher könnten Sie versucht sein zu glauben, dass das erste Element im realisierten [!UICONTROL traits]-Array die ID 5678 ist (da es mit `^B` beginnt). Dies ist nicht der Fall. Daher müssen Sie mit der Sequenz und Struktur einer Datendatei vertraut sein. Obwohl das erste Element im realisierten [!UICONTROL trait]-Array (oder einem der anderen Arrays in einer [!UICONTROL CDF]-Datei) mit `^A` beginnt, definiert die Reihenfolge des Erscheinungsbilds oder der Position in der Datei den Anfang eines Arrays. Und das erste Element in einem Array wird immer vom vorherigen Eintrag durch `^A` getrennt.

## Beispieldatei [!UICONTROL CDF] {#sample-file}

Eine [!UICONTROL CDF]-Beispieldatei könnte in etwa wie folgt aussehen: Wir haben Zeilenumbrüche in dieses Beispiel eingefügt, damit es an die Seite angepasst werden kann.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Namenskonventionen für Dateien {#cdf-naming-conventions}

In den folgenden Abschnitten werden die Elemente in Ihrem [!UICONTROL CDF]-Dateinamen aufgelistet und definiert.

## [!UICONTROL CDF] Dateiname: Syntax und Beispiel {#cdf-file-name}

Ein typischer [!UICONTROL CDF]-Dateiname enthält die unten aufgeführten Elemente. Hinweis: *kursiv* gibt einen Variablenplatzhalter an:

### Syntax

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Beispiel

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

Im Speicher-Bucket [!DNL S3] werden Dateien in aufsteigender Reihenfolge nach Partner-ID ([!UICONTROL PID]), Tag und Stunde sortiert.

## [!UICONTROL CDF] Definierte Dateinamenelemente {#cdf-file-name-elements}

In der folgenden Tabelle sind die Elemente in einem [!UICONTROL CDF]-Dateinamen aufgeführt und definiert.

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
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Der Name des schreibgeschützten S3-Buckets, der Ihre CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem Ihre Datei verarbeitet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitwert, der in 24-Stunden-Notation ausgedrückt und in der UTC-Zeitzone festgelegt wird. Siehe auch <a href="#different-processing-times"> Zeitpunkte für CDF-Dateien und Zeiten für Dateiinhalte ...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Ihre Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Eine interne Prozess-ID, <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Eine gzip-Dateierweiterung. CDF-Dateien sind gzip-komprimiert. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Dateiverarbeitungsbenachrichtigungen {#cdf-file-processing-notifications}

[!DNL Audience Manager] schreibt eine  `.info` Datei in Ihr  [!DNL S3] Verzeichnis, um Sie darüber zu informieren, wann Ihr ( [!UICONTROL Customer Data File] [!UICONTROL CDF]) zum Download bereit ist. Die `.info`-Datei enthält auch [!DNL JSON] formatierte Metadaten zum Inhalt Ihrer [!UICONTROL CDF]-Dateien. In diesem Abschnitt finden Sie Informationen zur Syntax und zu den Feldern, die von dieser Benachrichtigungsdatei verwendet werden.

## Beispiel-Info-Datei {#sample-info-file}

Jede `.info`-Datei enthält einen Abschnitt `Files` und `Totals` . Der Abschnitt `Files` enthält ein Array, das spezifische Metriken für jede stündliche Datei enthält. Der Abschnitt `Totals` enthält Metriken, die über all Ihre [!UICONTROL CDF]-Dateien für einen bestimmten Tag hinweg aggregiert werden. Der Inhalt Ihrer `.info`-Datei könnte in etwa wie im folgenden Beispiel aussehen.

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

## Definierte Informationsdateifelder {#info-file-fields-defined}

In den folgenden Tabellen sind die Elemente in einer [!UICONTROL CDF] `.info`-Datei aufgeführt und definiert.

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
   <td colname="col2"> <p>Startet das Array, das Metadaten zu Ihren CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Das Amazon S3 ETag. Die Zahl nach dem Bindestrich zeigt die Anzahl der Teile an, die zum Erstellen der Datei während des mehrteiligen Uploads verwendet wurden. <code> ETag</code> ist nicht mit der MD5-Prüfsumme der Datei identisch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Der Dateiname. Siehe <a href="#cdf-naming-conventions"> Namenskonventionen für CDF-Dateien</a>. </p> </td> 
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
   <td colname="col2"> <p>Startet das Objekt, das aggregierte Daten zu allen CDF-Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Der Tag, für den die Daten verfügbar sind. Verwendet das Format <i>yyyy-mm-dd</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Die Stunde, für die Daten verfügbar sind. Verwendet das in der UTC-Zeitzone eingestellte 24-Stunden-Format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtgröße aller CDF-Dateien für dieses Datum in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtzahl der in das S3-Verzeichnis hochgeladenen Dateien. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Dateinamenzeiten und Dateiinhaltszeiten sind unterschiedlich {#different-processing-times}

Ihre [!UICONTROL CDF]-Datei enthält Zeitstempel im Dateinamen und Dateiinhalt. Diese Zeitstempel zeichnen verschiedene Ereignisprozesse für dieselbe [!UICONTROL CDF]-Datei auf. Es ist nicht ungewöhnlich, verschiedene Zeitstempel im Namen und Inhalt derselben Datei zu sehen. Die Kenntnis jedes Zeitstempels kann Ihnen dabei helfen, häufige Fehler beim Arbeiten mit diesen Daten oder beim Versuch, sie nach Zeit zu sortieren, zu vermeiden.

## Suchen nach [!UICONTROL CDF] Datei-Zeitstempeln {#locating-timestamps}

[!UICONTROL CDF] -Dateien verzeichnen die Zeit an zwei verschiedenen Speicherorten unterschiedlich.

![](assets/cdf-timestamp.png)

## Unterschiede zwischen Zeitstempeln verstehen {#understanding-timestamps}

Die folgende Tabelle enthält weitere Details zu Ihren [!UICONTROL CDF] Datei-Zeitstempeln sowie Informationen zur ordnungsgemäßen Verwendung dieser Zeitstempel.

| Zeitstempelstandort | Beschreibung |
|--- |--- |
| Dateiname | Der Zeitstempel im Dateinamen [!DNL CDF] gibt den Zeitpunkt an, zu dem [!DNL Audience Manager] mit der Vorbereitung der Datei für die Bereitstellung begonnen hat. Dieser Zeitstempel wird in der Zeitzone [!DNL UTC] festgelegt. Es wird der Parameter `hour=` verwendet, wobei die Zeit als 2-stellige Stunde in 24-Stunden-Notation formatiert ist. Diese Zeit kann sich von der im Dateiinhalt aufgezeichneten Ereigniszeit unterscheiden. Beim Arbeiten mit [!DNL CDF]-Dateien werden Sie manchmal feststellen, dass Ihr [!DNL S3]-Bucket für eine bestimmte Stunde leer ist. Ein leerer Behälter bedeutet, dass er eine der folgenden Bedeutungen haben kann:<ul><li>Für diese bestimmte Stunde liegen keine Daten vor. </li><li> Unsere Server sind stark ausgelastet und können Dateien für eine bestimmte Stunde nicht verarbeiten. Wenn der Server den Upload aufnimmt, werden die Dateien, die in frühere Zeitbehälter-Dateien hätte aufgenommen werden sollen, in einen Bucket mit einem späteren Zeitwert eingefügt. Dies wird beispielsweise angezeigt, wenn eine Datei, die in der Gruppe &quot;Stunde 17&quot;enthalten sein sollte, im Bucket &quot;Stunde 18&quot;angezeigt wird (mit `hour=18` im Dateinamen). In diesem Fall hat der Server wahrscheinlich mit der Verarbeitung Ihrer Datei in Stunde 17 begonnen, konnte sie jedoch nicht innerhalb dieses Zeitintervalls abschließen. Stattdessen wird die Datei an den nächsten stündlichen Zeitbehälter gesendet.</li></ul><br>**Wichtig**: Verwenden Sie nicht den Zeitstempel des Dateinamens, um Ereignisse nach Zeit zu gruppieren. Wenn Sie eine Gruppierung nach Zeit durchführen müssen, verwenden Sie den Zeitstempel `EventTime` im Dateiinhalt. |
| Dateiinhalt | Der Zeitstempel in Ihrem [!DNL CDF]-Dateiinhalt markiert den Zeitpunkt, zu dem [!DNL Data Collection Servers] mit der Verarbeitung der Datei begonnen hat. Dieser Zeitstempel wird in der Zeitzone [!DNL UTC] festgelegt. Es wird das Feld `EventTime` verwendet, wobei die Zeit als *`yyyy-mm-dd hh:mm:ss`* formatiert ist. Diese Zeit entspricht in etwa der tatsächlichen Zeit des Ereignisses auf der Seite, kann sich jedoch von der Stundenanzeige im Dateinamen unterscheiden. <br> **Tipp**: Im Gegensatz zum  `hour=` Zeitstempel im Dateinamen können Sie  `EventTime` zum Gruppieren von Daten nach Zeit verwenden. |

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Kundendaten-Feeds](../faq/faq-cdf.md)

