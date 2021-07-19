---
description: Beschreibt die Syntax und die Parameter, die im ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und Audience Manager verwendet werden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an Audience Manager gesendet haben.
seo-description: Beschreibt die Syntax und die Parameter, die im ersten HTTP-Aufruf zum Synchronisieren von Benutzer-IDs zwischen einem Anbieter und Audience Manager verwendet werden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an Audience Manager gesendet haben.
seo-title: ID-Synchronisierung für eingehende Datenübertragungen
solution: Audience Manager
title: ID-Synchronisierung für eingehende Datenübertragungen
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Übertragungen von Inbound-Daten
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 8%

---

# ID-Synchronisierung für eingehende Datenübertragungen {#id-synchronization-for-inbound-data-transfers}

Beschreibt die Syntax und die Parameter, die im ersten `HTTP`-Aufruf zur Synchronisierung der Benutzer-IDs zwischen einem Anbieter und [!DNL Audience Manager] verwendet werden. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Datentaxonomie an [!DNL Audience Manager] gesendet haben.

Die ID-Synchronisierung ist der erste Schritt im Prozess der eingehenden, asynchronen Datenübertragung. In diesem Schritt vergleichen [!DNL Audience Manager] und der Anbieter IDs für die jeweiligen Site-Besucher und stimmen sie überein. So kann beispielsweise ein [!DNL Audience Manager]-Kunde einen Benutzer anhand der ID 123 kennen. Ihr Datenpartner könnte diesen Benutzer jedoch mit ID 456 identifizieren. Der Synchronisierungsprozess ermöglicht es [!DNL Audience Manager] und einem Datenanbieter, diese verschiedenen IDs abzustimmen und Benutzer in ihren jeweiligen Systemen zu identifizieren. Nach Abschluss sollten [!DNL Audience Manager] und Ihr Drittanbieter-Partner über entsprechende IDs für jeden eindeutigen Benutzer verfügen, der in unseren Netzwerken angezeigt wird.

Sie können die folgenden Methoden verwenden, um Ihre Daten in [!DNL Audience Manager] zu übertragen:

* [ID-Synchronisierungs-HTTP-Anforderung](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Declared ID-Ereignis](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-Synchronisierung von einem E-Mail-eingebetteten Bild](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID-Synchronisierung `HTTP` Anforderung {#id-sync-http}

Bei einem ID-Austausch sollte eine ordnungsgemäß formatierte [!DNL URL]-Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

Der [!DNL URL]-Aufruf für Ihren eingehenden ID-Synchronisierungsaufruf sollte Variablen enthalten, die in der folgenden Tabelle beschrieben sind.

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
   <td colname="col2"> <p>Eindeutige ID für den Inhaltsanbieter (zugewiesen durch <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (Prozent) Kodierte Darstellung Ihrer Unique User ID. Neben der Kodierung reservierter ASCII-Zeichen sollten alle Nicht-ASCII-Zeichen basierend auf der UTF-8-Zeichencodierungstabelle prozentual kodiert werden. </p> <p>Weitere Informationen finden Sie auf der Website <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL-Codierung/Decode Online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Eine kodierte URL-Umleitung mit dem Makro <code> ${DD_UUID}</code>, das darin eingebettet ist. </p> <p>Hinweis:  Es wurde nur hinzugefügt, wenn der Inhalts-Provider den -Aufruf initiiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Fügen Sie diesen Parameter hinzu, wenn Sie das <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF verwenden.</a></p> <p><code> gdpr</code> kann 0 (DSGVO trifft nicht zu) oder 1 (DSGVO trifft zu) betragen. </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit  <code>gdpr_consent</code>verwendet werden.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optional. Fügen Sie diesen Parameter hinzu, wenn Sie das <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF verwenden.</a></p> <p><code>gdpr_consent</code> ist die URL-sichere base64-kodierte DSGVO-Zustimmungszeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit  <code>gdpr</code>verwendet werden.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID]Ereignis- {#declared-id-event}

Weitere Informationen finden Sie unter [Deklarierte IDs](../../../features/declared-ids.md).

## ID-Synchronisierung von einem E-Mail-eingebetteten Bild {#id-sync-email-image}

Das Format für übereinstimmende IDs über ein E-Mail-Bild ist mit dem oben gezeigten Format identisch. Beachten Sie jedoch, dass Bilder in einer E-Mail aktiviert werden müssen, damit dies funktioniert. Dies kann sich auf die ID-Synchronisierung per E-Mail auswirken, da die meisten E-Mail-Systeme Bilder standardmäßig deaktivieren.

>[!MORELIKETHIS]
>
>* [Datenerfassungskomponenten](../../../reference/system-components/components-data-collection.md)

