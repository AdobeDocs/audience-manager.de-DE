---
description: Wenn eine eingehende Server-in-Server-Datei verarbeitet wird, wird ein Beleg per E-Email an Partnerlösungen gesendet und, falls konfiguriert, dem Partner.
seo-description: Wenn eine eingehende Server-in-Server-Datei verarbeitet wird, wird ein Beleg per E-Email an Partnerlösungen gesendet und, falls konfiguriert, dem Partner.
seo-title: Beispielnachricht für Partner nach der eingehenden Verarbeitung
solution: Audience Manager
title: Beispielnachricht für Partner nach der eingehenden Verarbeitung
uuid: 69 e 3 a 8 b 3-8465-4 f 4 c -8005-8 a 9 ff 15 ae 19 a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Beispielnachricht für Partner nach der eingehenden Verarbeitung{#sample-message-to-partners-after-inbound-processing}

Wenn eine Inbound [!UICONTROL Server-to-Server] -Datei verarbeitet wird, wird ein Beleg per E-Mail an Partnerlösungen gesendet und, falls konfiguriert, dem Partner.

<!-- r_inbound_message.xml -->

Das folgende Beispiel zeigt eine Beispiel-E-Mail-Nachricht. Die Tabelle unter der Nachricht beschreibt die verschiedenen Zeilen in der Nachricht.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Von: aam-noreply@adobe.com </b> </p> <p> <b>Betreff: Adobe Audience Manager Server-Zu-Server-Verarbeitungsergebnis:</b> </p> <p> <b>Lieber Adobe Partner: (ID: 7)</b><b></b> </p> <p> <b>Wir haben Ihre Adobe Audience Manager Server-To-Server-Dateibereitstellung erhalten.</b> </p> <p> <b>Dateiname:</b><i></i> </p> <p> <b> s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806402. sync</b> </p> <p> <b> s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-16/ftp_ dpm_ 7_ 901_ 1368655202. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784804. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806403. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784802. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784803. sync </b> </p> <p> <b>s 3 n:// &lt;<i>bucket_ name &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806404. sync</b> </p> <p> <b>Empfangene Datensätze: 40669900</b> </p> <p><b>Formatfehler: 0</b> </p> <p> <b>Ungültige AAM-ID: 112 </b> </p> <p> <b>Keine übereinstimmende AAM-ID: 0 </b> </p> <p> <b>Kein Merkmal gefunden: 26730823 </b> </p> <p> <b>Datensätze verarbeitet: 40669900 </b> </p> <p> <b>Gespeicherte Datensätze: 13938958 </b> </p> <p> <b>Geräte insgesamt: 21 </b> </p> <p> <b>Signale insgesamt: 918878926 </b> </p> <p> <b>Nicht verwendete Signale: 660348376 </b> </p> <p> <b>Gesamte neu entwickelte Eigenschaften: 258086908 </b> </p> <p> <b>Insgesamt entfernte Eigenschaften: 0 </b> </p> <p> <b>Fehlgeschlagene Überprüfung der Überprüfung: 0 </b> </p> <p> <b>Benutzer mit Eigenschaften, die die Überprüfung fehlgeschlagen haben: 0 </b> </p> <p> <b>Auftragsstartzeit: 2018-05-17 18:07:49 </b> </p> <p> <b>Auftragsendzeit: 2018-05-17 18:45:02</b> </p> </td> 
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
   <td colname="col2"> <p>Liste aller eingehenden Dateien, die Adobe für diesen Partner empfangen hat, die zusammen verarbeitet wurden. In der vorherigen Beispiel-E-Email-Nachricht lautet die Partner-ID 7 und die Data Warehouse-ID 901. </p> <p>Die Zeilennummer (1,2,3…) ist die aufgeteilte Nummer, die entweder vom Kunden oder vom eingehenden Verteiler hinzugefügt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Empfangene Datensätze </td> 
   <td colname="col2"> <p>Gesamtanzahl der Datensätze, die Adobe für alle Dateien empfangen hat. In den meisten Fällen sollte dies die Gesamtzahl der Zeilen in Inbound-Dateien sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formatfehler </td> 
   <td colname="col2"> <p>Anzahl der Zeilen, die nicht mit dem erwarteten Format übereinstimmten. Diese Zeilen wurden vom eingehenden Auftrag nicht erkannt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ungültige AAM-ID </td> 
   <td colname="col2"> <p>Anzahl der uuids von Audience Manager, die nicht dem erwarteten 38-stelligen Format entsprachen. Oder die in der Datei gesendeten uuids von Audience Manager sind keine Zahlen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Keine übereinstimmende AAM-ID </td> 
   <td colname="col2"> <p>Gesamtanzahl der Benutzer, für die Audience Manager keine übereinstimmende UUID gefunden hat. Diese Dateien wurden nicht synchronisiert, sodass Audience Manager die UUID nicht nachschlagen kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kein Trait-Format </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, bei denen keines der Signale in der Zeile einer Eigenschaft Audience Manager zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datensätze verarbeitet </td> 
   <td colname="col2"> <p>Gesamtanzahl der Datensätze, die von Audience Manager verarbeitet wurden. In den meisten Fällen sollte diese Zahl mit "Empfangenen Datensätzen" identisch sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gespeicherte Datensätze </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die zu Daten führen, die in das System geladen werden = Datensätze Verarbeitet - Fehlerfehler - Ungültige AAM-IDs - keine übereinstimmende AAM-ID - Kein Merkmal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Geräte insgesamt </td> 
   <td colname="col2"> <p>Anzahl der Geräte, für die Daten in das System geladen wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Signale insgesamt </td> 
   <td colname="col2"> <p> Gesamtanzahl aller Signale für alle Benutzer in allen Inbound-Dateien (Gesamtanzahl der Schlüssel/Wert-Paare in den verarbeiteten Datensätzen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nicht verwendete Signale </td> 
   <td colname="col2"> <p>Gesamtanzahl nicht verwendeter Signal für alle Benutzer in allen Inbound-Dateien (Schlüssel/Wert-Paare, die den Audience Manager-Eigenschaften nicht zugeordnet wurden). In den meisten Fällen bedeutet dies, dass Audience Manager keine für das Signal definierten Regeln definiert hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Neu gestaltete Eigenschaften </td> 
   <td colname="col2"> <p>Anzahl der Zielgruppen-Manager-Eigenschaften für alle Benutzer auf allen Inbound-Dateien basierend auf den Signalen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entfernte Eigenschaften insgesamt </td> 
   <td colname="col2"> <p> Gesamtanzahl entfernter Eigenschaften für alle Benutzer in allen Inbound-Dateien. Für vollständige Synchronisierungen tritt dies ein, wenn der Benutzer die Eigenschaft in einem vorherigen Laufwerk, aber nicht im aktuellen Ausführen hatte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Überprüfung der gesamten Überprüfung fehlgeschlagen </td> 
   <td colname="col2"> <p>Stellt die Anzahl der Eigenschaften dar, die nicht zu der im Dateinamen deklarierten Datenquelle gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Benutzer, die über Eigenschaften verfügen, die die Überprüfung fehlgeschlagen haben </td> 
   <td colname="col2"> <p>Die Anzahl der Datensätze, die die Überprüfung fehlschlugen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auftragsstartzeit </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag beginnt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auftragsendzeit </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem der eingehende Auftrag endet. </p> </td> 
  </tr> 
 </tbody> 
</table>