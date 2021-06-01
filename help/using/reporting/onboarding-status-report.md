---
description: Der Onboarding-Statusbericht überprüft Erfolgs- und Fehlerquoten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und bietet Zusammenfassungsmetriken in Tabellenform. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Sie finden diesen Bericht unter Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.
seo-description: Der Onboarding-Statusbericht überprüft Erfolgs- und Fehlerquoten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und bietet Zusammenfassungsmetriken in Tabellenform. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Sie finden diesen Bericht unter Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.
seo-title: Integrationsstatusbericht
solution: Audience Manager
title: Integrationsstatusbericht
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Eingehende und ausgehende Berichte
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 7%

---

# Integrationsstatusbericht{#onboarding-status-report-about}

Der Onboarding-Statusbericht überprüft Erfolgs- und Fehlerquoten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und bietet Zusammenfassungsmetriken in Tabellenform. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Sie finden diesen Bericht unter Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.

>[!NOTE]
>
>Dieser Bericht wird nur Benutzern mit Administratorrechten in der Benutzeroberfläche von Audience Manager angezeigt. Sie können Benutzer ohne Administratorrechte über den Status der hochgeladenen eingehenden Dateien informieren lassen, indem Sie ihre E-Mails zum Bericht hinzufügen. Siehe [E-Mail-Benachrichtigungen empfangen](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding-Statusbericht: Über {#onboarding-status-about}

Der [!UICONTROL Onboarding Status Report] überprüft Erfolgs- und Fehlerquoten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und bietet Zusammenfassungsmetriken in Tabellenform. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Sie finden diesen Bericht unter **[!UICONTROL Analytics > Onboarding Status Report]**. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.

## Fehlerberichte und Fehler-Sampling {#error-reporting-sampling}

Fehlerberichte und Fehlerproben sind zwei separate Funktionen des Berichts [!UICONTROL Onboarding Status] .

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Fehlerberichte</b> </p> </td>
   <td colname="col2"> <p>Die Fehlerberichte zeigen Ihnen die Erfolgs- und Fehlerquoten für die Anzahl der in einer eingehenden Datenquelle verarbeiteten Datensätze. Es werden Daten in einem interaktiven, gestapelten Balkendiagramm sowie als Zusammenfassungsmetriken in Tabellen unter dem Diagramm zurückgegeben. </p> <p>Die Fehlerberichterstellung erfolgt automatisch. Sie wird für alle eingehenden Datenquellen kontinuierlich ausgeführt. Es werden Daten basierend auf dem Bereich voreingestellter Zeitintervalle oder einem benutzerdefinierten Zeitintervall zurückgegeben, das Sie mit einem Kalender-Widget festlegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fehler-Sampling</b> </p> </td>
   <td colname="col2"> <p>Beim Fehlersampling werden die Inhalte Ihrer Datendateien analysiert und die zehn häufigsten Fehler für jeden Fehlertyp zurückgegeben. Die Fehler in Ihren eingehenden Datendateien verhindern die Verarbeitung einzelner Datensätze. Verwenden Sie diesen Bericht als Tool zur Fehlerbehebung, um die Anzahl der Dateifehler zu reduzieren und die Verarbeitungsrate zu verbessern. </p> <p>Sie müssen die Fehlerberechnung manuell aktivieren. Er dauert 14 Tage ab dem Aktivierungstag und deaktiviert sich dann selbst. Sie können die Fehlerberechnung wieder aktivieren, nachdem das 14-Tage-Intervall abgelaufen ist. Sie aktivieren das Fehlersampling, wenn Sie <a href="../features/manage-datasources.md#create-data-source"> eine eingehende Datenquelle</a> erstellen oder indem Sie das Kontrollkästchen <b><span class="uicontrol"> Fehler-Sampling</span></b> im Abschnitt <span class="wintitle"> Datenquelleneinstellungen</span> einer vorhandenen eingehenden Datenquelle aktivieren. </p> <p>Das Stichproben von Fehlern ist ein rechnerisch anspruchsvolles Verfahren. Daher werden nur die ersten 10 Fehler für jede Fehlerkategorie zurückgegeben. Sie ist nicht dazu bestimmt, alle Fehler zurückzugeben, die in einer eingehenden Datenquelle enthalten sind. Diese Fehler sind eine repräsentative Stichprobe einer potenziell größeren Gruppe ähnlicher Fehler. Überprüfen Sie die gesamte Datei auf die Fehlertypen, die dieser Bericht kennzeichnet, formatieren Sie die Datei neu und senden Sie sie erneut. </p> <p>Siehe <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele</a> für weitere Informationen zur ordnungsgemäßen Formatierung einer Datendatei für eine eingehende Datenquelle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Balkendiagramm des Fehlerberichts {#error-report-bar-chart}

Der Fehlerbericht zeigt die Erfolgs- und Fehlerquoten für die Datensatzverarbeitung in einem gestapelten Balkendiagramm an, wie im folgenden Beispiel gezeigt. Das Diagramm ist interaktiv. Wenn Sie auf eine Leiste klicken, werden in einer Tabelle unter dem Diagramm Zusammenfassungsmetriken für diesen Tag angezeigt.

![](assets/stacked-graph.png)

## Fehlerberichtstabellen {#error-report-tables}

Der Fehlerbericht zeigt Tabellendaten unter dem Balkendiagramm an. Die Tabelle zeigt Erfolgs- und Fehlerraten sowie Summen und Prozentsätze an.

**Erfolgreiche und fehlgeschlagene Aufzeichnungen**

Diese Standardansicht zeigt die Anzahl der Gesamt-Datensätze in Ihrem Bericht sowie eine Aufschlüsselung der Fehler nach Fehlertyp.

![](assets/success-failure.png)

**Gesamt und Prozentsatz**

Klicken Sie auf **[!UICONTROL Totals & Percentages]** , um zu sehen, welcher Prozentsatz Ihrer Dateien erfolgreich verarbeitet wurde.

![](assets/totals-percentages.png)

## Fehler-Sampling-Bericht für 14 Tage {#error-reporting-14-days}

Wenn die Fehlerauswahl aktiv ist, werden Ihnen im Bericht die 10 häufigsten Fehler für jeden Fehlertyp angezeigt. Klicken Sie oben im Bericht auf die Schaltfläche &quot;Fehlertyp&quot;, um die einzelnen Sätze von Stichprobendaten anzuzeigen.

>[!NOTE]
>
>Der Bericht zeigt keine Datensatzfehler in dieser aktuellen Version an. Um Dateifehler zu finden und zu beheben, sollten Sie die Ergebnisse überprüfen und mit den Spezifikationen in der Dokumentation [Inhalt der eingehenden Datendatei](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) vergleichen.

![](assets/error-samples.png)

## E-Mail-Benachrichtigungen empfangen {#receive-email-notifications}

Sie können die E-Mail-Adressen der Empfänger hinzufügen, die über den Status der hochgeladenen eingehenden Dateien informiert werden sollen. Beachten Sie, dass Sie für verschiedene Datenquellen unterschiedliche Empfänger auswählen können.

![](assets/mail-notifications.png)

## Erstellen eines Onboarding-Statusberichts {#create-onboard-status-report}

Ein [!UICONTROL Sample Error Report] gibt die Anzahl der Datensätze in einer Datenquelle zurück, die erfolgreich verarbeitet wurden und wie viele fehlgeschlagen sind. Führen Sie diese Schritte aus, um einen [!UICONTROL Sample Error Report] zu generieren.

<!-- 

create-onboarding-status-report.xml

 -->


1. Gehen Sie zu **[!UICONTROL Analytics > Onboarding Status Report]**. Suchen Sie nach einer Datenquelle oder wählen Sie eine aus der Liste aus.

2. Wählen Sie einen Datumsbereich aus. Zu den Optionen zählen:

   * Ein Satz fester Berichtsintervalle.
   * Kalender-Widgets, mit denen Sie einen benutzerdefinierten Datumsbereich erstellen können.

3. Klicken **[!UICONTROL OK]**.

## Begriffe und Definitionen des Onboarding-Statusberichts {#report-terms-conditions}

Ein Referenzhandbuch für die in diesem Bericht verwendeten Bezeichnungen und Begriffe.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Begriff </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Data Sync File Name</b> </p> </td> 
   <td colname="col2"> <p>Listet Dateien auf, die <span class="keyword"> Audience Manager</span> von Ihrer ausgewählten eingehenden Datenquelle erhalten und verarbeitet haben. </p> <p>Die Dateiverarbeitung schlägt fehl, wenn der Dateiname falsch formatiert ist. Die Anforderungen an Dateinamen hängen davon ab, wie Sie diese Daten an <span class="keyword"> Audience Manager</span> senden. Zu den Bereitstellungsmethoden gehören <span class="keyword"> Amazon S3</span> und FTP. Anweisungen zum Benennen Ihrer Dateien finden Sie unter: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Anforderungen an Namen der über Amazon S3 eingehenden Datendateien </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Formatfehler</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der Datensätze auf, für die die Verarbeitung fehlgeschlagen ist, da diese nicht den Syntax- oder Formatierungsanforderungen entsprachen. Siehe <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele</a> für Informationen zur Formatierung Ihrer Daten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ungültige AAM-ID</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der falsch formatierten <span class="keyword"> Audience Manager</span> Benutzer-IDs (UUID) auf. Normalerweise weist dies auf die IDs hin: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Entsprach nicht dem erwarteten 38-stelligen Format. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">enthält alphabetische Zeichen. IDs sollten nur Zahlen sein. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>Ungültige Geräte-ID</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der falsch formatierten globalen Geräte-IDs auf. Weitere Informationen dazu, wie Geräte-IDs formatiert werden sollen und welche globalen Datenquellen Sie verwenden sollten, finden Sie unter <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> und <a href="../features/global-data-sources.md">Globale Data Sources</a> , je nach Gerätetyp.</p>
  <p>Der Abschnitt zur Fehlerberechnung des Berichts enthält detaillierte Informationen zu den ungültigen Geräte-IDs, z. B.:</p>
   <ul>
    <li>Die Datenquellen-ID, die der ungültigen Geräte-ID entspricht;</li>
    <li>Die ungültige Geräte-ID;</li>
    <li>Der Typ der erwarteten Geräte-ID, basierend auf der Datenquelle.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Keine übereinstimmende AAM-ID</b> </p> </td> 
   <td colname="col2"> <p>Hierbei handelt es sich um integrierte IDs <span class="keyword"> Audience Manager</span>, die nicht mit einer vorhandenen ID übereinstimmen können. Integrierte IDs können diesen Status aufweisen, wenn <span class="keyword"> Audience Manager</span> noch keine ID-Synchronisierung durchgeführt hat oder die ID auch nach einer Synchronisierung nicht übereinstimmt. </p> <p>Bei nicht übereinstimmenden mobilen IDs führt <span class="keyword"> der Audience Manager</span> wie folgt aus: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Speichern Sie die ID weiter und versuchen Sie, sie zu synchronisieren. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Notieren Sie ihn als <span class="wintitle"> gespeicherten Datensatz</span> im Bericht, wenn die ID nicht synchronisiert werden kann. </li> 
    </ul> <p>Wenn Ihre integrierte Datei mobile IDs enthält, können Sie diese Zahlen etwas leichter behandeln als die anderen Metriken. Sie wirken sich nicht auf die Erfolgs- und Übereinstimmungsraten für nachfolgende Dateien aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Keine Eigenschaft realisiert</b> </p> </td> 
   <td colname="col2"> <p>Listet Eigenschaften auf, die <span class="keyword"> Audience Manager</span> nicht mit einer integrierten Eigenschaft übereinstimmen können. Dies könnte das Ergebnis von: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Unordnungsgemäß formatierte Eigenschaften in Ihrer eingehenden Datendatei. Informationen zum Formatieren Ihrer Datendatei finden Sie unter <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Eigenschaften, die noch nicht in <span class="keyword"> Audience Manager</span> definiert wurden. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Prozent Erfolg</b> </p> </td> 
   <td colname="col2"> <p>Der Prozentsatz der Datensätze in Ihrer Datei, die erfolgreich gespeichert wurden. Prozentualer Erfolg = verarbeitete Datensätze / Anzahl der Datensätze in einer Datei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erhaltene Datensätze</b> </p> </td> 
   <td colname="col2"> <p>Die Gesamtzahl der empfangenen Datensätze. In den meisten Fällen sollte diese Zahl mit der Gesamtzahl der Datensätze (Zeilen) in Ihrer eingehenden Datendatei übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gespeicherte Datensätze</b> </p> </td> 
   <td colname="col2"> <p>Anzahl der erfolgreich gespeicherten Datensätze. Aufgrund von Fehlern beim Dateiformat werden einige der empfangenen Datensätze möglicherweise nicht von <span class="keyword"> Audience Manager</span> gespeichert. Die Anzahl der gespeicherten Datensätze kann kleiner als die Anzahl der empfangenen Datensätze sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gesamtzahl der realisierten Eigenschaften</b> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaften für alle Benutzer in allen eingehenden Dateien, die auf der <span class="keyword">-Audience Manager</span>-Plattform gespeichert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ungenutzte Signale insgesamt</b> </p> </td> 
   <td colname="col2"> <p>Gesamtzahl der nicht verwendeten Signale, die im Bericht empfangen wurden. Dieser Gesamtwert basiert auf der Gesamtzahl der erfolgreich gespeicherten Datensätze. </p> <p>Weitere Informationen finden Sie unter <a href="../reporting/dynamic-reports/unused-signals.md"> Bericht zu nicht verwendeten Signalen</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>
