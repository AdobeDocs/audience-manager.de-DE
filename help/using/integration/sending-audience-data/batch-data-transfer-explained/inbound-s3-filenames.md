---
description: Beschreibt die erforderlichen Felder, die Syntax, Namenskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager befolgt werden müssen. Legen Sie die Namen und Größen Ihrer Dateien entsprechend diesen Spezifikationen fest, wenn Sie Daten an ein Audience Manager-/Amazon S3-Verzeichnis senden.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Anforderungen an Amazon S3-Namen und -Dateigrößen für eingehende Datendateien
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 2%

---

# Anforderungen an [!DNL Amazon S3] und Dateigröße eingehender Datendateien {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, die Syntax, Namenskonventionen und Dateigrößen, die beim Senden von Daten an [!DNL Audience Manager] befolgt werden müssen. Legen Sie die Namen und Größen Ihrer Dateien entsprechend diesen Spezifikationen fest, wenn Sie Daten an ein [!DNL Audience Manager]/[!DNL Amazon S3]-Verzeichnis senden.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument weisen auf Codeelemente und Optionen hin. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Dateinamensyntax {#file-name-syntax}

[!DNL S3] Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

* **[!DNL S3]:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Dateinamenelemente:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Informationen zu anderen akzeptierten Dateinamenformaten finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] verarbeitet nur [!DNL ASCII] und [!DNL UTF-8] Dateien.

### Namenselemente

