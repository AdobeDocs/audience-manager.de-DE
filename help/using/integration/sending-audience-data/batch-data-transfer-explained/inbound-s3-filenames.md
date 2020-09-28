---
description: Beschreibt die erforderlichen Felder, die Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien entsprechend diesen Spezifikationen fest, wenn Sie Daten an einen Audience Manager/Amazon S3-Ordner senden.
seo-description: Beschreibt die erforderlichen Felder, die Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien entsprechend diesen Spezifikationen fest, wenn Sie Daten an einen Audience Manager/Amazon S3-Ordner senden.
seo-title: Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien
solution: Audience Manager
title: Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e8eb1c1c7a235c0c9dd32182e522ad0b6e965c61
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 7%

---


# [!DNL Amazon S3]Anforderungen an Namen und Dateigrößen der über eingehenden Datendateien{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, die Syntax, Benennungskonventionen und Dateigrößen, die beim Senden der Daten an [!DNL Audience Manager]eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien entsprechend diesen Spezifikationen fest, wenn Sie Daten an ein [!DNL Audience Manager] /- [!DNL Amazon S3] Verzeichnis senden.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Codeelemente und Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax des Dateinamens {#file-name-syntax}

[!DNL S3] Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

* **[!DNL S3]Präfix:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Dateinamenelemente:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Weitere akzeptierte Dateinamenformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] verarbeitet [!DNL ASCII] und [!DNL UTF-8] kodiert.

### Elemente benennen

Die Tabelle definiert die Elemente in einem [!DNL S3] Dateinamen.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namenselement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Der Pfad und der Name Ihres Amazon S3-Behälters. Wenden Sie sich an Ihren Kundenbetreuer, um Ihren S3-Ordnernamen, -Pfad und Ihre Anmeldeinformationen zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitstempel (basierend auf der UTC-Zeit), mit dem die Dateien an den S3-Behälter gesendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Eine ID, die dem <span class="keyword"> Audience Manager</span> mitteilt, ob eine Datendatei Ihre eigenen Benutzer-IDs, Android-IDs, iOS-IDs oder andere IDs enthält, die zu <a href="/help/using/features/global-data-sources.md"> globalen Datenquellen</a>gehören. Akzeptiert die folgenden Optionen:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Datenquellen-ID (auch als Datenanbieter-ID bezeichnet):</b> Hierbei handelt es sich um eine eindeutige ID, die Audience Manager einer Datenquelle zuweist (siehe Audience Manager- <a href="/help/using/reference/ids-in-aam.md"> Index der IDs </a>). Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten mit Ihren eigenen Benutzer-IDs senden. Weisen Sie z. B. <code>...ftp_dpm_21_123456789.sync</code> Audience Manager <span class="keyword"></span> zu integrierten Daten an IDs aus, die zu Datenquelle 21 gehören. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-IDs (GAID):</b> Verwenden Sie die ID 20914 in einem Datendateinamen, wenn sie Android-IDs enthält. Weist <code>...ftp_dpm_20914_123456789.sync</code> Audience Manager <span class="keyword"></span> beispielsweise an, dass die Datendatei nur Android-IDs enthält. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-IDs (IDFA):</b> Verwenden Sie die ID 20915 in einem Datendateinamen, wenn sie iOS-IDs enthält. Weist <code>...ftp_dpm_20915_123456789.sync</code> Audience Manager <span class="keyword"></span> beispielsweise an, dass die Datendatei nur iOS-IDs enthält. </li>
     <li> <b>IDs, die zu anderen globalen Datenquellen</b>gehören: Sie können Roku-IDs für Werbung (RIDA), Microsoft Advertising IDs (MAID) und andere IDs einbinden. Verwenden Sie die ID für jede Datenquelle, wie im Artikel <a href="/help/using/features/global-data-sources.md"> zu</a>globalen Datenquellen beschrieben.</li> 
    </ul> <p> <p>Hinweis:  Mischen Sie keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise die Android-ID enthält, sollten Sie keine iOS-IDs oder Ihre eigenen IDs in die Datendatei aufnehmen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Ein Platzhalter für eine ID. Sie können sie beispielsweise auf Ihre <span class="keyword"> Audience Manager</span> -ID einstellen, wenn Sie die DPID auf eine Datenquellen-ID oder eine Android- oder iOS-ID festlegen. Dadurch kann <span class="keyword"> Audience Manager</span> die Dateidaten wieder mit Ihrem Unternehmen verknüpfen. </p> <p>Beispiel: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> zeigt, dass ein Partner mit ID 21 Daten aus einer Datenquelle mit ID 33 gesendet hat. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> zeigt, dass ein Partner mit ID 21 Daten gesendet hat, die Android-IDs enthalten. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> zeigt, dass ein Partner mit ID 21 Daten gesendet hat, die iOS-IDs enthalten. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Der Firmen- oder Organisationsname, den Sie in <span class="keyword"> Audience Manager</span>verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UTC UNIX-Zeitstempel in Sekunden. Der Zeitstempel hilft, jeden Dateinamen eindeutig zu machen. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Zu den Synchronisierungsoptionen gehören: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normales Szenario, bei dem Drittanbieter von Daten Eigenschaften auf Benutzerbasis senden, die im Audience Manager-System hinzugefügt oder entfernt werden sollen. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Damit können Datenanbieter eine Liste von Eigenschaften pro Benutzer senden, die alle bestehenden Drittanbietereigenschaften dieses Benutzers für diesen Datenanbieter im Audience Manager überschreiben sollte. Sie müssen nicht alle Benutzer in eine Überschreibungsdatei einschließen. Schließen Sie nur die Benutzer ein, die Sie ändern möchten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile teilen, um die Verarbeitungszeit zu verbessern. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. </p> <p>Zur effizienten Dateiverarbeitung teilen Sie die Datendateien wie folgt: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Unkomprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>Siehe die ersten beiden Beispiele für <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> Dateinamen</a> unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie beim Senden von Dateien an Amazon S3 nur die gzip-Komprimierung. Nach der Komprimierung erhalten diese Dateien die <code> .gz</code> Erweiterung. Verwenden Sie keine ZIP-Komprimierung. </p> <p>Komprimierte Dateien müssen mindestens 3 GB groß sein. Wenn Ihre Dateien größer sind, wenden Sie sich bitte an den Kundendienst. Obwohl Audience Manager große Dateien verarbeiten kann, können wir Ihnen möglicherweise helfen, die Dateigröße zu reduzieren und die Datenübertragung effizienter zu gestalten. Siehe <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Dateikomprimierung für eingehende Datenübertragungsdateien</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateinamen {#file-name-examples}

Die folgenden Beispiele zeigen korrekt formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Sie können die Beispieldatei [herunterladen](assets/ftp_dpm_1234_1445374061.overwrite) , wenn Sie weitere Beispiele wünschen. Diese Datei wurde mit der `.overwrite` Dateierweiterung gespeichert. Öffnen Sie es mit einem einfachen Texteditor.

## Akzeptierte Dateigrößen {#accepted-file-sizes}

Betrachten Sie die unten stehenden Zahlen für eine schnellste/früheste Verarbeitung Ihrer Dateien sowie für Dateigrößenbeschränkungen, wenn Sie Daten an ein [!DNL Audience Manager] / [!DNL Amazon S3] Verzeichnis senden.

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
   <td colname="col1"><b>komprimiert</b> </td> 
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

>[!NOTE]
>
>Der Prozess der eingehenden Datenvalidierung markiert leere Dateien als ungültig und verarbeitet sie nicht.

>[!MORELIKETHIS]
>
>* [FTP-Namensanforderungen für Inbound-Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

