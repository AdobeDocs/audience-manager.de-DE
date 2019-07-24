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


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie die erste ID-Synchronisierung versuchen.

<!-- c_id_sync_out.xml -->

## Zweck der ID-Synchronisierung

Die ID-Synchronisierung ist der erste Schritt im ausgehenden, asynchronen Datenübertragungsprozess. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Ihr Datenpartner könnte diesen Benutzer jedoch mit ID 456 identifizieren. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## URL-Syntax

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-Parameter

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
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VENDOR_ ID &gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VENDOR_ UUID &gt;</i></code> </td> 
   <td colname="col2"> Unique User ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>Hinweis:</b> Wird nur hinzugefügt, wenn der Datenanbieter den Aufruf startet. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kann 0 sein (GDPR nicht angewendet) oder 1 (GDPR angewendet).</p><p><b>Hinweis:</b> <ul><li>The <code>gdpr</code> and <code>gdpr_consent</code> parameters are being gradually rolled out in ID sync URLs with activation partners. See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
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

