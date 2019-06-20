---
description: Häufig gestellte Fragen zum Einbinden von Offline-Daten in Audience Manager
keywords: ftp oder s 3; s 3 oder ftp
seo-description: Häufig gestellte Fragen zum Einbinden von Offline-Daten in Audience Manager
seo-title: Häufig gestellte Fragen zur Datenaufnahme in eingehende Kunden
solution: Audience Manager
title: Häufig gestellte Fragen zur Datenaufnahme in eingehende Kunden
uuid: 491 e 9 ec 1-4731-46 a 8-86 e 7-d 8 c 613 e 6 cedc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Häufig gestellte Fragen zum Einbinden von Offline-Daten in Audience Manager

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Können Sie den Onboarding-Prozess zusammenfassen?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). Dazu gehören:

* ID-Synchronisierung
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Nachfolgend finden Sie eine Liste mit Fragen und Antworten, die Sie nach der Überprüfung der Dokumentation finden können.

>[!NOTE]
>
>Die Beispiele in diesem Abschnitt werden für Atemberaub- und Demonstrationszwecke vereinfacht oder verkürzt. Ausführliche Spezifikationen zu Dateiformaten und Syntax finden Sie in der Dokumentation zu Inbound Data Ingestion.

<br> 

**Können Sie den Bereitstellungsprozess zusammenfassen?**

Wir empfehlen Folgendes:

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Stellen Sie DIL/ID-Synchronisierung zur Produktion bereit. Die ID-Synchronisierung wird bereits als Modul im DIL-Code von Ihrem Adobe-Berater konfiguriert.
* Transfer production data files to [!DNL Audience Manager]. Angesichts der Abhängigkeiten bei ID-Synchronisierungszuordnungen kann es sinnvoll sein, Daten nach der Bereitstellung des Produktionscodes bis zu einer Woche zu übertragen. Sie können die Datendateien jedoch sofort nach der Produktion übertragen.

<br> 

**Welchen FTP-Modus sollte ich verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Kann ich eine Eingangs-Datendatei ([!DNL .sync]oder eine[!DNL .overwrite]-Datei) hochladen, bevor ich[!DNL Audience Manager]Code in der Produktionsumgebung implementiere?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>1. Fall</b> </p> </td> 
   <td colname="col2"> <p>Am Montag meldet sich ein Besucher, der in der CRM-Datenbank als Besucher ABC angemeldet ist, an, der eine clientseitige ID-Synchronisierung initiiert. <span class="keyword"> Audience Manager</span> speichert die Zuordnung von Besuchern ABC zu <span class="keyword"> Audience Manager</span> Visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender" = "männlich", "luxury_ shopper" = "yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Erkennt Besucher ABC aus der gespeicherten ID-Synchronisierungszuordnung. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>2. Fall</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "female", "wine_ enthusiast" = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> hat keinen Datensatz dieses Besuchers (oder eine zugehörige Besucher-ID), sodass dieser Datensatz nicht verarbeitet wird. </p> <p>Am Dienstag meldet sich der Besucher-DEF an. Diese Aktion initiiert die erste clientseitige ID-Synchronisierung für diesen Besucher. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. Dieser Besucher hat jedoch keine CRM-Daten, die mit ihrem Profil verknüpft sind. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "female", "wine_ enthusiast" = "yes", "dma" = "paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Erkennt Besucher-DEF aus der gespeicherten ID-Synchronisierungszuordnung. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>3. Fall</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> . sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> . überschreiben</code> Datei mit: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender" = "männlich" "wine_ enthusiast" = "no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender" = "weiblich" "wine_ enthusiast" = "ja"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> speichert einen zugeordneten Datensatz von Besucher JKL zu ID 789 von einer früheren ID-Synchronisierung. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Erkennt die JKL des Besuchers aus der gespeicherten ID-Synchronisierungszuordnung. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignoriert die Zuordnung der Eigenschaft für Besucher GHI, da die ID nur im aktuellen Batch synchronisiert wurde. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Wie lange sollte ich meine Datei übertragen?**

[!DNL Audience Manager] prüft und verarbeitet Dateien mehrmals im Verlauf. Laden Sie Ihre Daten hoch, sobald Sie bereit sind.

<br> 

**Wie lange dauert es, bis Daten aus einer hochgeladenen Datei für das Targeting verfügbar sind?**

Daten sind nach 48 Stunden für das Targeting verfügbar. Interpretieren Sie die E-Mail zum Hochladen nicht als Auszug, dass die Daten verfügbar sind. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**Wie oft sollte ich Dateien senden und sollten diese vollständige oder inkrementelle Dateien sein?**

Wir empfehlen, eine inkrementelle Datei einmal pro Tag für neue Besucher und für Besucher, deren Daten sich geändert haben, zu senden. Many [!DNL Audience Manager] customers send a full file once per month. Diese Dateiintervalle und -abschnitte sind jedoch flexibel. Sie sollten Daten in Inkrementen senden, die für Sie sinnvoll sind.

<br> 

**Wie lange hält Audience Manager meine Dateien auf dem Server weiter?**

