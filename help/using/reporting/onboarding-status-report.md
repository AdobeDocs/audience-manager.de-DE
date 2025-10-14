---
description: Der Onboarding-Statusbericht prüft die Erfolgs- und Fehlerquoten bei der Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt Zusammenfassungsmetriken in tabellarischer Form bereit. Außerdem enthält es eine Option, mit der Dateien für ein festes Zeitintervall abgefragt werden und die häufigsten Fehler für jeden Fehlertyp angezeigt werden. Diesen Bericht finden Sie unter Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: Onboarding-Statusbericht
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 0%

---

# Onboarding-Statusbericht{#onboarding-status-report-about}

Der Onboarding-Statusbericht prüft die Erfolgs- und Fehlerquoten bei der Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt Zusammenfassungsmetriken in tabellarischer Form bereit. Außerdem enthält es eine Option, mit der Dateien für ein festes Zeitintervall abgefragt werden und die häufigsten Fehler für jeden Fehlertyp angezeigt werden. Diesen Bericht finden Sie unter Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.

>[!NOTE]
>
>Nur Benutzer mit Administratorrechten können diesen Bericht in der Benutzeroberfläche von Audience Manager sehen. Sie können Benutzerinnen und Benutzer ohne Administratorrechte über den Status der hochgeladenen eingehenden Dateien benachrichtigen lassen, indem Sie ihre E-Mails zum Bericht hinzufügen. Siehe [E-Mail-Benachrichtigungen empfangen](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding-Statusbericht: Über {#onboarding-status-about}

Die [!UICONTROL Onboarding Status Report] überprüft die Erfolgs- und Fehlerquoten bei der Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt Zusammenfassungsmetriken in tabellarischer Form bereit. Außerdem enthält es eine Option, mit der Dateien für ein festes Zeitintervall abgefragt werden und die häufigsten Fehler für jeden Fehlertyp angezeigt werden. Diesen Bericht finden Sie in **[!UICONTROL Analytics > Onboarding Status Report]**. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.

## Fehlerberichte und Fehlerstichproben {#error-reporting-sampling}

Die Fehlerberichterstattung und die Fehlerauswahl sind zwei separate Funktionen des [!UICONTROL Onboarding Status].

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Fehlerberichterstattung</b> </p> </td>
   <td colname="col2"> <p>Die Fehlerberichterstattung zeigt die Erfolgs- und Fehlerquoten für die Anzahl der in einer eingehenden Datenquelle verarbeiteten Datensätze an. Es werden Daten in einem interaktiven, gestapelten Balkendiagramm und als Zusammenfassungsmetriken in Tabellen unter dem Diagramm zurückgegeben. </p> <p>Die Fehlerberichterstattung erfolgt automatisch. Es wird kontinuierlich für alle eingehenden Datenquellen ausgeführt. Es gibt Daten zurück, die auf dem Bereich der voreingestellten Zeitintervalle oder einem benutzerdefinierten Zeitintervall basieren, das Sie mit einem Kalender-Widget festlegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fehler-Sampling</b> </p> </td>
   <td colname="col2"> <p>Das Fehlerbeispiel analysiert den Inhalt Ihrer Datendateien und gibt für jeden Fehlertyp die 10 häufigsten Fehler zurück. Die Fehler in Ihren eingehenden Datendateien verhindern die Verarbeitung einzelner Datensätze. Verwenden Sie diesen Bericht als Tool zur Fehlerbehebung, um die Anzahl der Dateifehler zu reduzieren und die Verarbeitungsraten zu verbessern. </p> <p>Sie müssen das Fehler-Sampling manuell aktivieren. Er läuft ab dem Tag der Aktivierung 14 Tage und schaltet sich dann selbst aus. Sie können das Fehler-Sampling nach Ablauf des 14-tägigen Intervalls wieder aktivieren. Sie aktivieren das Fehler-Sampling, wenn Sie eine eingehende Datenquelle erstellen <a href="../features/manage-datasources.md#create-data-source"></a> oder indem Sie das Kontrollkästchen <b><span class="uicontrol">-Fehler</span></b>Sampling im Abschnitt <span class="wintitle"> Data Source Settings</span> einer vorhandenen eingehenden Datenquelle aktivieren. </p> <p>Das Sampling von Fehlern ist ein rechenintensiver Prozess. Daher werden für jede Fehlerkategorie nur die ersten 10 Fehler zurückgegeben. Sie ist nicht so konzipiert, dass sie alle in einer eingehenden Datenquelle enthaltenen Fehler zurückgibt. Diese Fehler sind ein repräsentatives Beispiel für eine potenziell größere Gruppe ähnlicher Fehler. Überprüfen Sie die gesamte Datei auf die Fehlertypen, die dieser Bericht kennzeichnet, formatieren Sie die Datei neu und senden Sie sie erneut. </p> <p>Weitere Informationen <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> richtigen Formatierung einer Datendatei für eine eingehende Datenquelle finden Sie unter </a> der eingehenden Datendateiinhalte: Syntax, Variablen und Beispiele. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Balkendiagramm für Fehlerbericht {#error-report-bar-chart}

Der Fehlerbericht stellt die Erfolgs- und Fehlerquoten bei der Datensatzverarbeitung in einem gestapelten Balkendiagramm dar, wie im folgenden Beispiel gezeigt. Das Diagramm ist interaktiv. Durch Klicken auf einen Balken werden die Zusammenfassungsmetriken für diesen Tag in einer Tabelle unter dem Diagramm angezeigt.

![](assets/stacked-graph.png)

## Tabellen für Fehlerberichte {#error-report-tables}

Der Fehlerbericht zeigt tabellarische Daten unterhalb des Balkendiagramms an. Die Tabelle zeigt die Erfolgs- und Fehlerquoten sowie Gesamtwerte und Prozentsätze.

**Erfolgreiche und fehlgeschlagene Datensätze**

Diese Standardansicht zeigt eine Häufigkeitsanzahl der gesamten Datensätze in Ihrem Bericht an und enthält eine Aufschlüsselung der Fehler nach Fehlertyp.

![](assets/success-failure.png)

**Gesamtwerte und Prozentsätze**

Klicken Sie auf **[!UICONTROL Totals & Percentages]** , um zu sehen, wie % Ihrer Dateien erfolgreich verarbeitet wurden.

![](assets/totals-percentages.png)

## Fehler-Sampling-Bericht für 14 Tage {#error-reporting-14-days}

Wenn das Fehler-Sampling aktiv ist, zeigt der Bericht für jeden Fehlertyp die 10 häufigsten Fehler an. Klicken Sie oben im Bericht auf die Schaltfläche für den Fehlertyp, um die einzelnen Datensätze anzuzeigen.

>[!NOTE]
>
>In diesem Bericht werden keine Datensatzfehler mit dieser aktuellen Version hervorgehoben. Um Dateifehler zu finden und zu beheben, sollten Sie die Ergebnisse überprüfen und mit den Spezifikationen in der Dokumentation [Inhalte eingehender Datendateien“ &#x200B;](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

![](assets/error-samples.png)

## E-Mail-Benachrichtigungen empfangen {#receive-email-notifications}

Sie können die E-Mail-Adressen von Empfängern hinzufügen, die über den Status der hochgeladenen eingehenden Dateien benachrichtigt werden sollen. Beachten Sie, dass Sie für verschiedene Datenquellen unterschiedliche Empfänger auswählen können.

![](assets/mail-notifications.png)

## Erstellen eines Onboarding-Statusberichts {#create-onboard-status-report}

Ein [!UICONTROL Sample Error Report] gibt die Anzahl der Datensätze in einer Datenquelle zurück, die erfolgreich verarbeitet wurden und bei denen ein Fehler aufgetreten ist. Führen Sie die folgenden Schritte aus, um eine [!UICONTROL Sample Error Report] zu generieren.

<!-- 

create-onboarding-status-report.xml

 -->


1. Gehe zu **[!UICONTROL Analytics > Onboarding Status Report]**. Nach einer Datenquelle suchen oder eine Datenquelle aus der Liste auswählen.

2. Einen Datumsbereich auswählen. Zu den Optionen zählen:

   * Ein Satz fester Berichtsintervalle.
   * Kalender-Widgets zum Erstellen eines benutzerdefinierten Datumsbereichs.

3. Klicken Sie auf **[!UICONTROL OK]**.

## Bedingungen und Definitionen für Onboarding-Statusberichte {#report-terms-conditions}

Ein Referenzhandbuch für die in diesem Bericht verwendeten Beschriftungen und Begriffe.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Begriff </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Dateiname für die Datensynchronisation</b> </p> </td> 
   <td colname="col2"> <p>Listet die Dateien auf, die <span class="keyword"> Audience Manager</span> empfangen und verarbeitet haben, von der ausgewählten eingehenden Datenquelle. </p> <p>Die Dateiverarbeitung schlägt fehl, wenn der Dateiname falsch formatiert ist. Die Anforderungen an Dateinamen variieren je nachdem, wie Sie diese Daten an <span class="keyword"> Audience Manager senden</span>. Zu den Versandmethoden gehören <span class="keyword"> Amazon S3</span> und FTP. Anweisungen zum Benennen Ihrer Dateien finden Sie unter: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Anforderungen an Amazon S3-Namen für eingehende Datendateien </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Formatierungsfehler</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der Datensätze auf, bei denen die Verarbeitung fehlgeschlagen ist, weil sie nicht der Syntax oder den Formatierungsanforderungen entsprachen. Informationen zum Formatieren <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Daten finden Sie unter Inhalte eingehender Datendateien: Syntax</a> Variablen und Beispiele . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ungültige AAM-ID</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der <span class="keyword"> Audience Manager falsch formatierten Benutzer</span>IDs (UUID) auf. Normalerweise werden damit die IDs angegeben: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Entsprach nicht dem erwarteten 38-stelligen Format. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Enthalten alphabetische Zeichen. IDs sollten nur Zahlen sein. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>Ungültige Geräte-ID</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der falsch formatierten globalen Geräte-IDs auf. Unter <a href="../reference/ids-in-aam.md">Index der IDs in Audience Manager</a> und <a href="../features/global-data-sources.md">Globale Datenquellen</a> finden Sie Details dazu, wie Geräte-IDs formatiert werden sollten und welche globalen Datenquellen Sie je nach Gerätetyp verwenden sollten.</p>
  <p>Der Abschnitt „Fehler-Sampling“ des Berichts enthält detaillierte Informationen zu den ungültigen Geräte-IDs, wie zum Beispiel:</p>
   <ul>
    <li>Die Datenquellen-ID, die der ungültigen Geräte-ID entspricht.</li>
    <li>Die ungültige Geräte-ID;</li>
    <li>Der Typ der erwarteten Geräte-ID, basierend auf der Datenquelle.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Keine übereinstimmende AAM-ID</b> </p> </td> 
   <td colname="col2"> <p>Hierbei handelt es sich um integrierte IDs <span class="keyword"> Audience Manager</span> die nicht mit einer vorhandenen ID übereinstimmen können. Onboarded IDs können diesen Status haben, wenn <span class="keyword"> Audience Manager</span> noch keine ID-Synchronisierung durchgeführt hat oder auch nach einer Synchronisierung immer noch nicht mit der ID übereinstimmen kann. </p> <p>Bei nicht übereinstimmenden Mobile-IDs wird <span class="keyword"> Audience Manager</span> wie folgt aussehen: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Fahren Sie mit dem Speichern fort und versuchen Sie, diese ID zu synchronisieren. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Wenn die ID nicht synchronisiert werden kann<span class="wintitle"> wird der Datensatz im Bericht als </span> gespeicherter Datensatz aufgezeichnet. </li> 
    </ul> <p>Wenn Ihre integrierte Datei mobile IDs enthält, können Sie diese Zahlen etwas leichter behandeln als die anderen Metriken. Sie wirken sich nicht auf die Erfolgs- und Übereinstimmungsraten für nachfolgende Dateien aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Keine Eigenschaft erkannt</b> </p> </td> 
   <td colname="col2"> <p>Listet Merkmale auf, die <span class="keyword"> Audience Manager</span> nicht mit einer integrierten Eigenschaft übereinstimmen können. Dies könnte die Folge sein von: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Falsch formatierte Eigenschaften in der eingehenden Datendatei. Informationen zum Formatieren Ihrer Datendatei finden Sie unter <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> der Inhalte eingehender Datendateien: Syntax, Variablen und Beispiele</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Eigenschaften, die noch nicht in <span class="keyword"> Audience Manager definiert </span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erfolgsquote</b> </p> </td> 
   <td colname="col2"> <p>Der Prozentsatz der Einträge in Ihrer Datei, die erfolgreich gespeichert wurden. Percent success = Anzahl verarbeiteter Datensätze / Anzahl der Datensätze in einer Datei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Datensätze erhalten</b> </p> </td> 
   <td colname="col2"> <p>Die Gesamtzahl der empfangenen Datensätze. In den meisten Fällen sollte diese Zahl mit der Gesamtzahl der Datensätze (Zeilen) in Ihrer eingehenden Datendatei übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gespeicherte Datensätze</b> </p> </td> 
   <td colname="col2"> <p>Anzahl der erfolgreich gespeicherten Datensätze. Aufgrund von Dateiformatfehlern können einige der empfangenen Datensätze von <span class="keyword"> Audience Manager nicht gespeichert werden</span>. Die Anzahl der gespeicherten Datensätze kann kleiner sein als die Anzahl der empfangenen Datensätze. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Insgesamt realisierte Eigenschaften</b> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaften für alle Benutzer in allen eingehenden Dateien, die in der <span class="keyword"> Audience Manager</span>-Plattform gespeichert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ungenutzte Signale insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Gesamtzahl der im Bericht empfangenen nicht verwendeten Signale. Diese Gesamtzahl bezieht sich auf die Gesamtzahl der erfolgreich gespeicherten Datensätze. </p> <p>Weitere Informationen finden Sie <a href="../reporting/dynamic-reports/unused-signals.md"> Bericht </a> nicht verwendete Signale . </p> </td> 
  </tr> 
 </tbody> 
</table>
