---
description: Diese Seite zeigt Informationen an, die direkt von unseren Partnern bereitgestellt werden, und zwar zusammen mit allen Auswirkungen im Zusammenhang mit der Praxis Ihres Audience Managers. Wichtige Auswirkungen von Partnern, die diese Updates vornehmen, sind das Ergebnis von GDPR (Allgemeine Datenschutzregeln), die am 25. Mai 2018 eingeführt wurden, und das neue IAB-GDPR Transparency & Approval Framework (IAB Framework).
seo-description: Diese Seite zeigt Informationen an, die direkt von unseren Partnern bereitgestellt werden, und zwar zusammen mit allen Auswirkungen im Zusammenhang mit der Praxis Ihres Audience Managers. Wichtige Auswirkungen von Partnern, die diese Updates vornehmen, sind das Ergebnis von GDPR (Allgemeine Datenschutzregeln), die am 25. Mai 2018 eingeführt wurden, und das neue IAB-GDPR Transparency & Approval Framework (IAB Framework).
seo-title: GDPR-Überlegungen für Ziele
solution: Audience Manager
title: GDPR-Überlegungen für Ziele
uuid: e 8 a 40060-086 c -4 f 03-b 48 c -9 c 903 acb 7891
translation-type: tm+mt
source-git-commit: 0ddc86391cbc751dfd4d46946222d555cefbfe38

---


# GDPR-Überlegungen für Ziele{#gdpr-considerations-for-destinations}

Diese Seite zeigt Informationen an, die direkt von unseren Partnern bereitgestellt werden, und zwar zusammen mit allen Auswirkungen im Zusammenhang mit der Praxis Ihres Audience Managers. Wichtige Auswirkungen von Partnern, die diese Updates vornehmen, sind das Ergebnis von GDPR (Allgemeine Datenschutzregeln), die am 25. Mai 2018 eingeführt wurden, und das neue IAB-GDPR Transparency &amp; Approval Framework (IAB Framework).

Adobe Partner sind Eigentümer ihrer Geschäftsprozesse und können ihre Integrationsanforderungen jederzeit mit Audience Manager aktualisieren. Wir arbeiten proaktiv mit unserem Audience Manager Partner-System zusammen, um unsere Kunden über Änderungen zu informieren.

## Audience Manager-Partneraktualisierungen - ID-Synchronisierungen {#partner-updates-id-syncs}

Einige Partner, wie in der folgenden Tabelle aufgeführt, haben ihre Integrationsanforderungen in Audience Manager geändert, um Unterstützung auf Basis des IAB-Frameworks einzubeziehen, um den GDPR-Standards zu entsprechen.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partnername </p> </th> 
   <th colname="col2" class="entry"> <p>Erwartete Auswirkung </p> </th> 
   <th colname="col3" class="entry"> <p>Status der Änderung </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/datax </p> </td> 
   <td colname="col2"> <p>ID-Synchronisierungen für Benutzer in der Europäischen Union werden vom Partner entfernt </p> </td> 
   <td colname="col3"> <p>Live seit 22. Mai 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID-Synchronisierungen für Benutzer in der Europäischen Union werden vom Partner entfernt </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID-Synchronisierungen für Benutzer in der Europäischen Union werden vom Partner entfernt </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Liveramp </p> </td> 
   <td colname="col2"> <p>ID-Synchronisierungen für Benutzer in der Europäischen Union werden vom Partner entfernt </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aktualisierung der Benutzeroberfläche von Audience Manager - Yahoo/Oath/datax-Integration {#ui-update}

Zusätzlich zu den Aktualisierungen des oben erwähnten IAB-Frameworks hat Yahoo/Oath/datax neue Parameter, **gdpr** und **gdpr_ mode**, ihren Taxonomy und Audience apis hinzugefügt. Ihre Parameter informieren Yahoo/Oath/datax darüber, dass sie über die Rechte zum Verarbeiten eines bestimmten Segments als Datenprozessor oder als Datencontroller verfügen. Demzufolge müssen Audience Manager-Kunden, die Segmente an ein Yahoo/Oath/datax-Ziel senden, je nach Vereinbarung mit Oath den entsprechenden Parameter (Prozessor oder Controller) angeben.

Bitte wenden Sie sich an Ihren Berater oder Kundendienst, um den richtigen Parameter festzulegen. Adobe kann dieses Update nur für einen Kunden vornehmen, wenn wir eine schriftliche Korrespondenz erhalten und diese Aktualisierung anfordern. Bitte wenden Sie sich an Ihren Yahoo/Oath/datax-Vertreter, um die vollständige Definition dieser Parameter zu verstehen.

## Audience Manager-Partner mit Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

Damit unsere Kunden GDPR-Anforderungen automatisieren können, benachrichtigt Audience Manager unsere Aktivierungspartner über das Löschen von Anforderungen aus Datenthemen, indem sie diese unsegmentiert (oder Segmentinformationen entfernen) sendet.

Einige unserer Aktivierungspartner:

1. Keine Segmentanfragen von Adobe und/oder
1. Es ist nicht möglich, in 30 Tagen mehr als einmal Updates von uns zu erhalten.

In diesen Fällen können Sie nicht automatisierte Anfragen an Aktivierungspartner über Audience Manager senden. Laden Sie unser [Partner Excel Sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-March2019.xlsx) herunter, um zu sehen, welche Audience Manager-Aktivierungspartner das Segment unterstützen.
