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


# ID-Synchronisierung für eingehende Datenübertragungen{#id-synchronization-for-inbound-data-transfers}

Beschreibt die Syntax und Parameter, die im ersten `HTTP` Aufruf verwendet werden, um Benutzer-IDs zwischen einem Anbieter und Audience Manager zu synchronisieren. Die ID-Synchronisierung kann beginnen, nachdem Sie Ihre Daten-Taxonomie an Audience Manager gesendet haben.

<!-- c_id_sync_in.xml -->

Die ID-Synchronisierung ist der erste Schritt im eingehenden, asynchronen Datenübertragungsprozess. In diesem Schritt vergleichen Audience Manager und der Anbieter IDs für ihre jeweiligen Site-Besucher. Ein [!DNL Audience Manager] Kunde kann z. B. einen Benutzer nach ID 123 erkennen. Ihr Datenpartner könnte diesen Benutzer jedoch mit ID 456 identifizieren. Der Synchronisierungsprozess ermöglicht [!DNL Audience Manager] es und einem Datenanbieter, diese verschiedenen IDs zu vereinheitlichen und Benutzer in ihren jeweiligen Systemen zu identifizieren. Sobald [!DNL Audience Manager] der Abschluss abgeschlossen ist und Ihr Partner für Drittanbieter entsprechende IDs für jeden in unseren Netzwerken angezeigten Benutzer haben sollte.

Sie können die folgenden Methoden verwenden, um Ihre Daten zu [!DNL Audience Manager]erhalten:

* [HTTP-Anfrage für die ID-Synchronisierung](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Deklariertes ID-Ereignis](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-Synchronisierung von einem eingebetteten E-Mail-Bild](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID `HTTP` -Synchronisierungsanforderung {#id-sync-http}

Bei einem ID-Austausch sollte eine korrekt formatierte [!DNL URL] Zeichenfolge wie folgt aussehen:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code><i>&lt; VENDOR_ ID &gt;</i></code> </td> 
   <td colname="col2"> <p>Eindeutige ID für den Content Provider (von <span class="keyword"> Audience Manager</span>zugewiesen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; VENDOR_ UUID &gt;</i></code> </td> 
   <td colname="col2"> <p>URL (Prozent) Kodierte Darstellung Ihrer eindeutigen Benutzer-ID. Neben der Kodierung reservierte ASCII-Zeichen sollten alle Nicht-ASCII-Zeichen basierend auf der UTF -8-Zeichenkodierung-Tabelle prozentkodiert sein. </p> <p>Weitere Informationen finden Sie auf der <a href="https://www.url-encode-decode.com" format="http" scope="external"> Online</a> -Website Encode/Decode. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2"> <p>Eine kodierte URL-Umleitung mit eingebettetem Makro <code> $ {DD_ UUID}</code> . </p> <p>Hinweis: Wird nur hinzugefügt, wenn der Content Provider den Aufruf startet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>Optional. Fügen Sie diesen Parameter hinzu, wenn Sie das <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager-Plugin für IAB TCF verwenden.</a></p> <p><code> gdpr</code> kann 0 sein (GDPR nicht angewendet) oder 1 (GDPR angewendet). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr_ consent verwendet</code>werden.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ consent = &lt; ENCODED STRING &gt;</i></code> </td> 
   <td colname="col2"> <p>Optional. Fügen Sie diesen Parameter hinzu, wenn Sie das <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager-Plugin für IAB TCF verwenden.</a></p> <p><code>gdpr_ consent</code> ist die URL-sichere Base 64-kodierte GDPR-Zeichenfolge (siehe <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-Spezifikation</a>). </p> <p> <b>Hinweis:</b> Dieser Parameter kann nur zusammen mit <code>gdpr verwendet</code>werden.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Deklariertes ID-Ereignis {#declared-id-event}

Weitere Informationen finden Sie unter [Deklarierte IDs](../../../features/declared-ids.md).

## ID-Synchronisierung von einem eingebetteten E-Mail-Bild {#id-sync-email-image}

Das Format für übereinstimmende IDs über ein E-Email-Bild entspricht dem oben dargestellten Format. Beachten Sie jedoch, dass Bilder in einer E-Mail für diese Funktion aktiviert werden müssen. Dies kann sich auf die ID-Synchronisierung per E-Email auswirken, da die meisten E-Mail-Systeme standardmäßig Bilder deaktivieren.

>[!MORE_ LIKE_ THIS]
>
>* [Datenerfassungskomponenten](../../../reference/system-components/components-data-collection.md)

