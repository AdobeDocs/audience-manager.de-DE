---
description: Häufig gestellte Fragen zum Einfügen von Offlinedaten in Audience Manager
keywords: ftp or s3;s3 or ftp
seo-description: Häufig gestellte Fragen zum Einfügen von Offlinedaten in Audience Manager
seo-title: Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten
solution: Audience Manager
title: Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 187874fb5d0c4363f771297766f3c4bc9d967c9b

---


# Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten{#inbound-customer-data-ingestion-faq}

Häufig gestellte Fragen zum Einfügen von Offlinedaten in Audience Manager

 

**Können Sie den Einstiegsprozess zusammenfassen?**

Der Einbootungsprozess besteht aus zwei Schritten, die unter Stapeldaten an Audience Manager [senden beschrieben werden](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Schritt 1: Benutzer-IDs synchronisieren;
* Schritt 2: Erstellen und übertragen Sie Ihre eingehende Datendatei unter Einhaltung der Dateiformatanforderungen.

 

**Können Sie den Bereitstellungsprozess zusammenfassen?**

Wir empfehlen Folgendes:

* Arbeiten Sie mit Ihrem Datenanbieter zusammen, um die täglich eingehende Datendatei gemäß den Adobe-Spezifikationen zu formatieren. Informationen zu Dateibenennung und Syntaxanforderungen finden Sie in der folgenden Dokumentation:
   * [Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Inhalt der eingehenden Datendatei: Syntax, ungültige Zeichen, Variablen und Beispiele](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Amazon S3-Anforderungen an Name und Dateigröße für eingehende Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Wenden Sie sich an Ihren [!DNL Adobe] Berater, um eine Testdatendatei zur Formatüberprüfung [!DNL Adobe] zu übertragen.
* Arbeiten Sie mit Ihrem [!DNL Adobe] Berater zusammen, um eine Taxonomie zu entwickeln, die für die Interpretation des Inhalts der Datendatei geeignet ist.
* Vergewissern Sie sich in der Umgebung für Staging/Entwicklung, dass die ID-Synchronisierung so konfiguriert ist, dass die Besucher-ID des Datenanbieters ordnungsgemäß abgerufen und in Echtzeit auf die [!DNL Audience Manager] Server übertragen wird.
* Stellen Sie die DIL/ID-Synchronisierung für die Produktion bereit. Die ID-Synchronisierung wird von Ihrem Adobe-Berater bereits als Modul im DIL-Code konfiguriert.
* Produktionsdatendateien übertragen auf [!DNL Audience Manager]. Aufgrund der Abhängigkeiten von ID-Synchronisierungs-Zuordnungen kann es sinnvoll sein, bis zu einer Woche nach der Bereitstellung des Produktionscodes mit der Datenübertragung zu beginnen. Sie können jedoch Beginn beim Übertragen der Datendateien einsetzen, sobald der Code in die Produktion eingeht.

 

**Welchen FTP-Modus sollte ich verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen?**

Siehe [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Die Unterstützung für FTP-Konfigurationen wird schrittweise eingestellt. Während die Erfassung eingehender Datendateien in bestehenden FTP-Integrationen weiterhin unterstützt wird, empfehlen wir dringend, für neue Integrationen Offlinedaten mit Amazon S3 zu integrieren. Weitere Informationen finden Sie unter [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

 

**Kann ich eine Eingangs-Datendatei ([!DNL .sync] oder eine [!DNL .overwrite]-Datei) hochladen, bevor ich [!DNL Audience Manager] Code in der Produktionsumgebung implementiere?**

Ja. Solange Sie zum Speichern der hochgeladenen CRM-Daten eine geräteübergreifende Datenquelle verwenden, speichert Audience Manager die Daten immer. Nachdem Audience Manager im Oktober 2019 die Profil Merge Rules-Erweiterungen gestartet hat, die ausschließlich Offline-Anwendungsfälle ermöglichen, können Sie Daten hochladen und Aktionen ausführen, ohne Audience Manager-Code in der Produktionsumgebung bereitzustellen. Siehe:

* [Verbesserungen der Profil Merge Rules](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
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

**Zu welcher Tageszeit sollte ich meine Datei übertragen?**

[!DNL Audience Manager] prüft und verarbeitet Dateien mehrmals am Tag. Laden Sie Ihre Daten hoch, sobald Sie bereit sind.

 

**Wie lange dauert es, bis Daten aus einer hochgeladenen Datei für das Targeting verfügbar sind?**

Daten sind für das Targeting nach 48 Stunden verfügbar. Außerdem sollten Sie die E-Mail zum erfolgreichen Hochladen nicht als Aussage interpretieren, dass die Daten verfügbar sind. Dies bedeutet nur, dass die Datei aufgenommen und der erste Verarbeitungsschritt abgeschlossen [!DNL Audience Manager] wurde.

 

**Wie oft sollte ich Dateien versenden, und sollten es sich um vollständige oder inkrementelle Dateien handeln?**

Als Best Practice sollten Sie eine inkrementelle Datei einmal täglich für neue Besucher und Besucher senden, deren Daten sich geändert haben. Viele [!DNL Audience Manager] Kunden senden eine vollständige Datei einmal pro Monat. Diese Dateiintervalle und -inkremente sind jedoch flexibel. Sie sollten Daten in Schritten und zu Zeiten senden, die für Sie sinnvoll sind.

 

**Wie lange hält Audience Manager meine Dateien auf dem Server?**

FTP-Dateien werden nach der Verarbeitung entfernt. [!DNL S3] Dateien werden nach 30 Tagen entfernt. Dateien, die aufgrund von Format, Syntax oder anderen Fehlern nicht verarbeitet werden können, werden entfernt. Siehe auch Häufig gestellte Fragen zum [Datenschutz und zur Datenaufbewahrung](../faq/faq-privacy.md).

 

**Was ist der Unterschied zwischen vollständigen und inkrementellen Dateien?**

* **Vollständig:** Eine Volldatei überschreibt alle vorhandenen Besucher-Profil und ersetzt sie durch die Daten in Ihrer Datei. Vollständige Dateien werden durch das `.overwrite` Tag gekennzeichnet, das an den Dateinamen angehängt wird. Sie können eine `.overwrite` Datei verwenden, um Eigenschaften von Besuchern zurückzusetzen oder veraltete Eigenschaften zu entfernen.

   >[!NOTE]
   >
   >Die [!DNL .overwrite] Dateien überschreiben nur die mit diesem Datenanbieter verknüpften [!DNL Audience Manager] Profil-Daten. Mit anderen Worten, alle mit dem Besucher verknüpften [!DNL Adobe Analytics] Daten bleiben erhalten, nachdem eine [!DNL .overwrite] Datei verarbeitet wurde.

* **Inkrementell:** Eine inkrementelle Datei hängt neue Daten an Ihre bestehenden Besucher-Profil an. Inkrementelle Dateien werden durch das `.sync` Tag identifiziert, das an den Dateinamen angehängt wird. Beim Senden einer inkrementellen Datei werden vorhandene Profile nicht gelöscht oder überschrieben.

Die folgenden Anwendungsfälle zeigen, wie sich diese Dateitypen auf gespeicherte Besucher-Profil auswirken.

| Nutzungsszenario | Beschreibung |
|---|---|
| Inkrementell und vollständig | <ul><li>Tag 1 `.sync` Dateiinhalt: `visitor123 = a,b,c`</li><li>Inhalt der `.overwrite` Datei Tag 2: `visitor123 = c,d,e`</li><li>Besucher-Profil-ID 123: `c,d,e`</li></ul> |
| Nur inkrementell | <ul><li>Tag 1 `.sync` Dateiinhalt: `visitor123 = a,b,c`</li><li>Inhalt der `.sync` Datei Tag 2: `visitor123 = c,d,e`</li><li>Besucher-Profil-ID 123: `a,b,c,d,e`</li></ul> |

Weitere Informationen zu vollständigen und inkrementellen Dateitypen finden Sie unter:

* [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Daten...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Was passiert, wenn ich eine Datei mit IDs für Besucher einreiche, die die On-Page-ID-Synchronisierung noch nie durchgeführt haben?**

Während der Verarbeitung [!DNL Audience Manager] überspringt diese Aufzeichnung und wechselt zum nächsten. Wenn eine [DPID (Datenanbieter-ID)](../reference/ids-in-aam.md) als geräteübergreifende DPID eingerichtet ist, werden Daten, die vor einer ID-Synchronisierung erfasst werden, gespeichert und stehen kurz nach der ID-Synchronisierung zur Verwendung zur Verfügung.

 

**Was ist der Zeitstempel, wofür wird er verwendet, und können Sie ein Beispiel geben?**

Zeitstempel werden zur Protokollierung und Aufbewahrung von Datensätzen verwendet. Sie werden von der Syntax für einen ordnungsgemäß formatierten eingehenden Dateinamen benötigt. Siehe:

* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Was ist eine Datenanbieter-ID (DPID) und wie erhalte ich sie?**

Ihr Adobe-Berater weist Ihrer Datenquelle eine dreistellige oder vierstellige [DPID (Datenanbieter-ID)](../reference/ids-in-aam.md) zu. Diese ID ist eindeutig und ändert sich nicht.

 

**Wie groß können die täglichen Datendateien sein?**

Siehe [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Unterstützt Audience Manager die Dateikomprimierung?**

Ja, siehe:

* [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Der Hauptschlüssel in meiner Datenquellendatenbank ist eine E-Mail-Adresse. Wird dies als personenbezogene Daten betrachtet?**

Ja. [!DNL Audience Manager] speichert keine E-Mail-Adressen in der Datenbank. Besuchern sollte vor dem Initiieren von ID-Synchronisierungen eine zufällig generierte ID oder eine einseitige Hash-Version der E-Mail-Adresse zugewiesen werden.

 

**Ist beim Inhalt der Datendatei die Groß-/Kleinschreibung zu beachten? Wie sieht es mit der ID-Synchronisierung aus?**

Es gibt zwei grundlegende Komponenten einer Datendatei: A [!UICONTROL User ID] (siehe [!UICONTROL User ID] unter [Dateivariablen definiert](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) und Profil-Daten, üblicherweise in Form von Schlüssel-Wert-Paaren oder -Codes. Bei der [!UICONTROL User ID] ist die Groß-/Kleinschreibung zu beachten. Im Allgemeinen wird bei Profil- oder Schlüsselwertdaten nicht zwischen Groß- und Kleinschreibung unterschieden.

 

**Soll ich FTP verwenden oder Dateien übertragen[!DNL Amazon S3]?**

Als Best Practice empfehlen wir, [!DNL Amazon S3] weil der Prozess einfacher ist. [!DNL Audience Manager] überträgt FTP-Dateien [!DNL S3] unabhängig voneinander, sodass der Prozess optimiert wird, wenn Sie die Dateien selbst ablegen [!DNL Amazon S3] . Kunden, die gleichzeitig auf FTP hochladen, teilen außerdem die Bandbreite des FTP-Dienstes, sodass sie langsamere Upload-Geschwindigkeiten erwarten sollten. [!DNL Amazon S3] wird auch repliziert und verteilt, daher ist es im Allgemeinen sicherer und zuverlässiger als ein FTP-Server. Weitere Informationen finden Sie unter [Info zu Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Die Unterstützung für FTP-Konfigurationen wird schrittweise eingestellt. Während die Erfassung eingehender Datendateien in bestehenden FTP-Integrationen weiterhin unterstützt wird, empfehlen wir dringend, für neue Integrationen Offlinedaten mit Amazon S3 zu integrieren. Weitere Informationen finden Sie unter [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

 

**Wie verarbeitet Audience Manager eingehende Dateien?**

[!DNL Audience Manager] Verwendungen [!DNL Amazon Simple Queue Service (SQS)] für die eingehende Datenverarbeitung. So funktioniert das:

1. [!DNL Audience Manager] Kunden laden ihre eingehenden Daten in einen [!DNL Amazon S3] Behälter hoch.
1. Die Daten werden in die [!DNL Amazon SQS] Warteschlange gestellt und warten darauf, von [!DNL Audience Manager]Ihnen verarbeitet zu werden.
1. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS] Warteschlange und teilt sie in bis zu 3 Stapel auf. Dateien in jedem Stapel werden gleichzeitig verarbeitet.

 

**Ich muss mehrere Dateien gleichzeitig hochladen. Werden die Dateien gleichzeitig verarbeitet?**

Es kommt darauf an. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS] Warteschlange und teilt sie in bis zu 3 Stapel auf. Ihre Dateien werden nur dann gleichzeitig verarbeitet, wenn sie im selben Stapel landen. Aufgrund der hohen Datenmenge, die täglich von [!DNL Audience Manager] uns aufgenommen wird, können wir jedoch keine Dateiverarbeitungsaufträge garantieren.

>[!MORELIKETHIS]
>
>* [Stapeldatenübermittlungsprozess beschrieben](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