FTP-Dateien werden nach der Verarbeitung entfernt. [!DNL S3] Dateien werden nach 30 Tagen entfernt. Dateien, die aufgrund von Format, Syntax oder anderen Fehlern nicht verarbeitet werden können, werden entfernt. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Was ist der Unterschied zwischen vollständigen und inkrementellen Dateien?**

* **Voll:** Eine vollständige Datei überschreibt alle vorhandenen Besucherprofile und ersetzt sie durch die Daten in Ihrer Datei. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Inkrementell:** Eine inkrementelle Datei hängt neue Daten an Ihre vorhandenen Besucherprofile an. Incremental files are identified by the `.sync` tag appended to the file name. Durch Senden einer inkrementellen Datei werden vorhandene Profile nicht gelöscht oder überschrieben.

Die folgenden Anwendungsfälle zeigen, wie diese Dateitypen gespeicherte Besucherprofile beeinflussen.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Inkrementell und vollständig</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nur inkrementell</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Weitere Informationen zu vollständigen und inkrementellen Dateitypen finden Sie unter:

* [Anforderungen an Name und Dateigröße von Amazon S 3 für eingehende Daten…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Anforderungen an FTP-Name und Dateigröße für Inbound-Datendateien…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Was geschieht, wenn ich eine Datei mit IDs für Besucher sende, die nie die On-Page ID synchronisiert haben?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. Wenn eine DPID (Datenanbieter-ID) als geräteübergreifende DPID eingerichtet wird, werden Daten, die vor einer ID-Synchronisierung erfasst werden, gespeichert und stehen kurz nach der ID-Synchronisierung zur Verfügung.

<br> 

**Was ist der Zeitstempel, wofür ist er und können Sie ein Beispiel angeben?**

Zeitstempel werden für die Protokollierung und Aufzeichnung verwendet. Sie sind für die Syntax erforderlich, die für einen ordnungsgemäß formatierten Dateinamen verwendet wird. Siehe:

* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Anforderungen an FTP-Name und Dateigröße für Inbound-Datendateien…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Was ist eine Datenanbieter-ID (DPID) und wie erhalte ich sie?**

Ihr Adobe-Berater weist Ihrer jeweiligen Datenquelle eine dreistellige oder vierstellige DPID zu. Diese ID ist eindeutig und ändert sich nicht.

<br> 

**Wie groß können die täglichen Datendateien sein?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Unterstützt Audience Manager die Dateikomprimierung?**

Ja, siehe:

* [Dateikomprimierung für Dateien mit Inbound-Datenübertragung](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [FTP-Namensanforderungen für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Der primäre Schlüssel in meiner Datenquellendatenbank ist eine E-Mail-Adresse. Is that considered personally identifiable information?**

Ja. [!DNL Audience Manager] speichert keine E-Email-Adressen in unserer Datenbank. Vor der Initiierung von ID-Synchronisierungen sollte dem Besucher eine zufällige ID oder eine versionssensitive Version der E-Email-Adresse zugewiesen werden.

<br> 

**Muss die Groß-/Kleinschreibung der Datendatei beachtet werden? How about the ID sync?**

Es gibt zwei grundlegende Komponenten einer Datendatei: Eine Unique User ID (UUID) und Profildaten, normalerweise in Form von Schlüsselwertpaaren oder -codes. Bei der UUID muss die Groß-/Kleinschreibung beachtet werden. Im Allgemeinen wird bei Profil- oder Schlüsselwertdaten nicht zwischen Groß- und Kleinschreibung unterschieden.

<br> 

**Sollte ich FTP verwenden oder[!DNL Amazon S3]Dateien übertragen?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] übertragen FTP-Dateien [!DNL S3] an, sodass der Prozess optimiert wird, wenn Sie die Dateien selbst [!DNL Amazon S3] ablegen. Darüber hinaus werden Kunden, die gleichzeitig auf FTP hochgeladen werden, die Bandbreite des FTP freigeben. Daher sollten sie langsamere Upload-Geschwindigkeiten erwarten. [!DNL Amazon S3] repliziert und verteilt wird, ist daher im Allgemeinen sicherer und zuverlässiger als ein FTP-Server. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**Wie verarbeitet der Zielgruppenmanger eingehende Dateien?**

[!DNL Audience Manager] für [!DNL Amazon Simple Queue Service (SQS)] eingehende Datenverarbeitung verwendet. So funktioniert das:

1. [!DNL Audience Manager] Kunden laden ihre eingehenden Daten in einen [!DNL Amazon S3] Behälter hoch.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS] Warteschlange und teilt sie in bis zu 3 Stapeln auf. Dateien in jedem Batch werden gleichzeitig verarbeitet.

<br> 

**Ich muss mehrere Dateien gleichzeitig hochladen. Will the files be processed simultaneously?**

Dies hängt davon ab. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS] Warteschlange und teilt sie in bis zu 3 Stapeln auf. Ihre Dateien werden nur gleichzeitig verarbeitet, wenn sie im selben Stapel enden. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ LIKE_ THIS]
>
>* [Batch-Datenübertragungsprozess beschrieben](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

