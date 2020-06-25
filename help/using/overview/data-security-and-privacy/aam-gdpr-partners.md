---
description: Auf dieser Seite werden die Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie zur Verfügung stehen, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Auf dieser Seite werden die Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie zur Verfügung stehen, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR-Überlegungen zu Zielen
solution: Audience Manager
title: GDPR-Überlegungen zu Zielen
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---


# GDPR-Überlegungen zu Zielen{#gdpr-considerations-for-destinations}

Auf dieser Seite werden die Informationen, die direkt von unseren Partnern bereitgestellt werden, zusammengefasst, sobald sie zur Verfügung stehen, sowie alle Auswirkungen, die sich auf Ihre Audience Manager-Praxis beziehen. Die wichtigsten Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, sind das Ergebnis der GDPR (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft trat, und des neuen IAB GDPR Transparency &amp; Consent Framework (IAB Framework).

Adobe-Partner besitzen ihre Geschäftsprozesse und können sich entscheiden, ihre Integrationsanforderungen von Zeit zu Zeit zu Audience Manager zu aktualisieren. Wir arbeiten aktiv mit unserem Audience Manager-Partner-Ökosystem zusammen, um unsere Kunden über Veränderungen auf dem Laufenden zu halten.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Audience Manager-Benutzeroberflächenaktualisierung - Yahoo/Oath/DataX-Integration {#ui-update}

Zusätzlich zu den oben erwähnten Aktualisierungen des IAB-Frameworks haben Yahoo/Oath/DataX neue Parameter, **gdpr** und **gdpr_mode**, zu ihren Taxonomie- und Audience-APIs hinzugefügt. Ihre Parameter teilen Yahoo/Oath/DataX mit, dass sie berechtigt sind, ein bestimmtes Segment als Datenprozessor oder als Datencontroller zu verarbeiten. Daher müssen Audience Manager, die Segmente an ein Yahoo/Oath/DataX-Ziel senden, den entsprechenden Parameter (Prozessor oder Controller) entsprechend ihrer Vereinbarung mit Oath angeben.

Wenden Sie sich an Ihren Berater oder an den Kundendienst, um den richtigen Parameter festzulegen. Adobe kann dieses Update nur im Namen eines Kunden vornehmen, wenn wir eine schriftliche Korrespondenz erhalten und diese Aktualisierung anfordern. Bitte wenden Sie sich an Ihren Yahoo/Oath/DataX-Kundenbetreuer, um die vollständige Definition dieser Parameter zu verstehen.
