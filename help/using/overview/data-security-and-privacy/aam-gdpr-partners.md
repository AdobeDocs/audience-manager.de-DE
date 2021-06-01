---
description: Auf dieser Seite werden die direkt von unseren Partnern bereitgestellten Informationen sowie die Auswirkungen auf Ihr Vorgehen in Audience Manager beschrieben. Wesentliche Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, ergeben sich aus der DSGVO (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft getreten ist, und aus dem neuen IAB Framework (IAB DSGVO Transparency & Consent Framework).
seo-description: Auf dieser Seite werden die direkt von unseren Partnern bereitgestellten Informationen sowie die Auswirkungen auf Ihr Vorgehen in Audience Manager beschrieben. Wesentliche Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, ergeben sich aus der DSGVO (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft getreten ist, und aus dem neuen IAB Framework (IAB DSGVO Transparency & Consent Framework).
seo-title: DSGVO-Überlegungen für Ziele
solution: Audience Manager
title: DSGVO-Überlegungen für Ziele
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance und Datenschutz
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 96%

---

# DSGVO-Überlegungen für Ziele {#gdpr-considerations-for-destinations}

Auf dieser Seite werden die direkt von unseren Partnern bereitgestellten Informationen sowie die Auswirkungen auf Ihr Vorgehen in Audience Manager beschrieben. Wesentliche Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, ergeben sich aus der DSGVO (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft getreten ist, und aus dem neuen IAB Framework (IAB DSGVO Transparency &amp; Consent Framework).

Adobe-Partner sind für ihre eigenen Geschäftsprozesse verantwortlich und können von Zeit zu Zeit ihre Integrationsanforderungen an Audience Manager aktualisieren. Wir arbeiten aktiv mit unserem Audience Manager-Partnersystem zusammen, um unsere Kunden über Änderungen auf dem Laufenden zu halten.

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

Zusätzlich zu den oben erwähnten Aktualisierungen des IAB-Framework haben Yahoo/Oath/DataX neue Parameter, **gdpr** und **gdpr_mode**, zu ihrer Taxonomie und den Audience-APIs hinzugefügt. Diese Parameter informieren Yahoo/Oath/DataX, dass sie berechtigt sind, ein bestimmtes Segment als Datenverarbeiter oder als Datenverantwortlicher zu verarbeiten. Daher müssen Audience Manager-Kunden, die Segmente an ein Yahoo/Oath/DataX-Ziel senden, den entsprechenden Parameter (Verarbeiter oder Verantwortlicher) entsprechend ihrer Vereinbarung mit Oath angeben.

Wenden Sie sich an Ihren Berater oder an die Kundenunterstützung, um den richtigen Parameter festzulegen. Adobe kann dieses Aktualisierung nur dann im Namen eines Kunden vornehmen, wenn diese Aktualisierung schriftlich bei uns angefordert wird. Bitte wenden Sie sich an Ihren Yahoo/Oath/DataX-Support-Mitarbeiter, um die vollständige Definition dieser Parameter zu verstehen.
