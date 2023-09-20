---
description: Was zu tun ist, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanfrage fehlschlägt.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Tipps zur Fehlerbehebung für die Tools zur Massenverwaltung
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 3%

---

# Tipps zur Fehlerbehebung für die Tools zur Massenverwaltung{#troubleshooting-tips-for-bulk-management-tools}

Was zu tun ist, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanfrage fehlschlägt.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) in der [!DNL Audience Manager] Die Benutzeroberfläche wird im Abschnitt [!UICONTROL Bulk Management Tools].

Faktoren wie starker Netzwerk-Traffic, Servernutzung und große Datensätze können dazu führen, dass eine Massenanforderung fehlschlägt oder eine Zeitüberschreitung auftritt. Wenn ein Problem auftritt, hört das Arbeitsblatt auf, Daten zu schreiben, und zeigt eine Fehlermeldung an. In diesem Fall sollten Sie:

* Lesen Sie die Fehlermeldung.
* Beheben Sie das Problem.
* Löschen Sie alle Zeilen, die bereits aktualisiert wurden.
* Versuchen Sie die Massenanforderung erneut.

## Authentifizierungsfehler, lange Verzögerungen oder nicht reagierendes Verhalten {#delays-behavior}

In der folgenden Tabelle sind einige häufige Probleme aufgeführt, die bei Massenanfragen mit den Arbeitsblättern auftreten können. Versuchen Sie, diese Probleme mit den empfohlenen Lösungen zu beheben. Wenn die empfohlenen Lösungen das Problem nicht lösen, sollten Sie Ihre Arbeit speichern, den Computer neu starten und die Anfrage erneut ausführen, ohne andere Anwendungen zu starten oder zu verwenden.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problem </th> 
   <th colname="col2" class="entry"> Lösung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Authentifizierungsfehler</b> </td> 
   <td colname="col2"> 
    <b>Aktualisierung auf die neueste Version von Microsoft Excel</b>: Wenn eine neue Version von Microsoft Excel veröffentlicht wird und Sie eine ältere Version verwenden, tritt möglicherweise ein Authentifizierungsfehler im Arbeitsblatt für die Massenverwaltung auf. Aktualisieren Sie auf die neueste Version von Microsoft Excel, um den Authentifizierungsfehler zu beheben.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lange Verzögerungen</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Kompatibilitätsmodus deaktivieren</b>: Überprüfen Sie, ob andere Arbeitsblätter im Kompatibilitätsmodus von Microsoft Excel geöffnet sind. Der Kompatibilitätsmodus kann die Laufzeit erhöhen. Schließen Sie alle Tabellen, die Sie in diesem Modus geöffnet haben, und versuchen Sie es erneut mit der Massenanforderung. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Systemressourcen</b>: Begrenzte Systemressourcen tragen zu langen Verzögerungen bei. Versuchen Sie, alle anderen Programme zu schließen, bevor Sie eine Massenanfrage stellen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Keine Antwort</b> </td> 
   <td colname="col2">Wenn Sie auf eine Aktionsschaltfläche klicken und nichts passiert: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Stellen Sie sicher, dass Sie über die richtigen Kopfzeilen für die Auswahlaktion verfügen. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Stellen Sie sicher, dass Sie das richtige Arbeitsblatt für die kopierten Kopfzeilen verwenden. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Überprüfen Sie die Position der Daten, die Sie in einem Massenvorgang verwenden möchten. Alle Kopfzeilen beginnen in Spalte A Zeile 1. Alle Daten werden in entsprechende Kopfzeilen aufgenommen, die in Spalte A Zeile 2 beginnen (direkt unter den Kopfzeilen). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fehlermeldungen

Manchmal können Sie Fehlermeldungen erhalten, wenn Sie Massenänderungen vornehmen. Informationen zur Interpretation der Fehlermeldung finden Sie unter [Definierte Antwortcodes](/help/using/api/rest-api-main/aam-api-getting-started.md) in unserer API-Dokumentation.
