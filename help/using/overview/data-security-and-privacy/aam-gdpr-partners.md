---
description: Auf dieser Seite werden die direkt von unseren Partnern bereitgestellten Informationen sowie die Auswirkungen auf Ihr Vorgehen in Audience Manager beschrieben. Wesentliche Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, ergeben sich aus der DSGVO (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft getreten ist, und aus dem neuen IAB Framework (IAB DSGVO Transparency & Consent Framework).
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: DSGVO-Überlegungen für Ziele
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# DSGVO-Überlegungen für Ziele{#gdpr-considerations-for-destinations}

Auf dieser Seite werden die direkt von unseren Partnern bereitgestellten Informationen sowie die Auswirkungen auf Ihr Vorgehen in Audience Manager beschrieben. Wesentliche Auswirkungen für die Partner, die diese Aktualisierungen vornehmen, ergeben sich aus der DSGVO (Allgemeine Datenschutzverordnung), die am 25. Mai 2018 in Kraft getreten ist, und aus dem neuen IAB Framework (IAB DSGVO Transparency &amp; Consent Framework).

Adobe-Partner sind für ihre eigenen Geschäftsprozesse verantwortlich und können von Zeit zu Zeit ihre Integrationsanforderungen an Audience Manager aktualisieren. Wir arbeiten aktiv mit unserem Audience Manager-Partnersystem zusammen, um unsere Kunden über Änderungen auf dem Laufenden zu halten.

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

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
</table>
-->

## Aktualisierung der Audience Manager-Benutzeroberfläche - Yahoo/Oath/DataX-Integration {#ui-update}

Zusätzlich zu den oben erwähnten Aktualisierungen des IAB-Framework haben Yahoo/Oath/DataX neue Parameter, **gdpr** und **gdpr_mode**, zu ihrer Taxonomie und den Audience-APIs hinzugefügt. Diese Parameter informieren Yahoo/Oath/DataX, dass sie berechtigt sind, ein bestimmtes Segment als Datenverarbeiter oder als Datenverantwortlicher zu verarbeiten. Daher müssen Audience Manager-Kunden, die Segmente an ein Yahoo/Oath/DataX-Ziel senden, den entsprechenden Parameter (Verarbeiter oder Verantwortlicher) entsprechend ihrer Vereinbarung mit Oath angeben.

Wenden Sie sich an Ihren Berater oder an die Kundenunterstützung, um den richtigen Parameter festzulegen. Adobe kann dieses Aktualisierung nur dann im Namen eines Kunden vornehmen, wenn diese Aktualisierung schriftlich bei uns angefordert wird. Bitte wenden Sie sich an Ihren Yahoo/Oath/DataX-Support-Mitarbeiter, um die vollständige Definition dieser Parameter zu verstehen.
