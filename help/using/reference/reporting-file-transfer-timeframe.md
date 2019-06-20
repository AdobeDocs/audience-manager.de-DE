---
description: Audience Manager erhält jeden Tag eine enorme Menge an Daten. Dies wirkt sich auf die Zeit aus, die zum Verarbeiten Ihrer Daten benötigt wird, und generiert Berichtsergebnisse. Der Inhalt in diesem Abschnitt beschreibt, wie diese Zeitintervalle Ihr Audience Manager-Konto beeinflussen. Außerdem sind die hier beschriebenen Zeitrahmen und Zeitpläne nur allgemeine Richtlinien. Diese Pläne stellen keine slas (Service Level Agreements) oder Verpflichtungen bezüglich der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitrahmen und Zeitpläne jederzeit ohne Vorankündigung zu ändern.
seo-description: Audience Manager erhält jeden Tag eine enorme Menge an Daten. Dies wirkt sich auf die Zeit aus, die zum Verarbeiten Ihrer Daten benötigt wird, und generiert Berichtsergebnisse. Der Inhalt in diesem Abschnitt beschreibt, wie diese Zeitintervalle Ihr Audience Manager-Konto beeinflussen. Außerdem sind die hier beschriebenen Zeitrahmen und Zeitpläne nur allgemeine Richtlinien. Diese Pläne stellen keine slas (Service Level Agreements) oder Verpflichtungen bezüglich der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitrahmen und Zeitpläne jederzeit ohne Vorankündigung zu ändern.
seo-title: Einfluss der Datenauslieferung und der Dateiverarbeitungszeiten auf Berichte
solution: Audience Manager
title: Einfluss der Datenauslieferung und der Dateiverarbeitungszeiten auf Berichte
uuid: 4 b 975512-f 67 e -4749-a 7 ef -168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager erhält jeden Tag eine enorme Menge an Daten. Dies wirkt sich auf die Zeit aus, die zum Verarbeiten Ihrer Daten benötigt wird, und generiert Berichtsergebnisse. Der Inhalt in diesem Abschnitt beschreibt, wie diese Zeitintervalle Ihr Audience Manager-Konto beeinflussen. Außerdem sind die hier beschriebenen Zeitrahmen und Zeitpläne nur allgemeine Richtlinien. Diese Pläne stellen keine slas (Service Level Agreements) oder Verpflichtungen bezüglich der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitrahmen und Zeitpläne jederzeit ohne Vorankündigung zu ändern.

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

In der folgenden Tabelle sind die Zeitintervalle in unseren allgemeinen und Echtzeitberichten aufgeführt und beschrieben.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datentyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Echtzeitdaten</b> </p> </td> 
   <td colname="col2"> <p> Die Echtzeitzahlen für heute sind für die Stunden 00:00 bis 23:59:59 UTC von gestern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Allgemeine Berichtsdaten</b> </p> </td> 
   <td colname="col2"> <p>The data in the <a href="../reporting/general-reports.md#general-reports-overview"> General Reports</a> depends on the successful completion of other job processes and the amount of data received for a particular day. Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verarbeitet und sendet eingehende und ausgehende [!UICONTROL Server-to-Server (S2S)] Dateiübertragungen gemäß den in diesem Abschnitt beschriebenen Plänen. In diesen Zeitplänen und den Zeitüberschreitungszeiten werden möglicherweise Diskrepanzen bei neuen Segmenten zwischen Echtzeit- und Gesamtsegmentzahlen angezeigt.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateityp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Inbound File Capture (Offline-Daten)</b> </p> </td> 
   <td colname="col2"> <p>Die Dateiverarbeitung wird zweimal pro Tag ausgeführt. Diese Verfahren erfassen Daten und bereiten die Bereitstellung vor. </p> <p>Die Dateibereitstellungszeiten variieren, da sie von der Gesamtmenge an Kundendaten betroffen sind, die verarbeitet werden müssen. You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ausgehende (Exportieren) Dateien</b> </p> </td> 
   <td colname="col2"> <p>Die Dateiverarbeitung und Bereitstellung erfolgt einmal pro Tag und ca. 14:00 UTC. Beachten Sie, dass die Verarbeitung und Bereitstellung von der Gesamtanzahl und der Größe dieser Dateien betroffen sind. In einigen Fällen kann die Dateiverarbeitung länger als 24 Stunden dauern. When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. Anhand dieser Bedingungen ist es schwierig, die Bereitstellungszeiten für ausgehende Daten zu schätzen. </p> <p>Um festzustellen, ob Sie einen vollständigen Dateisatz erhalten haben, überprüfen Sie den Zeitstempel und suchen Sie nach fehlenden Tagen. Dies ist ein 13-stelliger UNIX UTC-Zeitstempel, der den Zeitpunkt der Erstellung der Datei aufzeichnet. See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zur Datenaufnahme in eingehende Kunden](../faq/faq-inbound-data-ingestion.md)

