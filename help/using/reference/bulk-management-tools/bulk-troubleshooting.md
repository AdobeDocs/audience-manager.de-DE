---
description: Was soll getan werden, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanforderung fehlschlägt
seo-description: Was soll getan werden, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanforderung fehlschlägt
seo-title: Tipps zur Fehlerbehebung für Massenverwaltungswerkzeuge
solution: Audience Manager
title: Tipps zur Fehlerbehebung für Massenverwaltungswerkzeuge
uuid: 550908 a 1-e 24 e -4 f 31-954 b -7132 c 0 c 8 dc 3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

Was soll getan werden, wenn die Arbeitsblätter einen Fehler zurückgeben oder Ihre Massenanforderung fehlschlägt



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

Faktoren wie starke Netzwerkverkehr, Servernutzung und große Datensätze können dazu führen, dass eine Massenanforderung fehlschlägt oder Zeitüberschreitung verursacht. Wenn es ein Problem gibt, werden mit dem Arbeitsblatt Daten beendet und eine Fehlermeldung angezeigt. In diesem Fall sollten Sie Folgendes tun:

* Lesen Sie die Fehlermeldung.
* Beheben Sie das Problem.
* Löschen Sie alle bereits aktualisierten Zeilen.
* Versuchen Sie es erneut mit der Massenanforderung.

## Long delays or unresponsive behavior {#delays-behavior}

In der folgenden Tabelle sind einige allgemeine Probleme aufgeführt, die auftreten können, wenn Sie Massenanforderungen mit den Arbeitsblättern erstellen. Versuchen Sie, diese Probleme mit den empfohlenen Lösungen zu beheben. Wenn die empfohlenen Lösungen das Problem nicht lösen, sollten Sie Ihre Arbeit speichern, Ihren Computer neu starten und die Anforderung erneut versuchen, ohne mit anderen Anwendungen zu starten oder arbeiten zu müssen.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problem </th> 
   <th colname="col2" class="entry"> Lösung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Lange Verzögerungen</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Deaktivieren des Kompatibilitätsmodus</b>: Überprüfen Sie, ob im Kompatibilitätsmodus von Microsoft Excel andere Arbeitsblätter geöffnet sind. Der Kompatibilitätsmodus kann die Laufzeiten erhöhen. Schließen Sie alle Tabellen, die in diesem Modus geöffnet sind, und versuchen Sie erneut, Ihre Massenanforderung zu wiederholen. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Systemressourcen</b>: Eingeschränkte Systemressourcen tragen zu langen Verzögerungen bei. Schließen Sie alle anderen Programme, bevor Sie eine Massenanforderung durchführen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Keine Antwort</b> </td> 
   <td colname="col2">Wenn Sie auf eine Aktionsschaltfläche klicken und nichts passiert: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Stellen Sie sicher, dass Sie über den richtigen Header für die Auswahlaktion verfügen. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Stellen Sie sicher, dass Sie das richtige Arbeitsblatt für die kopierten Kopfzeilen verwenden. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Überprüfen Sie die Position der Daten, die Sie in einem Massenvorgang verwenden möchten. Alle Header beginnen in Spalte A, Zeile 1. Alle Daten werden in den entsprechenden Headern beginnend in Spalte A, Zeile 2 (unmittelbar unterhalb der Kopfzeilen) übernommen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

