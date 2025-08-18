---
description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und Audience Manager verwendet wurden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an Audience Manager gesendet haben.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: ID-Synchronisierung für eingehende Datenübertragungen
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# ID-Synchronisierung für eingehende Datenübertragungen {#id-synchronization-for-inbound-data-transfers}

Beschreibt die Syntax und die Parameter, die beim ersten `HTTP`-Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und [!DNL Audience Manager] verwendet wurden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an [!DNL Audience Manager] gesendet haben.

Die ID-Synchronisierung ist der erste Schritt im eingehenden, asynchronen Datenübertragungsprozess. In diesem Schritt vergleichen [!DNL Audience Manager] und der Anbieter die IDs der jeweiligen Site-Besucher und gleichen diese ab. Beispielsweise kann ein [!DNL Audience Manager] Kunde einen Benutzer anhand der ID 123 kennen. Ihr Datenpartner kann diesen Benutzer jedoch mit der ID 456 identifizieren. Durch den Synchronisierungsprozess können [!DNL Audience Manager] und ein Datenanbieter diese verschiedenen IDs miteinander in Einklang bringen und Benutzer in ihren jeweiligen Systemen identifizieren. Nach Abschluss des Vorgangs sollten [!DNL Audience Manager] und Ihr Drittanbieterpartner über entsprechende IDs für jeden einzelnen Benutzer in unseren Netzwerken verfügen.

Sie können die folgenden Methoden verwenden, um Ihre Daten in zu [!DNL Audience Manager]:

* [HTTP-Anfrage zur ID-Synchronisierung](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Declared ID Event](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-Synchronisierung aus einem eingebetteten E-Mail-Bild](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID-Synchronisierung `HTTP` Anfrage {#id-sync-http}

Bei einem ID-Austausch sollte eine ordnungsgemäß formatierte [!DNL URL]-Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Eindeutige ID für den Inhaltsanbieter (von <span class="keyword"> Audience Manager zugewiesen</span>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (Prozent)-kodierte Darstellung der Unique User ID. Zusätzlich zur Codierung reservierter ASCII-Zeichen sollten alle Nicht-ASCII-Zeichen basierend auf der UTF-8-Zeichenkodierungstabelle prozentual codiert werden. </p> <p>Weitere Informationen finden Sie auf der Website <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Eine codierte URL-Umleitung mit dem darin eingebetteten Makro <code> ${DD_UUID}</code>. </p> <p>Hinweis: Wird nur hinzugefügt, wenn der Content Provider den Aufruf initiiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Fügen Sie diesen Parameter hinzu, wenn Sie das <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF verwenden.</a></p> <p><code> gdpr</code> kann 0 (die DSGVO gilt nicht) oder 1 (die DSGVO gilt nicht) sein. </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr_consent</code> verwendet werden.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Fügen Sie diesen Parameter hinzu, wenn Sie das <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF verwenden.</a></p> <p><code>gdpr_consent</code> ist die URL-sichere base64-kodierte DSGVO-Einverständniszeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr</code> verwendet werden.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] {#declared-id-event}

Weitere Informationen finden Sie unter [Declared IDs](../../../features/declared-ids.md).

## ID-Synchronisierung aus einem eingebetteten E-Mail-Bild {#id-sync-email-image}

Das Format für den Abgleich von IDs über ein E-Mail-Bild ist dasselbe wie oben gezeigt. Beachten Sie jedoch, dass Bilder in einer E-Mail aktiviert sein müssen, damit dies funktioniert. Dies kann sich auf die ID-Synchronisierung per E-Mail auswirken, da die meisten E-Mail-Systeme Bilder standardmäßig deaktivieren.

>[!MORELIKETHIS]
>
>* [Datenerfassungskomponenten](../../../reference/system-components/components-data-collection.md)
