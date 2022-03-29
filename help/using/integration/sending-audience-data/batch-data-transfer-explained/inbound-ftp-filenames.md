---
description: Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager beachtet werden müssen. Legen Sie die Dateinamen und Dateigrößen beim Senden von Daten an ein Audience Manager-FTP-Verzeichnis entsprechend diesen Spezifikationen fest.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Anforderungen an Namen und Dateigrößen der über FTP eingehenden Datendateien
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: 7721083fd538f0b74f72cfc78981e2cc76777790
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 6%

---

# [!DNL FTP]Anforderungen an Namen und Dateigrößen der über eingehenden Datendateien {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an [!DNL Audience Manager]. Legen Sie die Namen und Größen Ihrer Dateien beim Senden von Daten an einen Audience Manager gemäß diesen Spezifikationen fest. [!DNL FTP] Verzeichnis.

>[!WARNING]
>
>Die Unterstützung für [!DNL FTP] -Konfigurationen. Die Erfassung eingehender Datendateien wird weiterhin in vorhandenen unterstützt [!DNL FTP] Integrationen verwenden, wird dringend empfohlen, [!DNL Amazon S3] , um Offline-Daten für neue Integrationen zu integrieren. Weitere Informationen finden Sie unter [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Code-Elemente und -Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax von Dateinamen {#file-name-syntax}

[!DNL FTP] -Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Weitere akzeptierte Dateinamenformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] Nur Prozesse [!DNL ASCII] und [!DNL UTF-8] kodierte Dateien.

### Elemente benennen

Die Tabelle definiert die Elemente in einer [!DNL FTP] Dateiname.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateinamenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Pfad und Name Ihrer <span class="keyword"> Audience Manager</span> FTP-Verzeichnis. Wenden Sie sich an Ihren Kundenbetreuer, um das FTP-Verzeichnis und die Anmeldeinformationen zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Eine lD, die <span class="keyword"> Audience Manager</span> wenn eine Datendatei Ihre eigenen Benutzer-IDs, Android-IDs, iOS-IDs oder andere IDs enthält, die zu <a href="/help/using/features/global-data-sources.md"> globale Datenquellen</a>. Akzeptiert die folgenden Optionen:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Datenquellen-ID (auch als Datenanbieter-ID bezeichnet):</b> Dies ist eine eindeutige ID, die der Audience Manager einer Datenquelle zuweist (siehe Audience Manager <a href="/help/using/reference/ids-in-aam.md"> Index der IDs </a>). Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. Beispiel: <code>...ftp_dpm_21_123456789.sync</code> records <span class="keyword"> Audience Manager</span> , um Daten an IDs zu integrieren, die zur Datenquelle 21 gehören. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android IDs (GAID):</b> Verwenden Sie die ID 20914 in einem Datendateinamen, wenn sie Android-IDs enthält. Sie müssen das Feld verwenden <code><i>_DPID_TARGET_DATA_OWNER</i></code> wenn Sie Android-IDs verwenden. Beispiel: <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> records <span class="keyword"> Audience Manager</span> dass die Datendatei nur Android-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zu der <code><i>_DPID_TARGET_DATA_OWNER</i></code> Datenquelle.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS IDs (IDFA):</b> Verwenden Sie die ID 20915 in einem Datendateinamen, wenn sie iOS-IDs enthält. Sie müssen das Feld verwenden <code><i>_DPID_TARGET_DATA_OWNER</i></code> wenn Sie iOS IDs verwenden. Beispiel: <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> records <span class="keyword"> Audience Manager</span> dass die Datendatei nur iOS IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zu der <code><i>_DPID_TARGET_DATA_OWNER</i></code> Datenquelle.</li>
     <li> <b>IDs, die zu anderen globalen Datenquellen gehören</b>: Sie können Roku-IDs für Werbung (RIDA), Microsoft Advertising IDs (MAID) und andere IDs integrieren. Verwenden Sie die den einzelnen Datenquellen entsprechende Kennung, wie im Abschnitt <a href="/help/using/features/global-data-sources.md"> Artikel zu globalen Datenquellen</a>.</li> 
    </ul> <p> <p>Hinweis: Mischen Sie keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise die Android-ID enthält, dürfen Sie keine iOS IDs oder Ihre eigenen IDs in die Datendatei aufnehmen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Dieses Feld gibt dem Audience Manager an, zu welcher Datenquelle Daten integriert werden sollen. Dieses Feld ist erforderlich, wenn Sie die DPID auf eine Android-ID, iOS ID oder eine andere ID festlegen, die zu globalen Datenquellen gehört. Mit <span class="keyword"> Audience Manager</span> die Dateidaten wieder mit Ihrer Organisation verknüpfen. <br> Diese Zieldatenquelle muss Ihrem Unternehmen gehören. Um Daten von Zweitanbietern in eine Zieldatenquelle eines anderen Unternehmens aufnehmen zu können, müssen Sie über eine Zugriffszuordnung zwischen Ihrem Unternehmen und der Zieldatenquelle verfügen. Wenden Sie sich an Ihren Adobe-Berater oder an den Kundensupport, um die Zuordnung einzurichten.</p><p><b>Wichtiger Hinweis:</b> You <i>nicht</i> eine Zuordnung für bestehende Datenfreigabe-Beziehungen anfordern (für Zieldatenquellen, die zu anderen Unternehmen gehören, in die Sie Daten vor dem 14. März 2022 integriert haben). Die Zuordnung ist auch nicht erforderlich, wenn Daten in Zieldatenquellen integriert werden, die zu Ihrer PID gehören. </p> <p>Beispiel: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> teilt dem Audience Manager mit, dass Sie Kunden-IDs qualifizieren, die zur Datenquelle 33 gehören, und zwar für Eigenschaften oder Signale, die zur Datenquelle 21 gehören. </li> 
     <li> <b>Android IDs (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> records <span class="keyword"> Audience Manager</span> dass die Datendatei nur Android-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zur Datenquelle 21 gehören.</li> 
     <li> <b>iOS IDs (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> records <span class="keyword"> Audience Manager</span> dass die Datendatei nur iOS IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zur Datenquelle 21 gehören.</li>
     <li> <b>IDs, die zu anderen globalen Datenquellen gehören</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> records <span class="keyword"> Audience Manager</span> dass die Datendatei nur Roku-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zur Datenquelle 21 gehören. Verwenden Sie die den einzelnen Datenquellen entsprechende Kennung, wie im Abschnitt <a href="/help/using/features/global-data-sources.md"> Artikel zu globalen Datenquellen</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Zu den Synchronisierungsoptionen gehören: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normales Szenario, in dem Datenanbieter von Drittanbietern Eigenschaften pro Benutzer senden, um sie im Audience Manager-System hinzuzufügen oder zu entfernen. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Ermöglicht es Kunden und Datenanbietern, eine Liste von Eigenschaften pro Benutzer zu senden, die alle vorhandenen Eigenschaften dieses Benutzers für eine bestimmte Datenquelle in Audience Manager überschreiben sollten. Sie müssen nicht alle Ihre Benutzer in eine Überschreibungsdatei aufnehmen. Schließen Sie nur die Benutzer ein, die Sie ändern möchten. Eigenschaften, die nicht der Zieldatenquelle zugewiesen sind, werden nicht gelöscht. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile aufteilen, um die Verarbeitungszeiten zu verbessern. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. </p> <p>Um eine effiziente Dateiverarbeitung zu gewährleisten, teilen Sie Ihre Datendateien wie angegeben auf: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">unkomprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>Siehe die ersten 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> Beispiele für Dateinamen</a> unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UTC UNIX-Zeitstempel in Sekunden. Der Zeitstempel hilft dabei, jeden Dateinamen eindeutig zu machen. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip ist das zulässige Komprimierungsformat für einen FTP-Dateinamen. Wenn Sie die Dateikomprimierung verwenden, stellen Sie sicher, dass der Dateiname über die richtige Erweiterung verfügt. </p> <p>Komprimierte Dateien müssen 3 GB oder kleiner sein. Wenn Ihre Dateien größer sind, wenden Sie sich an die Kundenunterstützung. Obwohl Audience Manager große Dateien verarbeiten kann, können wir Ihnen möglicherweise helfen, die Dateigröße zu reduzieren und die Datenübertragung effizienter zu gestalten. Siehe <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Dateikomprimierung für eingehende Datenübertragungsdateien</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateinamen {#file-name-examples}

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Download](assets/ftp_dpm_1234_1445374061.overwrite) die Beispieldatei, wenn Sie zusätzliche Beispiele benötigen. Diese Datei wird zusammen mit dem `.overwrite` Dateierweiterung. Öffnen Sie es mit einem einfachen Texteditor.

## Akzeptierte Dateigrößen {#accepted-file-sizes}

Beachten Sie die folgenden Zahlen für die schnellste/früheste Verarbeitung Ihrer Dateien sowie für Dateigrößenbeschränkungen beim Senden von Daten an eine [!DNL Audience Manager] / [!DNL FTP] Verzeichnis.

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
   <td colname="col1"><b>unkomprimiert</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

