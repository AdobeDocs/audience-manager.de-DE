---
description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter verwendet wurden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie die erste ID-Synchronisierung durchführen.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: ID-Synchronisierung für ausgehende Datenübertragungen
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# ID-Synchronisierung für ausgehende Datenübertragungen{#id-synchronization-for-outbound-data-transfers}

Beschreibt die Syntax und die Parameter, die beim ersten `HTTP`-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter verwendet wurden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie die erste ID-Synchronisierung durchführen.

<!-- c_id_sync_out.xml -->

## Zweck der ID-Synchronisierung

Die ID-Synchronisierung ist der erste Schritt im ausgehenden, asynchronen Datenübertragungsprozess. In diesem Schritt vergleichen [!DNL Audience Manager] und der Anbieter die IDs der jeweiligen Site-Besucher und gleichen diese ab. Beispielsweise kann ein [!DNL Audience Manager] Kunde einen Benutzer anhand der ID 123 kennen. Ihr Datenpartner kann diesen Benutzer jedoch mit der ID 456 identifizieren. Durch den Synchronisierungsprozess können [!DNL Audience Manager] und ein Datenanbieter diese verschiedenen IDs miteinander in Einklang bringen und Benutzer in ihren jeweiligen Systemen identifizieren. Nach Abschluss des Vorgangs sollten [!DNL Audience Manager] und der Drittanbieter-Datenanbieter über entsprechende IDs für jeden einzelnen Benutzer verfügen, der in unseren Netzwerken gesehen wird.

## URL-Syntax

Bei einem ID-Austausch sollte eine ordnungsgemäß formatierte [!DNL URL]-Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-Parameter

Die [!DNL URL] für Ihren eingehenden ID-Synchronisierungsaufruf sollte Variablen enthalten, die in der folgenden Tabelle beschrieben sind.

>[!NOTE]
>
>Ersetzen kursiv formatierter Inhalte durch tatsächliche Parameterwerte.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">Eindeutige ID für den Datenanbieter (von <span class="keyword"> Audience Manager zugewiesen</span>) </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Unique User ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Eine codierte URL-Umleitung mit dem darin eingebetteten Makro <code> ${DD_UUID}</code>. <p><b>Hinweis:</b> Wird nur hinzugefügt, wenn der Datenanbieter den Aufruf initiiert. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kann 0 (die DSGVO gilt nicht) oder 1 (die DSGVO gilt nicht) sein.</p><p><b>Hinweis:</b> <ul><li>Die <code>gdpr</code>- und <code>gdpr_consent</code> werden schrittweise in ID-Synchronisierungs-URLs mit Aktivierungspartnern eingeführt. Siehe Aktivierungspartner, die IAB TCF im <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager-Plug-in für IAB TCF unterstützen.</a></li><li>Dieser Parameter kann nur zusammen mit <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> ist die URL-sichere base64-kodierte DSGVO-Einverständniszeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>).</p><p><b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr</code> verwendet werden.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-Methoden und -Code des Datenerfassungsservers (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md)