Die Tabelle definiert die Elemente in einem [!DNL S3] Dateinamen.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name des Elements </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Der Pfad zu und der Name Ihres Amazon S3-Buckets. Wenden Sie sich an Ihren Account Manager, um Ihren S3-Verzeichnisnamen, -Pfad und Ihre Anmeldeinformationen zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitstempel (basierend auf der UTC-Zeit), der angibt, wann Sie die Dateien an Ihren S3-Bucket senden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Eine L-ID, die <span class="keyword"> Audience Manager </span>, wenn eine Datendatei Ihre eigenen Benutzer-IDs, Android-IDs, iOS-IDs oder andere IDs enthält, die zu <a href="/help/using/features/global-data-sources.md"> globalen Datenquellen gehören</a>. Akzeptiert die folgenden Optionen:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Daten-Source-ID (auch als Datenanbieter-ID bezeichnet):</b> Dies ist eine eindeutige ID, die Audience Manager einer Datenquelle zuweist (siehe den Audience Manager <a href="/help/using/reference/ids-in-aam.md">-ID-Index </a>). Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. Beispielsweise weist <code>...ftp_dpm_21_123456789.sync</code> <span class="keyword"> Audience Manager an</span> Daten in IDs zu integrieren, die zur Datenquelle 21 gehören. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-IDs (GAID):</b> Verwenden Sie ID-20914 in einem Datendateinamen, wenn sie Android-IDs enthält. Sie müssen die <code><i>_DPID_TARGET_DATA_OWNER</i></code> verwenden, wenn Sie Android-IDs verwenden. Beispielsweise teilt <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> <span class="keyword"> Audience Manager mit</span> dass die Datendatei nur Android-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zur <code><i>_DPID_TARGET_DATA_OWNER</i></code> Datenquelle gehören.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-IDs (IDFA):</b> Verwenden Sie ID-20915 in einem Datendateinamen, wenn sie iOS-IDs enthält. Sie müssen die <code><i>_DPID_TARGET_DATA_OWNER</i></code> verwenden, wenn Sie iOS-IDs verwenden. Beispielsweise teilt <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> <span class="keyword"> Audience Manager mit</span> dass die Datendatei nur iOS-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zur <code><i>_DPID_TARGET_DATA_OWNER</i></code> Datenquelle gehören.</li>
     <li> <b>IDs, die zu anderen globalen Datenquellen gehören</b>: Sie können Roku-IDs für Advertising (RIDA), Microsoft Advertising-IDs (MAID) und andere IDs integrieren. Verwenden Sie die ID, die jeder Datenquelle entspricht, wie im Artikel <a href="/help/using/features/global-data-sources.md"> globale Datenquellen beschrieben</a>.</li> 
    </ul> <p> <p>Hinweis: Mischen Sie keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise die Android-Kennung enthält, fügen Sie keine iOS-IDs oder Ihre eigenen IDs in die Datendatei ein. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Dieses Feld teilt Audience Manager mit, in welche Datenquelle Daten integriert werden sollen. Dieses Feld ist obligatorisch, wenn Sie für die DPID eine Android-ID, eine iOS-ID oder eine andere ID festlegen, die zu globalen Datenquellen gehört. Auf diese Weise kann Audience Manager die Dateidaten mit Ihrer Organisation verknüpfen. <br> Diese Zieldatenquelle muss Ihrem Unternehmen gehören. Für die gemeinsame Datennutzung durch Zweitanbieter müssen Sie über ein Zugriffs-Mapping zwischen Ihrem Unternehmen und der Zieldatenquelle verfügen, um Daten in eine Zieldatenquelle eines anderen Unternehmens aufnehmen zu können. Wenden Sie sich an Ihren Adobe-Berater oder den Kunden-Support, um die Zuordnung einzurichten.</p> <p><b>Wichtiger Hinweis:</b> Sie <i>müssen </i> eine Zuordnung für bestehende Datenfreigabebeziehungen anfordern (für Zieldatenquellen anderer Unternehmen, in die Sie vor dem 14. März 2022 Daten integriert haben). Die Zuordnung ist auch nicht erforderlich, wenn Daten in Zieldatenquellen integriert werden, die zu Ihrer PID gehören. </p> <p>Beispiel: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> teilt Audience Manager mit, dass Sie Kunden-IDs aus Datenquelle 33 für Eigenschaften oder Signale aus Datenquelle 21 qualifizieren. </li> 
     <li> <b>Android-IDs (GAID): </b> <code>...ftp_dpm_20914_21_1234567890.sync</code> teilt <span class="keyword"> Audience Manager mit</span> dass die Datendatei nur Android-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zu Datenquelle 21 gehören.</li> 
     <li> <b>iOS-IDs (IDFA): </b> <code>...ftp_dpm_20915_21_1234567890.sync</code> teilt <span class="keyword"> Audience Manager mit</span> dass die Datendatei nur iOS-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zu Datenquelle 21 gehören.</li>
     <li> <b>IDs, die zu anderen globalen Datenquellen gehören</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> teilt <span class="keyword"> Audience Manager </span> mit, dass die Datendatei nur Roku-IDs enthält und die IDs für die Eigenschaften qualifiziert sein sollten, die zu Datenquelle 21 gehören. Verwenden Sie die ID, die jeder Datenquelle entspricht, wie im Artikel <a href="/help/using/features/global-data-sources.md"> globale Datenquellen beschrieben</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Der Unternehmens- oder Organisationsname, den Sie in <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UTC-UNIX-Zeitstempel in Sekunden. Der Zeitstempel hilft dabei, jeden Dateinamen eindeutig zu machen. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Zu den Synchronisierungsoptionen gehören: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normales Szenario, in dem Drittanbieter von Daten Eigenschaften pro Benutzer senden, um sie im Audience Manager-System hinzuzufügen oder zu entfernen. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Ermöglicht es Datenanbietern, eine Liste von Eigenschaften pro Benutzer zu senden, durch die alle bestehenden Drittanbietereigenschaften dieses Benutzers für diesen Datenanbieter in der Audience Manager überschrieben werden sollen. Sie müssen nicht alle Ihre Benutzer in eine Überschreibungsdatei einbeziehen. Nur die Benutzer einbeziehen, die geändert werden sollen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile aufteilen, um die Verarbeitungszeit zu verbessern. Die Zahl gibt an, welchen Teil der Originaldatei Sie senden. </p> <p>Teilen Sie Ihre Datendateien wie angegeben auf, um eine effiziente Dateiverarbeitung zu gewährleisten: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Unkomprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>Nachfolgend finden Sie die ersten zwei Beispiele für <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples">-</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie beim Senden von Dateien an Amazon S3 nur gzip-Komprimierung. Nach der Komprimierung erhalten diese Dateien die Erweiterung <code> .gz</code> . Verwenden Sie keine .zip-Komprimierung. </p> <p>Komprimierte Dateien müssen 3 GB oder weniger groß sein. Wenn Ihre Dateien größer sind, wenden Sie sich an die Kundenunterstützung. Auch wenn Audience Manager große Dateien verarbeiten kann, können wir Sie möglicherweise dabei unterstützen, die Größe Ihrer Dateien zu reduzieren und die Datenübertragung effizienter zu gestalten. Siehe <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Dateikomprimierung für eingehende Datenübertragungsdateien</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateinamen {#file-name-examples}

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Sie können [ Beispieldatei ](assets/ftp_dpm_1234_1445374061.overwrite), wenn Sie zusätzliche Beispiele benötigen. Diese Datei wurde mit der Dateierweiterung `.overwrite` gespeichert. Öffnen Sie sie mit einem einfachen Texteditor.

## Akzeptierte Dateigrößen {#accepted-file-sizes}

Beachten Sie die folgenden Zahlen für die schnellste/früheste Verarbeitung Ihrer Dateien sowie für Dateigrößenbeschränkungen, wenn Sie Daten an ein [!DNL Audience Manager]/[!DNL Amazon S3]-Verzeichnis senden.

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


>[!NOTE]
>
>Der Validierungsprozess eingehender Daten markiert leere Dateien als ungültig und verarbeitet sie nicht.

## Längenbeschränkungen für Zeilen {#line-limits}

Eingehende Datendateien haben eine Zeilenlängenbeschränkung von 102400 Byte. Zeilen, die diesen Grenzwert überschreiten, sind von der Übertragung ausgeschlossen.

>[!MORELIKETHIS]
>
>* [FTP-Namensanforderungen für Inbound-Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
