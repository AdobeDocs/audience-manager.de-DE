---
description: In diesem Dokument werden die technischen Einzelheiten der Einhaltung der Datenschutzbestimmungen für den Audience Manager behandelt.
seo-description: In diesem Dokument werden die technischen Einzelheiten der Einhaltung der Datenschutzbestimmungen für den Audience Manager behandelt.
seo-title: Datenschutzanforderungen
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Datenschutzanforderungen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 1%

---


# Datenschutzanforderungen {#data-privacy-requests}

## Überblick {#overview}

Dieses Dokument bietet einen Überblick über die Verwaltung individueller Datendatenschutzanforderungen und Abmeldeanforderungen, die Sie [!DNL Audience Manager] über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Privacy Service und die **[!DNL Privacy Service API]** Benutzeroberfläche senden können.

Mit diesen Tools können Sie Anfragen zum Datenschutz von Kunden senden, die unter [!DNL GDPR] und [!DNL CCPA]ausgeführt werden.

Bevor Sie diesen Artikel lesen, sollten Sie das Glossar [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA Glossar](aam-ccpa-glossary.md)durchlaufen, um die hier verwendete Terminologie besser zu verstehen.

Sie können einzelne Anforderungen senden, um auf Verbrauchsdaten zuzugreifen und diese zu löschen. Dazu haben Sie zwei Möglichkeiten [!DNL Audience Manager]:

