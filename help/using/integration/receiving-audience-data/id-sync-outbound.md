---
description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter für Daten verwendet werden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie Ihre erste ID-Synchronisierung durchführen.
seo-description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter für Daten verwendet werden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie Ihre erste ID-Synchronisierung durchführen.
seo-title: ID-Synchronisierung für ausgehende Datenübertragungen
solution: Audience Manager
title: ID-Synchronisierung für ausgehende Datenübertragungen
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: b1e438a77a472c192117a2c1ddcf63f4eb25d07d

---


# ID-Synchronisierung für ausgehende Datenübertragungen{#id-synchronization-for-outbound-data-transfers}

Beschreibt die Syntax und die Parameter, die beim ersten `HTTP` Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter für Daten verwendet werden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie Ihre erste ID-Synchronisierung durchführen.

<!-- c_id_sync_out.xml -->

## Zweck der ID-Synchronisierung

Die ID-Synchronisierung ist der erste Schritt im ausgehenden, asynchronen Datenübermittlungsprozess. In diesem Schritt vergleicht [!DNL Audience Manager] der Anbieter IDs für die jeweiligen Sitebesucher und stimmt sie überein. Ein [!DNL Audience Manager] Kunde kann beispielsweise einen Benutzer mit der ID 123 kennen. Ihr Datenpartner könnte diesen Benutzer jedoch mit der ID 456 identifizieren. Der Synchronisierungsprozess ermöglicht es [!DNL Audience Manager] und einem Datenanbieter, diese unterschiedlichen IDs miteinander zu vereinbaren und Benutzer in ihren jeweiligen Systemen zu identifizieren. Nach Abschluss des Vorgangs sollte [!DNL Audience Manager] der Drittanbieter über entsprechende IDs für jeden eindeutigen Benutzer in unseren Netzwerken verfügen.

## URL-Syntax

Bei einem ID-Austausch sollte eine ordnungsgemäß formatierte [!DNL URL] Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-Parameter

Die Variablen [!DNL URL] für Ihren Aufruf zur ID-Synchronisierung mit Inbound sollten in der folgenden Tabelle beschrieben werden.

>[!NOTE]
>
>Ersetzen Sie kursiv gedruckten Inhalt durch tatsächliche Parameterwerte.

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
   <td colname="col2">Eindeutige ID für den Datenanbieter (von <span class="keyword"> Audience Manager</span>zugewiesen). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Eindeutige Benutzer-ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Eine kodierte URL-Umleitung mit dem darin eingebetteten Makro <code> ${DD_UUID}</code> . <p><b></b> Hinweis: Wird nur hinzugefügt, wenn der Datenanbieter den Aufruf initiiert. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kann 0 (GDPR gilt nicht) oder 1 (GDPR gilt) betragen.</p><p><b>Hinweis:</b> <ul><li>Die <code>gdpr</code> und <code>gdpr_consent</code> Parameter werden schrittweise in URLs zur ID-Synchronisierung mit Aktivierungspartnern bereitgestellt. Siehe Aktivierungspartner, die die IAB-TCF im <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager-Plugin für die IAB-TCF unterstützen.</a></li><li>Dieser Parameter kann nur zusammen mit <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> ist die URL-sichere Base64-kodierte GDPR-Zustimmungszeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>).</p><p><b></b> Hinweis: Dieser Parameter kann nur zusammen mit verwendet werden <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-Methoden und Code für Datenerfassungsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md)

