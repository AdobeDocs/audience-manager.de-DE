---
description: Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien gemäß diesen Spezifikationen fest, wenn Sie Daten an einen Zielgruppen-Manager/Amazon S 3-Ordner senden.
seo-description: Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien gemäß diesen Spezifikationen fest, wenn Sie Daten an einen Zielgruppen-Manager/Amazon S 3-Ordner senden.
seo-title: Anforderungen an Name und Dateigröße von Amazon S 3 für Inbound-Datendateien
solution: Audience Manager
title: Anforderungen an Name und Dateigröße von Amazon S 3 für Inbound-Datendateien
uuid: 3692 a 122-6 ad 5-468 c -934 e -53067 bd 8 cf 71
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Amazon S3 Name and File Size Requirements for Inbound Data Files{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / [!DNL Amazon S3] directory.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## File Name Syntax {#file-name-syntax}

[!DNL S3] Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

* **[!DNL S3]Präfix:**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Dateinamenelemente:**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {important = "high"}
>
>[!DNL Audience Manager] nur Prozesse [!DNL ASCII] und [!DNL UTF-8] kodierte Dateien.

### Elemente benennen

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namenselement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>AWS_ Verzeichnis</i></code> </p> </td> 
   <td colname="col2"> <p>Der Pfad und der Name Ihres Amazon S 3 Bucket. Wenden Sie sich für Ihren Ordnernamen, Pfad und Ihre Anmeldeinformationen an Ihren Kundenbetreuer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date =<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitstempel (basierend auf der UTC-Zeit), wenn Sie die Dateien an den S 3-Behälter senden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="term"> Data Provider ID</span> (DPID) is an identifier that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Akzeptiert die folgenden Optionen: </p> <p> <b>Datenpartner-ID</b> </p> <p>Dies ist eine eindeutige ID Audience Manager für Ihr Unternehmen oder Unternehmen. Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </p> <p> <b>Android-IDs (GAID)</b> </p> <p> Verwenden Sie ID 20914 als DPID in einem Datendateinamen, wenn die Datei Android-IDs enthält. When you use ID 20914 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Angenommen, Sie übermitteln Dateien mit Android-IDs und Ihre Datenanbieter-ID ist 21. In this case, the file name would look like <code>...ftp_dpm_20914_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains Android IDs and is from a partner identified by ID 21. </p> <p> <b>Ios-IDs (IDFA)</b> </p> <p> Verwenden Sie ID 20915 als DPID in einem Datendateinamen, wenn die Datei ios-IDs enthält. When you use ID 20915 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Angenommen, Sie übermitteln Dateien mit Android-IDs und Ihre Datenanbieter-ID ist 21. In this case, the file name would look like <code>...ftp_dpm_20915_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains iOS IDs and is from a partner identified by ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Datenpartner-ID:</b> Dies ist eine eindeutige ID Audience Manager für Ihr Unternehmen oder Unternehmen. Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-IDs (GAID):</b> Verwenden Sie die ID 20914 in einem Datendateinamen, wenn sie Android-ID enthält. For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. Hinweis: Die ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>Ios-IDs (IDFA):</b> Verwenden Sie die ID 20915 in einem Datendateinamen, wenn sie ios-IDs enthält. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    </draft-comment> <p> <p>Hinweis: Keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise den Android-Bezeichner enthält, dürfen Sie keine ios-IDs oder keine eigenen IDs in der Datendatei angeben. </p> </p> <p>See also the <code><i>_DPID_TARGET_DATA_OWNER</i></code> entry below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Platzhalter für eine ID. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>Beispiel: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> zeigt einen Partner mit ID 21 an, der Daten aus einer Datenquelle gesendet hat, die ID 33 verwendet. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> zeigt einen Partner mit ID 21 an, der Daten mit Android-IDs gesendet hat. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> zeigt einen Partner mit ID 21 an, der Daten mit ios-IDs gesendet hat. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Eine 10-stellige UTC-Zeitstempel in Sekunden. Der Zeitstempel trägt dazu bei, jeden Dateinamen eindeutig zu machen. </p> 
    <draft-comment> 
     <p> <p>Hinweis: Audience Manager verwendet während der Verarbeitung von Inbound-Dateien den Zeitstempel nicht. Der Zeitstempel im Dateinamen wurde in Audience Manager nicht mehr unterstützt, ist aber dennoch für die Abwärtskompatibilität erforderlich. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synchronisierungsoptionen, die Folgendes beinhalten: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> synchronisieren: Normales Szenario, wenn Drittanbieter von Daten Eigenschaften pro Benutzer senden, um sie im Audience Manager-System hinzuzufügen oder zu entfernen.</code> </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> überschreiben</code>: Ermöglicht es Datenanbietern, eine Liste von Eigenschaften pro Benutzer zu senden, die alle bestehenden Drittanbietereigenschaften dieses Benutzers für diesen Datenanbieter im Audience Manager überschreiben sollten. Sie müssen nicht alle Benutzer in eine Überschreibungsdatei aufnehmen. Schließen Sie nur die Benutzer ein, die Sie ändern möchten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile aufteilen, um die Verarbeitungszeiten zu verbessern. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. </p> <p>Für eine effiziente Dateiverarbeitung teilen Sie die Datendateien wie angegeben: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Nicht komprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie beim Senden von Dateien an Amazon S 3 nur gzip-Komprimierung. When compressed, these files get the <code> .gz</code> extension. Verwenden Sie nicht.zip compression. </p> <p>Komprimierte Dateien müssen mindestens 3 GB groß sein. Wenn Ihre Dateien größer sind, wenden Sie sich an den Kundendienst. Obwohl Audience Manager große Dateien verarbeiten kann, können wir Ihnen eventuell dabei helfen, die Größe Ihrer Dateien zu verringern und Datenübertragungen effizienter zu gestalten. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. sync</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

You can [download](assets/ftp_dpm_1234_1445374061.overwrite) the sample file if you want additional examples. This file has been saved with the `.overwrite` file extension. Öffnen Sie es mit einem einfachen Texteditor.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateityp </th> 
   <th colname="col2" class="entry"> Optimale Größe </th> 
   <th colname="col3" class="entry"> Maximale Größe </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Komprimiert</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Nicht komprimiert</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Der eingehende Datenvalidierungsprozess markiert leere Dateien als ungültig und verarbeitet sie nicht.

>[!MORE_ LIKE_ THIS]
>
>* [FTP-Namensanforderungen für Inbound-Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

