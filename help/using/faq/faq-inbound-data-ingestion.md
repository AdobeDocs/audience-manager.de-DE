---
description: Häufig gestellte Fragen zum Übertragen von Offlinedaten in Audience Manager
keywords: ftp or s3;s3 or ftp
seo-description: Häufig gestellte Fragen zum Übertragen von Offlinedaten in Audience Manager
seo-title: Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten
solution: Audience Manager
title: Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 6b9afa7c53f5bc2738f185440160f62a87e0bda1

---


# Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten{#inbound-customer-data-ingestion-faq}

Häufig gestellte Fragen zum Übertragen von Offlinedaten in Audience Manager

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Können Sie den Einstiegsprozess zusammenfassen?**

Der Einbootungsprozess besteht aus 2 Kernkomponenten, die unter [Stapeldatenübertragung beschrieben](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)werden. Dazu gehören:

* ID-Synchronisierung
* Inbound-Datendatei ( [!DNL .sync] Datei oder [!DNL .overwrite] Datei)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Im Folgenden finden Sie eine Liste der Fragen und Antworten, die Sie nach der Überprüfung der Dokumentation möglicherweise hilfreich finden.

>[!NOTE]
>
>Die Beispiele in diesem Abschnitt werden aus Gründen der Schnelligkeit und Demonstration vereinfacht oder verkürzt. Detaillierte Spezifikationen zu Dateiformaten und zur Syntax finden Sie in der Inbound Data Ingestion-Dokumentation.

<br> 

**Können Sie den Bereitstellungsprozess zusammenfassen?**

Wir empfehlen Folgendes:

* Arbeiten Sie mit Ihrem Datenanbieter zusammen, um die täglich eingehende Datendatei gemäß den [!DNL Adobe] Spezifikationen zu formatieren.
* Übertragen Sie eine Testdatendatei [!DNL Adobe] zur Formatüberprüfung.
* Arbeiten Sie mit Ihrem [!DNL Adobe] Berater zusammen, um eine für die Interpretation des Inhalts der Datendatei geeignete Taxonomie zu entwickeln.
* Vergewissern Sie sich in der Staging-/Entwicklungsumgebung, dass die ID-Synchronisierung so konfiguriert ist, dass die Besucher-ID des Datenanbieters ordnungsgemäß abgerufen und in Echtzeit auf die [!DNL Audience Manager] Server übertragen wird.
* Stellen Sie DIL/ID-Synchronisierung für die Produktion bereit. Die ID-Synchronisierung wird von Ihrem Adobe-Berater bereits als Modul im DIL-Code konfiguriert.
* Produktionsdatendateien übertragen auf [!DNL Audience Manager]. Aufgrund der Abhängigkeiten von ID-Synchronisierungs-Zuordnungen kann es sinnvoll sein, bis zu einer Woche nach der Bereitstellung des Produktionscodes mit der Datenübertragung zu beginnen. Sie können allerdings auch mit der Übertragung der Datendateien beginnen, sobald Code in die Produktion eingeht.

<br> 

**Welchen FTP-Modus sollte ich verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen?**

