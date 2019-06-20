---
description: Der Onboarding-Statusbericht überprüft Erfolgs- und Fehlerraten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt zusammenfassende Metriken in Tabellenform bereit. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Diesen Bericht finden Sie in Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.
seo-description: Der Onboarding-Statusbericht überprüft Erfolgs- und Fehlerraten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt zusammenfassende Metriken in Tabellenform bereit. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Diesen Bericht finden Sie in Analytics > Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.
seo-title: Onboarding-Statusbericht über
solution: Audience Manager
title: Onboarding-Statusbericht über
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Onboarding-Statusbericht{#onboarding-status-report-about}

Der Onboarding-Statusbericht überprüft Erfolgs- und Fehlerraten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt zusammenfassende Metriken in Tabellenform bereit. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Diesen Bericht finden Sie in Analytics &gt; Onboarding-Statusbericht. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.

>[!NOTE]
>
>Diesen Bericht können nur Benutzer mit Administratorrechten in der Benutzeroberfläche von Audience Manager sehen. Sie können Benutzer ohne Administratorrechte über den Status der hochgeladenen eingehenden Dateien benachrichtigen, indem Sie dem Bericht ihre E-Mails hinzufügen. Siehe [E-Mail-Benachrichtigungen empfangen](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding-Statusbericht: Info {#onboarding-status-about}

Die [!UICONTROL Onboarding Status Report] Erfolgs- und Fehlerraten für die Verarbeitung von Datensätzen in Ihren eingehenden Datenquellendateien. Dieser Bericht zeigt Daten in einem interaktiven Balkendiagramm an und stellt zusammenfassende Metriken in Tabellenform bereit. Außerdem enthält er eine Option zur Untersuchung von Dateien innerhalb eines festgelegten Zeitintervalls und Anzeige der häufigsten Fehler für jeden Fehlertyp. Diesen Bericht finden **[!UICONTROL Analytics > Onboarding Status Report]** Sie in. Dieser Bericht ist auch verfügbar, wenn Sie eine eingehende Datenquelle erstellen.

## Fehlerberichterstellung und Fehlerberechnung {#error-reporting-sampling}

Fehlerberichte und Fehlerstichproben sind 2 separate Funktionen des [!UICONTROL Onboarding Status] Berichts.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Fehlerberichterstellung</b> </p> </td>
   <td colname="col2"> <p>Die Fehlerberichterstellung zeigt Ihnen die Erfolgs- und Fehlerraten für die Anzahl der in einer eingehenden Datenquelle verarbeiteten Datensätze. Gibt Daten in einem interaktiven, gestapelten Balkendiagramm und als Zusammenfassungsmetriken in Tabellen unterhalb des Diagramms zurück. </p> <p>Die Fehlerberichterstellung ist automatisch. Sie wird für alle Ihre eingehenden Datenquellen kontinuierlich ausgeführt. Sie gibt Daten basierend auf voreingestellten Zeitintervallen oder einem angepassten Zeitintervall zurück, das Sie mit einem Kalender-Widget festlegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fehlerstichproben</b> </p> </td>
   <td colname="col2"> <p>Fehlerstichproben analysieren den Inhalt Ihrer Datendateien und geben die 10 häufigsten Fehler für jeden Fehlertyp zurück. Die Fehler in Ihren eingehenden Datendateien verhindern, dass einzelne Datensätze verarbeitet werden. Verwenden Sie diesen Bericht als Fehlerbehebung, um die Anzahl der Dateifehler zu reduzieren und die Verarbeitungsraten zu verbessern. </p> <p>Sie müssen Fehlerstichproben manuell aktivieren. Sie wird 14 Tage nach dem Aktivierungsdatum ausgeführt und wird dann deaktiviert. Sie können Fehlerstichproben nach Ablauf des 14-Tage-Intervalls wieder aktivieren. Sie aktivieren Fehlerstichproben, wenn Sie <a href="../features/manage-datasources.md#create-data-source"> eine eingehende Datenquelle</a> erstellen oder das Kontrollkästchen <b><span class="uicontrol"> Fehlerstichprobe im</span></b> Abschnitt <span class="wintitle"> Datenquelleneinstellungen</span> einer vorhandenen eingehenden Datenquelle überprüfen. </p> <p>Fehlerstichproben sind ein rechnerdefinierter Prozess. Daher werden nur ersten 10 Fehler für jede Fehlerkategorie ausgegeben. Es ist nicht so ausgelegt, jeden Fehler zurückzugeben, der in einer eingehenden Datenquelle enthalten ist. Diese Fehler sind ein repräsentatives Beispiel einer potenziell größeren Gruppe ähnlicher Fehler. Überprüfen Sie Ihre gesamte Datei auf die Fehlertypen, die in diesem Bericht aufgeführt sind, formatieren Sie die Datei und senden Sie sie erneut. </p> <p>Siehe <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inhalt von Inbound-Datendateien: Syntax, Variablen und Beispiele</a> für weitere Informationen zur korrekten Formatierung einer Datendatei für eine eingehende Datenquelle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fehlerberichtsbalkendiagramm {#error-report-bar-chart}

Der Fehlerbericht zeigt die Erfolgs- und Fehlerraten für die Datensatzverarbeitung in einem gestapelten Balkendiagramm wie im folgenden Beispiel dargestellt an. Das Diagramm ist interaktiv. Durch Klicken auf eine Leiste werden Zusammenfassungsmetriken für diesen Tag in einer Tabelle unterhalb des Diagramms angezeigt.

![](assets/stacked-graph.png)

## Fehlerberichtstabellen {#error-report-tables}

Der Fehlerbericht zeigt Tabellendaten unter dem Balkendiagramm an. In der Tabelle werden Erfolgs- und Fehlerraten zusammen mit Gesamtwerten und Prozentwerten angezeigt.

**Erfolgreiche und fehlgeschlagene Datensätze**

Diese Standardansicht zeigt eine Häufigkeitsanzahl der Gesamtzahlen in Ihrem Bericht und enthält eine Aufschlüsselung der Fehler nach Fehlertyp.

![](assets/success-failure.png)

**Gesamtwerte &amp; Prozent**

Klicken **[!UICONTROL Totals & Percentages]** Sie auf, um zu sehen, welche % der Dateien erfolgreich verarbeitet wurden.

![](assets/totals-percentages.png)

## Fehlerbericht für 14 Tage {#error-reporting-14-days}

Wenn die Fehlerberechnung aktiv ist, zeigt der Bericht Ihnen die Top -10-Fehler für jeden Fehlertyp an. Klicken Sie oben im Bericht auf eine Fehlertyp-Schaltfläche, um die einzelnen Stichproben von Stichproben anzuzeigen.

>[!NOTE]
>
>Der Bericht hebt keine Datensatzfehler mit dieser aktuellen Version hervor. Um Dateifehler zu suchen und zu beheben, sollten Sie die Ergebnisse überprüfen und diese mit den Spezifikationen in der Dokumentation [zu den Inbound](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) -Datendateiinhalten vergleichen.

![](assets/error-samples.png)

## E-Mail-Benachrichtigungen empfangen {#receive-email-notifications}

Sie können die E-Mail-Adressen der Empfänger hinzufügen, die über den Status der hochgeladenen eingehenden Dateien benachrichtigt werden sollen. Beachten Sie, dass Sie verschiedene Empfänger für verschiedene Datenquellen auswählen können.

![](assets/mail-notifications.png)

## Onboarding-Statusbericht erstellen {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] gibt die Anzahl der Datensätze in einer Datenquelle zurück und die Anzahl fehlgeschlagen. Führen Sie die folgenden Schritte aus, um eine [!UICONTROL Sample Error Report]zu generieren.

<!-- 

create-onboarding-status-report.xml

 -->


1. Gehe **[!UICONTROL Analytics > Onboarding Status Report]** zu. Suchen Sie nach einer Datenquelle oder wählen Sie eine aus der Liste.

2. Wählen Sie einen Datumsbereich aus. Zu den Optionen zählen:

   * Ein Satz festgelegter Berichtsintervalle.
   * Kalender-Widgets, mit denen Sie einen benutzerdefinierten Datumsbereich erstellen können.

3. Klicken Sie auf **[!UICONTROL OK]**.

## Begriffe und Definitionen des Onboarding-Status {#report-terms-conditions}

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
   <td colname="col1"> <p> <b>Datensynchronisierungsdateiname</b> </p> </td> 
   <td colname="col2"> <p>Listet Dateien auf, die <span class="keyword"> von Audience Manager</span> empfangen und verarbeitet wurden, wenn Sie die eingehende Datenquelle ausgewählt haben. </p> <p>Die Dateiverarbeitung schlägt fehl, wenn der Dateiname falsch formatiert ist. Die Dateinamensanforderungen variieren je nachdem, wie Sie diese Daten an <span class="keyword"> Audience Manager senden</span>. Bereitstellungsmethoden sind <span class="keyword"> Amazon S 3</span> und FTP. Anweisungen zum Benennen Ihrer Dateien finden Sie unter: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Namensanforderungen von Amazon S3 für Inbound-Datendateien </a> </li> 
      <li id="li_9590241AEC0C482D91C64DB760B32B0D"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md"> FTP-Namensanforderungen für Inbound-Datendateien </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Formatfehler</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der aufgetretenen Datensätze auf, da sie nicht mit den Syntax- oder Formatierungsanforderungen übereinstimmen. Siehe <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inhalt von Inbound-Datendateien: Syntax, Variablen und Beispiele</a> für Informationen zur Formatierung Ihrer Daten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ungültige AAM-ID</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl der falsch formatierten <span class="keyword"> Audience Manager</span> -Benutzer-IDs (UUID) auf. In der Regel werden die IDs angezeigt: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Entsprach nicht dem erwarteten 38-stelligen Format. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Alphabetische Zeichen enthalten. IDs sollten nur Zahlen sein. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>Ungültige Geräte-ID</b> </p> </td> 
   <td colname="col2"> <p>Listet die Anzahl falsch formatierter globaler Geräte-IDs auf. Einzelheiten dazu, wie Geräte-IDs formatiert und welche globalen Datenquellen Sie verwenden sollten, basierend auf dem Gerätetyp, finden Sie unter <a href="../reference/ids-in-aam.md">Index der IDs in Audience Manager</a> und <a href="../features/global-data-sources.md">Globale Datenquellen</a> .</p>
  <p>Der Fehlerbehebungsabschnitt des Berichts enthält detaillierte Informationen zu den ungültigen Geräte-IDs, z. B.:</p>
   <ul>
    <li>Die Datenquellen-ID, die der ungültigen Geräte-ID entspricht;</li>
    <li>Ungültige Geräte-ID;</li>
    <li>Der Typ der erwarteten Geräte-ID, basierend auf der Datenquelle.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Keine übereinstimmende AAM-ID</b> </p> </td> 
   <td colname="col2"> <p>Hierbei handelt es sich um Onboarded IDs <span class="keyword"> Audience Manager</span> , die mit einer vorhandenen ID nicht übereinstimmen können. Onboarded IDs können diesen Status haben, wenn <span class="keyword"> Audience Manager</span> noch keine ID-Synchronisierung durchgeführt hat oder die ID noch immer nicht mit der ID übereinstimmen kann. </p> <p>Bei nicht übereinstimmenden mobilen IDs wird <span class="keyword"> der Audience Manager</span> : </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Speichern Sie weiterhin diese ID und versuchen Sie, diese zu synchronisieren. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Notieren Sie es als <span class="wintitle"> gespeicherter Datensatz</span> im Bericht, wenn die ID nicht synchronisiert werden kann. </li> 
    </ul> <p>Wenn Ihre Onboardansicht mobile IDs enthält, können Sie diese Zahlen etwas leichter als die anderen behandeln. Sie wirken sich nicht auf Erfolgs- und Übereinstimmungsraten für folgende Dateien aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kein Trait-Format</b> </p> </td> 
   <td colname="col2"> <p>Listet Eigenschaften auf, <span class="keyword"> die Audience Manager</span> nicht mit einer Onboardanmerkung abgleichen kann. Dies könnte das Ergebnis von: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Falsch formatierte Eigenschaften in Ihrer eingehenden Datendatei. Informationen zum Formatieren Ihrer Datendatei finden Sie unter <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inhalt von Inbound-Datendateien: Syntax, Variablen und Beispiele</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Eigenschaften, die noch nicht in <span class="keyword"> Audience Manager definiert</span>wurden. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Prozenterfolg</b> </p> </td> 
   <td colname="col2"> <p>Der Prozentsatz der Datensätze in Ihrer Datei, die erfolgreich gespeichert wurden. Prozentwert-Erfolg = aufgezeichnet/Anzahl der Datensätze in einer Datei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Empfangene Datensätze</b> </p> </td> 
   <td colname="col2"> <p>Die Gesamtzahl der empfangenen Datensätze. In den meisten Fällen sollte diese Zahl mit der Gesamtanzahl der Datensätze (Zeilen) in Ihrer eingehenden Datendatei übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gespeicherte Datensätze</b> </p> </td> 
   <td colname="col2"> <p>Anzahl der erfolgreich gespeicherten Datensätze. Aufgrund von Dateiformatfehlern werden einige der empfangenen Datensätze möglicherweise nicht von <span class="keyword"> Audience Manager gespeichert</span>. Die Anzahl der gespeicherten Datensätze kann niedriger sein als die Anzahl der empfangenen Datensätze. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neu gestaltete Eigenschaften</b> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaften für alle Benutzer in allen Inbound-Dateien, die in der <span class="keyword"> Audience Manager</span> -Plattform gespeichert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nicht verwendete Signale</b> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der nicht verwendeten Signale, die im Bericht empfangen wurden. Diese Summe basiert auf der Gesamtanzahl der erfolgreich gespeicherten Datensätze. </p> <p>Weitere <a href="../reporting/dynamic-reports/unused-signals.md"> Informationen finden Sie unter</a> Berichte zu nicht verwendeten Signalen. </p> </td> 
  </tr> 
 </tbody> 
</table>
