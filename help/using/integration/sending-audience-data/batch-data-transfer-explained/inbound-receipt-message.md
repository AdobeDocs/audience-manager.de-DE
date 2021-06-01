---
description: Bei jeder Verarbeitung einer eingehenden Server-zu-Server-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet.
seo-description: Bei jeder Verarbeitung einer eingehenden Server-zu-Server-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet.
seo-title: Beispielnachricht an Partner nach der eingehenden Verarbeitung
solution: Audience Manager
title: Beispielnachricht an Partner nach der eingehenden Verarbeitung
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Übertragungen von Inbound-Daten
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---

# Beispielnachricht an Partner nach der eingehenden Verarbeitung{#sample-message-to-partners-after-inbound-processing}

Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server]-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet.

<!-- r_inbound_message.xml -->

Das folgende Beispiel zeigt eine Beispiel-E-Mail-Nachricht. In der Tabelle unter der Nachricht werden die einzelnen Zeilen der Nachricht beschrieben.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Von: aam-noreply@adobe.com  </b> </p> <p> <b>Betrifft: Adobe Audience Manager Server-zu-Server-Verarbeitungsergebnis:</b> </p> <p> <b>Sehr geehrte Adobe Partner: (ID:7)</b> <b></b> </p> <p> <b>Wir haben Ihre Adobe Audience Manager Server-to-Server-Dateibereitstellung erhalten</b> </p> <p> <b>Dateiname:</b> <i></i> </p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>Empfangsbestätigungen: 40669900</b> </p> <p><b>Formatfehler: 0</b> </p> <p> <b>Ungültige AAM-ID: 112  </b> </p> <p> <b>Keine übereinstimmende AAM-ID: 0  </b> </p> <p> <b>Keine Eigenschaft realisiert: 26730823  </b> </p> <p> <b>Verarbeitete Datensätze: 40669900  </b> </p> <p> <b>Gespeicherte Datensätze: 13938958  </b> </p> <p> <b>Geräte insgesamt: 21  </b> </p> <p> <b>Signale insgesamt: 918878926  </b> </p> <p> <b>Ungenutzte Signale insgesamt: 660348376  </b> </p> <p> <b>Gesamtzahl der realisierten Eigenschaften: 258086908  </b> </p> <p> <b>Gesamtzahl entfernter Eigenschaften: 0  </b> </p> <p> <b>Validierung der Gesamteigenschaften fehlgeschlagen: 0  </b> </p> <p> <b>Gesamtzahl der Benutzer mit Eigenschaften, bei denen die Validierung fehlgeschlagen ist: 0  </b> </p> <p> <b>Auftragsstartzeit: 17.05.2018 18:07:49  </b> </p> <p> <b>Auftragsendzeit: 17.05.2018 18:45:02</b> </p> </td> 
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
   <td colname="col2"> <p>Liste aller eingehenden Dateien, die die Adobe für diesen Partner erhalten hat und die zusammen verarbeitet wurden. In der vorherigen Beispiel-E-Mail-Nachricht ist die Partner-ID 7 und die Dateneigentümer-ID 901. </p> <p>Die Nummer "tail" (1,2,3 ...) ist die vom Kunden oder vom eingehenden Distributor hinzugefügte Splitnummer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erhaltene Aufzeichnungen </td> 
   <td colname="col2"> <p>Gesamtzahl der in allen Adoben empfangenen Datensätze. In den meisten Fällen sollte dies die Gesamtanzahl der Zeilen in eingehenden Dateien sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formatfehler </td> 
   <td colname="col2"> <p>Anzahl der Zeilen, die nicht dem erwarteten Format entsprachen. Diese Zeilen wurden vom eingehenden Auftrag nicht erkannt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ungültige AAM-ID </td> 
   <td colname="col2"> <p>Anzahl der Audience Manager-UUIDs, die nicht dem erwarteten 38-stelligen Format entsprachen. Oder die Audience Manager-UUIDs, die in der Datei gesendet werden, sind keine Zahlen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine übereinstimmende AAM-ID </td> 
   <td colname="col2"> <p>Gesamtzahl der Benutzer, für die der Audience Manager keine übereinstimmende UUID gefunden hat. Diese Dateien wurden nicht mit ID synchronisiert, sodass Audience Manager die UUID nicht nachschlagen können. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine Eigenschaft realisiert </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, bei denen keines der Signale auf der Zeile einer Audience Manager-Eigenschaft zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verarbeitete Datensätze </td> 
   <td colname="col2"> <p>Gesamtzahl der verarbeiteten Datensätze im Audience Manager. In den meisten Fällen sollte diese Zahl mit der Anzahl der empfangenen Datensätze übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gespeicherte Datensätze </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die dazu führen, dass Daten in das System geladen werden = verarbeitete Datensätze - Formatfehler - Ungültige AAM IDs - Keine Übereinstimmung AAM ID - Keine Eigenschaft realisiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geräte insgesamt </td> 
   <td colname="col2"> <p>Anzahl der Geräte, für die Daten in das System geladen wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamte Signale </td> 
   <td colname="col2"> <p> Gesamtzahl der Signale für alle Benutzer in allen eingehenden Dateien (Gesamtzahl der Schlüssel/Wert-Paare in den verarbeiteten Datensätzen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ungenutzte Signale insgesamt </td> 
   <td colname="col2"> <p>Gesamtzahl des nicht verwendeten Signals für alle Benutzer über alle eingehenden Dateien (Schlüssel/Wert-Paare, die nicht den Eigenschaften des Audience Managers zugeordnet waren). In den meisten Fällen bedeutet dies, dass für den Audience Manager keine Signalregeln definiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl der realisierten Eigenschaften </td> 
   <td colname="col2"> <p>Anzahl der Signaleigenschaften für alle Audience Manager in allen eingehenden Dateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl entfernter Eigenschaften </td> 
   <td colname="col2"> <p> Gesamtzahl der entfernten Eigenschaften für alle Benutzer in allen eingehenden Dateien. Bei vollständigen Synchronisierungen geschieht dies, wenn der Benutzer die Eigenschaft in einer vorherigen Ausführung, aber nicht im aktuellen Lauf hatte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Validierung von Eigenschaften insgesamt fehlgeschlagen </td> 
   <td colname="col2"> <p>Stellt die Anzahl der Eigenschaften dar, die nicht zur im Dateinamen deklarierten Datenquelle gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl der Benutzer mit Eigenschaften, bei denen die Validierung fehlgeschlagen ist </td> 
   <td colname="col2"> <p>Die Anzahl der Datensätze mit Eigenschaften, bei denen die Validierung fehlgeschlagen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Startzeit des Auftrags </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag gestartet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auftragsendzeit </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag endet. </p> </td> 
  </tr> 
 </tbody> 
</table>
