---
description: Auf dieser Seite werden Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie verfügbar werden, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Auf dieser Seite werden Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie verfügbar werden, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR-Überlegungen zu Zielen
solution: Audience Manager
title: GDPR-Überlegungen zu Zielen
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

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
   <td colname="col1"> <p> LiveRamp </p> </td> 
   <td colname="col2"> <p>ID-Syncs für Benutzer in der Europäischen Union werden vom Partner gelöscht </p> </td> 
   <td colname="col3"> <p>Noch nicht live </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aktualisierung der Benutzeroberfläche von Audience Manager - Yahoo/Oath/DataX-Integration {#ui-update}

Zusätzlich zu den oben erwähnten Aktualisierungen des IAB-Frameworks haben Yahoo/Oath/DataX neue Parameter, **gdpr** und **gdpr_mode**, zu ihren Taxonomie- und Audience-APIs hinzugefügt. Their parameters inform Yahoo/Oath/DataX that they have the rights to process a certain segment as a Data Processor or as a Data Controller. Daher müssen Audience Manager-Kunden, die Segmente an ein Yahoo/Oath/DataX-Ziel senden, den entsprechenden Parameter (Prozessor oder Controller) entsprechend ihrer Vereinbarung mit Oath angeben.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.
