---
description: Was zu tun ist, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanfrage fehlschlägt.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Tipps zur Fehlerbehebung für Tools für die Massenverwaltung
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Tipps zur Fehlerbehebung für Tools für die Massenverwaltung{#troubleshooting-tips-for-bulk-management-tools}

Was zu tun ist, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanfrage fehlschlägt.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support über die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md), die in der [!DNL Audience Manager]-Benutzeroberfläche zugewiesen sind, werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

Faktoren wie starker Netzwerk-Traffic, Server-Nutzung und große Datensätze können dazu führen, dass eine Massenanfrage fehlschlägt oder eine Zeitüberschreitung auftritt. Wenn ein Problem auftritt, schreibt das Arbeitsblatt keine Daten mehr und zeigt eine Fehlermeldung an. In diesem Fall sollten Sie:

* Lesen Sie die Fehlermeldung.
* Beheben Sie das Problem.
* Löschen Sie alle Zeilen, die bereits aktualisiert wurden.
* Versuchen Sie die Massenanfrage erneut.

## Authentifizierungsfehler, lange Verzögerungen oder nicht reagierendes Verhalten {#delays-behavior}

In der folgenden Tabelle sind einige häufige Probleme aufgeführt, auf die Sie bei Massenanfragen mit den Arbeitsblättern stoßen können. Beheben Sie diese Probleme mit den empfohlenen Lösungen. Wenn das Problem mit den empfohlenen Lösungen nicht behoben werden kann, sollten Sie Ihre Arbeit speichern, Ihren Computer neu starten und die Anfrage erneut versuchen, ohne andere Anwendungen zu starten oder mit ihnen zu arbeiten.

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
    <b>Aktualisierung auf die neueste Version von Microsoft Excel</b>: Wenn eine neue Version von Microsoft Excel veröffentlicht wird und Sie eine ältere Version verwenden, kann ein Authentifizierungsfehler im Bulk Management-Arbeitsblatt auftreten. Aktualisieren Sie auf die neueste Version von Microsoft Excel, um den Authentifizierungsfehler zu beheben.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lange Verzögerungen</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Kompatibilitätsmodus deaktivieren</b>: Überprüfen Sie, ob andere Arbeitsblätter im Kompatibilitätsmodus von Microsoft Excel geöffnet sind. Der Kompatibilitätsmodus kann die Laufzeiten erhöhen. Schließen Sie alle Tabellen, die in diesem Modus geöffnet sind, und wiederholen Sie die Massenanfrage. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Systemressourcen</b>: Begrenzte Systemressourcen tragen zu langen Verzögerungen bei. Schließen Sie alle anderen Programme, bevor Sie eine Massenanfrage stellen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Keine Antwort</b> </td> 
   <td colname="col2">Wenn Sie auf eine Aktionsschaltfläche klicken und nichts passiert: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Stellen Sie sicher, dass Sie über den richtigen Satz an Headern für die Auswahlaktion verfügen. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Stellen Sie sicher, dass Sie das richtige Arbeitsblatt für die kopierten Kopfzeilen verwenden. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Überprüfen Sie die Position der Daten, die Sie in einem Massenvorgang verwenden möchten. Alle Kopfzeilen beginnen in Spalte A, Zeile 1. Alle Daten werden in die entsprechenden Kopfzeilen eingefügt, die in Spalte A, Zeile 2 (direkt unter den Kopfzeilen) beginnen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fehlermeldungen

Manchmal erhalten Sie Fehlermeldungen, wenn Sie Massenänderungen vornehmen. Informationen zur Interpretation der Fehlermeldung finden Sie unter [Antwort-Codes definiert](/help/using/api/rest-api-main/aam-api-getting-started.md) in unserer API-Dokumentation.
