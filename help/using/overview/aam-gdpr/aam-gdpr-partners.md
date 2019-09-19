---
description: Auf dieser Seite werden Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie verfügbar werden, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Auf dieser Seite werden Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie verfügbar werden, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR-Überlegungen zu Zielen
solution: Audience Manager
title: GDPR-Überlegungen zu Zielen
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

---


# GDPR-Überlegungen zu Zielen{#gdpr-considerations-for-destinations}

Auf dieser Seite werden Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie verfügbar werden, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency &amp; Consent Framework (IAB Framework).

Adobe-Partner besitzen ihre Geschäftsprozesse und können sich entscheiden, ihre Integrationsanforderungen von Zeit zu Zeit mit Audience Manager zu aktualisieren. Wir arbeiten aktiv mit unserem Audience Manager Partner-Ökosystem zusammen, um unsere Kunden über Änderungen auf dem Laufenden zu halten.

## Audience Manager-Partneraktualisierungen - ID-Syncs {#partner-updates-id-syncs}

Einige Partner, wie in der folgenden Tabelle aufgeführt, haben ihre Integrationsanforderungen an Audience Manager geändert, um Unterstützung auf der Grundlage des IAB-Rahmens einzubeziehen, um die GDPR-Standards einzuhalten.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Name des Partners </p> </th> 
   <th colname="col2" class="entry"> <p>Erwartete Wirkung </p> </th> 
   <th colname="col3" class="entry"> <p>Status der Änderung </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID-Syncs für Benutzer in der Europäischen Union werden vom Partner gelöscht </p> </td> 
   <td colname="col3"> <p>Seit dem 22. Mai 2018 leben </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Handelsschalter </p> </td> 
   <td colname="col2"> <p>ID-Syncs für Benutzer in der Europäischen Union werden vom Partner gelöscht </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID-Syncs für Benutzer in der Europäischen Union werden vom Partner gelöscht </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID-Syncs für Benutzer in der Europäischen Union werden vom Partner gelöscht </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aktualisierung der Benutzeroberfläche von Audience Manager - Yahoo/Oath/DataX-Integration {#ui-update}

Zusätzlich zu den oben erwähnten Aktualisierungen des IAB-Frameworks haben Yahoo/Oath/DataX neue Parameter, **gdpr** und **gdpr_mode**, zu ihren Taxonomie- und Audience-APIs hinzugefügt. Ihre Parameter teilen Yahoo/Oath/DataX mit, dass sie berechtigt sind, ein bestimmtes Segment als Datenprozessor oder als Datencontroller zu verarbeiten. Daher müssen Audience Manager-Kunden, die Segmente an ein Yahoo/Oath/DataX-Ziel senden, den entsprechenden Parameter (Prozessor oder Controller) entsprechend ihrer Vereinbarung mit Oath angeben.

Wenden Sie sich an Ihren Berater oder an den Kundendienst, um den richtigen Parameter festzulegen. Adobe kann dieses Update nur im Namen eines Kunden vornehmen, wenn wir eine schriftliche Korrespondenz erhalten und diese Aktualisierung anfordern. Bitte wenden Sie sich an Ihren Yahoo/Oath/DataX-Kundenbetreuer, um die vollständige Definition dieser Parameter zu verstehen.

## Audience Manager-Partner mit Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

Um unseren Kunden bei der Automatisierung von GDPR-Anforderungen zu helfen, benachrichtigt Audience Manager unsere Aktivierungspartner über Löschungsanfragen von Datensubjekten, indem er ihnen Segmentinformationen sendet (oder entfernt).

Einige unserer Aktivierungspartner:

1. Keine Unterstützung von Nicht-Segment-Anfragen von Adobe und/oder
1. Wir können keine Updates von uns häufiger als einmal in 30 Tagen erhalten.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über Audience Manager an Aktivierungspartner zu senden. Laden Sie sich unser [Partner-Excel-Blatt](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) herunter, um zu sehen, welche Audience Manager-Aktivierungspartner das Segment nicht unterstützen.
