---
description: Häufig gestellte Fragen zum Einpflegen von Offline-Daten in Audience Manager.
keywords: ftp oder s3; s3 oder ftp
seo-description: Häufig gestellte Fragen zum Einpflegen von Offline-Daten in Audience Manager.
seo-title: Häufig gestellte Fragen zur Erfassung von eingehenden Kundendaten
solution: Audience Manager
title: Häufig gestellte Fragen zur Erfassung von eingehenden Kundendaten
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding von Offline-Daten
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 91%

---

# Häufig gestellte Fragen zur Erfassung von eingehenden Kundendaten{#inbound-customer-data-ingestion-faq}

Häufig gestellte Fragen zum Einpflegen von Offline-Daten in Audience Manager.

 

**Können Sie den Integrationsprozess zusammenfassen?**

Der Integrationsprozess besteht aus zwei Schritten, die unter [Senden von Batch-Daten an Audience Manager – Überblick](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) beschrieben sind:

* Schritt 1: Synchronisieren von Benutzer-IDs;
* Schritt 2: Erstellen und Übertragen Ihrer eingehenden Datendatei unter Einhaltung der Dateiformatanforderungen.

 

**Können Sie den Implementierungsprozess zusammenfassen?**

Wir empfehlen Folgendes:

* Arbeiten Sie mit Ihrem Datenanbieter zusammen, um die täglich eingehende Datendatei gemäß den Adobe-Spezifikationen zu formatieren. Informationen zu Dateinamen und Syntaxanforderungen finden Sie in der folgenden Dokumentation:
   * [Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Inhalt der eingehenden Datendatei: Syntax, ungültige Zeichen, Variablen und Beispiele](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Wenden Sie sich an Ihren [!DNL Adobe]-Berater, um eine Testdatendatei zur Formatprüfung an [!DNL Adobe] zu übertragen.
* Arbeiten Sie mit Ihrem [!DNL Adobe] Berater zusammen, um eine Taxonomie zu entwickeln, die für die Interpretation des Inhalts der Datendatei geeignet ist.
* Bestätigen Sie in der Staging-/Entwicklungsumgebung, dass die ID-Synchronisierung so konfiguriert ist, dass sie die Besucher-ID des Datenproviders korrekt aufnimmt und in Echtzeit an die [!DNL Audience Manager]-Server überträgt.
* Stellen Sie die DIL-/ID-Synchronisierung in der Produktionsumgebung bereit. Die ID-Synchronisierung wird von Ihrem Adobe-Berater bereits als Modul im DIL-Code konfiguriert.
* Übertragen Sie die Produktionsdatendateien an [!DNL Audience Manager]. Angesichts der Abhängigkeiten von ID-Synchronisierungszuordnungen kann es sinnvoll sein, mit der Übertragung von Daten bis zu einer Woche nach der Implementierung des produktiven Codes zu beginnen. Sie können jedoch mit der Übertragung der Datendateien beginnen, sobald der Code in der Produktionsumgebung implementiert wurde.

 

**Welchen FTP-Modus sollte ich verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen?**

Siehe [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Die Unterstützung für FTP-Konfigurationen wird schrittweise eingestellt. Während die Erfassung eingehender Datendateien in bestehenden FTP-Integrationen weiterhin unterstützt wird, empfehlen wir dringend, Amazon S3 zu verwenden, um Offline-Daten für neue Integrationen zu integrieren. Weitere Informationen finden Sie unter [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Kann ich eine eingehende Datendatei (eine [!DNL .sync] - oder eine [!DNL .overwrite] -Datei) hochladen, bevor ich [!DNL Audience Manager] Code in der Produktionsumgebung implementiere?**

Ja. Solange Sie zum Speichern der hochgeladenen CRM-Daten einen [!UICONTROL cross-device data source] verwenden, speichert Audience Manager immer die Daten. Aufgrund der im Oktober 2019 von Audience Manager eingeführten [!UICONTROL Profile Merge Rules]-Verbesserungen, die nur Offline-Anwendungsfälle ermöglichen, können Sie Daten hochladen und bearbeiten, ohne Audience Manager-Code in der Produktionsumgebung bereitzustellen. Siehe:

* [Verbesserungen der Profilzusammenführungsrichtlinien – Überblick](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] -  [Personalisierung basierend auf reinen Offline-Daten](https://docs.adobe.com/content/help/de-DE/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

[!DNL Audience Manager] prüft und verarbeitet Dateien mehrmals am Tag. Laden Sie Ihre Daten hoch, wann immer Sie wünschen.

 

**Wie lange dauert es, bis Daten aus einer hochgeladenen Datei für die Zielgruppenbestimmung verfügbar sind?**

Daten sind für die Zielgruppenbestimmung nach 48 Stunden verfügbar. Außerdem bedeutet die E-Mail, die das Hochladen als erfolgreich bestätigt, nicht, dass die Daten verfügbar sind. Sie bedeutet nur, dass [!DNL Audience Manager] die Datei aufgenommen und der erste Verarbeitungsschritt abgeschlossen wurde.

 

**Wie oft sollte ich Dateien versenden, und sollten es sich um vollständige oder inkrementelle Dateien handeln?**

Senden Sie als Best Practice einmal täglich eine inkrementelle Datei für neue Besucher und für Besucher, deren Daten sich geändert haben. Viele [!DNL Audience Manager]-Kunden senden einmal pro Monat eine vollständige Datei. Diese Dateiintervalle und -inkremente sind jedoch flexibel. Sie sollten Daten in Schritten und zu Zeiten senden, die für Sie sinnvoll sind.

 

**Wie lange bewahrt Audience Manager meine Dateien auf dem Server auf?**

FTP-Dateien werden nach der Verarbeitung entfernt. [!DNL S3]-Dateien werden nach 30 Tagen entfernt. Dateien, die aufgrund von Format, Syntax oder anderen Fehlern nicht verarbeitet werden können, werden entfernt. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zur Datenaufbewahrung](../faq/faq-privacy.md).

 

**Was ist der Unterschied zwischen vollständigen und inkrementellen Dateien?**

* **Vollständig:** Eine vollständige Datei überschreibt alle vorhandenen Besucherprofile und ersetzt sie durch die Daten in Ihrer Datei. Vollständige Dateien werden durch das an den Dateinamen angehängte `.overwrite`-Tag identifiziert. Sie können eine `.overwrite`-Datei verwenden, um Eigenschaften von Besuchern zurückzusetzen oder veraltete Eigenschaften zu entfernen.

   >[!NOTE]
   >
   >Die [!DNL .overwrite]-Dateien überschreiben nur die mit diesem Datenanbieter verknüpften [!DNL Audience Manager]-Profildaten. Mit anderen Worten, alle mit dem Besucher verknüpften [!DNL Audience Manager]-Daten bleiben erhalten, nachdem eine [!DNL .overwrite]-Datei verarbeitet wurde.

* **Inkrementell:** Eine inkrementelle Datei hängt neue Daten an Ihre bestehenden Besucherprofile an. Inkrementelle Dateien werden durch das an den Dateinamen angehängte `.sync`-Tag identifiziert. Beim Senden einer inkrementellen Datei werden vorhandene Profile weder gelöscht noch überschrieben.

Die folgenden Anwendungsfälle zeigen, wie sich diese Dateitypen auf gespeicherte Besucherprofile auswirken.

| Anwendungsfall | Beschreibung |
|---|---|
| Inkrementell und vollständig | <ul><li>1. Tag: `.sync`, Datei beinhaltet: `visitor123 = a,b,c`</li><li>2. Tag: `.overwrite`, Datei beinhaltet: `visitor123 = c,d,e`</li><li>3. Tag: Besucherprofil-ID „123“ beinhaltet: `c,d,e`</li></ul> |
| Nur inkrementell | <ul><li>Tag 1: Inhalt der `.sync`-Datei: `visitor123 = a,b,c`</li><li>2. Tag: `.sync`, Datei beinhaltet: `visitor123 = c,d,e`</li><li>3. Tag: Besucherprofil-ID „123“ beinhaltet: `a,b,c,d,e`</li></ul> |

Weitere Informationen zu vollständigen und inkrementellen Dateitypen finden Sie unter:

* [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Was passiert, wenn ich eine Datei mit IDs für Besucher sende, die noch nie die On-Page-ID-Synchronisierung durchgeführt haben?**

Während der Verarbeitung überspringt [!DNL Audience Manager] diesen Eintrag und wechselt zum nächsten. Wenn eine [DPID (Datenanbieter-ID)](../reference/ids-in-aam.md) als geräteübergreifende DPID eingerichtet ist, werden Daten, die vor einer ID-Synchronisierung erfasst werden, gespeichert und stehen kurz nach der ID-Synchronisierung zur Verwendung zur Verfügung.

 

**Was ist der Zeitstempel, wozu dient er, und können Sie ein Beispiel nennen?**

Zeitstempel werden zur Protokollierung und Aufzeichnung verwendet. Sie werden von der Syntax für einen ordnungsgemäß formatierten eingehenden Dateinamen benötigt. Siehe:

* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Was ist ein  [!DNL Data Provider ID (DPID)] und wie bekomme ich es?**

Ihr Adobe-Berater weist Ihrer Datenquelle eine dreistellige oder vierstellige [DPID (Datenanbieter-ID)](../reference/ids-in-aam.md) zu. Diese ID ist eindeutig und ändert sich nicht.

 

**Wie groß können die täglichen Datendateien sein?**

Siehe [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Unterstützt Audience Manager die Dateikomprimierung?**

Ja, siehe:

* [Dateikomprimierung für eingehende Datenübertragungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Der Primärschlüssel in meiner Datenquellendatenbank ist eine E-Mail-Adresse. Wird diese als persönlich identifizierbare Information angesehen?**

Ja. [!DNL Audience Manager] speichert keine E-Mail-Adressen in der Datenbank. Besuchern sollte vor dem Initiieren von ID-Synchronisierungen eine zufällig generierte ID oder eine unidirektionale Hash-Version der E-Mail-Adresse zugewiesen werden.

 

**Wird bei den Inhalten der Datendatei wird zwischen Groß- und Kleinschreibung unterschieden? Wie sieht es mit der ID-Synchronisierung aus?**

Es gibt zwei grundlegende Komponenten einer Datendatei: Eine [!UICONTROL User ID] (siehe [!UICONTROL User ID] unter [Definierte Dateivariablen](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) und die Profildaten, üblicherweise in Form von Schlüssel-Wert-Paaren oder Codes. Bei der [!UICONTROL User ID] ist die Groß-/Kleinschreibung zu beachten. Im Allgemeinen wird bei Profil- oder Schlüsselwertdaten nicht zwischen Groß- und Kleinschreibung unterschieden.

 

**Sollte ich zur Übertragung von Dateien FTP oder [!DNL Amazon S3] verwenden?**

Als Best Practice empfehlen wir [!DNL Amazon S3], da der Prozess einfacher ist. Unabhängig davon überträgt [!DNL Audience Manager] FTP-Dateien an [!DNL S3], sodass der Prozess optimiert wird, wenn Sie die Dateien selbst in [!DNL Amazon S3] ablegen. Darüber hinaus teilen Kunden, die gleichzeitig auf FTP hochladen, die Bandbreite mit dem FTP-Prozess, sodass sie mit langsameren Upload-Geschwindigkeiten rechnen müssen. [!DNL Amazon S3] wird auch repliziert und verteilt, sodass er im Allgemeinen sicherer und zuverlässiger als ein FTP-Server ist. Weitere Informationen finden Sie unter [Amazon S3: Info](../reference/amazon-s3.md).

>[!WARNING]
>
>Die Unterstützung für FTP-Konfigurationen wird schrittweise eingestellt. Während die Erfassung eingehender Datendateien in bestehenden FTP-Integrationen weiterhin unterstützt wird, empfehlen wir dringend, [!DNL Amazon S3] zu verwenden, um Offline-Daten für neue Integrationen zu integrieren. Weitere Informationen finden Sie unter [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Wie verarbeitet Audience Manager eingehende Dateien?**

[!DNL Audience Manager] verwendet [!DNL Amazon Simple Queue Service (SQS)], um die eingehenden Daten zu verarbeiten. Funktionsweise:

1. [!DNL Audience Manager]-Kunden laden ihre eingehenden Daten in einen [!DNL Amazon S3]-Behälter hoch.
1. Die Daten werden in die [!DNL Amazon SQS]-Warteschlange gestellt und warten auf die Verarbeitung durch [!DNL Audience Manager].
1. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS]-Warteschlange und teilt sie in bis zu 3 Batches auf. Die Dateien in jedem Batch werden gleichzeitig verarbeitet.

 

**Ich muss mehrere Dateien gleichzeitig hochladen. Werden die Dateien gleichzeitig verarbeitet?**

Das kommt darauf an. [!DNL Audience Manager] liest bis zu 119000 Einträge aus der [!DNL Amazon SQS]-Warteschlange und teilt sie in bis zu 3 Batches auf. Ihre Dateien werden nur dann gleichzeitig verarbeitet, wenn sie sich in demselben Batch befinden. Aufgrund der hohen Datenmenge, die [!DNL Audience Manager] täglich erfasst, können wir jedoch keine Dateiverarbeitungsreihenfolge garantieren.

>[!MORELIKETHIS]
>
>* [Beschreibung des Batch-Datenübertragungsprozesses](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

