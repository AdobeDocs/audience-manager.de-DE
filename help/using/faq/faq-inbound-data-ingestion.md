---
description: Häufig gestellte Fragen zum Übertragen von Offlinedaten in Audience Manager
keywords: ftp oder s3;s3 oder ftp
seo-description: Häufig gestellte Fragen zum Übertragen von Offlinedaten in Audience Manager
seo-title: Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten
solution: Audience Manager
title: Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

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

**Kann ich eine Eingangs-Datendatei ([!DNL .sync]oder eine[!DNL .overwrite]-Datei) hochladen, bevor ich[!DNL Audience Manager]Code in der Produktionsumgebung implementiere?**

* Wenn der Datenanbieter so konfiguriert ist, dass er [Profillink](../features/profile-merge-rules/merge-rules-overview.md) für geräteübergreifendes Targeting verwendet, werden die Daten, die kurz nach einer ID-Synchronisierung für das Targeting verfügbar sind, mit der entsprechenden [!DNL Audience Manager] Besucher-ID identifiziert.

* Wenn der Datenanbieter nicht für die Verwendung der [!UICONTROL Profile Link] Funktion konfiguriert ist, verarbeitet [!DNL Audience Manager] nur die Daten für Besucher-IDs in der eingehenden Datendatei, die zuvor mit einer [!DNL Audience Manager] Besucher-ID synchronisiert/abgeglichen wurden.

Berücksichtigen Sie die folgenden Anwendungsfälle, in denen der Datenanbieter nicht für die Verwendung konfiguriert ist [!UICONTROL Profile Merge]:

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
   <td colname="col2"> <p>Am Montag meldet sich ein Besucher, der in der CRM-Datenbank als Besucher-ABC identifiziert wurde, an, wodurch eine clientseitige ID-Synchronisierung initiiert wird. <span class="keyword"> Audience Manager</span> speichert die Zuordnung von Besucher-ABC zu <span class="keyword"> Audience Manager</span> Visitor 123. </p> <p>Am Dienstag überträgt die CRM-Datenbank eine Datendatei (<span class="filepath"> .sync</span>) mit folgendem Datensatz an den <span class="keyword"> Audience Manager- </span>Server: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxuriöse_Einkäufer"="yes"</code> </li> 
     </ul> </p> <p>In diesem Fall <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Erkennt Besucher-ABC aus der gespeicherten ID-Synchronisierungszuordnung. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Verbindet die Eigenschaften <code> männlich</code> und <code> luxuriös_shopper</code> mit dem Profil visitor 123. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>2. Fall</b> </p> </td> 
   <td colname="col2"> <p>Am Montag sendet die CRM-Datenbank eine Datendatei (<span class="filepath"> .sync</span>) mit folgendem Datensatz an den <span class="keyword"> Audience Manager</span> -Server: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="women","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> verfügt über keinen Datensatz zu diesem Besucher (oder einer zugehörigen Besucher-ID), sodass dieser Datensatz nicht verarbeitet wird. </p> <p>Am Dienstag meldet sich die Besucher-DEF an. Diese Aktion initiiert die erste clientseitige ID-Synchronisierung für diesen Besucher. Diese Aktion ordnet Besucher-DEF der <span class="keyword"> Audience Manager</span> -ID 456 zu. Diesem Besucher sind jedoch keine CRM-Daten zugeordnet. Daher wird <span class="keyword"> Audience Manager</span> nicht zurückgehen und alte Dateien erneut verarbeiten. </p> <p>Am Mittwoch sendet die CRM-Datenbank eine weitere Datendatei mit folgendem Datensatz an den <span class="keyword"> Audience Manager</span> -Server: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="women","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In diesem Fall <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Erkennt Besucher-DEF aus der gespeicherten ID-Synchronisierungszuordnung. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Verbindet die Eigenschaften <code> weiblich</code>, <code> paris</code>und <code> wine_enthusiast</code> mit dem Profil visitor 456. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>3. Fall</b> </p> </td> 
   <td colname="col2"> <p>Am Montag erhält der <span class="keyword"> Audience Manager</span> -Server zwei Dateien mit den folgenden Datensätzen: </p> <p> <code> .sync</code> -Datei mit: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> -Datei mit: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="women" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> speichert einen zugeordneten Datensatz von Besucher-JKL zu ID 789, ausgehend von einer vorherigen ID-Synchronisierung. </p> <p>In diesem Fall <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Erkennt Besucher-JKL aus der gespeicherten ID-Synchronisierungszuordnung. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Verbindet die Eigenschaften <code> weiblich</code> und <code> wine_enthusiast</code> mit dem Profil der Besucher-ID 789. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignoriert die Eigenschaftsverknüpfung für Besucher-GHI, da ihre ID nur im aktuellen Stapel synchronisiert wurde. Um Eigenschaften mit Besucher-GHI zu verknüpfen, müssen Sie sie in zukünftige <code> .overwrite</code> -Dateien einschließen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

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
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Tag 1 <code> .sync</code> -Dateiinhalt: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Tag 2 <code> .overwrite</code> -Dateiinhalte: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Tag 3 Besucherprofil-ID 123 enthält <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Nur inkrementell</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Tag 1 <code> .sync</code> -Dateiinhalt: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Tag 2 <code> .sync</code> -Dateiinhalt: <code> visitor123 = c,d,e</code> </li> 
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

Es gibt zwei grundlegende Komponenten einer Datendatei: Eine Unique User ID (UUID) und Profildaten, üblicherweise in Form von Schlüssel-Wert-Paaren oder -Codes. Bei der UUID wird zwischen Groß- und Kleinschreibung unterschieden. Im Allgemeinen wird bei Profil- oder Schlüsselwertdaten nicht zwischen Groß- und Kleinschreibung unterschieden.

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

>[!MORE_LIKE_THIS]
>
>* [Stapeldatenübermittlungsprozess beschrieben](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

