---
description: Beschreibt die Syntax und Parameter, die beim anfänglichen HTTP-Aufruf verwendet werden, um Benutzer-IDs zwischen Audience Manager und einem Drittanbieter-Datenprovider zu synchronisieren. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie die erste ID-Synchronisierung versuchen.
seo-description: Beschreibt die Syntax und Parameter, die beim anfänglichen HTTP-Aufruf verwendet werden, um Benutzer-IDs zwischen Audience Manager und einem Drittanbieter-Datenprovider zu synchronisieren. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie die erste ID-Synchronisierung versuchen.
seo-title: ID-Synchronisierung für ausgehende Datenübertragungen
solution: Audience Manager
title: ID-Synchronisierung für ausgehende Datenübertragungen
uuid: f 3849 be 8-1094-47 db -9296-7482 f 020 af 18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID-Synchronisierung für ausgehende Datenübertragungen{#id-synchronization-for-outbound-data-transfers}

Beschreibt die Syntax und Parameter, die im anfänglichen `HTTP` Aufruf verwendet werden, um Benutzer-IDs zwischen Audience Manager und einem Drittanbieter-Datenanbieter zu synchronisieren. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie die erste ID-Synchronisierung versuchen.

<!-- c_id_sync_out.xml -->

## Zweck der ID-Synchronisierung

Die ID-Synchronisierung ist der erste Schritt im ausgehenden, asynchronen Datenübertragungsprozess. In diesem Schritt [!DNL Audience Manager] und der Anbieter, der IDs für ihre jeweiligen Site-Besucher vergleichen und abgleicht. Ein [!DNL Audience Manager] Kunde kann z. B. einen Benutzer nach ID 123 erkennen. Ihr Datenpartner könnte diesen Benutzer jedoch mit ID 456 identifizieren. Der Synchronisierungsprozess ermöglicht [!DNL Audience Manager] es und einem Datenanbieter, diese verschiedenen IDs zu vereinheitlichen und Benutzer in ihren jeweiligen Systemen zu identifizieren. Sobald sie abgeschlossen sind [!DNL Audience Manager] und der Drittanbieter-Datenanbieter entsprechende IDs für jeden in unseren Netzwerken angezeigten Unique User besitzen sollte.

## URL-Syntax

Bei einem ID-Austausch sollte eine korrekt formatierte [!DNL URL] Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-Parameter

Der [!DNL URL] Synchronisierungsaufruf für eingehende Ids sollte Variablen enthalten, die in der unten stehenden Tabelle beschrieben sind.

>[!NOTE]
>
>Ersetzen Sie kursiv gesteuerte Inhalte durch tatsächliche Parameterwerte.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VENDOR_ ID &gt;</i></code> </td> 
   <td colname="col2">Eindeutige ID für den Datenanbieter (von <span class="keyword"> Audience Manager</span>zugewiesen). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VENDOR_ UUID &gt;</i></code> </td> 
   <td colname="col2"> Unique User ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">Eine kodierte URL-Umleitung mit eingebettetem Makro <code> $ {DD_ UUID}</code> . <p><b>Hinweis:</b> Wird nur hinzugefügt, wenn der Datenanbieter den Aufruf startet. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kann 0 sein (GDPR nicht angewendet) oder 1 (GDPR angewendet).</p><p><b>Hinweis:</b> <ul><li>Die Parameter <code>gdpr</code> und <code>gdpr_ consent</code> werden in ID-Synchronisierungs-urls mit Aktivierungspartnern schrittweise eingeführt. Siehe Aktivierungspartner, die IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager für IAB TCF unterstützen.</a></li><li>Dieser Parameter kann nur zusammen mit <code>gdpr_ consent verwendet werden.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ consent = &lt; ENCODED STRING &gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ consent</code> ist die URL-sichere Base 64-kodierte GDPR-Zeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>).</p><p><b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr verwendet</code>werden.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [API-Methoden und -code für Datenerfassungsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md)

