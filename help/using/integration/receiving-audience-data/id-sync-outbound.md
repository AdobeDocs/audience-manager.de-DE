---
description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter verwendet werden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie Ihre erste ID-Synchronisierung durchführen.
seo-description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter verwendet werden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie Ihre erste ID-Synchronisierung durchführen.
seo-title: ID-Synchronisierung für ausgehende Datenübertragungen
solution: Audience Manager
title: ID-Synchronisierung für ausgehende Datenübertragungen
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 12%

---


# ID-Synchronisierung für ausgehende Datenübertragungen{#id-synchronization-for-outbound-data-transfers}

Beschreibt die Syntax und die Parameter, die im initialen `HTTP`-Aufruf zum Synchronisieren von Benutzer-IDs zwischen Audience Manager und einem Drittanbieter für Daten verwendet werden. Wenden Sie sich an Ihren Adobe Audience Manager-Berater, bevor Sie Ihre erste ID-Synchronisierung durchführen.

<!-- c_id_sync_out.xml -->

## Zweck der ID-Synchronisierung

Die ID-Synchronisierung ist der erste Schritt im ausgehenden, asynchronen Datenübermittlungsprozess. In diesem Schritt vergleichen [!DNL Audience Manager] und der Anbieter IDs für die jeweiligen Site-Besucher und stimmen sie überein. Beispielsweise kann ein [!DNL Audience Manager]-Kunde einen Benutzer mit der ID 123 kennen. Ihr Datenpartner könnte diesen Benutzer jedoch mit der ID 456 identifizieren. Der Synchronisierungsprozess ermöglicht es [!DNL Audience Manager] und einem Datenanbieter, diese unterschiedlichen IDs miteinander zu verbinden und Benutzer in ihren jeweiligen Systemen zu identifizieren. Nach Abschluss des Vorgangs sollten [!DNL Audience Manager] und der Drittanbieter für Daten über entsprechende IDs für jeden eindeutigen Benutzer in unseren Netzwerken verfügen.

## URL-Syntax

Bei einem ID-Austausch sollte eine korrekt formatierte [!DNL URL]-Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-Parameter

Der [!DNL URL]-Aufruf für Ihre ID-Synchronisierung mit eingehenden IDs sollte Variablen enthalten, die in der folgenden Tabelle beschrieben sind.

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
   <td colname="col2">Eindeutige ID für den Datenanbieter (zugewiesen von <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Eindeutige Benutzer-ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Eine kodierte URL-Umleitung mit dem Makro <code> ${DD_UUID}</code>, das darin eingebettet ist. <p><b>Hinweis:Wird nur </b> hinzugefügt, wenn der Datenanbieter den Aufruf initiiert. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kann 0 (GDPR gilt nicht) oder 1 (GDPR gilt) betragen.</p><p><b>Hinweis:</b> <ul><li>Die Parameter <code>gdpr</code> und <code>gdpr_consent</code> werden schrittweise in ID-Synchronisierungs-URLs mit Aktivierung-Partnern ausgeführt. Siehe Aktivierungen-Partner, die die IAB-TCF in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager-Plugin für IAB TCF unterstützen.</a></li><li>Dieser Parameter kann nur zusammen mit <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> ist die URL-sichere base64-kodierte GDPR-Zustimmungszeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>).</p><p><b>Hinweis:</b> Dieser Parameter kann nur zusammen mit verwendet werden  <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-Methoden und Code für Datenerfassungs-Server (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md)

