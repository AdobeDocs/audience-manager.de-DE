---
description: Bei jeder Verarbeitung einer eingehenden Server-zu-Server-Datei wird eine Quittung per E-Mail an die Partnerlösungen und, falls konfiguriert, an den Partner gesendet.
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: Beispielnachricht an Partner nach der eingehenden Verarbeitung
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Beispielnachricht an Partner nach der eingehenden Verarbeitung{#sample-message-to-partners-after-inbound-processing}

Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server]-Datei wird eine Quittung per E-Mail an die Partnerlösungen und, falls konfiguriert, an den Partner gesendet.

<!-- r_inbound_message.xml -->

Im folgenden Beispiel wird eine E-Mail-Beispielnachricht angezeigt. In der Tabelle unter der Meldung werden die verschiedenen Zeilen der Meldung beschrieben.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Von: aam-noreply@adobe.com </b> </p> <p> <b>Betreff: Ergebnis der Adobe Audience Manager-Server-zu-Server-Verarbeitung:</b> </p> <p> <b>Sehr geehrter Adobe-Partner: (ID:7)</b> <b></b> </p> <p> <b>Wir haben Ihre Adobe Audience Manager Server-zu-Server-Dateibereitstellung erhalten</b> </p> <p> <b>Dateiname:</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Empfangene Einträge: 40669900</b> </p> <p><b>Formatfehler: 0</b> </p> <p> <b>Ungültige AAM-ID: 112 </b> </p> <p> <b>Keine übereinstimmende AAM-ID: 0 </b> </p> <p> <b>Keine Eigenschaft erkannt: 26730823 </b> </p> <p> <b>Verarbeitete Datensätze: 40669900 </b> </p> <p> <b>Gespeicherte Datensätze: 13938958 </b> </p> <p> <b>Geräte insgesamt: 21 </b> </p> <p> <b>Signale insgesamt: 918878926 </b> </p> <p> <b>Ungenutzte Signale insgesamt: 660348376 </b> </p> <p> <b>Insgesamt realisierte Eigenschaften: 258086908 </b> </p> <p> <b>Insgesamt entfernte Eigenschaften: 0 </b> </p> <p> <b>Fehlgeschlagene Validierung der Eigenschaften insgesamt: 0 </b> </p> <p> <b>Gesamtzahl der Benutzer mit Eigenschaften, bei denen die Validierung fehlgeschlagen ist: 0 </b> </p> <p> <b>Startzeit des Jobs: 17.05.2018 18:07:49 </b> </p> <p> <b>Endzeit des Auftrags: 17.05.2018:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die folgende Tabelle enthält Zeilen, die den Zeilen in der empfangenen E-Mail-Nachricht entsprechen.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linie </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dateiname </td> 
   <td colname="col2"> <p>Liste aller eingehenden Dateien, die Adobe für diesen Partner erhalten hat und die gemeinsam verarbeitet wurden. In der vorherigen Beispiel-E-Mail-Nachricht ist die Partner-ID 7 und die Dateneigentümer-ID 901. </p> <p>Die Hecknummer (1,2,3…) ist die Aufspaltungsnummer, die entweder vom Kunden oder vom Inbound-Distributor hinzugefügt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Empfangene Einträge </td> 
   <td colname="col2"> <p>Gesamtzahl der empfangenen Adobe-Einträge in allen Dateien. In den meisten Fällen sollte dies die Gesamtzahl der Zeilen in den eingehenden Dateien sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formatfehler </td> 
   <td colname="col2"> <p>Anzahl der Zeilen, die nicht dem erwarteten Format entsprechen. Diese Zeilen wurden vom eingehenden Auftrag nicht erkannt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ungültige AAM-ID </td> 
   <td colname="col2"> <p>Anzahl der Audience Manager-UUIDs, die nicht dem erwarteten 38-stelligen Format entsprachen. Oder die Audience Manager-UUIDs, die in der Datei gesendet werden, sind keine Zahlen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine übereinstimmende AAM-ID </td> 
   <td colname="col2"> <p>Gesamtzahl der Benutzenden, für die der Audience Manager keine übereinstimmende UUID gefunden hat. Diese Dateien wurden nicht mit der ID synchronisiert, sodass der Audience Manager die UUID nicht suchen kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine Eigenschaft erkannt </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, bei denen keines der Signale auf der Zeile einer Audience Manager-Eigenschaft zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verarbeitete Datensätze </td> 
   <td colname="col2"> <p>Gesamtzahl der vom Audience Manager verarbeiteten Datensätze. In den meisten Fällen sollte diese Zahl mit „Empfangene Datensätze“ übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gespeicherte Datensätze </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die zu den in das System zu ladenden Daten führen = Datensätze verarbeitet - Formatfehler - Ungültige AAM-IDs - Keine übereinstimmende AAM-ID - Keine Eigenschaft erkannt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geräte insgesamt </td> 
   <td colname="col2"> <p>Anzahl der Geräte, für die Daten in das System geladen wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Signale insgesamt </td> 
   <td colname="col2"> <p> Gesamtzahl der Signale für alle Benutzer in allen eingehenden Dateien (Gesamtzahl der Schlüssel/Wert-Paare in den verarbeiteten Datensätzen) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ungenutzte Signale insgesamt </td> 
   <td colname="col2"> <p>Gesamtzahl der nicht verwendeten Signale für alle Benutzer in allen eingehenden Dateien (Schlüssel/Wert-Paare, die nicht den Audience Manager-Eigenschaften zugeordnet sind). In den meisten Fällen bedeutet dies, dass für den Audience Manager keine Regeln für das Signal definiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Insgesamt realisierte Eigenschaften </td> 
   <td colname="col2"> <p>Anzahl der Signaleigenschaften für alle Audience Manager in allen eingehenden Dateien basierend auf den Signalen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Insgesamt entfernte Eigenschaften </td> 
   <td colname="col2"> <p> Gesamtzahl der entfernten Eigenschaften aller Benutzer in allen eingehenden Dateien. Bei vollständigen Synchronisationen geschieht dies, wenn der Benutzer die Eigenschaft in einer vorherigen Ausführung hatte, aber nicht in der aktuellen Ausführung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlgeschlagene Validierung der Eigenschaften insgesamt </td> 
   <td colname="col2"> <p>Stellt die Anzahl der Eigenschaften dar, die nicht zu der im Dateinamen angegebenen Datenquelle gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl der Benutzenden mit Eigenschaften, bei denen die Validierung fehlgeschlagen ist </td> 
   <td colname="col2"> <p>Die Anzahl der Datensätze mit Eigenschaften, deren Validierung fehlgeschlagen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Startzeit des Auftrags </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag gestartet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endzeit des Auftrags </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag beendet wird. </p> </td> 
  </tr> 
 </tbody> 
</table>
