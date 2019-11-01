---
description: Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf den Zeitraum aus, der für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. Der Inhalt in diesem Abschnitt beschreibt, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Die hier beschriebenen Zeitrahmen und Zeitpläne sind ebenfalls nur allgemeine Richtlinien. Diese Zeitpläne stellen keine Service-Level Agreements (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeiträume und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.
seo-description: Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf den Zeitraum aus, der für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. Der Inhalt in diesem Abschnitt beschreibt, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Die hier beschriebenen Zeitrahmen und Zeitpläne sind ebenfalls nur allgemeine Richtlinien. Diese Zeitpläne stellen keine Service-Level Agreements (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeiträume und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.
seo-title: Auswirkungen von Datenbereitstellung und Dateiverarbeitung auf Berichte
solution: Audience Manager
title: Auswirkungen von Datenbereitstellung und Dateiverarbeitung auf Berichte
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Auswirkungen von Datenbereitstellung und Dateiverarbeitung auf Berichte{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf den Zeitraum aus, der für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. Der Inhalt in diesem Abschnitt beschreibt, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Die hier beschriebenen Zeitrahmen und Zeitpläne sind ebenfalls nur allgemeine Richtlinien. Diese Zeitpläne stellen keine Service-Level Agreements (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeiträume und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.

## Berichtsnummern {#reporting-numbers}

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
   <td colname="col2"> <p> Echtzeit-Nummern für heute gelten für die Stunden 00:00 bis 23:59:59 UTC von gestern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Allgemeine Berichtsdaten</b> </p> </td> 
   <td colname="col2"> <p>Die Daten in den <a href="../reporting/general-reports.md#general-reports-overview"> allgemeinen Berichten</a> hängen vom erfolgreichen Abschluss anderer Auftragsabläufe und der Menge der an einem bestimmten Tag empfangenen Daten ab. Meistens sollten die Daten des <span class="wintitle"> allgemeinen Berichts</span> täglich um 18:00 Uhr (UTC) aktualisiert werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dateiübertragungen in- und ausgehende {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verarbeitet und sendet eingehende und ausgehende [!UICONTROL Server-to-Server (S2S)] Dateiübertragungen gemäß den in diesem Abschnitt beschriebenen Zeitplänen. Angesichts dieser Zeitpläne und der Cut-off-Zeiten können bei neuen Segmenten zwischen Echtzeit- und Gesamtsegmentzahlen Diskrepanzen auftreten.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateityp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Inbound File Ingestion (Offlinedaten)</b> </p> </td> 
   <td colname="col2"> <p>Die Dateiverarbeitung wird zweimal täglich ausgeführt. Diese Verfahren erfassen Daten und bereiten sie für die Bereitstellung vor. </p> <p>Die Auslieferungszeiten der Dateien variieren, da sie von der Gesamtanzahl der zu verarbeitenden Kundendaten betroffen sind. Sie sollten eine maximale Latenz von 48 Stunden zwischen dem Zeitpunkt, zu dem die Datei in <span class="keyword"> Audience Manager</span> hochgeladen wird, und dem Zeitpunkt erwarten, zu dem die Daten für die Berichterstellung und Aktivierung verfügbar sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ausgehende Dateien (Export)</b> </p> </td> 
   <td colname="col2"> <p>Die Dateiverarbeitung und -auslieferung erfolgt einmal täglich um etwa 14:00 UTC. Beachten Sie, dass die Verarbeitung und Bereitstellung durch die Gesamtanzahl und Größe dieser Dateien beeinträchtigt werden. In einigen Fällen kann es zu einer Verzögerung bei der Dateiverarbeitung bis zu 24 Stunden kommen. In diesem Fall sendet <span class="keyword"> Audience Manager</span> 2 Dateien für einen bestimmten Tag anstelle von 1. Wir werden unsere Kunden benachrichtigen, wenn <span class="keyword"> Audience Manager</span> die Verarbeitung einer Datei ganz einstellen muss. Unter diesen Umständen ist es schwierig, die Lieferzeiten für ausgehende Daten zu schätzen. </p> <p>Um festzustellen, ob Sie einen vollständigen Satz Dateien erhalten haben, überprüfen Sie den Zeitstempel und suchen Sie nach fehlenden Tagen. Dies ist ein 13-stelliger UNIX UTC-Zeitstempel, der den Zeitpunkt der Erstellung der Datei erfasst. Siehe <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Ausgehende Echtzeit-Datenübertragungen</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten](../faq/faq-inbound-data-ingestion.md)