Siehe [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Kann ich eine Eingangs-Datendatei ([!DNL .sync] oder eine [!DNL .overwrite]-Datei) hochladen, bevor ich [!DNL Audience Manager] Code in der Produktionsumgebung implementiere?**

Ja. Solange Sie zum Speichern der hochgeladenen CRM-Daten eine geräteübergreifende Datenquelle verwenden, speichert Audience Manager die Daten immer. Nach den im Oktober 2019 von Audience Manager gestarteten Erweiterungen der Regeln zur Profilzusammenführung, die ausschließlich Offline-Anwendungsfälle ermöglichen, können Sie Daten hochladen und Aktionen ausführen, ohne den Audience Manager-Code überhaupt in die Produktion einsetzen zu müssen. Siehe:

* [Übersicht über die Erweiterungen der Regeln zum Profilzusammenführen](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* Benutzerbasierte Ziele - [Personalisierung auf Basis von Nur-Offline-Daten](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**Wann sollte ich meine Datei übertragen?**

[!DNL Audience Manager] prüft und verarbeitet Dateien mehrmals am Tag. Laden Sie Ihre Daten hoch, sobald Sie bereit sind.

<br> 

**Wie lange dauert es, bis Daten aus einer hochgeladenen Datei für das Targeting verfügbar sind?**

Daten sind für das Targeting nach 48 Stunden verfügbar. Außerdem sollten Sie die E-Mail zum erfolgreichen Hochladen nicht als Aussage interpretieren, dass die Daten verfügbar sind. Dies bedeutet nur, dass die Datei aufgenommen und der erste Verarbeitungsschritt abgeschlossen [!DNL Audience Manager] wurde.

<br> 

**Wie oft sollte ich Dateien versenden, und sollten es sich um vollständige oder inkrementelle Dateien handeln?**

Als Best Practice sollten Sie eine inkrementelle Datei einmal täglich für neue Besucher und Besucher senden, deren Daten sich geändert haben. Viele [!DNL Audience Manager] Kunden senden eine vollständige Datei einmal pro Monat. Diese Dateiintervalle und -inkremente sind jedoch flexibel. Sie sollten Daten in Schritten und zu Zeiten senden, die für Sie sinnvoll sind.

<br> 

**Wie lange hält Audience Manager meine Dateien auf dem Server?**

FTP-Dateien werden nach der Verarbeitung entfernt. [!DNL S3] Dateien werden nach 30 Tagen entfernt. Dateien, die aufgrund von Format, Syntax oder anderen Fehlern nicht verarbeitet werden können, werden entfernt. Siehe auch Häufig gestellte Fragen zum [Datenschutz und zur Datenaufbewahrung](../faq/faq-privacy.md).

<br> 

**Was ist der Unterschied zwischen vollständigen und inkrementellen Dateien?**

* **** Vollständig: Eine vollständige Datei überschreibt alle vorhandenen Besucherprofile und ersetzt sie durch die Daten in Ihrer Datei. Vollständige Dateien werden durch das `.overwrite` Tag gekennzeichnet, das an den Dateinamen angehängt wird. Sie können eine `.overwrite` Datei verwenden, um Besuchereigenschaften zurückzusetzen oder veraltete Eigenschaften zu entfernen.

   >[!NOTE]
   >
   >Die [!DNL .overwrite] Dateien überschreiben nur [!DNL Audience Manager] Profildaten, die diesem Datenanbieter zugeordnet sind. Mit anderen Worten, alle mit dem Besucher verknüpften [!DNL Adobe Analytics] Daten bleiben erhalten, nachdem eine [!DNL .overwrite] Datei verarbeitet wurde.

* **** Inkrementell: Eine inkrementelle Datei hängt neue Daten an Ihre bestehenden Besucherprofile an. Inkrementelle Dateien werden durch das `.sync` Tag identifiziert, das an den Dateinamen angehängt wird. Beim Senden einer inkrementellen Datei werden vorhandene Profile nicht gelöscht oder überschrieben.

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
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Tag 1 <code> .sync</code> Dateiinhalt: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Inhalt der <code> .overwrite</code> Datei Tag 2: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Tag 3 Besucherprofil-ID 123 enthält <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nur inkrementell</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Tag 1 <code> .sync</code> Dateiinhalt: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Inhalt der <code> .sync</code> Datei Tag 2: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Tag 3 Besucherprofil-ID 123 enthält <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Weitere Informationen zu vollständigen und inkrementellen Dateitypen finden Sie unter:

* [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Daten...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**Was passiert, wenn ich eine Datei mit IDs für Besucher einschicke, die die On-Page-ID-Synchronisierung noch nie durchgeführt haben?**

Während der Verarbeitung überspringt [!DNL Audience Manager] diese Aufzeichnung und wechselt zum nächsten. Wenn eine DPID (Datenanbieter-ID) als geräteübergreifende DPID eingerichtet wird, werden Daten, die vor einer ID-Synchronisierung aufgenommen werden, gespeichert und stehen kurz nach der ID-Synchronisierung zur Verwendung zur Verfügung.

<br> 

**Was ist der Zeitstempel, wofür wird er verwendet, und können Sie ein Beispiel geben?**

Zeitstempel werden zur Protokollierung und Aufbewahrung von Datensätzen verwendet. Sie werden von der Syntax für einen ordnungsgemäß formatierten eingehenden Dateinamen benötigt. Siehe:

* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**Was ist eine Datenanbieter-ID (DPID) und wie erhalte ich sie?**

Ihr Adobe-Berater weist Ihrer Datenquelle eine dreistellige oder vierstellige DPID zu. Diese ID ist eindeutig und ändert sich nicht.

<br> 

**Wie groß können die täglichen Datendateien sein?**

Siehe [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Unterstützt Audience Manager die Dateikomprimierung?**

Ja, siehe:

* [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**Der Hauptschlüssel in meiner Datenquellendatenbank ist eine E-Mail-Adresse. Wird dies als personenbezogene Daten betrachtet?**

Ja. [!DNL Audience Manager] speichert keine E-Mail-Adressen in unserer Datenbank. Besuchern sollte vor dem Initiieren von ID-Synchronisierungen eine zufällige ID oder eine einseitige Hash-Version der E-Mail-Adresse zugewiesen werden.

<br> 

**Ist beim Inhalt der Datendatei die Groß-/Kleinschreibung zu beachten? Wie wäre es mit der ID-Synchronisierung?**

Es gibt zwei grundlegende Komponenten einer Datendatei: Eine Benutzer-ID (siehe Benutzer-ID in [Dateivariablen definiert](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) und Profildaten, üblicherweise in Form von Schlüssel-Wert-Paaren oder -Codes. Bei der Benutzer-ID wird zwischen Groß- und Kleinschreibung unterschieden. Im Allgemeinen wird bei Profil- oder Schlüsselwertdaten nicht zwischen Groß- und Kleinschreibung unterschieden.

<br> 

**Soll ich FTP verwenden oder Dateien übertragen[!DNL Amazon S3]?**

Als Best Practice empfehlen wir, [!DNL Amazon S3] weil der Prozess einfacher ist. [!DNL Audience Manager] überträgt FTP-Dateien [!DNL S3] unabhängig voneinander, sodass der Prozess optimiert wird, wenn Sie die Dateien selbst ablegen [!DNL Amazon S3] . Kunden, die gleichzeitig auf FTP hochladen, teilen außerdem die Bandbreite des FTP-Dienstes, sodass sie langsamere Upload-Geschwindigkeiten erwarten sollten. [!DNL Amazon S3] wird auch repliziert und verteilt, daher ist es im Allgemeinen sicherer und zuverlässiger als ein FTP-Server. Weitere Informationen finden Sie unter [Info zu Amazon S3](../reference/amazon-s3.md).

<br> 

**Wie verarbeitet Audience Manager eingehende Dateien?**

[!DNL Audience Manager] Verwendung [!DNL Amazon Simple Queue Service (SQS)] für die eingehende Datenverarbeitung. So funktioniert das:

1. [!DNL Audience Manager] Kunden laden ihre eingehenden Daten in einen [!DNL Amazon S3] Behälter hoch.

2. Die Daten werden in die [!DNL Amazon SQS] Warteschlange gestellt und warten darauf, von [!DNL Audience Manager]Ihnen verarbeitet zu werden.

3. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS] Warteschlange und teilt sie in bis zu 3 Stapel auf. Dateien in jedem Stapel werden gleichzeitig verarbeitet.

<br> 

**Ich muss mehrere Dateien gleichzeitig hochladen. Werden die Dateien gleichzeitig verarbeitet?**

Es kommt darauf an. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS] Warteschlange und teilt sie in bis zu 3 Stapel auf. Ihre Dateien werden nur dann gleichzeitig verarbeitet, wenn sie im selben Stapel landen. Aufgrund der hohen Datenmenge, die täglich von [!DNL Audience Manager] uns aufgenommen wird, können wir jedoch keine Dateiverarbeitungsaufträge garantieren.

>[!MORELIKETHIS]
>
>* [Stapeldatenübermittlungsprozess beschrieben](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

