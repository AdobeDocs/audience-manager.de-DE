---
description: Beschreibt die Syntax und Parameter, die beim anfänglichen HTTP-Aufruf verwendet werden, um Benutzer-IDs zwischen einem Anbieter und Audience Manager zu synchronisieren. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Daten-Taxonomie an Audience Manager gesendet haben.
seo-description: Beschreibt die Syntax und Parameter, die beim anfänglichen HTTP-Aufruf verwendet werden, um Benutzer-IDs zwischen einem Anbieter und Audience Manager zu synchronisieren. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Daten-Taxonomie an Audience Manager gesendet haben.
seo-title: ID-Synchronisierung für eingehende Datenübertragungen
solution: Audience Manager
title: ID-Synchronisierung für eingehende Datenübertragungen
uuid: 037 e 74 a 6-acfd -4 cef-b 693-16 b 7 aaa 8 e 976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Daten-Taxonomie an Audience Manager gesendet haben.

<!-- c_id_sync_in.xml -->

Die ID-Synchronisierung ist der erste Schritt im eingehenden, asynchronen Datenübertragungsprozess. In diesem Schritt vergleichen Audience Manager und der Anbieter IDs für ihre jeweiligen Site-Besucher. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Ihr Datenpartner könnte diesen Benutzer jedoch mit ID 456 identifizieren. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [HTTP-Anfrage für die ID-Synchronisierung](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Deklariertes ID-Ereignis](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-Synchronisierung von einem eingebetteten E-Mail-Bild](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

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
  <tr> 
   <td colname="col1"> <code><i>&lt; VENDOR_ ID &gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; VENDOR_ UUID &gt;</i></code> </td> 
   <td colname="col2"> <p>URL (Prozent) Kodierte Darstellung Ihrer eindeutigen Benutzer-ID. Neben der Kodierung reservierte ASCII-Zeichen sollten alle Nicht-ASCII-Zeichen basierend auf der UTF -8-Zeichenkodierung-Tabelle prozentkodiert sein. </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>Hinweis: Wird nur hinzugefügt, wenn der Content Provider den Aufruf startet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>Optional. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> gdpr</code> kann 0 sein (GDPR nicht angewendet) oder 1 (GDPR angewendet). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr_ consent verwendet</code>werden.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ consent = &lt; ENCODED STRING &gt;</i></code> </td> 
   <td colname="col2"> <p>Optional. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_ consent</code> ist die URL-sichere Base 64-kodierte GDPR-Zeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr verwendet</code>werden.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

Das Format für übereinstimmende IDs über ein E-Email-Bild entspricht dem oben dargestellten Format. Beachten Sie jedoch, dass Bilder in einer E-Mail für diese Funktion aktiviert werden müssen. Dies kann sich auf die ID-Synchronisierung per E-Email auswirken, da die meisten E-Mail-Systeme standardmäßig Bilder deaktivieren.

>[!MORE_ LIKE_ THIS]
>
>* [Datenerfassungskomponenten](../../../reference/system-components/components-data-collection.md)

