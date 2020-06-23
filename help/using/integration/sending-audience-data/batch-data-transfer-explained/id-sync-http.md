---
description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und Audience Manager verwendet werden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an Audience Manager gesendet haben.
seo-description: Beschreibt die Syntax und die Parameter, die beim ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und Audience Manager verwendet werden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an Audience Manager gesendet haben.
seo-title: ID-Synchronisierung für eingehende Datenübertragungen
solution: Audience Manager
title: ID-Synchronisierung für eingehende Datenübertragungen
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 3%

---


# ID-Synchronisierung für eingehende Datenübertragungen {#id-synchronization-for-inbound-data-transfers}

Beschreibt die Syntax und die Parameter, die beim ersten `HTTP` Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und [!DNL Audience Manager]einem Anbieter verwendet werden. Die ID-Synchronisierung kann nach dem Senden der Datentaxonomie an beginnen [!DNL Audience Manager].

Die ID-Synchronisierung ist der erste Schritt im Prozess der asynchronen Datenübertragung. In diesem Schritt vergleicht [!DNL Audience Manager] der Anbieter IDs für die jeweiligen Site-Besucher und stimmt sie überein. Ein [!DNL Audience Manager] Kunde kann beispielsweise einen Benutzer mit der ID 123 kennen. Ihr Datenpartner könnte diesen Benutzer jedoch mit der ID 456 identifizieren. Der Synchronisierungsprozess ermöglicht es [!DNL Audience Manager] und einem Datenlieferanten, diese unterschiedlichen IDs miteinander zu vereinbaren und Benutzer in ihren jeweiligen Systemen zu identifizieren. Nach Abschluss des Vorgangs sollte Ihr Drittanbieter-Partner über entsprechende IDs für jeden eindeutigen Benutzer in unseren Netzwerken verfügen. [!DNL Audience Manager]

Sie können die folgenden Methoden verwenden, um Ihre Daten abzurufen [!DNL Audience Manager]:

* [HTTP-Anforderung zur ID-Synchronisierung](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Deklariertes ID-Ereignis](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-Synchronisierung aus einem E-Mail-eingebetteten Bild](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID-Synchronisierungsanfrage `HTTP` {#id-sync-http}

Bei einem ID-Austausch sollte eine ordnungsgemäß formatierte [!DNL URL] Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Eindeutige ID für den Content Provider (durch <span class="keyword"> Audience Manager</span>zugewiesen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (Prozent) Kodierte Darstellung Ihrer Unique User ID. Neben der Kodierung reservierter ASCII-Zeichen sollten alle Nicht-ASCII-Zeichen basierend auf der UTF-8-Zeichenkodierungstabelle prozentual kodiert werden. </p> <p>Weitere Informationen finden Sie auf der Website <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL-Kodierung/Dekodierung</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Eine kodierte URL-Umleitung mit dem darin eingebetteten Makro <code> ${DD_UUID}</code> . </p> <p>Hinweis:  Wird nur hinzugefügt, wenn der Content Provider den Aufruf initiiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Hinzufügen Sie diesen Parameter, wenn Sie das <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF verwenden.</a></p> <p><code> gdpr</code> kann 0 (GDPR gilt nicht) oder 1 (GDPR gilt) betragen. </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit verwendet werden <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Hinzufügen Sie diesen Parameter, wenn Sie das <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF verwenden.</a></p> <p><code>gdpr_consent</code> ist die URL-sichere Base64-kodierte GDPR-Zustimmungszeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit verwendet werden <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Ereignis {#declared-id-event}

Weitere Informationen finden Sie unter [Deklarierte IDs](../../../features/declared-ids.md).

## ID-Synchronisierung aus einem E-Mail-eingebetteten Bild {#id-sync-email-image}

Das Format für die Zuordnung von IDs über ein E-Mail-Bild ist mit dem oben gezeigten Format identisch. Beachten Sie jedoch, dass Bilder in einer E-Mail aktiviert werden müssen, damit dies funktioniert. Dies kann sich auf die ID-Synchronisierung per E-Mail auswirken, da die meisten E-Mail-Systeme Bilder standardmäßig deaktivieren.

>[!MORELIKETHIS]
>
>* [Datenerfassungskomponenten](../../../reference/system-components/components-data-collection.md)

