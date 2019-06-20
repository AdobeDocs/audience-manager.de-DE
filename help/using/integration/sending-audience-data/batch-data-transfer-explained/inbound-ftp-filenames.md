---
description: Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien gemäß diesen Spezifikationen fest, wenn Sie Daten an einen FTP-Ordner von Audience Manager senden.
seo-description: Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien gemäß diesen Spezifikationen fest, wenn Sie Daten an einen FTP-Ordner von Audience Manager senden.
seo-title: Anforderungen an FTP-Name und Dateigröße für Inbound-Datendateien
solution: Audience Manager
title: Anforderungen an FTP-Name und Dateigröße für Inbound-Datendateien
uuid: 49 eaafac -5 cb 0-482 f -872 a -84 c 056016 bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Anforderungen an FTP-Name und Dateigröße für Inbound-Datendateien{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beschreibt die erforderlichen Felder, Syntax, Benennungskonventionen und Dateigrößen, die beim Senden von Daten an Audience Manager eingehalten werden müssen. Legen Sie die Namen und Größen Ihrer Dateien gemäß diesen Spezifikationen fest, wenn Sie Daten an einen Audience Manager [!DNL FTP] -Ordner senden.

>[!WARNING]
>
>FTP-Übertragung für eingehende Datendateien wird nicht mehr unterstützt. Bitte verwenden Sie Amazon S 3 für Offline-Offline-Daten. Weitere Informationen finden Sie unter [Amazon S 3-Name und Dateigrößenanforderungen für eingehende Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Dateinamensyntax {#file-name-syntax}

[!DNL FTP] Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Weitere akzeptierte Dateinamenformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {important = &quot;high&quot;}
>
>[!DNL Audience Manager] nur Prozesse [!DNL ASCII] und [!DNL UTF-8] kodierte Dateien.

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
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p>Der Pfad zu und den Namen Ihres <span class="keyword"> FTP-Ordners</span> für Audience Manager. Wenden Sie sich für den FTP-Ordner und die Anmeldeinformationen an Ihren Kundenbetreuer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Eine LD, die <span class="keyword"> Audience Manager</span> angibt, wenn eine Datendatei Ihre eigenen Benutzer-IDs oder Android- oder ios-IDs enthält. Akzeptiert die folgenden Optionen: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Datenpartner-ID:</b> Dies ist eine eindeutige ID Audience Manager für Ihr Unternehmen oder Unternehmen. Verwenden Sie diese zugewiesene ID in einem Dateinamen, wenn Sie Daten senden, die Ihre eigenen Benutzer-IDs enthalten. Beispiel: <code>… ftp_ dpm_ 21_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass ein Partner mit ID 21 die Datei versendet und die von diesem Partner zugewiesenen Benutzer-IDs enthält. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-IDs (GAID):</b> Verwenden Sie die ID 20914 in einem Datendateinamen, wenn sie Android-ID enthält. Beispiel: <code>… ftp_ dpm_ 20914_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass die Datendatei nur Android-IDs enthält. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>Ios-IDs (IDFA):</b> Verwenden Sie die ID 20915 in einem Datendateinamen, wenn sie ios-IDs enthält. Beispiel: <code>… ftp_ dpm_ 20915_ 123456789. sync</code> teilt <span class="keyword"> Audience Manager</span> mit, dass die Datendatei nur ios-IDs enthält. </li> 
    </ul> <p> <p>Hinweis: Keine ID-Typen in Ihren Datendateien. Wenn Ihr Dateiname beispielsweise den Android-Bezeichner enthält, dürfen Sie keine ios-IDs oder keine eigenen IDs in der Datendatei angeben. </p> </p> </td> 
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
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synchronisierungsoptionen, die Folgendes beinhalten: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normal scenario when third-party data providers send traits on a per-user basis to be added or removed in the Audience Manager system. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> überschreiben</code>: Ermöglicht Kunden und Datenanbietern, eine Liste von Eigenschaften pro Benutzer zu senden, die alle vorhandenen Eigenschaften dieses Benutzers für eine bestimmte Datenquelle in Audience Manager überschreiben sollten. Sie müssen nicht alle Benutzer in eine Überschreibungsdatei aufnehmen. Schließen Sie nur die Benutzer ein, die Sie ändern möchten. Eigenschaften, die nicht der Zieldatenquelle zugewiesen sind, werden nicht gelöscht. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere Teile aufteilen, um die Verarbeitungszeiten zu verbessern. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. </p> <p>Für eine effiziente Dateiverarbeitung teilen Sie die Datendateien wie angegeben: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Nicht komprimiert: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimiert: 200-300 MB </li> 
    </ul> <p>Siehe die ersten 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> Dateinamen</a> unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Eine 10-stellige UTC-Zeitstempel in Sekunden. Der Zeitstempel trägt dazu bei, jeden Dateinamen eindeutig zu machen. </p> 
    <draft-comment> 
     <p> <p>Hinweis: Audience Manager verwendet während der Verarbeitung von Inbound-Dateien den Zeitstempel nicht. Der Zeitstempel im Dateinamen wurde in Audience Manager nicht mehr unterstützt, ist aber dennoch für die Abwärtskompatibilität erforderlich. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip ist das zulässige Komprimierungsformat für einen FTP-Dateinamen. Wenn Sie die Dateikomprimierung verwenden, stellen Sie sicher, dass der Dateiname über die richtige Erweiterung verfügt. </p> <p>Komprimierte Dateien müssen mindestens 3 GB groß sein. Wenn Ihre Dateien größer sind, wenden Sie sich bitte an den Kundendienst. Obwohl Audience Manager große Dateien verarbeiten kann, können wir Ihnen eventuell dabei helfen, die Größe Ihrer Dateien zu verringern und Datenübertragungen effizienter zu gestalten. Siehe <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Dateikomprimierung für Dateien</a> mit Inbound-Datenübertragung. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Dateiname {#file-name-examples}

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[Laden Sie](assets/ftp_dpm_1234_1445374061.overwrite) die Beispieldatei herunter, wenn Sie weitere Beispiele benötigen. Diese Datei wird mit der `.overwrite` Dateierweiterung gespeichert. Öffnen Sie es mit einem einfachen Texteditor.

## Akzeptierte Dateigrößen {#accepted-file-sizes}

Berücksichtigen Sie die unten stehenden Zahlen für die schnellste/früheste Verarbeitung Ihrer Dateien sowie für die Dateigrößenbeschränkungen, wenn Sie Daten an ein [!DNL Audience Manager] Verzeichnis senden [!DNL FTP] .

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

>[!MORE_ LIKE_ THIS]
>
>* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

