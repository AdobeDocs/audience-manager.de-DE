---
description: Beschreibt die erforderlichen Felder, die Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Dateinamen und -größen beim Senden von Daten an ein Audience Manager-FTP-Verzeichnis gemäß diesen Spezifikationen fest.
seo-description: Beschreibt die erforderlichen Felder, die Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Dateinamen und -größen beim Senden von Daten an ein Audience Manager-FTP-Verzeichnis gemäß diesen Spezifikationen fest.
seo-title: Anforderungen an Namen und Dateigrößen der über FTP eingehenden Datendateien
solution: Audience Manager
title: Anforderungen an Namen und Dateigrößen der über FTP eingehenden Datendateien
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 8%

---


# [!DNL FTP]Anforderungen an Namen und Dateigrößen der über eingehenden Datendateien{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, die Syntax, Benennungskonventionen und Dateigrößen, die beim Senden der Daten an [!DNL Audience Manager]eingehalten werden müssen. Legen Sie die Dateinamen und -größen beim Senden von Daten an einen Audience Manager- [!DNL FTP] Ordner gemäß diesen Spezifikationen fest.

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Weitere Informationen finden Sie unter [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Codeelemente und Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax des Dateinamens {#file-name-syntax}

[!DNL FTP] Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Weitere akzeptierte Dateinamenformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] verarbeitet [!DNL ASCII] und [!DNL UTF-8] kodiert.

### Elemente benennen

Die Tabelle definiert die Elemente in einem [!DNL FTP] Dateinamen.

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
   <td colname="col2"> <p>Pfad und Name des FTP-Ordners Ihres <span class="keyword"> Audience Managers</span> . Wenden Sie sich an Ihren Kundenbetreuer, um den FTP-Ordner und die Anmeldeinformationen zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Eine ID, die dem <span class="keyword"> Audience Manager</span> mitteilt, ob eine Datendatei Ihre eigenen Benutzer-IDs, Android-IDs, iOS-IDs oder andere IDs enthält, die zu <a href="/help/using/features/global-data-sources.md"> globalen Datenquellen</a>gehören. Akzeptiert die folgenden Optionen:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Datenquellen-ID (auch als Datenanbieter-ID bezeichnet):</b> Hierbei handelt es sich um eine eindeutige ID, die Audience Manager einer Datenquelle zuweist (siehe Audience Manager- <a href="/help/using/reference/ids-in-aam.md"> Index der IDs </a>). Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten mit Ihren eigenen Benutzer-IDs senden. Weisen Sie z. B. <code>...ftp_dpm_21_123456789.sync</code> Audience Manager <span class="keyword"></span> zu integrierten Daten an IDs aus, die zu Datenquelle 21 gehören. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-IDs (GAID):</b> Verwenden Sie die ID 20914 in einem Datendateinamen, wenn sie Android-IDs enthält. Sie müssen das Feld verwenden, <code><i>_DPID_TARGET_DATA_OWNER</i></code> wenn Sie Android-IDs verwenden. Weist <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> Audience Manager <span class="keyword"> beispielsweise an, dass die Datendatei nur Android-IDs enthält und die IDs für die Eigenschaften der</span> <code><i>_DPID_TARGET_DATA_OWNER</i></code> Datenquelle qualifiziert sein sollten.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-IDs (IDFA):</b> Verwenden Sie die ID 20915 in einem Datendateinamen, wenn sie iOS-IDs enthält. Sie müssen das Feld verwenden, <code><i>_DPID_TARGET_DATA_OWNER</i></code> wenn Sie iOS-IDs verwenden. Weisen Sie beispielsweise <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> den <span class="keyword"> Audience Manager</span> an, dass die Datendatei nur iOS-IDs enthält und die IDs für die Eigenschaften der <code><i>_DPID_TARGET_DATA_OWNER</i></code> Datenquelle qualifiziert sein sollten.</li>
     <li> <b>IDs, die zu anderen globalen Datenquellen</b>gehören: Sie können Roku-IDs für Werbung (RIDA), Microsoft Advertising IDs (MAID) und andere IDs einbinden. Verwenden Sie die ID für jede Datenquelle, wie im Artikel <a href="/help/using/features/global-data-sources.md"> zu</a>globalen Datenquellen beschrieben.</li> 
    </ul> <p> <p>Hinweis:  Mischen Sie keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise die Android-ID enthält, sollten Sie keine iOS-IDs oder Ihre eigenen IDs in die Datendatei aufnehmen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Dieses Feld gibt Audience Manager an, zu welcher Datenquelle Daten an Bord gesendet werden sollen. Dieses Feld ist obligatorisch, wenn Sie die DPID auf eine Android-ID, iOS-ID oder eine andere ID festlegen, die zu globalen Datenquellen gehört. Dadurch kann <span class="keyword"> Audience Manager</span> die Dateidaten wieder mit Ihrem Unternehmen verknüpfen. </p> <p>Beispiel: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> weist Audience Manager an, dass Sie Kunden-IDs aus der Datenquelle 33 für Eigenschaften oder Signale aus der Datenquelle 21 qualifizieren. </li> 
     <li> <b>Android-IDs (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> weist <span class="keyword"> Audience Manager</span> an, dass die Datendatei nur Android-IDs enthält und die IDs für die Eigenschaften von Datenquelle 21 qualifiziert sein sollten.</li> 
     <li> <b>iOS-IDs (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> weist <span class="keyword"> Audience Manager</span> an, dass die Datendatei nur iOS-IDs enthält und die IDs für die Eigenschaften von Datenquelle 21 qualifiziert sein sollten.</li>
     <li> <b>IDs, die zu anderen globalen Datenquellen</b>gehören: <code>...ftp_dpm_121963_21_1234567890.sync</code> weist <span class="keyword"> Audience Manager</span> an, dass die Datendatei nur Roku-IDs enthält und die IDs für die Eigenschaften von Datenquelle 21 qualifiziert sein sollten. Verwenden Sie die ID für jede Datenquelle, wie im Artikel <a href="/help/using/features/global-data-sources.md"> zu</a>globalen Datenquellen beschrieben.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Zu den Synchronisierungsoptionen gehören: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normales Szenario, bei dem Drittanbieter von Daten Eigenschaften auf Benutzerbasis senden, die im Audience Manager-System hinzugefügt oder entfernt werden sollen. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Ermöglicht es Kunden und Datenanbietern, eine Liste von Eigenschaften pro Benutzer zu senden, die alle bestehenden Eigenschaften dieses Benutzers für eine bestimmte Datenquelle in Audience Manager überschreiben sollten. Sie müssen nicht alle Benutzer in eine Überschreibungsdatei einschließen. Schließen Sie nur die Benutzer ein, die Sie ändern möchten. Eigenschaften, die nicht der Datenquelle der Zielgruppe zugewiesen sind, werden nicht gelöscht. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile teilen, um die Verarbeitungszeit zu verbessern. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. </p> <p>Zur effizienten Dateiverarbeitung teilen Sie die Datendateien wie folgt: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Unkomprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>Siehe die ersten beiden Beispiele für <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> Dateinamen</a> unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UTC UNIX-Zeitstempel in Sekunden. Der Zeitstempel hilft, jeden Dateinamen eindeutig zu machen. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip ist das zulässige Komprimierungsformat für einen FTP-Dateinamen. Wenn Sie die Dateikomprimierung verwenden, stellen Sie sicher, dass der Dateiname die richtige Erweiterung hat. </p> <p>Komprimierte Dateien müssen mindestens 3 GB groß sein. Falls Ihre Dateien größer sind, wenden Sie sich bitte an den Kundendienst. Obwohl Audience Manager große Dateien verarbeiten kann, können wir Ihnen möglicherweise helfen, die Dateigröße zu reduzieren und die Datenübertragung effizienter zu gestalten. Siehe <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Dateikomprimierung für eingehende Datenübertragungsdateien</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateinamen {#file-name-examples}

Die folgenden Beispiele zeigen korrekt formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Laden Sie](assets/ftp_dpm_1234_1445374061.overwrite) die Beispieldatei herunter, wenn Sie weitere Beispiele benötigen. Diese Datei wird mit der `.overwrite` Dateierweiterung gespeichert. Öffnen Sie es mit einem einfachen Texteditor.

## Akzeptierte Dateigrößen {#accepted-file-sizes}

Betrachten Sie die unten stehenden Zahlen für eine schnellste/früheste Verarbeitung Ihrer Dateien sowie für Dateigrößenbeschränkungen, wenn Sie Daten an ein [!DNL Audience Manager] / [!DNL FTP] Verzeichnis senden.

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

>[!MORELIKETHIS]
>
>* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