* Über die Benutzeroberfläche des [Privacy Service](https://privacyui.cloud.adobe.io/). Die Dokumentation finden Sie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Durch die **[!DNL Privacy Service API]**. Die Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) und die [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Beim Senden individueller Datendatenschutzanforderungen können Sie alle [!DNL Audience Manager] IDs (IDs), wie im Abschnitt &quot; **[Audience Manager-IDs](data-privacy-ids.md)**&quot;beschrieben, zusammen mit ihren jeweiligen Namensraum-IDs (Datenquellen-IDs) senden.

Der [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) unterstützt zwei Anforderungstypen: Anforderungen zum Datenzugriff und zum Löschen von Daten.

## Datenzugriffsanforderungen {#access-data}

Sie können individuelle Datenzugriffsanfragen über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Privacy Service ( [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)Dokumentation) oder durch Aufruf der [!DNL Privacy Service API] (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

Über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Privacy Service können Sie neue Auftragsanforderungen entweder mithilfe der [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON] Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON] Datei aussieht, können Sie eine JSON-Musterdatei [herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir verstehen Ihre Verpflichtung, Ihre Datenschutzanforderungen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Datenlöschungsanforderungen {#delete-data}

Sie können Datenlöschungsanfragen über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Privacy Service ( [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)Dokumentation) oder durch Aufruf der [!DNL Privacy Service API] (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

Über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Privacy Service können Sie neue Auftragsanforderungen entweder mithilfe der [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON] Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON] Datei aussieht, können Sie eine JSON-Musterdatei [herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe versteht Ihr Eintreten für die Einhaltung der Datenschutzanforderungen von Kunden innerhalb von 30 Tagen. Deshalb [!DNL Adobe] ist es uns verpflichtet, Ihre Anforderung zum Löschen von Daten so schnell wie möglich zu bearbeiten.

Löscht als Reaktion auf die Anforderung zum Löschen von Benutzerdaten Eigenschaften und Segmente, die mit der in der Anforderung enthaltenen [!DNL Audience Manager] [!DNL Audience Manager] Kennung verknüpft sind. Darüber hinaus werden die entsprechenden [!DNL Audience Manager] IDs für die von der weiteren Datenerfassung abgewiesene Person [!DNL Audience Manager] und die entsprechenden ID-Zuordnungen entfernt.

Wenn Sie deklarierte IDs, wie z. B. geräteübergreifende [!DNL CRM] IDs oder [!DNL cookie] IDs, in Datenschutzanforderungen senden, führen [!DNL Audience Manager] Sie den erforderlichen Löschvorgang auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

[!DNL Audience Manager] versucht, die Aktivierung-Partner über Löschungsanfragen zu benachrichtigen, indem sie ihnen Segmentinformationen für Datensubjekte senden, die das Löschen bestimmter Daten anfordern. Einige Partnereinrichtungen der Aktivierung:

1. Segmentanforderungen können nicht unterstützt (oder entfernt werden) [!DNL Audience Manager] und/oder
2. sind nicht in der Lage, Updates von [!DNL Audience Manager] einer Häufigkeit von weniger als 30 Tagen zu erhalten. In diesen Fällen sind [!DNL Audience Manager] Kunden nicht in der Lage, Löschanfragen automatisch an Aktivierungen-Partner zu senden [!DNL Audience Manager].

In diesen Fällen ist es nicht möglich, Löschanfragen automatisch an Aktivierungen-Partner zu senden [!DNL Audience Manager].

Laden Sie sich unser [Partner-Excel-Blatt](assets/AAM-Partners-October2019.xlsx) herunter, um zu sehen, welche [!DNL Audience Manager] Partnerunternehmen Segmentunterschiede unterstützen.

## Abmeldeanforderungen {#opt-out-requests}

[!DNL Audience Manager] unterstützt branchenweite Standards für das Opt-out-Management. Lesen Sie für vollständige Informationen zu den von [!DNL Audience Manager]unterstützten Opt-out-Typen.

Während Datenzugriffs- und Löschanforderungen über den [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)verarbeitet werden, werden Abmeldeanforderungen derzeit über den unterstützt [!DNL DCS API]. Lesen Sie weiter, um zu erfahren, wie die Ausschluss- [!DNL API] Anrufe aussehen sollten.

### Globale Abmeldeanforderungen

Das globale Opt-out stellt ein Opt-out für alle Marken [!DNL Audience Manager] und andere [!DNL Adobe Experience Cloud] Lösungen dar. In der folgenden Tabelle werden die Methoden für die globale Abmeldung Liste:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Abmeldung für </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Auf der Seite <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> "Datenschutzoptionen" </a> stehen Funktionen mit einem Klick zur Verfügung, mit denen Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Anzeigenlösungen (einschließlich Audience Manager) steuern und abwählen können. Weitere Informationen finden Sie im Abschnitt zum <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Geschäftskunden </a> auf der Seite "Datenschutzoptionen". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkte API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Ihre Benutzer können die Datenerfassung durch alle Audience Manager-Marken ausschließen, indem Sie unten die DCS API aufrufen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID einschließen </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daher werden Cookies für die gesendete Audience Manager-ID gesetzt <code>demdex=NOTARGET</code> und <code>dextp=NOTARGET</code> Cookies gesetzt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Ausschluss- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Ihre Endbenutzer können die globale Datenerfassung auch Opt-out, indem sie die Websites unserer Partner für Industriestandards besuchen.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Befolgen Sie die oben beschriebenen Abmeldeanfragen:

* [!DNL Audience Manager] beendet die Datenerfassung, Segmentierung oder Aktivierung, solange der Benutzer seine Browser-Cookies nicht löscht.
* Historische Daten werden nach 120 Tagen aus dem Profil entfernt.

### Abmeldeoption auf Partnerebene mit erklärten ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager] Partner ausschließen. Sie können Abmeldeanfragen auf Partnerebene für geräteübergreifende IDs, einschließlich [!DNL CRM] IDs und Hash-E-Mail-Adressen, senden.

Nach einer Abmeldung auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird bei der Datenerfassung nicht berücksichtigt.
* [!DNL Audience Manager] beendet alle Datenerfassung, Segmentierung oder Aktivierung für die [!DNL CRM] ID und die letzte Geräte-ID, die mit der [!DNL CRM] ID verknüpft ist;
* [!DNL Audience Manager] Aufhebung der Segmentierung der Ausschluss- [!DNL CRM] ID und der letzten Geräte-ID aus allen Segmenten;
* [!UICONTROL Destination] Partner erhalten die Nicht-Segment-Anforderung für die [!DNL CRM] ID und die letzte Geräte-ID. Die Segmentierung funktioniert sowohl für [Echtzeit](data-privacy-requests.md#aam-partners-with-unsegmentation) - als auch für Stapelziele.
* Es werden keine Verlaufsdaten gelöscht.

Wenn [!DNL Audience Manager] eine Abmeldeanfrage auf Partnerebene gesendet wird, enthält der vom [!DNL JSON] zurückgegebene [!DNL DCS] Fehlercode 171 [mit der Meldung](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)anstelle der [!UICONTROL "Encountered opt out tag"][!DNL Audience Manager] Benutzer-ID.

Sie können eine deklarierte ID-Abmeldeanforderung mit den Paaren `d_cid` und dem Schlüssel- `d_cid_ic` -Wert erstellen. Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Ausschluss mit [!DNL CID] und [!DNL CID_IC]

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine Datenanbieter-ID und Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Ein Integrationscode und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere `d_cid` und `d_cid_ic` Schlüssel/Wert-Paare. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Ausschluss auf Partnerebene mit Geräte-ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager] Partner ausschließen. Sie können die Datenerfassung für eine bestimmte Geräte-ID für eine Marke deaktivieren, indem Sie die folgenden Aufrufe an die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)richten:

| Ausschluss mit | Codebeispiel |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Mehr darüber `uuid`und `mid` im `imsOrgId` IDs-Index in Audience Manager [](/help/using/reference/ids-in-aam.md).

Nach einer Abmeldung auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte-ID wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner und führt die Gerätenutzung weiter durch.
* [!DNL Audience Manager] die Segmentierung der Geräte-ID aus allen Segmenten aufheben;
* Zielpartner erhalten die Anforderung zum Entfernen des Segments für die Geräte-ID. Die Segmentierung funktioniert sowohl für [Echtzeit](data-privacy-requests.md#aam-partners-with-unsegmentation) - als auch für Stapelziele.
* Es werden keine Verlaufsdaten gelöscht.

## [!DNL Audience Manager] Partner mit Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

Um Ihnen bei der Automatisierung Ihrer Verbraucherdatendatenschutzanforderungen zu helfen, [!DNL Audience Manager] wird versucht, die Aktivierung-Partner über Löschungsanfragen von Datensubjekten zu informieren, indem diese die Segmentinformationen löschen (oder entfernen).

Einige unserer Partner in der Aktivierung:

1. Nicht-Segmentanforderungen von [!DNL Audience Manager] und/oder können nicht unterstützt werden
2. sind nicht in der Lage, Updates von [!DNL Audience Manager] häufiger als einmal in 30 Tagen zu erhalten.

In diesen Fällen ist es nicht möglich, Löschanfragen automatisch an Aktivierungen-Partner zu senden [!DNL Audience Manager].

Prüfen Sie die [Liste der gerätebasierten Ziele](/help/using/features/destinations/device-based-destinations-list.md) , um zu ermitteln, welche [!DNL Audience Manager] Aktivierungen von den Partnern nicht segmentiert werden.

## Datenkorrekturanforderungen {#correction}

Da dies nicht die Quelle der Daten [!DNL Audience Manager] ist, ist die Datenkorrektur in [!DNL Audience Manager]diesem Bereich begrenzt. Die Korrektur könnte bedeuten, dass der Verbraucher beantragt hat, entweder von einer falschen [!UICONTROL trait]/[!UICONTROL segment] oder der gewünschten [!UICONTROL trait]/[!UICONTROL segment]qualifiziert zu werden.

[!DNL Audience Manager] Kunden können die relevanten Signale/Eigenschaften/Segmente gegen Profil von Benutzern erfassen und diese Informationen über die [Offline-Datenerfassung](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an senden [!DNL Audience Manager]. Bitte beachten Sie, dass der Benutzer sich weiterhin für das Original qualifiziert [!UICONTROL trait] und [!UICONTROL segments] sein Verhalten wiederholt.
