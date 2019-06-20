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


# Anforderungen an Name und Dateigröße von Amazon S 3 für Inbound-Datendateien{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen der Dateien gemäß diesen Spezifikationen fest, wenn Sie Daten an einen Zielgruppen-Manager/- [!DNL Amazon S3] Ordner senden.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Dateinamensyntax {#file-name-syntax}

[!DNL S3] Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

* **[!DNL S3]Präfix:**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Dateinamenelemente:**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Weitere akzeptierte Dateinamenformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {important = &quot;high&quot;}
>
>[!DNL Audience Manager] nur Prozesse [!DNL ASCII] und [!DNL UTF-8] kodierte Dateien.

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
   <td colname="col1"> <p> <code><i>AWS_ Verzeichnis</i></code> </p> </td> 
   <td colname="col2"> <p>Der Pfad und der Name Ihres Amazon S 3 Bucket. Wenden Sie sich für Ihren Ordnernamen, Pfad und Ihre Anmeldeinformationen an Ihren Kundenbetreuer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date =<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Zeitstempel (basierend auf der UTC-Zeit), wenn Sie die Dateien an den S 3-Behälter senden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Die <span class="term"> Data Provider ID</span> (DPID) ist eine Kennung, die <span class="keyword"> Audience Manager</span> teilt, wenn eine Datendatei Ihre eigenen Benutzer-IDs oder Android- oder ios-IDs enthält. Akzeptiert die folgenden Optionen: </p> <p> <b>Datenpartner-ID</b> </p> <p>Dies ist eine eindeutige ID Audience Manager für Ihr Unternehmen oder Unternehmen. Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. Beispiel: <code>… ftp_ dpm_ 21_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass ein Partner mit ID 21 die Datei versendet und die von diesem Partner zugewiesenen Benutzer-IDs enthält. </p> <p> <b>Android-IDs (GAID)</b> </p> <p> Verwenden Sie ID 20914 als DPID in einem Datendateinamen, wenn die Datei Android-IDs enthält. Wenn Sie ID 20914 als DPID verwenden, müssen Sie Ihr Unternehmen dennoch für <span class="keyword"> Audience Manager identifizieren</span>. Das bedeutet, dass der Dateiname den Parameter <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> verwenden muss, um Ihre Unternehmens-ID aufzunehmen. Angenommen, Sie übermitteln Dateien mit Android-IDs und Ihre Datenanbieter-ID ist 21. In diesem Fall würde der Dateiname wie <code>folgt aussehen:… ftp_ dpm_ 20914_ 21_ 123456789. sync</code>. Dies teilt <span class="keyword"> Audience Manager</span> mit, dass die Datei Android-IDs enthält und von einem Partner stammt, der durch ID 21 identifiziert wird. </p> <p> <b>Ios-IDs (IDFA)</b> </p> <p> Verwenden Sie ID 20915 als DPID in einem Datendateinamen, wenn die Datei ios-IDs enthält. Wenn Sie ID 20915 als DPID verwenden, müssen Sie Ihr Unternehmen dennoch für <span class="keyword"> Audience Manager identifizieren</span>. Das bedeutet, dass der Dateiname den Parameter <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> verwenden muss, um Ihre Unternehmens-ID aufzunehmen. Angenommen, Sie übermitteln Dateien mit Android-IDs und Ihre Datenanbieter-ID ist 21. In diesem Fall würde der Dateiname wie <code>folgt aussehen:… ftp_ dpm_ 20915_ 21_ 123456789. sync</code>. Dies teilt <span class="keyword"> Audience Manager</span> mit, dass die Datei ios-IDs enthält und von einem Partner stammt, der durch ID 21 identifiziert wird. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Datenpartner-ID:</b> Dies ist eine eindeutige ID Audience Manager für Ihr Unternehmen oder Unternehmen. Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. Beispiel: <code>… ftp_ dpm_ 21_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass ein Partner mit ID 21 die Datei versendet und die von diesem Partner zugewiesenen Benutzer-IDs enthält. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-IDs (GAID):</b> Verwenden Sie die ID 20914 in einem Datendateinamen, wenn sie Android-ID enthält. Beispiel: <code>… ftp_ dpm_ 20914_ 21_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass die Datendatei nur Android-IDs enthält. Hinweis: Die ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>Ios-IDs (IDFA):</b> Verwenden Sie die ID 20915 in einem Datendateinamen, wenn sie ios-IDs enthält. Beispiel: <code>… ftp_ dpm_ 20915_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass die Datendatei nur ios-IDs enthält. </li> 
     </ul> 
    </draft-comment> <p> <p>Hinweis: Keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise den Android-Bezeichner enthält, dürfen Sie keine ios-IDs oder keine eigenen IDs in der Datendatei angeben. </p> </p> <p>Siehe auch der <code><i>unten stehende Eintrag_ DPID_ TARGET_ DATA_ OWNER</i></code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Ein Platzhalter für eine ID. Sie können es beispielsweise auf Ihre <span class="keyword"> Audience Manager</span> -ID festlegen, wenn Sie die DPID auf eine Datenquellen-ID oder eine Android- oder ios-ID setzen. Dadurch kann <span class="keyword"> Audience Manager</span> die Dateidaten wieder an Ihr Unternehmen zurücksenden. </p> <p>Beispiel: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> zeigt einen Partner mit ID 21 an, der Daten aus einer Datenquelle gesendet hat, die ID 33 verwendet. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> zeigt einen Partner mit ID 21 an, der Daten mit Android-IDs gesendet hat. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> zeigt einen Partner mit ID 21 an, der Daten mit ios-IDs gesendet hat. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>Das Unternehmen oder der Unternehmensname, den Sie in <span class="keyword"> Audience Manager verwenden</span>. </p> </td> 
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
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normal scenario when third-party data providers send traits on a per-user basis to be added or removed in the Audience Manager system. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> überschreiben</code>: Ermöglicht es Datenanbietern, eine Liste von Eigenschaften pro Benutzer zu senden, die alle bestehenden Drittanbietereigenschaften dieses Benutzers für diesen Datenanbieter im Audience Manager überschreiben sollten. Sie müssen nicht alle Benutzer in eine Überschreibungsdatei aufnehmen. Schließen Sie nur die Benutzer ein, die Sie ändern möchten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile aufteilen, um die Verarbeitungszeiten zu verbessern. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. </p> <p>Für eine effiziente Dateiverarbeitung teilen Sie die Datendateien wie angegeben: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Nicht komprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>Siehe die ersten 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> Dateinamen</a> unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie beim Senden von Dateien an Amazon S 3 nur gzip-Komprimierung. Bei Komprimierung erhalten diese Dateien die <code> .gz</code> Erweiterung. Verwenden Sie nicht.zip compression. </p> <p>Komprimierte Dateien müssen mindestens 3 GB groß sein. Wenn Ihre Dateien größer sind, wenden Sie sich an den Kundendienst. Obwohl Audience Manager große Dateien verarbeiten kann, können wir Ihnen eventuell dabei helfen, die Größe Ihrer Dateien zu verringern und Datenübertragungen effizienter zu gestalten. Siehe <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Dateikomprimierung für Dateien mit Inbound-Datenübertragung</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateiname {#file-name-examples}

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. sync</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

Sie können [die Beispieldatei herunterladen](assets/ftp_dpm_1234_1445374061.overwrite) , wenn Sie weitere Beispiele wünschen. Diese Datei wurde mit der `.overwrite` Dateierweiterung gespeichert. Öffnen Sie es mit einem einfachen Texteditor.

## Akzeptierte Dateigrößen {#accepted-file-sizes}

Berücksichtigen Sie die unten stehenden Zahlen für die schnellste/früheste Verarbeitung Ihrer Dateien sowie für die Dateigrößenbeschränkungen, wenn Sie Daten an ein [!DNL Audience Manager] Verzeichnis senden [!DNL Amazon S3] .

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

