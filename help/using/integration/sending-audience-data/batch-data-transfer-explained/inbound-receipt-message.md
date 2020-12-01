---
description: Bei jeder Verarbeitung einer eingehenden Server-zu-Server-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet.
seo-description: Bei jeder Verarbeitung einer eingehenden Server-zu-Server-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet.
seo-title: Beispielnachricht an Partner nach der eingehenden Verarbeitung
solution: Audience Manager
title: Beispielnachricht an Partner nach der eingehenden Verarbeitung
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 3%

---


# Beispielnachricht an Partner nach der eingehenden Verarbeitung{#sample-message-to-partners-after-inbound-processing}

Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server]-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet.

<!-- r_inbound_message.xml -->

Das folgende Beispiel zeigt eine E-Mail-Musternachricht. Die Tabelle unter der Nachricht beschreibt die verschiedenen Zeilen in der Nachricht.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Von: aam-noreply@adobe.com  </b> </p> <p> <b>Betrifft: Adobe Audience Manager Server-to-Server-Verarbeitungsergebnis:</b> </p> <p> <b>Sehr geehrte Adobe Partner: (ID:7)</b> <b></b> </p> <p> <b>Wir haben Ihren Adobe Audience Manager Server-to-Server-Versand erhalten.</b> </p> <p> <b>Dateiname:</b> <i></i> </p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>eingegangenen Aufzeichnungen: 40669900</b> </p> <p><b>Formatfehler: 0</b> </p> <p> <b>Ungültige AAM-ID: 112  </b> </p> <p> <b>Keine übereinstimmende AAM-ID: 0  </b> </p> <p> <b>Keine Eigenschaft realisiert: 26730823  </b> </p> <p> <b>Aufbereitete Datensätze: 40669900  </b> </p> <p> <b>Gespeicherte Datensätze: 13938958  </b> </p> <p> <b>Geräte insgesamt: 21  </b> </p> <p> <b>Signale insgesamt: 918878926  </b> </p> <p> <b>Nicht verwendete Signale insgesamt: 660348376  </b> </p> <p> <b>Gesamtzahl der realisierten Eigenschaften: 258086908  </b> </p> <p> <b>Entfernte Eigenschaften insgesamt: 0  </b> </p> <p> <b>Überprüfung der Gesamtzahl der Eigenschaften fehlgeschlagen: 0  </b> </p> <p> <b>Gesamtzahl der Benutzer mit Eigenschaften, bei denen die Überprüfung fehlgeschlagen ist: 0  </b> </p> <p> <b>Beginn des Auftrags: 2018-05-17 18:07:49  </b> </p> <p> <b>Auftragsendzeit: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Die folgende Tabelle enthält Zeilen, die den Zeilen in der empfangenen E-Mail entsprechen.

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
   <td colname="col2"> <p>Liste aller eingehenden Dateien, die die Adobe für diesen Partner erhalten hat und die zusammen verarbeitet wurden. In der vorherigen Beispiel-E-Mail-Nachricht ist die Partner-ID 7 und die Dateneigner-ID 901. </p> <p>Die Zahl "Tail"(1,2,3...) ist die vom Kunden oder vom Händler hinzugefügte Teilungsnummer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aufgenommene Aufzeichnungen </td> 
   <td colname="col2"> <p>Gesamtzahl der Adoben, die in allen Dateien eingegangen sind. In den meisten Fällen sollte dies die Gesamtanzahl der Zeilen in eingehenden Dateien sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formatfehler </td> 
   <td colname="col2"> <p>Anzahl der Zeilen, die nicht dem erwarteten Format entsprachen. Diese Linien waren vom Inbound-Auftrag nicht erkennbar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ungültige AAM-ID </td> 
   <td colname="col2"> <p>Anzahl der Audience Manager-UUIDs, die nicht dem erwarteten 38-stelligen Format entsprachen. Oder die Audience Manager-UUIDs, die in der Datei gesendet werden, sind keine Zahlen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine übereinstimmende AAM-ID </td> 
   <td colname="col2"> <p>Gesamtanzahl der Benutzer, für die Audience Manager keine übereinstimmende UUID gefunden haben. Diese Dateien wurden nicht mit ID synchronisiert, sodass Audience Manager die UUID nicht nachschlagen kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine Eigenschaft realisiert </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, bei denen keines der Signale auf der Linie einem Audience Manager-Merkmal zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aufbereitete Datensätze </td> 
   <td colname="col2"> <p>Gesamtzahl der verarbeiteten Datensätze, Audience Manager. In den meisten Fällen sollte diese Zahl mit der Zahl der eingegangenen Datensätze übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gespeicherte Datensätze </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die dazu führen, dass Daten in das System geladen werden = verarbeitete Datensätze - Formatfehler - Ungültige AAM-IDs - Keine übereinstimmende AAM-ID - Keine Eigenschaft erkannt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geräte insgesamt </td> 
   <td colname="col2"> <p>Anzahl der Geräte, auf denen Daten in das System geladen wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Signale insgesamt </td> 
   <td colname="col2"> <p> Gesamtanzahl der Signale für alle Benutzer in allen eingehenden Dateien (Gesamtanzahl der Schlüssel/Wert-Paare in den verarbeiteten Datensätzen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nicht verwendete Signale </td> 
   <td colname="col2"> <p>Gesamtanzahl der nicht verwendeten Signale für alle Benutzer in allen eingehenden Dateien (Schlüssel/Wert-Paare, die nicht den Eigenschaften des Audience Managers zugeordnet wurden). In den meisten Fällen bedeutet dies, dass für Audience Manager keine Signalregeln definiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl der realisierten Eigenschaften </td> 
   <td colname="col2"> <p>Anzahl der Audience Manager-Eigenschaften für alle Benutzer in allen eingehenden Dateien, basierend auf den Signalen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl entfernter Eigenschaften </td> 
   <td colname="col2"> <p> Gesamtanzahl der entfernten Eigenschaften für alle Benutzer in allen eingehenden Dateien. Bei vollständigen Synchronisierungen geschieht dies, wenn der Benutzer die Eigenschaft in einem vorherigen, aber nicht in der aktuellen Ausführung hatte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Überprüfung der Gesamtzahl der Eigenschaften fehlgeschlagen </td> 
   <td colname="col2"> <p>Stellt die Anzahl der Eigenschaften dar, die nicht zur Datenquelle gehören, die im Dateinamen deklariert wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gesamtzahl der Benutzer mit Eigenschaften, bei denen die Überprüfung fehlgeschlagen ist </td> 
   <td colname="col2"> <p>Die Anzahl der Datensätze mit Eigenschaften, bei denen die Überprüfung fehlgeschlagen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Beginn </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag Beginn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auftragsendzeit </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag endet. </p> </td> 
  </tr> 
 </tbody> 
</table>